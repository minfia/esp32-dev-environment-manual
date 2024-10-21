# sdkconfigとKconfig.projbuildの関係
Kconfigとsdkconfigの関係を記載する。\
すべての記述に記載しているわけではないと思われるので、都度更新が必要。

## 1 sdkconfig
### 1.1 作成方法
sdkconfigの作成方法として以下の2つがある。
1. プロジェクトのビルド\
新規作成時のみ内容が変更される。
1. `idf.py menuconfig`コマンドの実行\
新規作成時と内容変更時に保存することで内容が更新される。\
また、sdkconfig.oldを作成し新たにsdkconfigファイルを作成する。

プロジェクトのビルドを行うことでsdkconfigファイルの内容が"sdkconfig.h"に定義され、ソースコード上から使用することができる。\
一部の情報は、Kconfigをベースに作成される。

どちらの場合も、設定変更済みのsdkconfigファイルを削除すると初期値で再作成されるため誤って削除しないように注意が必要。

### 1.2 各項目の変更方法
変更方法は2通りある。
1. IDEの"Project Explorer"から"sdkconfig"をダブルクリック\
GUIで変更が可能で保存時にsdkconfig.oldファイルが作成される。\
また、場合によってはsdkconfigファイル内のデータ順序が前後することがある。
1. `idf.py menuconfig`コマンドを実行\
CUIで変更が可能で実行時にsdkconfig.oldが作成される。

基本的にどちらで使っても実動作に問題はないため好みに合わせて使用する。

### 1.3 項目の追加方法
sdkconfigファイルは、ESP-IDFが提供する設定とは別に、ユーザーでも設定を追加することが可能となっている。\
追加方法として、Kconfigファイルに記載することで追加できる。

### 1.4 項目の認識方法
sdkconfigは以下のようにして項目化される。
```
#
# メニュー名
#
設定項目名=値
     :
設定項目名=値
# end of メニュー名
```
以下に項目化の記述例を示す。
```
#
# Example Configuration
#
CONFIG_ESP_WIFI_SSID="myssid"
CONFIG_ESP_WIFI_PASSWORD="mypassword"
# end of Example Configuration
```

## 2 Kconfig.projbuild
Kconfig.projbuildについて記載する。\
Kconfig.projbuildはLinuxカーネルの"Kconfig"と似た記述がされている。

### 2.1 作成方法
プロジェクト作成時に作成される。\
もしファイルがない場合は、"Kconfig.projbuild"で"main"ディレクトリ内に作成する必要がある。

### 2.2 記述方法
Kconfigは以下のように記述される。
```
menu <"文字列">
    config <文字列>
        type <"文字列">
        default <typeに対応した値>
        help
            <表示する文章>
endmenu
```
以下にKconfigの記述例を示す。
```
# put here your custom config value
menu "Example Configuration"
    config ESP_WIFI_SSID
        string "WiFi SSID"
        default "myssid"
        help
            SSID (network name) for the example to connect to.

    config ESP_WIFI_PASSWORD
        string "WiFi Password"
        default "mypassword"
        help
            WiFi password (WPA or WPA2) for the example to use.
endmenu
```

一部の記述について説明する。

#### 2.2.1 コメント
"#"の後ろに記述する。\
日本語の使用が可能。\
以下のように記述する。
```
# <文字列>
```
例
```
# Comment String
```

#### 2.2.2 menu
メニュー名がsdkconfigでのメニュー名になる。\
メニュー名に日本語は使えない。\
以下のように記述する。
```
menu <"文字列">

endmenu
```
例
```
menu "Test Configuration"

endmenu
```

#### 2.2.3 config
<文字列>はsdkconfig.hのdefine名になる。\
<文字列>に日本語は使えない。\
以下のように記述する。
```
config <文字列>
```
例
```
config TEST_DEFINE
```

#### 2.2.4 type
"type"は設定する値の型を指定する。\
[title]は[config](#223-config)で表示する文字列を入れる。\
文字列を入力しない場合は固定値として変更可能項目には表示されない。\
[title]に日本語を使用可能。\
以下のように記述する。
```
type [title]
```
例
```
type "Test Title"
```
typeは以下の種類がある。
* int
* string
* bool

floatやdoubleは使用できない。

#### 2.2.5 default
[type](#224-type)で定義した型の初期値を指定する。\
以下のように記述する。
```
default <value>
```
例
```
default 0
```

"default \<value\>"と別に"default \<value\> if 条件"を記述することでその条件で初期値を定義できる。
以下のように記述する。
```
default <value> if <assess>
```
例
```
default 9 if !(TEST_TARGET_1 || TEST_TARGET_2) && TEST_TARGET_3
default 0
```
条件に論理和と論理積、論理否定を使用できる。

#### 2.2.6 help
[config](#223-config)の説明を書くする。\
また、2行以降も記述可能。\
<文字列>に日本語を使用可能。
以下のように記述する。
```
help
    <文字列>
```
例
```
help
    Test help
```

#### 2.2.7 range
[config](#223-config)で使用する値の範囲を指定することができる。\
範囲外を指定した場合はエラーとなり値は変更されない。\
以下のように記述する。
```
range <MIN> <MAX>
```
例
```
range 0 33
```

#### 2.2.8 choice
値の選択をすることができる項目を作成する。\
この中に[config](#223-config)や[help](#226-help)などを記述する。\
<文字列>がdefine名にならず、選択されたconfigが"define名 1"として宣言される。\
この項目を変更できるようにするには[prompt](#229-prompt)を記述する必要がある。\
以下のように記述する。
```
choice <文字列>

endchoice
```
例
```
choice TEST_CHOICE

endchoice
```

#### 2.2.9 prompt
[choice](#228-choice)で\<title\>を表示するために使用する。\
この項目がないと[choice](#228-choice)の変更ができない。\
<文字列>に日本語を使用可能。
以下のように記述する。
```
prompt "<文字列>"
```
例
```
prompt "Test choice title"
```

#### 2.2.10 depends on
<文字列>条件有効時に[config](#223-config)や[choice](#228-choice)の項目を変更できるようにする。\
以下のように記述する。
```
depends on <文字列>
```
例
```
depends on TEST_CHOICE_1
```

#### 2.2.11 orsource
外部のKconfigを参照することができる。\
"orsource"の有効範囲は記述したファイルの範囲だと思われる。\
記述位置はKconfigファイル内であればどこでもよい。\
以下のように記述する。
```
orsource "<ファイルパス>"
```
例
```
orsource "./test/test/test.conf"
```
