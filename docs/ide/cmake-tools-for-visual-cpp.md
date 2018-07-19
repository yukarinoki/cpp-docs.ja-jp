---
title: Visual C++ での CMake プロジェクト | Microsoft Docs
ms.custom: ''
ms.date: 04/28/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 38bcd102e94ac98aba56a4eb98b69df6d3f16111
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238566"
---
# <a name="cmake-projects-in-visual-c"></a>Visual C++ での CMake プロジェクト

この記事では、複数のプラットフォームで動作するビルド プロセスを定義するためのクロスプラットフォームのオープン ソース ツールである CMake についてよく理解していることを前提としています。

Visual Studio 2015 では、Visual Studio のユーザーは [CMake ジェネレーター](https://cmake.org/cmake/help/v3.9/manual/cmake-generators.7.html)を使って MSBuild プロジェクト ファイルを生成し、IDE はそのファイルを IntelliSense、参照、およびコンパイルに使っていました。 

Visual Studio 2017 以降、**CMake の Visual C++ ツール** コンポーネントは、IntelliSense と参照のために、**フォルダーを開く**機能を使って IDE が CMake プロジェクト ファイル (CMakeLists.txt など) を直接使用できるようにします。 Visual Studio ジェネレーターを使用した場合は、一時プロジェクト ファイルが生成されて msbuild.exe に渡されますが、IntelliSense または参照のために読み込まれることはありません。 

**Visual Studio 2017 バージョン 15.3**: Ninja ジェネレーターと Visual Studio ジェネレーターの両方がサポートされます。

**Visual Studio 2017 バージョン 15.4**: Linux 上の CMake のサポートが追加されます。 詳細については、「[Configure a Linux CMake Project](../linux/cmake-linux-project.md)」 (Linux CMake プロジェクトを構成する) を参照してください。

**Visual Studio 2017 バージョン 15.5**: 既存の CMake キャッシュのインポートのサポートが追加されます。 Visual Studio はカスタマイズされた変数を自動的に抽出し、事前設定済みの CMakeSettings.json ファイルを作成します。

**Visual Studio 2017 バージョン 15.7**: キャッシュの自動生成の無効化、**ソリューション エクスプローラー**でのターゲット ビュー、単一ファイルのコンパイルのサポートが追加されます。

## <a name="installation"></a>インストール

**CMake の Visual C++ ツール**は、**C++ によるデスクトップ開発**ワークロードの一部として既定でインストールされます。

![C++ デスクトップ ワークロードでの CMake コンポーネント](media/cmake-install.png)
 
## <a name="ide-integration"></a>IDE の統合

**[ファイル] > [開く] > [フォルダー]** を選んで、CMakeLists.txt ファイルを含むフォルダーを開くと、次の処理が行われます。

- Visual Studio は、CMake スクリプトを表示および編集するためのコマンドを含む **[CMake]** メニュー項目を、メイン メニューに追加します。
- **ソリューション エクスプローラー**に、フォルダーの構造とファイルが表示されます。
- Visual Studio は CMake.exe を実行して、既定の "*構成*" (x86 デバッグ) 用の CMake キャッシュを生成します。 CMake コマンド ラインおよび CMake からの追加出力が、**出力ウィンドウ**に表示されます。  **Visual Studio 2017 バージョン 15.7 以降**: キャッシュの自動生成は、**[ツール] > [オプション] > [CMake] > [全般]** ダイアログで無効にできます。
- Visual Studio は、IntelliSense、情報の参照、リファクタリングなどを有効にするためのソース ファイルのインデックス付けを、バックグラウンドで開始します。 ユーザーが作業を行っている間、Visual Studio は、エディターおよびディスク上での変更を監視し、インデックスとソースの同期を維持します。
 
開くフォルダーに含まれる CMake プロジェクトの数は制限されていません。 Visual Studio は、ワークスペース内にあるすべての "ルート" CMakeLists.txt ファイルを検出して構成します。 CMake の操作 (構成、ビルド、デバッグ) および C++ の IntelliSense と参照は、ワークスペース内のすべての CMake プロジェクトが使用できます。

![複数のルートを持つ CMake プロジェクト](media/cmake-multiple-roots.png)  

**Visual Studio 2017 バージョン 15.7 以降**: ターゲットごとに論理的にまとめられたプロジェクトを参照することも可能です。 **ソリューション エクスプローラー** ツールバーのドロップダウンから、**[ターゲット ビュー]** を選択します。

![CMake ターゲット ビュー ボタン](media/cmake-targets-view.png)

## <a name="import-an-existing-cache"></a>既存のキャッシュをインポートする

ユーザーが既存の CMakeCache.txt ファイルをインポートすると、Visual Studio はカスタマイズされた変数を自動的に抽出し、それを基にして事前設定済みの CMakeSettings.json ファイルを作成します。 元のキャッシュには、どのような変更も加えられておらず、コマンド ラインから、またはキャッシュの生成に使われた任意のツールや IDE で、使用することができます。 新しい CMakeSettings.json ファイルは、プロジェクトのルートの CMakeLists.txt と共に配置されます。 Visual Studio は、設定ファイルに基づいて新しいキャッシュを生成します。  


**Visual Studio 2017 バージョン 15.7 以降**: キャッシュの自動生成は、**[ツール] > [オプション] > [CMake] > [全般]** ダイアログでオーバーライドできます。

キャッシュ内のすべてのものがインポートされるわけではありません。  ジェネレーターや、コンパイラの場所などのプロパティは、IDE で問題なく機能することがわかっている既定値に置き換えられます。

### <a name="to-import-an-existing-cache"></a>既存のキャッシュをインポートするには

1. メイン メニューから **[ファイル] > [開く] > [CMake]** を選びます。

   ![CMake を開く](media/cmake-file-open.png "[ファイル] > [開く] > [CMake]") 

   これにより、**キャッシュからの CMake のインポート** ウィザードが起動します。 
   
2. インポートする CMakeCache.txt ファイルに選んで、**[OK]** をクリックします。 **[キャッシュから CMake のプロジェクトをインポートします]** ウィザードが表示されます。

   ![CMake キャッシュのインポート](media/cmake-import-wizard.png "CMake キャッシュ インポート ウィザードを開く") 

   ウィザードが完了すると、**ソリューション エクスプローラー**でプロジェクトのルート CMakeLists.txt ファイルの隣に新しい CMakeCache.txt ファイルが表示されます。


## <a name="building-cmake-projects"></a>CMake プロジェクトのビルド

CMake プロジェクトをビルドするには、次の選択肢があります。

1. **[デバッグ]** ドロップダウンでターゲットを選び、**F5** キーを押すか、**[実行]** (緑色の三角形) ボタンをクリックします。 Visual Studio ソリューションと同じように、プロジェクトは最初に自動的にビルドされます。
1. CMakeLists.txt を右クリックして、コンテキスト メニューから **[ビルド]** を選びます。 フォルダー構造内に複数のターゲットがある場合は、すべてをビルドするか、特定の 1 つのターゲットだけをビルドするかを選べます。
1. メイン メニューから、**[ビルド] > [ソリューションのビルド]** (**F7** キーまたは **Ctrl + Shift + B** キー) を選びます。 **[全般]** ツール バーの **[スタートアップ アイテム]** ドロップダウンで CMake ターゲットが既に選択されていることを確認します。

![CMake のビルド メニュー コマンド](media/cmake-build-menu.png "CMake のビルド コマンド メニュー") 

アクティブな構成に対して Visual Studio ジェネレーターが選択されている場合、`-m -v:minimal` 引数を指定して MSBuild.exe が呼び出されます。 ビルドをカスタマイズするには、CMakeSettings.json ファイル内で、`buildCommandArgs` プロパティによりビルド システムに渡される追加のコマンド ライン引数を指定できます。

```json
"buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
```

想像したとおり、ビルド結果が**出力ウィンドウ**と**エラー一覧**に表示されます。
 
![CMake ビルド エラー](media/cmake-build-errors.png "CMake ビルド エラー")

フォルダーに複数のビルド ターゲットがある場合は、**[CMake]** メニューまたは **CMakeLists.txt** のコンテキスト メニューで **[ビルド]** 項目を選び、ビルドする CMake ターゲットを指定できます。 CMake プロジェクトで **Ctrl + Shift + B** キーを押して、現在アクティブなドキュメントをビルドします。

## <a name="debug-the-project"></a>プロジェクトをデバッグする

CMake プロジェクトをデバッグするには、対象の構成を選んで、**F5** キーを押すか、またはツール バーの **[実行]** ボタンをクリックします。 **[実行]** ボタンに [スタートアップ アイテムの選択] と表示されている場合は、ドロップダウン矢印を選んで、実行するターゲットを選びます (CMake プロジェクトでは、[現在のドキュメント] オプションは .cpp ファイルの場合にのみ有効です)。 

![CMake の実行ボタン](media/cmake-run-button.png "CMake の実行ボタン")

**[実行]** または **F5** コマンドを選ぶと、前回のビルドの後で何かが変更されている場合は、最初にプロジェクトがビルドされます。

## <a name="configure-cmake-debugging-sessions"></a>CMake デバッグ セッションを構成する

すべての実行可能な CMake ターゲットが、**[全般]** ツール バーの **[スタートアップ アイテム]** ドロップダウンに表示されます。 デバッグ セッションを開始するには、1 つを選択してデバッガーを起動するだけです。

![CMake のスタートアップ アイテム ドロップダウン](media/cmake-startup-item-dropdown.png "CMake のスタートアップ アイテム ドロップダウン")


CMake メニューからデバッグ セッションを開始することもできます。

プロジェクト内の実行可能な CMake ターゲットのデバッガー設定をカスタマイズするには、特定の CMakeLists.txt ファイルを右クリックして、**[デバッグ設定と起動設定]** を選びます。 サブメニューで CMake ターゲットを選ぶと、launch.vs.json という名前のファイルが作成されます。 このファイルには選んだ CMake ターゲットに関する情報があらかじめ入力されており、プログラムの引数やデバッガーの種類などの他のパラメーターを指定することができます。 CMakeSettings.json ファイル内のキーを参照するには、launch.vs.json 内で前に "CMake." を付けます。 次に示す簡単な launch.vs.json ファイルの例では、現在選択されている構成に対して、CMakeSettings.json ファイル内の "remoteCopySources" キーの値を取得しています。

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
   {
      "type": "default",
      "project": "CMakeLists.txt",
      "projectTarget": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "name": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "args": ["${cmake.remoteCopySources}"]
    }
  ]
}
```

launch.vs.json ファイルを保存するとすぐに、**[スタートアップ アイテム]** ドロップダウン内に新しい名前のエントリが作成されます。 launch.vs.json ファイルを編集することで、任意の数の CMake ターゲットに対し、いくつでもデバッグ構成を作成できます。

**Visual Studio 2017 バージョン 15.4**: launch.vs.json は、CMakeSettings.json (下記参照) で宣言されていて、現在選択されている構成に適用される変数をサポートします。 "currentDir" という名前のキーもあり、これは起動しているアプリの現在のディレクトリを設定します。


```json
{
"type": "default",
"project": "CMakeLists.txt",
"projectTarget": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"name": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"currentDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}"
}
```

アプリを実行すると、`currentDir` の値は次のようになります。

```cmd
C:\Users\satyan\7f14809a-2626-873e-952e-cdf038211175\
```

## <a name="editing-cmakeliststxt-files"></a>CMakeLists.txt ファイルの編集

CMakeLists.txt ファイルを編集するには、**ソリューション エクスプローラー**でファイルを右クリックして、**[開く]** を選びます。 ファイルを変更すると表示される黄色いステータス バーでは、IntelliSense が更新されることが示され、更新操作をキャンセルできます。 CMakeLists.txt については、[CMake のドキュメント](https://cmake.org/documentation/)をご覧ください。

   ![CMakeLists.txt ファイルの編集](media/cmake-cmakelists.png "CMakeLists.txt ファイルの編集")


ファイルを保存するとすぐに構成手順が自動的に再び実行され、**[出力]** ウィンドウに情報が表示されます。 エラーと警告は、**[エラー一覧]** または **[出力]** ウィンドウに表示されます。 **[エラー一覧]** でエラーをダブルクリックすると、CMakeLists.txt で問題が発生した行に移動します。

   ![CMakeLists.txt ファイルのエラー](media/cmake-cmakelists-error.png "CMakeLists.txt ファイルのエラー")

## <a name="cmake_settings"></a> CMake の設定とカスタム構成

Visual Studio では、6 つの既定の CMake 構成 ("x86-Debug"、"x86-Release"、"x64-Debug"、"x64-Release"、"Linux-Debug"、"Linux-Release") が提供されています。 これらの構成では、特定のプロジェクトの CMake キャッシュを作成するために CMake.exe が呼び出される方法が定義されています。 これらの構成を変更するには、または新しいカスタム構成を作成するには、**[CMake] > [CMake の設定を変更]** を選んでから、設定を適用する CMakeLists.txt ファイルを選びます。 **[CMake の設定を変更]** コマンドは、**ソリューション エクスプローラー**のファイルのコンテキスト メニューでも利用できます。 このコマンドでは、プロジェクト フォルダーに CMakeSettings.json ファイルが作成されます。 このファイルは、たとえば**クリーン**操作の後などに、CMake キャッシュ ファイルを再作成するために使われます。 

   ![設定変更のための CMake メイン メニュー コマンド](media/cmake-change-settings.png)

JSON の IntelliSense は、CMakeSettings.json ファイルの編集を支援します。

   ![CMake の JSON IntelliSense](media/cmake-json-intellisense.png "CMake の JSON IntelliSense")

次にサンプルの構成を示します。これを基にして、独自の CMakeSettings.json を作成できます。

```json
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "-v",
      "ctestCommandArgs": ""
    },

```

1. **name**: C++ の構成ドロップダウンに表示される名前です。 このプロパティ値をマクロ `${name}` として使って、他のプロパティ値を指定することもできます。 例については、CMakeSettings.json の **buildRoot** の定義をご覧ください。
1. **generator**: **-G** スイッチに対応し、使用するジェネレーターを指定します。 このプロパティをマクロ `${generator}` として使って、他のプロパティ値を指定することもできます。 現在、Visual Studio では次の CMake ジェネレーターがサポートされています。

    - "Ninja"
    - "Visual Studio 14 2015"
    - "Visual Studio 14 2015 ARM"
    - "Visual Studio 14 2015 Win64"
    - "Visual Studio 15 2017"
    - "Visual Studio 15 2017 ARM"
    - "Visual Studio 15 2017 Win64"

Ninja は柔軟性や機能ではなく、ビルド速度が速いことを目的に設計されているため、既定値としてこれが設定されます。 ただし、CMake プロジェクトによっては、Ninja を使うと正しくビルドできないことがあります。 そのような場合は、代わりに Visual Studio プロジェクトを生成するように CMake に指示できます。

Visual Studio ジェネレーターを指定するには、メイン メニューから **[CMake] > [CMake の設定を変更]** を選んで、CMakeSettings.json を開きます。 "Ninja" を削除して「V」と入力します。 これにより IntelliSense がアクティブになり、必要なジェネレーターを選択できます。

1. **buildRoot**: **-DCMAKE_BINARY_DIR** スイッチに対応し、CMake キャッシュが作成される場所を指定します。 フォルダーが存在しない場合は、作成されます。
1. **variables**: **-D**<_名前_>**=**<_値_> として CMake に渡される、CMake 変数の名前と値のペアを含みます。 CMake プロジェクトのビルド命令で CMake キャッシュ ファイルに直接変数を追加するように指定している場合は、代わりにここで追加することをお勧めします。
1. **cmakeCommandArgs**: CMake.exe に渡す追加のスイッチを指定します。
1. **configurationType**: 選択したジェネレーターのビルド構成の種類を定義します。 現在サポートされている値は、"Debug"、"MinSizeRel"、"Release"、"RelWithDebInfo" です。

### <a name="environment-variables"></a>環境変数

CMakeSettings.json では、上記のすべてのプロパティにおいて環境変数を使うこともできます。 `${env.FOO}` という構文を使うと、環境変数 %FOO% が展開されます。
このファイルの内部で組み込みマクロにアクセスすることもできます。

- `${workspaceRoot}` – ワークスペース フォルダーの完全なパスを提供します
- `${workspaceHash}` – ワークスペースの場所のハッシュです。現在のワークスペースの一意識別子を作成するのに便利です (たとえば、フォルダーのパスで使用する場合)
- `${projectFile}` – ルート CMakeLists.txt ファイルの完全なパスです
- `${projectDir}` – ルート CMakeLists.txt ファイルのフォルダーの完全なパスです
- `${thisFile}` – CMakeSettings.json ファイルの完全なパスです
- `${name}` – 構成の名前です
- `${generator}` – この構成で使用される CMake ジェネレーターの名前です

### <a name="ninja-command-line-arguments"></a>Ninja のコマンド ライン引数

ターゲットを指定しないと、"default" ターゲットがビルドされます (マニュアルを参照)。

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|オプション|説明|
|--------------|------------|
| --version  | Ninja のバージョンを書き出します ("1.7.1")|
|   -C DIR   | 何かを実行する前に、DIR (ディレクトリ) に変更します|
|   -f FILE  | 入力ビルド ファイルを指定します (既定値は build.ninja)|
|   -j N     | N 個のジョブを並列実行します (既定値は 14、使用可能な CPU の数から派生)|
|   -k N     | N 個のジョブが失敗するまで続けます (既定値は 1)|
|   -l N     | 負荷の平均が N より大きい場合は、新しいジョブを開始しません|
|   -n      | ドライ実行 (コマンドを実行しませんが、成功したように動作します)|
|   -v       | ビルド中にすべてのコマンド ラインを表示します|
|   -d MODE  | デバッグを有効にします (モードを一覧表示するには -d list を使用)|
|   -t TOOL  | サブツールを実行します (サブツールを一覧表示するには -t list を使用)。 トップレベルのオプションを終了します。さらにフラグがツールに渡されます| 
|   -w FLAG  | 警告を調整します (警告を一覧表示するには -w list を使用)|

### <a name="inherited-environments-visual-studio-2017-version-155"></a>継承された環境 (Visual Studio 2017 バージョン 15.5)
CMakeSettings.json は、継承された環境をサポートするようになっています。 この機能を使うと、(1) 既定の環境を継承することができ、(2) 実行時に CMake.exe に渡されるカスタム環境変数を作成できます。

```json
  "inheritEnvironments": [ "msvc_x64_x64" ]
```

上の例は、**-arch=amd64 -host_arch=amd64** 引数を指定して **VS 2017 の開発者コマンド プロンプト**を実行するのと同じです。

次の表では、既定値と、それに同等のコマンド ラインを示します。

|コンテキスト名|説明|
|-----------|-----------------|
|vsdev|既定の Visual Studio 環境|
|msvc_x86|x86 ツールを使って、x86 用にコンパイルします|
|msvc_arm| x86 ツールを使って、ARM 用にコンパイルします|
|msvc_arm64|x86 ツールを使って、ARM64 用にコンパイルします|
|msvc_x86_x64|x86 ツールを使って、AMD64 用にコンパイルします|
|msvc_x64_x64|64 ビット ツールを使って、AMD64 用にコンパイルします|
|msvc_arm_x64|64 ビット ツールを使って、ARM 用にコンパイルします|
|msvc_arm64_x64|64 ビット ツールを使って、ARM64 用にコンパイルします|

### <a name="custom-environment-variables"></a>カスタム環境変数
CMakeSettings.json では、グローバルに、または **environments** プロパティを使用して構成ごとに、カスタム環境変数を定義できます。 次の例では、1 つのグローバル変数 **BuildDir** を定義します。これは、x86-Debug と x64-Debug の両方の構成で継承されます。 各構成は、この変数を使って、その構成の **buildRoot** プロパティの値を指定します。 各構成が **inheritEnvironments** プロパティを使ってその構成のみに適用される変数を指定する方法にも注意してください。

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x86 compiler.
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.BuildDir}\\${name}"    },
    {
      "name": "x64-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x64 compiler.
      "inheritEnvironments": [ "msvc_x64" ],
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

次の例では、x86-Debug 構成が **BuildDir** プロパティに独自の値を定義しています。この値は、**BuildRoot** が `D:\custom-builddir\x86-Debug` と評価されるように、グローバルな **BuildDir** プロパティによって設定される値をオーバーライドします。

```json
{
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",

      // The syntax for this property is the same as the global one above.
      "environments": [
        {
          // Replace the global property entirely.
          "BuildDir": "D:\\custom-builddir",
        }
      ],

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      // Evaluates to "D:\custom-builddir\x86-Debug"
      "buildRoot": "${env.BuildDir}\\${name}"
    },
    {
      "name": "x64-Debug",

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x64" ], 
      // Since this configuration doesn’t modify BuildDir, it inherits
      // from the one defined globally.
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

## <a name="cmake-configure-step"></a>CMake の構成ステップ

CMakeSettings.json ファイルまたは CMakeLists.txt ファイルが大幅に変更されると、Visual Studio は CMake の構成ステップを自動的に再実行します。 構成ステップがエラーなしで完了すると、収集された情報が、C++ の IntelliSense サービスと言語サービス、およびビルドとデバッグの操作で使用できるようになります。

複数の CMake プロジェクトが同じ CMake 構成名 (x86-Debug など) を使っている場合、その構成を選ぶと、すべてのプロジェクトが構成されて (それぞれのビルド ルート フォルダーに) ビルドされます。 その CMake 構成に参加しているすべての CMake プロジェクトから、ターゲットをデバッグすることができます。

   ![CMake の [ビルドのみ] メニュー項目](media/cmake-build-only.png "CMake の [ビルドのみ] メニュー項目")

ビルドおよびデバッグ セッションをワークスペース内のプロジェクトのサブセットに制限するには、CMakeSettings.json ファイルに一意名を使って新しい構成を作成し、それらのプロジェクトのみに適用します。 その構成を選ぶと、IntelliSense およびビルドとデバッグのコマンドは、指定されているプロジェクトに対してのみ有効になります。

## <a name="troubleshooting-cmake-cache-errors"></a>CMake キャッシュ エラーのトラブルシューティング

問題を診断するために CMake キャッシュの状態に関する詳しい情報が必要な場合は、**CMake** のメイン メニューまたは**ソリューション エクスプローラー**で **CMakeLists.txt** のコンテキスト メニューを開き、次のコマンドのいずれかを実行します。

- **[キャッシュの表示]** は、ビルド ルート フォルダーの CMakeCache.txt ファイルをエディターで開きます (ここで CMakeCache.txt に対して編集した内容はすべて、キャッシュをクリーンアップするとワイプされます。 キャッシュがクリーンアップされた後も残るように変更する方法については、前の「[CMake の設定とカスタム構成](#cmake_settings)」をご覧ください)。
- **[キャッシュ フォルダーを開く]** は、エクスプローラー ウィンドウでビルド ルート フォルダーを開きます。  
- **[キャッシュをクリーン]** は、次の CMake 構成ステップがクリーンなキャッシュから開始されるように、ビルド ルート フォルダーを削除します。
- **[キャッシュを生成]** は、Visual Studio が環境は最新の状態であると判断した場合でも、生成ステップを強制的に実行します。
 
**Visual Studio 2017 バージョン 15.7 以降**: キャッシュの自動生成は、**[ツール] > [オプション] > [CMake] > [全般]** ダイアログで無効にできます。

## <a name="single-file-compilation"></a>単一ファイルのコンパイル

**Visual Studio 2017 バージョン 15.7 以降**: CMake プロジェクトに単一ファイルをビルドするには、**ソリューション エクスプローラー**でファイルを右クリックし、**[コンパイル]** を選択します。 メインの CMake メニューを使用すると、エディターで現在開いているファイルをビルドすることも可能です。

![CMake の単一ファイルのコンパイル](media/cmake-single-file-compile.png)