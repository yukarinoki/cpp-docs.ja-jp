---
title: Visual C++ での "フォルダーを開く" プロジェクト | Microsoft Docs
ms.custom: ''
ms.date: 06/01/2018
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
ms.openlocfilehash: d4444e70ec158d7afa35c3955bbef9af4bfa12f2
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "43131324"
---
# <a name="open-folder-projects-in-visual-c"></a>Visual C++ での "フォルダーを開く" プロジェクト

Visual Studio 2017 以降で "フォルダーを開く" 機能を使うと、ソース ファイルのフォルダーを開き、IntelliSense、参照、リファクタリング、デバッグなどのサポートを利用してコーディングをすぐに始めることができます。 .sln または .vcxproj ファイルは読み込まれません。必要な場合は、カスタム タスクを指定し、簡単な .json ファイルを使ってパラメーターをビルドして起動できます。 "フォルダーを開く" を利用することで、Visual C++ は、ファイルの厳密でないコレクションだけでなく、CMake、Ninja、QMake (Qt プロジェクトの場合)、gyp、SCons、Gradle、Buck、make などのほとんどすべてのビルド システムもサポートできるようになります。 

"フォルダーを開く" を使うには、メイン メニューから *[ファイル] > [開く] > [フォルダー]* を選ぶか、*Ctrl + Shift + Alt + O* キーを押します。フォルダー内のすべてのファイルがソリューション エクスプローラーにすぐに表示されます。 任意のファイルをクリックして、編集を開始できます。 バックグラウンドでは、Visual Studio は、ファイルのインデックス作成を開始して、IntelliSense、ナビゲーション、およびリファクタリング機能を有効にします。 ファイルを編集、作成、移動、または削除すると、Visual Studio は自動的に変更を追跡し、IntelliSense インデックスを継続的に更新します。 
  
## <a name="cmake-projects"></a>CMake プロジェクト
CMake は、C++ デスクトップ ワークロードのコンポーネントである CMake Tools for Visual C++ として Visual Studio IDE に統合されています。 詳細については、「[CMake Tools for Visual C++](cmake-tools-for-visual-cpp.md)」 (Visual C++ の CMake ツール) をご覧ください。
 
## <a name="qmake-projects-that-target-the-qt-framework"></a>Qt フレームワークを対象とする QMake プロジェクト
CMake Tools for Visual C++ を使って Qt を対象に Qt プロジェクトをビルドするか、または Visual Studio 2015 または Visual Studio 2017 のどちらかで [Qt Visual Studio 拡張機能](https://download.qt.io/development_releases/vsaddin/)を使うことができます。

## <a name="gyp-cons-scons-buck-etc"></a>gyp、Cons、SCons、Buck など
任意のビルド システムを Visual C++ で使いながら、Visual C++ IDE とデバッガーの利点を利用することもできます。 プロジェクトのルート フォルダーを開くと、Visual C++ はヒューリスティックを使って IntelliSense と参照のためにソース ファイルにインデックスを付けます。 CppProperties.json ファイルを編集することにより、コードの構造についてのヒントを提供できます。 同様の方法で、launch.vs.json ファイルを編集することにより、ビルド プログラムを構成できます。 

## <a name="configuring-open-folder-projects"></a>"フォルダーを開く" プロジェクトの構成
次の 3 つの JSON ファイルを使って、"フォルダーを開く" プロジェクトをカスタマイズできます。
|||
|-|-|
|CppProperties.json|参照のためのカスタム構成情報を指定します。 必要な場合は、ルート プロジェクト フォルダーにこのファイルを作成します。|
|launch.vs.json|コマンド ライン引数を指定します。 指定するには、**ソリューション エクスプローラー**のコンテキスト メニュー項目 **[デバッグ設定と起動設定]** を使用します。|
|tasks.vs.json|カスタム ビルド コマンドとコンパイラ スイッチを指定します。 指定するには、**ソリューション エクスプローラー**のコンテキスト メニュー項目 **[タスクの構成]** を使用します。|

### <a name="configure-intellisense-with-cpppropertiesjson"></a>CppProperties.json を使って IntelliSense を構成する
IntelliSense と参照の動作は、#include のパス、コンパイラ スイッチ、およびその他のパラメーターを定義するアクティブなビルド構成に部分的に依存します。 既定では、Visual Studio はデバッグ構成とリリース構成を提供します。 一部のプロジェクトでは、IntelliSense と参照の機能がコードを完全に理解するために、カスタム構成の作成が必要な場合があります。 新しい構成を定義するには、CppProperties.json という名前のファイルをルート フォルダーに作成します。 次に例を示します。

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
構成には、次のどのプロパティでも含めることができます。

|||  
|-|-| 
|`name`|C++ の構成ドロップダウンに表示される構成の名前です|
|`includePath`|インクルード パスで指定する必要があるフォルダーのリストです (ほとんどのコンパイラで /I に対応します)|
|`defines`|定義する必要のあるマクロのリストです (ほとんどのコンパイラで /D に対応します)|
|`compilerSwitches`|IntelliSense の動作に影響を与えることができる 1 つ以上の追加スイッチです|
|`forcedInclude`|すべてのコンパイル単位に自動的にインクルードされるヘッダーです (MSVC の /FI または clang の -include に対応します)|
|`undefines`|未定義にするマクロのリストです (MSVC の /U に対応します)|
|`intelliSenseMode`|使用する IntelliSense エンジンです。 MSVC、gcc、または Clang に対するアーキテクチャ固有のバリエーションを指定できます。
- msvc-x86 (既定)
- msvc-x64
- msvc-arm
- windows-clang-x86
- windows-clang-x64
- windows-clang-arm
- Linux-x64
- Linux-x86
- Linux-arm
- gccarm

#### <a name="environment-variables"></a>環境変数
CppProperties.json は、インクルード パスと他のプロパティ値に対するシステム環境変数の展開をサポートします。 環境変数 `%FOODIR%` を展開する場合の構文は `${env.FOODIR}` です。 次のシステム定義変数もサポートされます。

|変数名|説明|  
|-----------|-----------------|
|vsdev|既定の Visual Studio 環境|
|msvc_x86|x86 ツールを使って、x86 用にコンパイルします|
|msvc_arm|x86 ツールを使って、ARM 用にコンパイルします|
|msvc_arm64|x86 ツールを使って、ARM64 用にコンパイルします|
|msvc_x86_x64|x86 ツールを使って、AMD64 用にコンパイルします|
|msvc_x64_x64|64 ビット ツールを使って、AMD64 用にコンパイルします|
|msvc_arm_x64|64 ビット ツールを使って、ARM 用にコンパイルします|
|msvc_arm64_x64|64 ビット ツールを使って、ARM64 用にコンパイルします|

Linux ワークロードがインストールされている場合、Linux および WSL をリモートでターゲットにするために次の環境変数を使用できます。

|変数名|説明|  
|-----------|-----------------|
|linux_x86|x86 Linux をリモートでターゲットにします|
|linux_x64|x64 Linux をリモートでターゲットにします|
|linux_arm|ARM Linux をリモートでターゲットにします|

CppProperties.json では、カスタム環境変数をグローバルに、または構成単位で定義できます。 次の例では、既定の環境変数およびカスタム環境変数を宣言して使う方法を示します。 グローバルな **environments** プロパティでは、任意の構成で使用できる **INCLUDE** という名前の変数が宣言されています。

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
構成の内部で **environments** プロパティを定義することで、その構成のみにプロパティを適用して、同じ名前のグローバル変数をオーバーライドすることもできます。 次の例の x64 構成で定義されているローカルな **INCLUDE** 変数は、グローバルな値をオーバーライドします。

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

すべてのカスタム環境変数と既定の環境変数は、tasks.vs.json および launch.vs.json でも使うことができます。

#### <a name="macros"></a>[マクロ]
CppProperties.json 内の次の組み込みマクロにアクセスできます。
|||
|-|-|
|`${workspaceRoot}`| ワークスペース フォルダーへの完全なパスです|
|`${projectRoot}`| CppProperties.json が配置されているフォルダーへの完全なパスです|
|`${vsInstallDir}`| VS 2017 の実行中のインスタンスがインストールされているフォルダーへの完全なパスです|

たとえば、プロジェクトにインクルード フォルダーがあるだけでなく、windows.h および他の共通ヘッダーも Windows SDK からインクルードしている場合、CppProperties.json の構成ファイルをこれらのインクルードで更新したい場合があります。

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

**注:** `%WindowsSdkDir%` と `%VCToolsInstallDir%` はグローバル環境変数として設定されていないため、これらの変数を定義する devenv.exe は "開発者コマンド プロンプト for VS 2017" から起動してください。

インクルード パスがないことにより発生する IntelliSense のエラーをトラブルシューティングするには、**[エラー一覧]** を開き、出力を "IntelliSense のみ" およびエラー コード E1696 "ソース ファイル ... を開くことができません" でフィルター処理します。 

CppProperties.json では任意の数の構成を作成できます。 それぞれが、構成ドロップダウンに表示されます。

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

!["フォルダーを開く" のタスクの構成](media/open-folder-config-tasks.png)

これにより、Visual Studio がルート プロジェクト フォルダーに作成する .vs フォルダー内の `tasks.vs.json` ファイルが作成されます (または開かれます)。 このファイルで任意のタスクを定義し、**ソリューション エクスプローラー**のコンテキスト メニューから呼び出すことができます。 単一のタスクを定義する tasks.vs.json ファイルの例を次に示します。 `taskName` では、コンテキスト メニューに表示される名前を定義します。 `appliesTo` では、コマンドを実行できるファイルを定義します。 `command` プロパティは、コンソール (Windows では cmd.exe) のパスを示す COMSPEC 環境変数を参照します。 CppProperties.json または CMakeSettings.json で宣言されている環境変数を参照することもできます。 `args` プロパティでは、呼び出すコマンド ラインを指定します。 `${file}` マクロは、**ソリューション エクスプローラー**で選択したファイルを取得します。 次の例では、現在選択されている .cpp ファイルのファイル名が表示されます。

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
tasks.vs.json を保存した後、フォルダー内の任意の .cpp ファイルを右クリックし、コンテキスト メニューから **[Echo filename]** を選んで、[出力] ウィンドウにファイル名が表示されることを確認します。



#### <a name="appliesto"></a>AppliesTo
任意のファイルまたはフォルダーのタスクを作成するには、`appliesTo` フィールドに名前を指定します (例:`"appliesTo" : "hello.cpp"`)。 次のファイル マスクを値として使用できます。
|||
|-|-|
|`"*"`| タスクは、ワークスペース内のすべてのファイルとフォルダーで使用できます|
|`"*/"`| タスクは、ワークスペース内のすべてのフォルダーで使用できます|
|`"*.cpp"`| タスクは、ワークスペース内の拡張子が .cpp のすべてのファイルで使用できます|
|`"/*.cpp"`| タスクは、ワークスペースのルートにある拡張子が .cpp のすべてのファイルで使用できます|
|`"src/*/"`| タスクは、"src" フォルダーのすべてのサブフォルダーで使用できます|
|`"makefile"`| タスクは、ワークスペース内のすべての makefile ファイルで使用できます|
|`"/makefile"`| タスクは、ワークスペースのルートにある makefile にのみ使用できます|

#### <a name="output"></a>出力
`output` プロパティを使って、**F5** キーを押すと起動する実行可能ファイルを指定します。 例:

```json
      "output": "${workspaceRoot}\\bin\\hellomake.exe" 
```

#### <a name="macros-for-tasksvsjson"></a>tasks.vs.json のマクロ

|||
|-|-|
|`${env.<VARIABLE>}`| 開発者コマンド プロンプトに設定されている環境変数 (${env.PATH}、${env.COMSPEC} など) を指定します。 詳細については、「[Visual Studio 用開発者コマンド プロンプト](/dotnet/framework/tools/developer-command-prompt-for-vs)」を参照してください。|
|`${workspaceRoot}`| ワークスペース フォルダーの完全なパスです (例: "C:\sources\hello")|
|`${file}`| このタスクの実行対象として選択されたファイルまたはフォルダーの完全なパスです (例: "C:\sources\hello\src\hello.cpp")|
|`${relativeFile}`| ファイルまたはフォルダーの相対パスです (例: "src\hello.cpp")|
|`${fileBasename}`| パスまたは拡張子のないファイル名です (例: "hello")|
|`${fileDirname}`| ファイル名を除いたファイルの完全なパスです (例: "C:\sources\hello\src")|
|`${fileExtname}`| 選択したファイルの拡張子です (例: ".cpp")|

#### <a name="custom-macros"></a>カスタム マクロ
tasks.vs.json でカスタム マクロを定義するには、タスク ブロックの前に名前と値のペアを追加します。 次の例では、`args` プロパティで使用される `outDir` という名前のマクロを定義しています。

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

### <a name="configure-debugging-parameters-with-launchvsjson"></a>launch.vs.json でデバッグ パラメーターを構成する
プログラムのコマンド ライン引数をカスタマイズするには、**ソリューション エクスプローラー**で実行可能ファイルを右クリックし、**[デバッグ設定と起動設定]** を選びます。 これにより、既存の `launch.vs.json` ファイルが開きます。または、存在しない場合は、新しいファイルが作成されて、選んだプログラムに関する情報が設定されます。 

追加の引数を指定するには、次の例で示すように、`args` JSON 配列に追加するだけです。

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

このファイルを保存すると、[デバッグ ターゲット] ドロップダウンに新しい構成が表示され、名前を選択してデバッガーを起動できるようになります。 必要に応じて、任意の数の実行可能ファイルに対し、デバッグ構成をいくつでも作成できます。 ここで **F5** キーを押すと、デバッガーが起動し、既に設定してあるブレークポイントにヒットします。 使い慣れたすべてのデバッガー ウィンドウとそれらの機能を使用できるようになりました。

## <a name="see-also"></a>参照
[IDE と Visual C++ 開発用ツール](ide-and-tools-for-visual-cpp-development.md)

