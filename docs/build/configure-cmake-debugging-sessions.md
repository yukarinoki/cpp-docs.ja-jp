---
title: Visual Studio で CMake デバッグ セッションを構成する
ms.date: 03/21/2019
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: 41f53c0c3ea46a8a1aa11215968aaee6c13c2dea
ms.sourcegitcommit: e33126222c418daf977533ea9e2819d99e0d7b8d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72534106"
---
# <a name="configure-cmake-debugging-sessions"></a>CMake デバッグ セッションを構成する

すべての実行可能な CMake ターゲットが、 **[全般]** ツール バーの **[スタートアップ アイテム]** ドロップダウンに表示されます。 デバッグ セッションを開始するには、1 つを選択してデバッガーを起動するだけです。

![CMake スタートアップ項目のドロップダウン](media/cmake-startup-item-dropdown.png "CMake スタートアップ項目のドロップダウン")

ソリューションエクスプローラーからデバッグセッションを開始することもできます。 最初に、 **[ソリューションエクスプローラー]** ウィンドウの [ **Cmake ターゲット] ビュー**に切り替えます。

![CMake ターゲットビューのボタン](media/cmake-targets-view.png  "CMake ターゲットビューのメニュー項目")

次に、任意の実行可能ファイルを右クリックし、 **[デバッグ]** または **[デバッグと起動の設定]** を選択します。 **デバッグ**は、アクティブな構成に基づいて、選択したターゲットのデバッグを自動的に開始します。 **デバッグと起動の設定**では、*起動した json*ファイルが開き、選択したターゲットの新しいデバッグ構成が追加されます。

## <a name="customize-debugger-settings"></a>デバッガー設定をカスタマイズする

プロジェクト内の実行可能な CMake ターゲットのデバッガー設定をカスタマイズするには、特定の CMakeLists.txt ファイルを右クリックして、 **[デバッグ設定と起動設定]** を選びます。 (または、**ソリューションエクスプローラー**の [**ターゲット] ビュー**でターゲットを選択します。)サブメニューで CMake ターゲットを選択すると、 **launch**というファイルが作成されます。 このファイルには選んだ CMake ターゲットに関する情報があらかじめ入力されており、プログラムの引数やデバッガーの種類などの他のパラメーターを指定することができます。 **Cmakesettings. json**ファイル内の任意のキーを参照するには、「 **launch. vs. json**」で `cmake.` を先頭に付けます。 次の例は、現在選択されている構成の**Cmakesettings. json**ファイル内の `remoteCopySources` キーの値を取得する単純な**起動と json**ファイルを示しています。

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

起動ファイルと**json**ファイルを保存するとすぐに、新しい名前の付いた **[スタートアップ項目]** ドロップダウンにエントリが作成されます。 **起動と json**ファイルを編集することで、任意の数の cmake ターゲットに必要な数のデバッグ構成を作成できます。

## <a name="support-for-cmakesettings-variables"></a>CMakeSettings 変数のサポート

 **Launch. json**は、 **cmakesettings. json** (下記参照) で宣言され、現在選択されている構成に適用される変数をサポートします。 また、`currentDir` という名前のキーもあります。これにより、ローカルプロジェクトの起動中のアプリの現在のディレクトリが設定されます。

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

キー ' cwd ' は、リモートプロジェクトの起動中のアプリの現在のディレクトリを設定します。 既定値は ' $ {debugInfo. System.defaultworkingdirectory} ' で、に評価されます。 

```cmd
/var/tmp/src/bfc6f7f4-4f0f-8b35-80d7-9198fa973fb9/Linux-Debug
```

## <a name="see-also"></a>関連項目

[Visual Studio の CMake プロジェクト](cmake-projects-in-visual-studio.md)<br/>
[Linux CMake プロジェクトを構成する](../linux/cmake-linux-project.md)<br/>
[リモートの Linux コンピューターに接続する](../linux/connect-to-your-remote-linux-computer.md)<br/>
[CMake のビルド設定をカスタマイズする](customize-cmake-settings.md)<br/>
[CMake デバッグ セッションを構成する](configure-cmake-debugging-sessions.md)<br/>
[Linux プロジェクトの配置、実行、デバッグ](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake 定義済み構成リファレンス](cmake-predefined-configuration-reference.md)<br/>
