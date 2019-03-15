---
title: Visual Studio で C++ のビルド システムのフォルダーのサポートを開く
ms.date: 01/21/2019
helpviewer_keywords:
- Open Folder Projects in Visual C++
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: a7e352d7978ba5c973d779224639006fa984e4f0
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827218"
---
# <a name="open-folder-projects-for-c"></a>C++ プロジェクトのフォルダーを開く

Visual Studio 2017 以降で "フォルダーを開く" 機能を使うと、ソース ファイルのフォルダーを開き、IntelliSense、参照、リファクタリング、デバッグなどのサポートを利用してコーディングをすぐに始めることができます。 .sln または .vcxproj ファイルは読み込まれません。必要な場合は、カスタム タスクを指定し、簡単な .json ファイルを使ってパラメーターをビルドして起動できます。 開いているフォルダーの詳細については、次を参照してください。[プロジェクトまたはソリューションなしの Visual Studio でコードを開発](/visualstudio/ide/develop-code-in-visual-studio-without-projects-or-solutions)します。

CMake が統合されています、Visual Studio IDE で CMake Tools for Visual Studio、C++ デスクトップ ワークロードのコンポーネント。 詳細については、次を参照してください。 [Visual Studio で CMake プロジェクト](cmake-projects-in-visual-studio.md)します。 ビルド システムでは、フォルダーを開く機能を使用することができます。 フォルダーを開くには、コード エディター、デバッガーのアナライザーのビルド システムとコンパイラ ツールセットを効果的と切り離されます。 C++ のコード エディターを使用するには、豊富な IntelliSense の機能、コード アナライザー、および CMake、Ninja、QMake (Qt プロジェクト) に対して、gyp、SCons、Gradle、Buck、make をなど、あらゆるビルド システムで Visual Studio デバッガーを使用します。 1 つのファイルとビルド システムのファイルの loose コレクションでも動作します。

"フォルダーを開く" を使うには、メイン メニューから **[ファイル] > [開く] > [フォルダー]** を選ぶか、**Ctrl + Shift + Alt + O** キーを押します。フォルダー内のすべてのファイルがソリューション エクスプローラーにすぐに表示されます。 任意のファイルをクリックして、編集を開始できます。 バックグラウンドでは、Visual Studio は、ファイルのインデックス作成を開始して、IntelliSense、ナビゲーション、およびリファクタリング機能を有効にします。 ファイルを編集、作成、移動、または削除すると、Visual Studio は自動的に変更を追跡し、IntelliSense インデックスを継続的に更新します。 

## <a name="qmake-projects-that-target-the-qt-framework"></a>Qt フレームワークを対象とする QMake プロジェクト

CMake Tools for Visual Studio を使用して、Qt、Qt プロジェクトをビルドするターゲットまたは使用することができます、 [Qt Visual Studio 拡張機能](https://download.qt.io/development_releases/vsaddin/)の Visual Studio 2015 または Visual Studio 2017 のいずれか。

## <a name="gyp-cons-scons-buck-etc"></a>gyp、Cons、SCons、Buck など

Visual Studio で任意のビルド システムを使用し、引き続き C++ IDE とデバッガーの利点も活用できます。 プロジェクトのルート フォルダーを開くと、C コード エディターはヒューリスティックを使用して、IntelliSense および参照ソース ファイルのインデックスを作成します。 CppProperties.json ファイルを編集することにより、コードの構造についてのヒントを提供できます。 同様の方法では、構成し、launch.vs.json ファイルを編集して、ビルドのプログラムを起動します。

## <a name="configuring-open-folder-projects"></a>"フォルダーを開く" プロジェクトの構成

次の 3 つの JSON ファイルを使って、"フォルダーを開く" プロジェクトをカスタマイズできます。

| | |
|-|-|
|CppProperties.json|参照のためのカスタム構成情報を指定します。 必要な場合は、ルート プロジェクト フォルダーにこのファイルを作成します。 (で使用されない CMake プロジェクト。)|
|tasks.vs.json|カスタム ビルド コマンドとコンパイラ スイッチを指定します。 指定するには、**ソリューション エクスプローラー**のコンテキスト メニュー項目 **[タスクの構成]** を使用します。|
|launch.vs.json|デバッガーのコマンドライン引数を指定します。 指定するには、**ソリューション エクスプローラー**のコンテキスト メニュー項目 **[デバッグ設定と起動設定]** を使用します。|

### <a name="configure-intellisense-and-browsing-hints-with-cpppropertiesjson"></a>IntelliSense および閲覧 CppProperties.json を使用してヒントを構成します。

IntelliSense と参照の動作は、#include のパス、コンパイラ スイッチ、およびその他のパラメーターを定義するアクティブなビルド構成に部分的に依存します。 既定では、Visual Studio はデバッグ構成とリリース構成を提供します。 CMake プロジェクトは、この目的に CMakeSettings.json ファイルにより、CMakeLists.txt ファイルを使用します。 その他の種類のフォルダーを開くプロジェクトでは、IntelliSense および参照機能は、コードを完全に理解するためにカスタム構成を作成する必要があります。 新しい構成を定義するには、CppProperties.json という名前のファイルをルート フォルダーに作成します。 次に例を示します。

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
詳細については、次を参照してください。 [CppProperties スキーマ リファレンス](cppproperties-schema-reference.md)します。

### <a name="define-build-tasks-with-tasksvsjson"></a>Tasks.vs.json でタスクをビルド定義します。

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

詳細については、次を参照してください。 [Tasks.vs.json スキーマ リファレンス](tasks-vs-json-schema-reference-cpp.md)します。

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

## <a name="see-also"></a>関連項目


