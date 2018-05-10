---
title: Visual C でフォルダーのプロジェクトを開く |Microsoft ドキュメント
ms.custom: ''
ms.date: 08/02/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Open Folder Projects in Visual C++
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0fe4eba09f06b987ab11f35429e13796fe6baafb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="open-folder-projects-in-visual-c"></a>Visual C でフォルダーのプロジェクトを開く
Visual Studio 2017 を使用すると、ソース ファイルのフォルダーを開いてすぐに、参照、リファクタリング、デバッグ、IntelliSense のサポートとコーディングを開始し、「フォルダーを開く」機能が導入されています。 .Sln または .vcxproj ファイルが読み込まれていません。必要な場合、カスタム タスクをビルドし、単純な .json ファイルを起動してパラメーターを指定できます。 開いているフォルダーでの電源を Visual C サポートできますだけでなく、ファイルの厳密でないコレクションも事実上、ビルド システム、CMake、忍者、QMake (カタール プロジェクト) に対して、gyp、SCons、Gradle、Buck、make をなどです。 

開いているフォルダーを使用するメイン メニューから選択*ファイル |開いている |フォルダー*またはキーを押して*Ctrl + Shift + Alt + O*です。ソリューション エクスプ ローラーでは、フォルダー内のすべてのファイルがすぐが表示されます。 任意のファイルをクリックして、編集を開始できます。 バックグラウンドでは、Visual Studio は、ファイルのインデックス作成を開始して、IntelliSense、ナビゲーション、およびリファクタリング機能を有効にします。 ファイルを編集、作成、移動、または削除すると、Visual Studio は自動的に変更を追跡し、IntelliSense インデックスを継続的に更新します。 
  
## <a name="cmake-projects"></a>CMake プロジェクト
CMake は、Visual C、C++ デスクトップ ワークロードのコンポーネントの CMake ツールとして、Visual Studio IDE に統合されています。 詳細については、「[CMake Tools for Visual C++](cmake-tools-for-visual-cpp.md)」 (Visual C++ の CMake ツール) をご覧ください。
 
## <a name="qmake-projects-that-target-the-qt-framework"></a>Qt framework を対象とする QMake プロジェクト
CMake ツールを使用して Visual C のターゲット Qt Qt プロジェクトをビルドまたは Qt Visual Studio 拡張機能を使用することができます。 注: 2017 年 8 月時点で、 [Qt Visual Studio 拡張機能のサポートの Visual Studio 2017](https://download.qt.io/development_releases/vsaddin/)はベータ版として使用できます。

## <a name="gyp-cons-scons-buck-etc"></a>gyp、短所、SCons、Buck など
Visual C では、ビルド システムを使用して Visual C の IDE とデバッガーの利点を利用できます。 プロジェクトのルート フォルダーを開くと、Visual C はヒューリスティックを使用して、IntelliSense および参照するため、ソース ファイルのインデックスを作成します。 CppProperties.json ファイルを編集して、コードの構造についてのヒントを提供できます。 同様の方法では、launch.vs.json ファイルを編集して、ビルドのプログラムを構成できます。 

## <a name="configuring-open-folder-projects"></a>フォルダーを開くプロジェクトの構成
フォルダーを開くプロジェクトは、次の 3 つの JSON ファイルをカスタマイズできます。
|||
|-|-|
|CppProperties.json|参照するためのカスタム構成情報を指定します。 ルート プロジェクト フォルダーに必要な場合は、このファイルを作成します。|
|launch.vs.json|コマンドライン引数を指定します。 指定するには、**ソリューション エクスプローラー**のコンテキスト メニュー項目 **[デバッグ設定と起動設定]** を使用します。|
|tasks.vs.json|カスタム ビルド コマンドやコンパイラ スイッチを指定します。 指定するには、**ソリューション エクスプローラー**のコンテキスト メニュー項目 **[タスクの構成]** を使用します。|

### <a name="configure-intellisense-with-cpppropertiesjson"></a>CppProperties.json と IntelliSense を構成します。
IntelliSense および動作を部分的に参照を定義するアクティブなビルド構成に依存 #include のパス、コンパイラ スイッチ、およびその他のパラメーターです。 既定では、Visual Studio はデバッグ構成とリリース構成を提供します。 プロジェクトでは、IntelliSense および参照機能を完全にコードを理解するために、カスタム構成を作成する必要があります。 新しい構成を定義するのには、ルート フォルダーに CppProperties.json という名前のファイルを作成します。 次に例を示します。

```json
{
  "configurations": [
    {
      "name": "Windows x64",
      "includePath": [ "include" ],
      "defines": [ "_DEBUG" ],
      "compilerSwitches": "/std:c++17",
      "intelliSenseMode": "msvc-x64",
      "forcedInclude": [ "pch.h" ],
      "undefines": []
    }
  ]
}
```
構成は、次のプロパティのいずれかのがあります。

|||  
|-|-| 
|`name`|C++ の構成のドロップダウン リストに表示される構成名|
|`includePath`|(ほとんどのコンパイラの maps/I に) インクルード パスで指定するフォルダーの一覧|
|`defines`|定義されている (のマップを/D にほとんどのコンパイラ) をする必要のあるマクロの一覧|
|`compilerSwitches`|IntelliSense の動作に影響を与える 1 つ以上の追加スイッチ|
|`forcedInclude`|コンパイル単位ごとに自動的に含まれるヘッダー (MSVC の/FI にマップまたは - clang を含む)|
|`undefines`|未定義 (MSVC の/U にマッピング) にするマクロの一覧|
|`intelliSenseMode`|使用する IntelliSense エンジン。 MSVC、gcc または Clang アーキテクチャの特定のバリエーションを指定できます。
- msvc x86 (既定値)
- msvc-x64
- msvc-arm
- windows-clang-x86
- windows-clang-x64
- windows-clang-arm
- Linux-x64
- Linux-x86
- Linux arm
- gccarm

#### <a name="environment-variables"></a>環境変数
CppProperties.json サポート システム環境変数の展開には、パスとその他のプロパティ値が含まれます。 構文は`${env.FOODIR}`環境変数を展開する`%FOODIR%`です。 次のシステム定義の変数もサポートします。

|変数名|説明|  
|-----------|-----------------|
|vsdev|既定の Visual Studio 環境|
|msvc_x86|X86 を使用して x86 用にコンパイル ツール|
|msvc_arm|X86 を使用して arm コンパイル ツール|
|msvc_arm64|X86 を使用して for ARM64 コンパイル ツール|
|msvc_x86_x64|X86 を使用して AMD64 用にコンパイル ツール|
|msvc_x64_x64|64 ビット ツールを使用して AMD64 のコンパイル|
|msvc_arm_x64|64 ビット ツールを使用して ARM をコンパイルします。|
|msvc_arm64_x64|64 ビット ツールを使用して for ARM64 コンパイル|

Linux ワークロードがインストールされているときに、次の環境は Linux および WSL をリモートから指定できます。

|変数名|説明|  
|-----------|-----------------|
|linux_x86|X86 を対象と Linux でのリモート|
|linux_x64|X64 を対象と Linux でのリモート|
|linux_arm|リモート ARM Linux を対象します。|

カスタム環境変数を定義できます CppProperties.json にするか、グローバルまたは構成単位です。 次の例は、どのように既定およびカスタムの環境変数を宣言して使用できます。 グローバル**環境**プロパティという名前の変数を宣言して**INCLUDE**任意の構成で使用できます。

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\\src\\includes"
    }
  ],
 
  "configurations": [
    {
      "inheritEnvironments": [
        // Inherit the MSVC 32-bit environment and toolchain.
        "msvc_x86"
      ],
      "name": "x86",
      "includePath": [
        // Use the include path defined above.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "msvc-x86"
    },
    {
      "inheritEnvironments": [
        // Inherit the MSVC 64-bit environment and toolchain.
        "msvc_x64"
      ],
      "name": "x64",
      "includePath": [
        // Use the include path defined above.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "msvc-x64"
    }
  ]
}
```
定義することも、**環境**構成では、その構成にのみ適用して、同じ名前のグローバル変数を上書きするように内部プロパティです。 次の例では、x64 の構成で定義するローカル**INCLUDE**グローバル値をオーバーライドする変数。

```json
{
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\\src\\includes"
    }
  ],
 
  "configurations": [
    {
      "inheritEnvironments": [
        "msvc_x86"
      ],
      "name": "x86",
      "includePath": [
        // Use the include path defined in the global environments property.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "msvc-x86"
    },
    {
      "environments": [
        {
          // Append 64-bit specific include path to env.INCLUDE.
          "INCLUDE": "${env.INCLUDE};${workspaceRoot}\\src\\includes64"
        }
      ],
 
      "inheritEnvironments": [
        "msvc_x64"
      ],
      "name": "x64",
      "includePath": [
        // Use the include path defined in the local environments property.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "msvc-x64"
    }
  ]
}
```

すべてのカスタムし、既定の環境変数も tasks.vs.json および launch.vs.json で使用できます。

#### <a name="macros"></a>[マクロ]
次の組み込みのマクロ CppProperties.json 内へのアクセスがあります。
|||
|-|-|
|`${workspaceRoot}`| ワークスペースのフォルダーへの完全パス|
|`${projectRoot}`| CppProperties.json が配置されているフォルダーへの完全パス|
|`${vsInstallDir}`| VS 2017 の実行中のインスタンスがインストールされているフォルダーへの完全パス|

たとえば、プロジェクトには、含めるフォルダーがあり、windows.h と Windows SDK から他の一般的なヘッダーも含まれます、場合をこれらの構成ファイルが含まれています、CppProperties.json を更新します。

```json
{
  "configurations": [
    {
      "name": "Windows",
      "includePath": [
        // local include folder
        "${workspaceRoot}\\include",
        // Windows SDK and CRT headers
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\ucrt",
        "${env.NETFXSDKDir}\\include\\um",
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\um",
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\shared",
        "${env.VCToolsInstallDir}include"
      ]
    }
  ]
}
```

**注:** `%WindowsSdkDir%`と`%VCToolsInstallDir%`グローバル環境変数になるように、"開発者コマンド プロンプトから VS 2017 の"これらの変数を定義する devenv.exe を起動することを確認するように設定されていません。

IntelliSense のトラブルシューティングを行うにされていない場合に発生したエラーは、パスを含めるを開く、**エラー一覧**"IntelliSense のみ"の出力をフィルター処理し、エラー コード E1696「を開けませんソース ファイル」です。 

CppProperties.json で任意の数の構成を作成できます。 それぞれが、構成のドロップダウン リストに表示されます。

```json
{
  "configurations": [
    {
      "name": "Windows",
      ...
    },
    {
      "name": "with EXTERNAL_CODECS",
      ...
    }
  ]
}
```
### <a name="define-tasks-with-tasksvsjson"></a>tasks.vs.json でタスクを定義する
IDE でタスクとして直接実行することで、現在のワークスペースにあるファイルに対してビルド スクリプトやその他の外部操作を自動化できます。 ファイルまたはフォルダーを右クリックし、**[タスクの構成]** を選択すると、新しいタスクを構成できます。 

![フォルダーを開くタスクを構成します。](media/open-folder-config-tasks.png)

これを作成 (またはが表示されます)、`tasks.vs.json`ファイル .vs フォルダーに Visual Studio がルート プロジェクト フォルダーに作成します。 このファイル内の任意のタスクを定義して、呼び出すことから、**ソリューション エクスプ ローラー**コンテキスト メニュー。 次の例では、1 つのタスクを定義する tasks.vs.json ファイルを示します。 `taskName` コンテキスト メニューに表示される名前を定義します。 `appliesTo` コマンドを実行できるファイルを定義します。 `command`プロパティは、コンソール (cmd.exe Windows 上) のパスを識別する文字列環境変数を参照します。 CppProperties.json または CMakeSettings.json で宣言されている環境変数を参照することもできます。 `args`プロパティが呼び出されるコマンドラインを指定します。 `${file}` マクロは、**ソリューション エクスプローラー**で選択したファイルを取得します。 次の例では、現在選択されている .cpp ファイルのファイル名が表示されます。

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskName": "Echo filename",
      "appliesTo": "*.cpp",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": ["echo ${file}"]
    }
  ]
}
```
Tasks.vs.json を保存した後、フォルダー内の .cpp ファイルを右クリックし、選択**エコー filename**からコンテキスト メニューとは、出力ウィンドウに表示されるファイル名を参照してください。



#### <a name="appliesto"></a>AppliesTo
任意のファイルまたはフォルダーのタスクを作成するには、`appliesTo` フィールドに名前を指定します (例:`"appliesTo" : "hello.cpp"`)。 次のファイル マスクを値として使用できます。
|||
|-|-|
|`"*"`| タスクは、ワークスペース内のすべてのファイルとフォルダーで使用できます|
|`"*/"`| タスクは、ワークスペース内のすべてのフォルダーで使用できます|
|`"*.cpp"`| タスクが ワークスペースで、拡張子 .cpp を持つすべてのファイルに利用可能|
|`"/*.cpp"`| タスクは、ワークスペースのルートに拡張子 .cpp を持つすべてのファイルに利用できます。|
|`"src/*/"`| タスクは、"src" フォルダーのすべてのサブフォルダーで使用できます|
|`"makefile"`| タスクは、ワークスペース内のすべての makefile ファイルで使用できます|
|`"/makefile"`| タスクは、ワークスペースのルートにある makefile にのみ使用できます|

#### <a name="output"></a>出力
使用して、`output`プロパティをキーを押したときに起動する実行可能ファイルを指定する**f5 キーを押して**です。 例えば:

```json
      "output": "${workspaceRoot}\\bin\\hellomake.exe" 
```

#### <a name="macros-for-tasksvsjson"></a>tasks.vs.json のマクロ

|||
|-|-|
|`${env.<VARIABLE>}`| 任意の環境変数 (たとえば、${env を指定します。パス} ${env.COMSPEC} というように) 開発者コマンド プロンプトに設定されています。 詳細については、「[Visual Studio 用開発者コマンド プロンプト](/dotnet/framework/tools/developer-command-prompt-for-vs)」を参照してください。|
|`${workspaceRoot}`| ワークスペース フォルダー (たとえば、"C:\sources\hello") への完全パス|
|`${file}`| ファイルまたは (たとえば、"C:\sources\hello\src\hello.cpp") に対してこのタスクの実行を選択したフォルダーの完全なパス|
|`${relativeFile}`| ファイルまたはフォルダー (たとえば、"src\hello.cpp"など) への相対パス|
|`${fileBasename}`| パスまたは拡張機能 (たとえば、「こんにちは」) のないファイルの名前|
|`${fileDirname}`| ファイル名 (たとえば、"C:\sources\hello\src") を除く、ファイルへの完全パス|
|`${fileExtname}`| 選択したファイル (たとえば、".cpp") の拡張機能|

#### <a name="custom-macros"></a>カスタム マクロ
Tasks.vs.json でカスタムのマクロを定義するには、タスクのブロックの前に名前と値のペアを追加します。 次の例は、という名前のマクロを定義`outDir`で消費する、`args`プロパティ。

```json
{
"version": "0.2.1",
  "outDir": "${workspaceRoot}\\bin",
  "tasks": [
    {
      "taskName": "List outputs",
      "*",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": [
        "dir ${outDir}"
      ]
    }
  ]
```

### <a name="configure-debugging-parameters-with-launchvsjson"></a>Launch.vs.json とデバッグのパラメーターを構成します。
実行可能ファイルを右クリックし、プログラムのコマンドライン引数をカスタマイズする**ソリューション エクスプ ローラー**選択**デバッグ構成と起動設定**です。 開き、既存`launch.vs.json`ファイル、または存在しない場合、選択したプログラムに関する情報があらかじめ設定された新しいファイルが作成されます。 

追加の引数を指定するだけで追加、`args`次の例で示すように、JSON 配列。

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "project": "CPP\\7zip\\Bundles\\Alone\\O\\7za.exe",
      "name": "7za.exe list content of helloworld.zip",
      "args": [ "l", "d:\\sources\\helloworld.zip" ]
    }
  ]
}
```

このファイルを保存して、デバッグ ターゲット ドロップダウン リストに、新しい構成が表示されます、デバッガーを開始するように選択できます。 実行可能ファイルの任意の数を好きなように、多くのデバッグ構成を作成できます。 キーを押す場合**f5 キーを押して**ここで、デバッガーが起動し、既に設定したすべてのブレークポイントがヒットされます。 使い慣れたデバッガーのすべての windows およびそれらの機能では、使用できるようになりました。

## <a name="see-also"></a>関連項目
[IDE と Visual C++ 開発用ツール](ide-and-tools-for-visual-cpp-development.md)

