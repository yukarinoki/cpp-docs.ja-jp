---
description: '詳細情報: Visual Studio での C++ ビルド システムの [フォルダーを開く] のサポート'
title: Visual Studio での C++ ビルド システムの [フォルダーを開く] のサポート
ms.date: 12/02/2019
helpviewer_keywords:
- Open Folder Projects in Visual Studio
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: 056ad4d1d611f2fc8b1c2d5594057a82b3e54a10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187573"
---
# <a name="open-folder-support-for-c-build-systems-in-visual-studio"></a>Visual Studio での C++ ビルド システムの [フォルダーを開く] のサポート

::: moniker range="msvc-140"

フォルダーを開く機能は Visual Studio 2017 以降で使用できます。

::: moniker-end

::: moniker range=">=msvc-150"

Visual Studio 2017 以降で "フォルダーを開く" 機能を使うと、ソース ファイルのフォルダーを開き、IntelliSense、参照、リファクタリング、デバッグなどのサポートを利用してコーディングをすぐに始めることができます。 ファイルを編集、作成、移動、または削除すると、Visual Studio は自動的に変更を追跡し、IntelliSense インデックスを継続的に更新します。 .sln または .vcxproj ファイルは読み込まれません。必要な場合は、カスタム タスクを指定し、簡単な .json ファイルを使ってパラメーターをビルドして起動できます。 この機能を使用すると、任意のサードパーティのビルド システムを Visual Studio に統合できます。 [フォルダーを開く] に関する詳細については、「[プロジェクトまたはソリューションを使用せずに Visual Studio でコードを開発する](/visualstudio/ide/develop-code-in-visual-studio-without-projects-or-solutions)」を参照してください。

## <a name="cmake-and-qt"></a>CMake と Qt

CMake は、C++ デスクトップ ワークロードのコンポーネントとして Visual Studio IDE に統合されています。 CMake のワークフローは、この記事で説明されているワークフローと同一ではありません。 CMake を使用する場合は、「[Visual Studio の CMake プロジェクト](cmake-projects-in-visual-studio.md)」をご覧ください。 CMake を使用して Qt プロジェクトをビルドすることもできます。また、Visual Studio 2015 または Visual Studio 2017 で [Qt Visual Studio 拡張機能](https://download.qt.io/development_releases/vsaddin/)を使用できます。

## <a name="other-build-systems"></a>その他のビルド システム

メイン メニューから直接サポートされないビルド システムまたはコンパイラ ツールセットを使用して Visual Studio IDE を使用するには、 **[ファイル] > [開く] > [フォルダー]** を選択するか、**Ctrl + Shift + Alt + O** を押します。ソース コード ファイルが格納されているフォルダーに移動します。 プロジェクトをビルドし、IntelliSense を構成し、デバッグ パラメーターを設定するために、3 つの JSON ファイルを追加します。

| ファイル | 説明 |
|-|-|
|CppProperties.json|参照のためのカスタム構成情報を指定します。 必要な場合は、ルート プロジェクト フォルダーにこのファイルを作成します。 (CMake プロジェクトで使用されません。)|
|tasks.vs.json|カスタム ビルド コマンドを指定します。 指定するには、**ソリューション エクスプローラー** のコンテキスト メニュー項目 **[タスクの構成]** を使用します。|
|launch.vs.json|デバッガーのコマンド ライン引数を指定します。 指定するには、**ソリューション エクスプローラー** のコンテキスト メニュー項目 **[デバッグ設定と起動設定]** を使用します。|

## <a name="configure-code-navigation-with-cpppropertiesjson"></a>CppProperties.json を使用してコードのナビゲーションを構成する

IntelliSense と、 **[定義へ移動]** などの参照の動作を正しく動作させるために、Visual Studio は、使用しているコンパイラ、システム ヘッダーの場所、および開いているフォルダーに追加のインクルード ファイルが直接含まれていない場合のそれらのインクルード ファイルの場所 (ワークスペース フォルダー) を認識している必要があります。 構成を指定するには、メイン ツールバーのドロップダウンから **[構成の管理]** を選択できます。

![[構成の管理] ドロップダウン](media/manage-configurations-dropdown.png)

Visual Studio には、次の既定の構成が用意されています。

![既定の構成](media/default-configurations.png)

たとえば **[x64-Debug]** を選択すると、Visual Studio によって *CppProperties.json* という名前のファイルがルート プロジェクト フォルダーに作成されます。

```json
{
  "configurations": [
    {
      "inheritEnvironments": [
        "msvc_x64"
      ],
      "name": "x64-Debug",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "_DEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x64"
    }
  ]
}
```

この構成では、Visual Studio の [x64 開発者コマンド プロンプト](building-on-the-command-line.md)の環境変数が継承されます。 これらの変数の 1 つが `INCLUDE` であり、`${env.INCLUDE}` マクロを使用してここでそれを参照できます。 `includePath` プロパティは、IntelliSense のために必要なすべてのソースを検索する場所を Visual Studio に通知します。 この場合、"INCLUDE 環境変数によって指定されたすべてのディレクトリと、現在の作業フォルダー ツリー内のすべてのディレクトリを検索" するように通知します。 `name` プロパティはドロップダウンに表示される名前であり、任意の名前を指定できます。 `defines` プロパティは、条件付きコンパイル ブロックが検出されたときに IntelliSense にヒントを提供します。 `intelliSenseMode` プロパティは、コンパイラの種類に基づいていくつかの追加のヒントを提供します。 MSVC、GCC、Clang 用のさまざまなオプションを使用できます。

> [!NOTE]
> Visual Studio で *CppProperties.json* の設定が無視されているように思われる場合は、次のように *.gitignore* ファイルに例外を追加してみてください: `!/CppProperties.json`

## <a name="default-configuration-for-mingw-w64"></a>MinGW-w64 の既定の構成

MinGW-W64 構成を追加すると、JSON は次のようになります。

```json
{
  {
      "inheritEnvironments": [
        "mingw_64"
      ],
      "name": "Mingw64",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "intelliSenseMode": "linux-gcc-x64",
      "environments": [
        {
          "MINGW64_ROOT": "C:\\msys64\\mingw64",
          "BIN_ROOT": "${env.MINGW64_ROOT}\\bin",
          "FLAVOR": "x86_64-w64-mingw32",
          "TOOLSET_VERSION": "9.1.0",
          "PATH": "${env.BIN_ROOT};${env.MINGW64_ROOT}\\..\\usr\\local\\bin;${env.MINGW64_ROOT}\\..\\usr\\bin;${env.MINGW64_ROOT}\\..\\bin;${env.PATH}",
          "INCLUDE": "${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION};${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION}\\tr1;${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION}\\${env.FLAVOR}",
          "environment": "mingw_64"
        }
      ]
    }
}
```

`environments` ブロックに注意してください。 これにより、環境変数と同様に動作するプロパティが定義され、それらを *CppProperties.json* ファイルだけでなく、他の構成ファイル(*task.vs.json* と *launch.vs.json*) でも使用できます。 `Mingw64` 構成では `mingw_w64` 環境が継承され、その `INCLUDE` プロパティを使用して `includePath` の値が指定されます。 必要に応じて、この配列プロパティに他のパスを追加できます。

`intelliSenseMode` プロパティには、GCC に適した値が設定されます。 これらすべてのプロパティの詳細については、「[CppProperties スキーマ リファレンス](cppproperties-schema-reference.md)」を参照してください。

すべてが正常に動作している場合は、型にマウス ポインターを合わせると、GCC ヘッダーから IntelliSense が表示されます。

![GCC IntelliSense](media/gcc-intellisense.png)

## <a name="enable-intellisense-diagnostics"></a>IntelliSense 診断を有効にする

予期した IntelliSense が表示されない場合、トラブルシューティングを行うには、 **[ツール]**  >  **[オプション]**  >  **[テキスト エディター]**  >  **[C/C++]**  >  **[詳細設定]** に移動し、 **[ログを有効にする]** を **`true`** に設定にします。 最初は、 **[ログ記録レベル]** を [5] に設定し、 **[ログ フィルター]** を [8] に設定します。

![診断ログ記録](media/diagnostic-logging.png)

出力は **[出力] ウィンドウ** にパイプ処理され、 *[出力元の表示: Visual C++ ログ]* を選択したときに表示されます。 出力には、IntelliSense が使おうとしている実際のインクルード パスの一覧が含まれます。 パスが *CppProperties.json* のパスと一致していない場合は、フォルダーを閉じ、キャッシュされた参照データが含まれている *.vs* サブフォルダーを削除してみてください。

### <a name="define-build-tasks-with-tasksvsjson"></a>tasks.vs.json でビルド タスクを定義する

IDE でタスクとして直接実行することで、現在のワークスペースにあるファイルに対してビルド スクリプトやその他の外部操作を自動化できます。 ファイルまたはフォルダーを右クリックし、 **[タスクの構成]** を選択すると、新しいタスクを構成できます。

!["フォルダーを開く" のタスクの構成](media/configure-tasks.png)

これにより、Visual Studio によってルート プロジェクト フォルダー内に作成される .vs フォルダーに *tasks.vs.json* ファイルが作成されます (またはファイルが開きます)。 このファイルで任意のタスクを定義し、**ソリューション エクスプローラー** のコンテキスト メニューから呼び出すことができます。 GCC の例を進めるために、次のスニペット に完全な *tasks.vs.json* ファイルを示します。これには、*g++.exe* を呼び出してプロジェクトをビルドする単一のタスクが含まれています。 プロジェクトには *hello.cpp* という名前の単一のファイルが含まれているとします。

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskLabel": "build hello",
      "appliesTo": "/",
      "type": "default",
      "command": "g++",
      "args": [
        "-g",
        "-o",
        "hello",
        "hello.cpp"
      ]
    }
  ]
}

```

この JSON ファイルは、 *.vs* サブフォルダーに配置されます。 このフォルダーを表示するには、**ソリューション エクスプローラー** の上部にある **[すべてのファイルを表示]** ボタンをクリックします。 **ソリューション エクスプローラー** でルート ノードを右クリックし、 **[build hello]\(hello のビルド\)** を選択することで、このタスクを実行できます。 タスクが完了すると、**ソリューション エクスプローラー** に新しいファイル (*hello.exe*) が表示されます。

さまざまな種類のタスクを定義できます。 単一のタスクを定義する *tasks.vs.json ファイル* の例を次に示します。 `taskLabel` では、コンテキスト メニューに表示される名前を定義します。 `appliesTo` では、コマンドを実行できるファイルを定義します。 `command` プロパティは、コンソール (Windows では *cmd.exe*) のパスを示す COMSPEC 環境変数を参照します。 CppProperties.json または CMakeSettings.json で宣言されている環境変数を参照することもできます。 `args` プロパティでは、呼び出すコマンド ラインを指定します。 `${file}` マクロは、**ソリューション エクスプローラー** で選択したファイルを取得します。 次の例では、現在選択されている .cpp ファイルのファイル名が表示されます。

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskLabel": "Echo filename",
      "appliesTo": "*.cpp",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": ["echo ${file}"]
    }
  ]
}
```

*tasks.vs.json* を保存した後、フォルダー内の任意の *.cpp* ファイルを右クリックし、コンテキスト メニューから **[Echo filename]** を選んで、[出力] ウィンドウにファイル名が表示されることを確認します。

詳細については、「[Tasks.vs.json schema reference](tasks-vs-json-schema-reference-cpp.md)」 (Tasks.vs.json スキーマ リファレンス) を参照してください。

### <a name="configure-debugging-parameters-with-launchvsjson"></a>launch.vs.json でデバッグ パラメーターを構成する

プログラムのコマンド ライン引数とデバッグ手順をカスタマイズするには、**ソリューション エクスプローラー** で実行可能ファイルを右クリックし、 **[デバッグ設定と起動設定]** を選びます。 これにより、既存の *launch.vs.json* ファイルが開きます。存在しない場合は、最小限の一連の起動設定を使用して新しいファイルが作成されます。 最初に、どの種類のデバッグ セッションを構成するかを選択します。 MinGw-w64 プロジェクトをデバッグする場合は、 **[C/C++ Launch for MinGW/Cygwin (gdb)]\(MinGW/Cygwin に対する C/C++ の起動 (gdb)\)** を選択します。 これにより、*gdb.exe* を使用するための、経験に基づく推測による既定値が設定された起動構成が作成されます。 これらの既定値の 1 つは `MINGW_PREFIX` です。 次に示すようにリテラル パスを置き換えることも、*CppProperties.json* に `MINGW_PREFIX` プロパティを定義することもできます。

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "cppdbg",
      "name": "hello.exe",
      "project": "hello.exe",
      "cwd": "${workspaceRoot}",
      "program": "${debugInfo.target}",
      "MIMode": "gdb",
      "miDebuggerPath": "c:\\msys64\\usr\\bin\\gdb.exe",
      "externalConsole": true
    }
  ]
}

```

デバッグを開始するには、[デバッグ] ドロップダウンで実行可能ファイルを選択し、緑色の矢印をクリックします。

![デバッガーを起動する](media/launch-debugger-gdb.png)

**[デバッガーの初期化]** ダイアログが表示された後、プログラムを実行している外部コンソール ウィンドウが表示されます。

詳細については、「[launch.vs.json スキーマ リファレンス](launch-vs-schema-reference-cpp.md)」を参照してください。

## <a name="launching-other-executables"></a>他の実行可能ファイルの起動

コンピューター上の任意の実行可能ファイルの起動設定を定義できます。 次の例では *7za* を起動し、追加の引数を `args` JSON 配列に追加することでそれらを指定しています。

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

::: moniker-end
