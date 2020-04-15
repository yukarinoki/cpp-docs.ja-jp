---
title: Visual Studio での C++ ビルド システムの [フォルダーを開く] のサポート
ms.date: 12/02/2019
helpviewer_keywords:
- Open Folder Projects in Visual Studio
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: 9264aa4bf77de406bdde9042ef9ec4251763f721
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320961"
---
# <a name="open-folder-support-for-c-build-systems-in-visual-studio"></a>Visual Studio での C++ ビルド システムの [フォルダーを開く] のサポート

::: moniker range="vs-2015"

フォルダーを開く機能は、Visual Studio 2017 以降で使用できます。

::: moniker-end

::: moniker range=">=vs-2017"

Visual Studio 2017 以降で "フォルダーを開く" 機能を使うと、ソース ファイルのフォルダーを開き、IntelliSense、参照、リファクタリング、デバッグなどのサポートを利用してコーディングをすぐに始めることができます。 ファイルを編集、作成、移動、または削除すると、Visual Studio は自動的に変更を追跡し、IntelliSense インデックスを継続的に更新します。 .sln または .vcxproj ファイルは読み込まれません。必要な場合は、カスタム タスクを指定し、簡単な .json ファイルを使ってパラメーターをビルドして起動できます。 この機能を使用すると、サードパーティ製のビルド システムを Visual Studio に統合できます。 [フォルダーを開く] に関する詳細については、「[プロジェクトまたはソリューションを使用せずに Visual Studio でコードを開発する](/visualstudio/ide/develop-code-in-visual-studio-without-projects-or-solutions)」を参照してください。

## <a name="cmake-and-qt"></a>CMake と Qt

CMake は、C++ デスクトップ ワークロードのコンポーネントとして Visual Studio IDE に統合されています。 CMake のワークフローは、この記事で説明したワークフローと同じではありません。 CMake を使用している場合は[、「CMake プロジェクトを Visual Studio で作成](cmake-projects-in-visual-studio.md)する」を参照してください。 CMake を使用して Qt プロジェクトをビルドすることも、Visual Studio 2015 または Visual Studio 2017 のいずれかの[Qt Visual Studio 拡張機能](https://download.qt.io/development_releases/vsaddin/)を使用することもできます。

## <a name="other-build-systems"></a>その他のビルドシステム

Visual Studio IDE を、メイン メニューから直接サポートされていないビルド システムまたはコンパイラ ツールセットで使用するには、[**ファイル |開く |フォルダ**を押すか **、Ctrl キーを押しながら Shift キーを押しながら Alt キーを押しながら O キーを押**します。ソース コード ファイルが含まれているフォルダーに移動します。 プロジェクトをビルドし、IntelliSense を構成し、デバッグ パラメーターを設定するには、次の 3 つの JSON ファイルを追加します。

| | |
|-|-|
|CppProperties.json|参照のためのカスタム構成情報を指定します。 必要な場合は、ルート プロジェクト フォルダーにこのファイルを作成します。 (CMake プロジェクトで使用されません。)|
|tasks.vs.json|カスタム ビルド コマンドを指定します。 指定するには、**ソリューション エクスプローラー**のコンテキスト メニュー項目 **[タスクの構成]** を使用します。|
|launch.vs.json|デバッガーのコマンド ライン引数を指定します。 指定するには、**ソリューション エクスプローラー**のコンテキスト メニュー項目 **[デバッグ設定と起動設定]** を使用します。|

## <a name="configure-code-navigation-with-cpppropertiesjson"></a>コード ナビゲーションを構成する

IntelliSense と参照動作 ([**定義へ移動]** など) が正しく動作するには、Visual Studio は、使用しているコンパイラ、システム ヘッダーの場所、および開いたフォルダー (ワークスペース フォルダー) に直接存在しない追加のインクルード ファイルがある場所を知る必要があります。 構成を指定するには、メインツールバーのドロップダウンから **「構成の管理**」を選択します。

![構成ドロップダウンの管理](media/manage-configurations-dropdown.png)

Visual Studio には、次の既定の構成があります。

![既定の構成](media/default-configurations.png)

たとえば **、[x64-Debug]** を選択した場合、Visual Studio はルート プロジェクト フォルダーに*CppProperties.json*という名前のファイルを作成します。

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

この構成は、Visual Studio [x64 開発者コマンド プロンプト](building-on-the-command-line.md)の環境変数を継承します。 これらの変数の 1`INCLUDE`つは、`${env.INCLUDE}`マクロを使用して、ここで参照できます。 プロパティ`includePath`は、IntelliSense に必要なすべてのソースを検索する場所を Visual Studio に指示します。 この場合、"INCLUDE 環境変数で指定されたすべてのディレクトリと、現在の作業フォルダ ツリー内のすべてのディレクトリを検索します。 プロパティ`name`は、ドロップダウンに表示される名前で、好きな名前にすることができます。 この`defines`プロパティは、条件付きコンパイル ブロックを検出したときに IntelliSense にヒントを提供します。 この`intelliSenseMode`プロパティは、コンパイラの種類に基づいていくつかの追加のヒントを提供します。 MSVC、GCC、および Clang には、いくつかのオプションが使用できます。

> [!NOTE]
> Visual Studio が*CppProperties.json*の設定を無視しているように見える場合は、*次のような .gitignore* `!/CppProperties.json`ファイルに例外を追加してみてください。

## <a name="default-configuration-for-mingw-w64"></a>MinGW-w64 のデフォルト設定

MinGW-W64 設定を追加すると、JSON は次のようになります。

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

ブロックに`environments`注意してください。 環境変数と同様に動作し *、CppProperties.json*ファイルだけでなく、他の構成ファイル*task.vs.json*および*launch.vs.json*でも使用できるプロパティを定義します。 構成`Mingw64`は環境を`mingw_w64`継承し、そのプロパティを`INCLUDE`使用して`includePath`の値を指定します。 必要に応じて、この配列プロパティに他のパスを追加できます。

プロパティ`intelliSenseMode`は GCC に適した値に設定されます。 これらのすべてのプロパティの詳細については[、「CppProperties スキーマ リファレンス](cppproperties-schema-reference.md)」を参照してください。

すべてが正常に動作している場合は、型の上にマウスを移動すると、GCC ヘッダーから IntelliSense が表示されます。

![GCC インテライセンス](media/gcc-intellisense.png)

## <a name="enable-intellisense-diagnostics"></a>インテリセンス診断を有効にする

期待する IntelliSense が表示されない場合は、[**ツール** > **オプション** > **テキスト エディター** > **C/C++** > **詳細設定**] に進み、[**ログ記録を有効**にする] を**true**に設定してトラブルシューティングを行うことができます。 まず、[**ログ出力レベル]** を 5 に設定し、[**ログ フィルタ] を**8 に設定します。

![診断ログ](media/diagnostic-logging.png)

出力は**出力ウィンドウ**にパイプされ、* 出力元の表示 *: Visual C++ ログ*を選択すると表示されます。 出力には、IntelliSense が使用しようとしている実際のインクルード パスの一覧が含まれています。 パスが*CppProperties.json*のパスと一致しない場合は、フォルダーを閉じて、キャッシュされた参照データを含む *.vs*サブフォルダーを削除します。

### <a name="define-build-tasks-with-tasksvsjson"></a>tasks.vs.json でビルド タスクを定義する

IDE でタスクとして直接実行することで、現在のワークスペースにあるファイルに対してビルド スクリプトやその他の外部操作を自動化できます。 ファイルまたはフォルダーを右クリックし、**[タスクの構成]** を選択すると、新しいタスクを構成できます。

!["フォルダーを開く" のタスクの構成](media/configure-tasks.png)

これにより、Visual Studio がルート プロジェクト フォルダーに作成する .vs フォルダーに*tasks.vs.json*ファイルが作成 (または開きます) されます。 このファイルで任意のタスクを定義し、**ソリューション エクスプローラー**のコンテキスト メニューから呼び出すことができます。 GCC の例を続けるため、次のスニペットは、プロジェクトをビルドするために*g++.exe*を呼び出す単一のタスクとして、完全な*tasks.vs.json*ファイルを示しています。 プロジェクトに*hello.cpp*という名前のファイルが 1 つ含まれていると仮定します。

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

JSON ファイルは *.vs*サブフォルダーに配置されます。 このフォルダを表示するには、**ソリューション エクスプローラ**の上部にある **[すべてのファイルを表示**] ボタンをクリックします。 このタスクを実行するには、**ソリューション エクスプローラー**でルート ノードを右クリックし、[**ビルド hello]** を選択します。 タスクが完了すると、**ソリューション エクスプローラ**に*hello.exe*という新しいファイルが表示されます。

さまざまな種類のタスクを定義できます。 次の例は、1 つのタスクを定義する*tasks.vs.json ファイル*を示しています。 `taskLabel` では、コンテキスト メニューに表示される名前を定義します。 `appliesTo` では、コマンドを実行できるファイルを定義します。 この`command`プロパティは、COMSPEC 環境変数を参照し、コンソール (Windows の*cmd.exe)* のパスを識別します。 CppProperties.json または CMakeSettings.json で宣言されている環境変数を参照することもできます。 `args` プロパティでは、呼び出すコマンド ラインを指定します。 `${file}` マクロは、**ソリューション エクスプローラー**で選択したファイルを取得します。 次の例では、現在選択されている .cpp ファイルのファイル名が表示されます。

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

*tasks.vs.json*を保存した後、フォルダー内の*任意の .cpp*ファイルを右クリックし、コンテキスト メニューから **[ファイル名をエコー** ] を選択して、出力ウィンドウに表示されるファイル名を確認できます。

詳細については、「[Tasks.vs.json schema reference](tasks-vs-json-schema-reference-cpp.md)」 (Tasks.vs.json スキーマ リファレンス) を参照してください。

### <a name="configure-debugging-parameters-with-launchvsjson"></a>launch.vs.json でデバッグ パラメーターを構成する

プログラムのコマンド ライン引数とデバッグ命令をカスタマイズするには、**ソリューション エクスプローラー**で実行可能ファイルを右クリックし、[**デバッグと起動の設定]** を選択します。 既存の*launch.vs.json*ファイルが開くか、存在しない場合は、最小起動設定のセットを使用して新しいファイルを作成します。 まず、構成するデバッグ セッションの種類を選択します。 MinGw-w64 プロジェクトのデバッグには **、MinGW/Cygwin (gdb) の C/C++ 起動を**選択します。 これにより *、gdb.exe*を使用するための起動構成が作成され、既定値に関する推測がいくつか行われます。 これらの既定値の 1`MINGW_PREFIX`つは です。 リテラル パスを置き換えること (以下を参照) するか`MINGW_PREFIX`*、CppProperties.json*でプロパティを定義することができます。

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

デバッグを開始するには、デバッグドロップダウンで実行可能ファイルを選択し、緑色の矢印をクリックします。

![デバッガを起動する](media/launch-debugger-gdb.png)

**[デバッガーの初期化**] ダイアログボックスが表示され、プログラムを実行している外部コンソール ウィンドウが表示されます。

詳細については、「 [launch.vs.json スキーマ リファレンス](launch-vs-schema-reference-cpp.md)」を参照してください。

## <a name="launching-other-executables"></a>他の実行可能ファイルの起動

コンピュータ上の実行可能ファイルの起動設定を定義できます。 次の例では *、7za*を起動し、JSON 配列に追加`args`することによって追加の引数を指定します。

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
