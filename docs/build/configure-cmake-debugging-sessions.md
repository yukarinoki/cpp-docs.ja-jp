---
title: Visual Studio で CMake デバッグ セッションを構成する
ms.date: 03/05/2019
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: 9a4dd009544a4590c336697ba2162eec45718869
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827928"
---
# <a name="configure-cmake-debugging-sessions"></a>CMake デバッグ セッションを構成する

すべての実行可能な CMake ターゲットが、**[全般]** ツール バーの **[スタートアップ アイテム]** ドロップダウンに表示されます。 デバッグ セッションを開始するには、1 つを選択してデバッガーを起動するだけです。

![CMake のスタートアップ アイテム ドロップダウン](media/cmake-startup-item-dropdown.png "CMake のスタートアップ アイテム ドロップダウン")

CMake メニューからデバッグ セッションを開始することもできます。

## <a name="customize-debugger-settings"></a>デバッガー設定をカスタマイズする

プロジェクト内の実行可能な CMake ターゲットのデバッガー設定をカスタマイズするには、特定の CMakeLists.txt ファイルを右クリックして、**[デバッグ設定と起動設定]** を選びます。 サブメニューで CMake ターゲットを選ぶと、`launch.vs.json` という名前のファイルが作成されます。 このファイルには選んだ CMake ターゲットに関する情報があらかじめ入力されており、プログラムの引数やデバッガーの種類などの他のパラメーターを指定することができます。 `CMakeSettings.json` ファイル内のキーを参照するには、`launch.vs.json` 内で前に `cmake.` を付けます。 次に示す簡単な `launch.vs.json` ファイルの例では、現在選択されている構成に対して、`CMakeSettings.json` ファイル内の `remoteCopySources` キーの値を取得しています。

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

`launch.vs.json` ファイルを保存するとすぐに、**[スタートアップ アイテム]** ドロップダウン内に新しい名前のエントリが作成されます。 `launch.vs.json` ファイルを編集することで、任意の数の CMake ターゲットに対し、いくつでもデバッグ構成を作成できます。

## <a name="support-for-cmakesettings-variables"></a>CMakeSettings 変数のサポート

 `Launch.vs.json` は、`CMakeSettings.json` (下記参照) で宣言されていて、現在選択されている構成に適用される変数をサポートします。 `currentDir` という名前のキーもあり、これは起動しているアプリの現在のディレクトリを設定します。

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
## <a name="see-also"></a>関連項目

[Visual Studio で CMake プロジェクト](cmake-projects-in-visual-studio.md)<br/>
[Linux CMake プロジェクトを構成する](../linux/cmake-linux-project.md)<br/>
[リモートの Linux コンピューターに接続する](../linux/connect-to-your-remote-linux-computer.md)<br/>
[CMake のビルド設定をカスタマイズする](customize-cmake-settings.md)<br/>
[CMake デバッグ セッションを構成する](configure-cmake-debugging-sessions.md)<br/>
[Linux プロジェクトの配置、実行、デバッグ](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake 定義済み構成リファレンス](cmake-predefined-configuration-reference.md)<br/>