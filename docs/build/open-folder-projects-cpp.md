---
title: Visual Studio での C++ ビルド システムの [フォルダーを開く] のサポート
ms.date: 03/21/2019
helpviewer_keywords:
- Open Folder Projects in Visual Studio
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: 4f59781833a303ad2db837549eddca2f2ce291b1
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220498"
---
# <a name="open-folder-projects-for-c"></a>C++ の [フォルダーを開く] プロジェクト

Visual Studio 2017 以降で "フォルダーを開く" 機能を使うと、ソース ファイルのフォルダーを開き、IntelliSense、参照、リファクタリング、デバッグなどのサポートを利用してコーディングをすぐに始めることができます。 .sln または .vcxproj ファイルは読み込まれません。必要な場合は、カスタム タスクを指定し、簡単な .json ファイルを使ってパラメーターをビルドして起動できます。 [フォルダーを開く] に関する詳細については、「[プロジェクトまたはソリューションを使用せずに Visual Studio でコードを開発する](/visualstudio/ide/develop-code-in-visual-studio-without-projects-or-solutions)」を参照してください。

CMake は、C++ デスクトップ ワークロードのコンポーネントである CMake Tools for Visual Studio として Visual Studio IDE に統合されています。 詳細については、「[CMake projects in Visual Studio](cmake-projects-in-visual-studio.md)」 (Visual Studio の CMake プロジェクト) をご覧ください。 他の任意のビルド システムでは、[フォルダーを開く] 機能を使用することができます。 [フォルダーを開く] によって、ビルド システムおよびコンパイラ ツールセットから、コード エディター、デバッガー、およびアナライザーが事実上切り離されます。 CMake、Ninja、QMake (Qt プロジェクトの場合)、gyp、SCons、Gradle、Buck、make などのほとんどすべてのビルド システムで、豊富な IntelliSense 機能を備えた C++ コード エディター、コード アナライザー、Visual Studio デバッガーを使用できます。 ビルド システムがない 1 つのファイルでもファイルの緩やかな集合でも動作します。

"フォルダーを開く" を使うには、メイン メニューから **[ファイル] > [開く] > [フォルダー]** を選ぶか、**Ctrl + Shift + Alt + O** キーを押します。フォルダー内のすべてのファイルがソリューション エクスプローラーにすぐに表示されます。 任意のファイルをクリックして、編集を開始できます。 バックグラウンドでは、Visual Studio は、ファイルのインデックス作成を開始して、IntelliSense、ナビゲーション、およびリファクタリング機能を有効にします。 ファイルを編集、作成、移動、または削除すると、Visual Studio は自動的に変更を追跡し、IntelliSense インデックスを継続的に更新します。 

## <a name="qmake-projects-that-target-the-qt-framework"></a>Qt フレームワークを対象とする QMake プロジェクト

CMake Tools for Visual Studio を使って Qt を対象に Qt プロジェクトをビルドするか、または Visual Studio 2015 または Visual Studio 2017 のどちらかで [Qt Visual Studio 拡張機能](https://download.qt.io/development_releases/vsaddin/)を使うことができます。

## <a name="gyp-cons-scons-buck-etc"></a>gyp、Cons、SCons、Buck など

任意のビルド システムを Visual Studio で使いながら、Visual C++ IDE とデバッガーの利点を利用することもできます。 プロジェクトのルート フォルダーを開くと、C++ コード エディターがヒューリスティックを使って IntelliSense と参照のためにソース ファイルにインデックスを付けます。 CppProperties.json ファイルを編集することにより、コードの構造についてのヒントを提供できます。 同様の方法で、launch.vs.json ファイルを編集することにより、ビルド プログラムを構成し、呼び出すことができます。

## <a name="configuring-open-folder-projects"></a>"フォルダーを開く" プロジェクトの構成

次の 3 つの JSON ファイルを使って、"フォルダーを開く" プロジェクトをカスタマイズできます。

| | |
|-|-|
|CppProperties.json|参照のためのカスタム構成情報を指定します。 必要な場合は、ルート プロジェクト フォルダーにこのファイルを作成します。 (CMake プロジェクトで使用されません。)|
|tasks.vs.json|カスタム ビルド コマンドとコンパイラ スイッチを指定します。 指定するには、**ソリューション エクスプローラー**のコンテキスト メニュー項目 **[タスクの構成]** を使用します。|
|launch.vs.json|デバッガーのコマンド ライン引数を指定します。 指定するには、**ソリューション エクスプローラー**のコンテキスト メニュー項目 **[デバッグ設定と起動設定]** を使用します。|

### <a name="configure-intellisense-and-browsing-hints-with-cpppropertiesjson"></a>CppProperties.json を使って IntelliSense と参照のヒントを構成する

IntelliSense と参照の動作は、#include のパス、コンパイラ スイッチ、およびその他のパラメーターを定義するアクティブなビルド構成に部分的に依存します。 既定では、Visual Studio はデバッグ構成とリリース構成を提供します。 CMake プロジェクトでは、この目的で CMakeSettings.json ファイルと CMakeLists.txt ファイルが使われます。 他の種類の [ファイルを開く] プロジェクトでは、IntelliSense と参照の機能がコードを完全に理解するために、カスタム構成の作成が必要な場合があります。 新しい構成を定義するには、CppProperties.json という名前のファイルをルート フォルダーに作成します。 次に例を示します。

```json
{
  "configurations": [
    {
      "name": "Windows x64",
      "includePath": [ "include" ],
      "defines": [ "_DEBUG" ],
      "compilerSwitches": "/std:c++17",
      "intelliSenseMode": "windows-msvc-x64",
      "forcedInclude": [ "pch.h" ],
      "undefines": []
    }
  ]
}
```
詳細については、「[CppProperties schema reference](cppproperties-schema-reference.md)」 (CppProperties スキーマ リファレンス) を参照してください。

### <a name="define-build-tasks-with-tasksvsjson"></a>tasks.vs.json でビルド タスクを定義する

IDE でタスクとして直接実行することで、現在のワークスペースにあるファイルに対してビルド スクリプトやその他の外部操作を自動化できます。 ファイルまたはフォルダーを右クリックし、**[タスクの構成]** を選択すると、新しいタスクを構成できます。

!["フォルダーを開く" のタスクの構成](media/open-folder-config-tasks.png)

これを作成します (または開きます)、 **tasks.vs.json**ファイルが .vs フォルダーに Visual Studio がルート プロジェクト フォルダーに作成されます。 このファイルで任意のタスクを定義し、**ソリューション エクスプローラー**のコンテキスト メニューから呼び出すことができます。 単一のタスクを定義する tasks.vs.json ファイルの例を次に示します。 `taskName` では、コンテキスト メニューに表示される名前を定義します。 `appliesTo` では、コマンドを実行できるファイルを定義します。 `command` プロパティは、コンソール (Windows では cmd.exe) のパスを示す COMSPEC 環境変数を参照します。 CppProperties.json または CMakeSettings.json で宣言されている環境変数を参照することもできます。 `args` プロパティでは、呼び出すコマンド ラインを指定します。 `${file}` マクロは、**ソリューション エクスプローラー**で選択したファイルを取得します。 次の例では、現在選択されている .cpp ファイルのファイル名が表示されます。

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

詳細については、「[Tasks.vs.json schema reference](tasks-vs-json-schema-reference-cpp.md)」 (Tasks.vs.json スキーマ リファレンス) を参照してください。

### <a name="configure-debugging-parameters-with-launchvsjson"></a>launch.vs.json でデバッグ パラメーターを構成する

プログラムのコマンド ライン引数をカスタマイズするには、**ソリューション エクスプローラー**で実行可能ファイルを右クリックし、**[デバッグ設定と起動設定]** を選びます。 これが、既存開きます**launch.vs.json**ファイル、または存在しない場合は、選択したプログラムに関する情報があらかじめ設定された新しいファイルが作成されます。

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
