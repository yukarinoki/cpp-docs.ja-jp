---
title: Visual C で CMake プロジェクト |Microsoft ドキュメント
ms.custom: ''
ms.date: 08/08/2017
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
ms.openlocfilehash: f3a65ae6cc58f649fee5f47b33a146263a3b6c55
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmake-projects-in-visual-c"></a>Visual C で CMake プロジェクト

この記事では、CMake、複数のプラットフォームで実行されるビルド プロセスを定義するためのプラットフォーム間でオープン ソース ツールに慣れていることを前提としています。

Visual Studio ユーザーが CMake を使用して、IDE が IntelliSense の使用し、MSBuild プロジェクト ファイルを生成する最近まで、参照、およびコンパイルします。 Visual Studio 2017、以降、 **CMake の Visual C ツール**コンポーネントを使用して、**フォルダーを開く**(CMakeLists.txt) など、目的のために直接の CMake プロジェクト ファイルを使用する IDE を有効にする機能IntelliSense および閲覧します。 ジェネレーターを Visual Studio を使用する場合、一時プロジェクト ファイルが生成され、msbuild.exe に渡されるはありません IntelliSense またはブラウズの目的で読み込まれます。 

**Visual Studio 2017 バージョン 15.3**: 忍者と Visual Studio の両方のジェネレーターのサポートを提供します。

**Visual Studio 2017 バージョン 15.4**: Linux 上の CMake のサポートを追加します。 詳細については、「[Configure a Linux CMake Project](../linux/cmake-linux-project.md)」 (Linux CMake プロジェクトを構成する) を参照してください。

**Visual Studio 2017 バージョン 15.5**: 既存の CMake キャッシュのインポートのサポートを追加します。 Visual Studio は自動的にカスタマイズされた変数を抽出し、事前設定済み CMakeSettings.json ファイルを作成します。


## <a name="installation"></a>インストール

**CMake の visual C ツール**がインストールされている既定の一部として、 **C++ を使用したデスクトップ開発**ワークロード。

![C++ デスクトップ ワークロードで CMake コンポーネント](media/cmake-install.png)
 
## <a name="ide-integration"></a>IDE の統合

選択すると**ファイル |開いている |フォルダー**を CMakeLists.txt ファイルを含むフォルダーを開くには、次の処理が行われます。

- Visual Studio は追加、 **CMake**表示および CMake スクリプトを編集用のコマンドで、メイン メニューにメニュー項目。
- **ソリューション エクスプ ローラー**フォルダー構造およびファイルを表示します。
- Visual Studio が CMake.exe を実行し、既定の CMake キャッシュを生成*構成*、これは、x86 をデバッグします。 CMake コマンド ラインが表示されます、**出力ウィンドウ**、と共に CMake から出力を追加します。
- バック グラウンドで、情報の閲覧、リファクタリング、IntelliSense を有効にするソース ファイルのインデックスを作成するために Visual Studio を起動します。 操作すると、Visual Studio は、エディターおよびそのインデックスがソースに同期するディスク上で変更を監視します。
 
CMake プロジェクトの任意の数を含むフォルダーを開くことができます。 Visual Studio では、検出し、ワークスペースにすべての"root"CMakeLists.txt ファイルを構成します。 CMake 操作 (構成、ビルド、デバッグ) も C++ IntelliSense および参照は、ワークスペース内のすべての CMake プロジェクトに使用します。

![複数のルートを持つ CMake プロジェクト](media/cmake-multiple-roots.png) 

## <a name="import-an-existing-cache"></a>既存のキャッシュをインポートします。

既存の CMakeCache.txt ファイルをインポートするときに、Visual Studio は自動的にカスタマイズされた変数を抽出し、それらに基づく、事前設定済み CMakeSettings.json ファイルを作成します。 元のキャッシュは、任意の方法では変更されず、使用またはコマンドラインからどのようなツールや IDE がそれを生成するために使用できます。 新しい CMakeSettings.json ファイルがプロジェクトのルート CMakeLists.txt と一緒に配置されます。 Visual Studio で新しい生成キャッシュ設定ファイルのベースします。 いないキャッシュ内のすべてがインポートされます。  コード ジェネレーターと、コンパイラの場所などのプロパティは、IDE でうまく機能する既知の既定値に置き換えられます。

### <a name="to-import-an-existing-cache"></a>既存のキャッシュをインポートするには

1. メイン メニューから選択**ファイル |開いている |CMake**:

   ![CMake を開く](media/cmake-file-open.png "ファイル、開く、CMake") 

   これにより、**キャッシュからのインポート CMake**ウィザード。 
   
2. をインポートする CMakeCache.txt ファイルに移動し、をクリックして**OK**です。 **キャッシュからのインポート CMake プロジェクト**ウィザードが表示されます。

   ![CMake キャッシュをインポート](media/cmake-import-wizard.png "CMake インポート キャッシュ ウィザードを開きます") 

   ウィザードが完了したら、することができます、新しい CMakeCache.txt ファイルを参照して**ソリューション エクスプ ローラー**プロジェクトのルート CMakeLists.txt ファイルの横にあります。


## <a name="building-cmake-projects"></a>CMake プロジェクトをビルドします。

CMake プロジェクトをビルドするには、これらの選択肢があります。

1. ターゲットを選択、**デバッグ**ドロップダウン リストとキーを押します**f5 キーを押して**、 をクリックして、**実行**(緑色の三角形) ボタンをクリックします。 プロジェクトは自動的に、Visual Studio ソリューションと同じように最初に、構築します。
1. CMakeLists.txt と選択 を右クリックして**ビルド**コンテキスト メニュー。 フォルダーの構造に複数のターゲットをした場合は、すべてまたは 1 つだけ特定のターゲットをビルドすることもできますか
1. メイン メニューから選択**ビルド |ソリューションをビルド**(**F7**または**Ctrl + Shift + B**)。 CMake ターゲットがで既に選択されていることを確認、**スタートアップ アイテム**ドロップダウン リストで、**全般**ツールバー。

![CMake は、メニュー コマンドを構築](media/cmake-build-menu.png "Cmake は、コマンド メニューを作成します。") 

MSBuild.exe が呼び出されると、アクティブな構成のジェネレーターを Visual Studio を選択すると、`-m -v:minimal`引数。 CMakeSettings.json ファイル内のビルドをカスタマイズするを使用して、ビルド システムに渡される追加のコマンドライン引数を指定、`buildCommandArgs`プロパティ。

```json
"buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
```

ビルド結果を表示、想定されるよう、**出力ウィンドウ**と**エラー一覧**です。
 
![CMake ビルド エラー](media/cmake-build-errors.png "CMake ビルド エラー")

複数のビルド ターゲットを持つフォルダーを選択できます、**ビルド**上の品目、 **CMake**メニューまたは**CMakeLists.txt**をビルドするには、どの CMake ターゲットを指定するコンテキスト メニュー。 キーを押して**Ctrl + Shift + B** CMake でプロジェクトが現在アクティブなドキュメントを構築します。

## <a name="debug-the-project"></a>プロジェクトをデバッグする

CMake プロジェクトをデバッグするには、選択、必要な構成とキーを押します**f5 キーを押して**、またはキーを押して、**実行**ツールバーのボタンです。 場合、**実行**ボタンの表示「スタートアップ アイテムの選択」、ドロップダウン矢印を選択して実行するターゲットを選択、します。 (「現在のドキュメント」CMake プロジェクトで .cpp ファイルのオプションはのみです)。 

![CMake の実行 ボタン](media/cmake-run-button.png "Cmake の実行 ボタン")


**実行**または**f5 キーを押して**コマンドは、前回のビルドからの変更が加えられた場合は、まずプロジェクトをビルドします。

## <a name="configure-cmake-debugging-sessions"></a>CMake、デバッグ セッションを構成します。

すべての実行可能 CMake ターゲットが表示されます、**スタートアップ アイテム**ドロップダウン リストで、**全般**ツールバー。 デバッグ セッションを開始するには、1 つを選択し、デバッガーを起動します。

![CMake スタートアップ項目のドロップダウン](media/cmake-startup-item-dropdown.png "CMake スタートアップ項目のドロップダウン リスト")


CMake メニューから、デバッグ セッションを開始することもできます。

プロジェクト内の任意の実行可能 CMake ターゲットのデバッガーの設定をカスタマイズするには、特定 CMakeLists.txt ファイルを右クリックし、選択**デバッグ構成と起動設定**です。 CMake ターゲットを選択して、サブメニューに launch.vs.json という名前のファイルが作成されます。 このファイルは、選択した CMake ターゲットに関する情報があらかじめ入力されており、プログラムの引数またはデバッガーの種類などの他のパラメーターを指定することができます。 CMakeSettings.json ファイル内の任意のキーを参照するには、"cmake"を付ける で launch.vs.json です。 次の例では、現在選択されている構成の CMakeSettings.json ファイル内の"remoteCopySources"キーの値を取り出す単純 launch.vs.json ファイルを示します。

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

内のエントリが作成 launch.vs.json ファイルを保存するとすぐに、**スタートアップ アイテム**新しい名前を含むドロップダウンします。 Launch.vs.json ファイルを編集するには、任意の数の CMake ターゲットに使用する多くのデバッグ構成とを作成できます。

**Visual Studio 2017 バージョン 15.4**: Launch.vs.json CMakeSettings.json (下記参照) で宣言されていると、現在選択されている構成に適用される変数をサポートしています。 "CurrentDir"は、起動中のアプリの現在のディレクトリ設定をという名前のキーもあります。


```json
{
"type": "default",
"project": "CMakeLists.txt",
"projectTarget": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"name": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"currentDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}"
}
```

値、アプリを実行すると`currentDir`以下のようには

```cmd
C:\Users\satyan\7f14809a-2626-873e-952e-cdf038211175\
```

## <a name="editing-cmakeliststxt-files"></a>CMakeLists.txt ファイルの編集

CMakeLists.txt ファイルを編集するでファイルを右クリックして**ソリューション エクスプ ローラー**選択**開く**です。 ファイルを変更する場合、黄色の状態バーが表示され、IntelliSense が更新され、更新操作をキャンセルする機会が与えられますが通知されます。 CMakeLists.txt 詳細については、次を参照してください。、 [CMake ドキュメント](https://cmake.org/documentation/)です。

   ![CMakeLists.txt ファイル編集](media/cmake-cmakelists.png "CMakeLists.txt ファイルの編集")


構成手順が自動的にもう一度実行し、内の情報を表示ファイルを保存するとすぐに、**出力**ウィンドウです。 エラーと警告がで示すように、**エラー一覧**または**出力**ウィンドウです。 エラーをダブルクリックして、**エラー一覧**CMakeLists.txt で問題が発生した行に移動します。

   ![CMakeLists.txt ファイル エラー](media/cmake-cmakelists-error.png "CMakeLists.txt ファイル エラー")

## <a name="cmake_settings"></a> CMake 設定とカスタム構成

既定では、Visual Studio は、6 つの既定の CMake 構成 (「x86 デバッグ」、"x86 Release"、「x64 デバッグ」、「x64 リリース」、「Linux デバッグ」と「Linux リリース」) を提供します。 これらの構成では、特定のプロジェクトの CMake キャッシュを作成する CMake.exe を呼び出す方法を定義します。 これらの構成を変更または新規のカスタム構成を作成、 **CMake |CMake 設定を変更する**、設定を適用する CMakeLists.txt ファイルを選択します。 **CMake 設定の変更**コマンドは、ファイルのコンテキスト メニューで利用可能なも**ソリューション エクスプ ローラー**です。 このコマンドは、プロジェクト フォルダーに CMakeSettings.json ファイルを作成します。 このファイルを使用して、ファイルを再作成、CMake キャッシュ、たとえば後に、**クリーン**操作します。 

   ![CMake メイン メニュー コマンドの設定の変更](media/cmake-change-settings.png)


JSON の IntelliSense を使用して、CMakeSettings.json ファイルを編集できます。

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

次の例は、CMakeSettings.json で独自に作成する開始点として使用することができます、サンプルの構成を示しています。

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

1. **名前**: C++ の構成のドロップダウン リストに表示される名前です。 このプロパティの値は、マクロとしても使用できます`${name}`、他のプロパティ値を指定します。 例については、次を参照してください。、 **buildRoot** CMakeSettings.json で定義します。
1. **ジェネレーター**: マップ、 **-g**切り替えを使用するコード ジェネレーターを指定します。 このプロパティは、マクロとしても使用できます`${generator}`、他のプロパティ値を指定したりします。 現在、visual Studio には、次の CMake ジェネレーターがサポートされています。


    - 「忍者」
    - "Visual Studio 2015 の 14"
    - "Visual Studio 2015 の 14 ARM"
    - "Visual Studio 2015 の 14 Win64"
    - "Visual Studio 15 2017"
    - "Visual Studio 15 2017 ARM"
    - "Visual Studio 15 2017 Win64"

忍者が高速なビルド速度は柔軟性と関数の代わりに設計されているため、既定値として設定されます。 ただし、いくつかの CMake プロジェクトは忍者を使用して、正しくビルドすることでない可能性があります。 この場合、代わりに、Visual Studio プロジェクトを生成する CMake に指示できます。

Visual Studio ジェネレーターを指定する、CMakeSettings.json メイン メニューからを選択して開きます**CMake |CMake 設定を変更する**です。 「忍者」を削除し、"V"を入力します。 これには、必要なジェネレーターを選択することができます、IntelliSense がアクティブにします。

1. **buildRoot**: マップ **-DCMAKE_BINARY_DIR**スイッチし、CMake キャッシュを作成するを指定します。 フォルダーが存在しない場合は作成されます。
1. **変数**: として受け渡される CMake 変数の名前と値のペアを含む **-d**_名前_**=**_値_ CMake にします。 CMake プロジェクトのビルド手順では、直接、CMake キャッシュ ファイルに任意の変数の追加を指定する場合は、追加することは、ここ代わりをお勧めします。
1. **cmakeCommandArgs**: CMake.exe に渡す追加のスイッチを指定します。
1. **configurationType**: 選択したコード ジェネレーターのビルド構成の種類を定義します。 現在サポートされている値は、"Debug"、"MinSizeRel"、"Release"および"RelWithDebInfo"です。

### <a name="environment-variables"></a>環境変数

CMakeSettings.json には、上記で説明したプロパティのいずれかでの使用の環境変数もサポートしています。 使用する構文は`${env.FOO}`を環境変数 %FOO% を展開します。
このファイル内で組み込みマクロへのアクセスもがあります。

- `${workspaceRoot}` – ワークスペース フォルダーの完全なパスを提供します。
- `${workspaceHash}` – ハッシュのワークスペースの場所です。(たとえば、フォルダー パスで使用する場合)、現在のワークスペースの一意の識別子を作成するのに役立ちます
- `${projectFile}` – ルート CMakeLists.txt ファイルの完全なパス
- `${projectDir}` – ルート CMakeLists.txt ファイルのフォルダーの完全なパス
- `${thisFile}` – CMakeSettings.json ファイルの完全なパス
- `${name}` – 構成の名前
- `${generator}` – この構成で使用される CMake ジェネレーターの名前

### <a name="ninja-command-line-arguments"></a>忍者コマンドライン引数

ターゲットが指定されていない場合は、'default' のターゲットをビルド (マニュアルを参照してください)。

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|オプション|説明|
|--------------|------------|
| --バージョン  | 忍者バージョン (「1.7.1」) を表示します。|
|   -C DIR   | 何を実行する前にディレクトリを変更します。|
|   -f ファイル  | ビルド入力ファイル (default=build.ninja) を指定します。|
|   -j N     | N ジョブの並列実行 (既定 = 14、利用可能な Cpu から派生)|
|   -k N     | N ジョブが失敗したまで読み進めて (既定値 = 1)|
|   -l N     | 負荷の平均値が N より大きい場合は、新しいジョブを開始しないでください。|
|   -n      | 実行ドライ (コマンドを実行しないが、動作が成功したように)|
|   -v       | ビルド中にすべてのコマンド ラインを表示します。|
|   -d モード  | デバッグ (-d リストをモードを使用する) を有効にします。|
|   -t ツール  | subtool (使用するには、-t リストをサブツール) を実行します。 終了 toplevel オプションです。さらに、ツールに渡されるはフラグ| 
|   -w フラグ  | 警告 (-w リストを警告を使用する) を調整します。|

### <a name="inherited-environments-visual-studio-2017-version-155"></a>継承された環境 (Visual Studio 2017 年 1 バージョン 15.5)
CMakeSettings.json は、継承された環境をサポートしています。 この機能を使用すると、(1) 既定の環境を継承し、(2) を実行するときに、CMake.exe に渡されるカスタムの環境変数を作成できます。

```json
  "inheritEnvironments": [ "msvc_x64_x64" ]
```

上記の例は、同じ実行されている、 **VS 2017 用開発者コマンド プロンプト**で、 **-arch = amd64-host_arch = amd64**引数。

次の表は、既定値と同等のコマンド ラインを示しています。

|コンテキストの名前|説明|
|-----------|-----------------|
|vsdev|既定の Visual Studio 環境|
|msvc_x86|X86 を使用して x86 用にコンパイル ツール|
|msvc_arm| X86 を使用して arm コンパイル ツール|
|msvc_arm64|X86 を使用して for ARM64 コンパイル ツール|
|msvc_x86_x64|X86 を使用して AMD64 用にコンパイル ツール|
|msvc_x64_x64|64 ビット ツールを使用して AMD64 のコンパイル|
|msvc_arm_x64|64 ビット ツールを使用して ARM をコンパイルします。|
|msvc_arm64_x64|64 ビット ツールを使用して for ARM64 コンパイル|

### <a name="custom-environment-variables"></a>カスタムの環境変数
CMakeSettings.json でのカスタム環境変数を定義できますグローバルに構成ごと、または、**環境**プロパティです。 次の例では、1 つのグローバル変数**BuildDir**、これがデバッグ x86 と x64 デバッグの両方の構成に継承します。 各構成の値を指定する変数を使用して、 **buildRoot**プロパティを構成します。 各構成の使用方法にも注意してください、 **inheritEnvironments**プロパティをその構成にのみ適用される変数を指定します。

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

次の例では、x86 デバッグ構成の定義をそれ自体の値、 **BuildDir**プロパティ、およびこの値ではグローバル設定の値をオーバーライド**BuildDir**プロパティように**BuildRoot**に評価される`D:\custom-builddir\x86-Debug`です。

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

## <a name="cmake-configure-step"></a>CMake ステップを構成します。

大幅な変更が加えられたときに、CMakeSettings.json または CMakeLists.txt ファイル、Visual Studio を自動的には、ステップを構成、CMake を再実行します。 構成手順は、エラーなく完了すると、収集される情報は C++ の IntelliSense および言語サービスとにも作成して操作をデバッグします。

CMake の複数のプロジェクトは、同じ CMake 構成名 (たとえば、x86 のデバッグ) を使用して、ときにそれらのすべてを構成してビルド (独自のビルド ルート フォルダー) にその構成を選択するとします。 すべての CMake 構成に参加している CMake プロジェクトからターゲットをデバッグすることができます。

   ![メニュー項目 CMake ビルドのみ](media/cmake-build-only.png "CMake ビルドのみメニュー項目")

ビルドを制限して、ワークスペース内のプロジェクトのサブセットにセッションのデバッグをするには、CMakeSettings.json ファイルに一意の名前で新しい構成を作成し、それらのプロジェクトのみに適用します。 その構成を選択すると、IntelliSense、ビルドとデバッグ コマンドは、指定されたプロジェクトに対してのみ有効です。

## <a name="troubleshooting-cmake-cache-errors"></a>CMake キャッシュ エラーのトラブルシューティング

詳細については、問題を診断 CMake キャッシュの状態を必要がある場合は、開く、 **CMake**メイン メニューまたは**CMakeLists.txt**のコンテキスト メニュー**ソリューション エクスプ ローラー**これらのコマンドのいずれかを実行します。

- **キャッシュを表示する**エディターで、ビルドのルート フォルダーから CMakeCache.txt ファイルを開きます。 (CMakeCache.txt には、ここに加えた編集は根絶キャッシュをクリーンアップする場合。 キャッシュがクリーンアップされた後に永続化を変更する場合は、次を参照してください[CMake 設定とカスタム構成](#cmake_settings)この記事で前述。)。
- **キャッシュ フォルダーを開く**ビルドのルート フォルダーに、エクスプ ローラー ウィンドウが開きます。  
- **キャッシュのクリーンアップ**次 CMake 構成クリーン キャッシュからのステップが開始されるように、ビルドのルート フォルダーを削除します。
- **キャッシュを生成する**強制的に生成するステップの場合でも、Visual Studio では、最新の状態の環境が考慮を実行します。
