---
title: Visual Studio で CMake デバッグ セッションを構成する
ms.date: 03/21/2019
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: 9899f99994935ec419fff400670644b7d78a190a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59035349"
---
# <a name="configure-cmake-debugging-sessions"></a>CMake デバッグ セッションを構成する

すべての実行可能な CMake ターゲットが、**[全般]** ツール バーの **[スタートアップ アイテム]** ドロップダウンに表示されます。 デバッグ セッションを開始するには、1 つを選択してデバッガーを起動するだけです。

![CMake のスタートアップ アイテム ドロップダウン](media/cmake-startup-item-dropdown.png "CMake のスタートアップ アイテム ドロップダウン")

CMake メニューからデバッグ セッションを開始することもできます。

## <a name="customize-debugger-settings"></a>デバッガー設定をカスタマイズする

プロジェクト内の実行可能な CMake ターゲットのデバッガー設定をカスタマイズするには、特定の CMakeLists.txt ファイルを右クリックして、**[デバッグ設定と起動設定]** を選びます。 (でターゲットを選択または**ターゲット ビュー**で**ソリューション エクスプ ローラー**)。サブメニューで CMake ターゲットを選択すると、ファイルと呼ばれる**launch.vs.json**が作成されます。 このファイルには選んだ CMake ターゲットに関する情報があらかじめ入力されており、プログラムの引数やデバッガーの種類などの他のパラメーターを指定することができます。 任意のキーを参照する、 **CMakeSettings.json**ファイルを付ける必要`cmake.`で**launch.vs.json**します。 次の例は、単純な**launch.vs.json**ファイルを取り込む場合の値を`remoteCopySources`キー、 **CMakeSettings.json**の現在選択されている構成ファイル。

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

保存するとすぐに、 **launch.vs.json**ファイルにエントリが作成、**スタートアップ アイテム**新しい名前を含むドロップダウンします。 編集することによって、 **launch.vs.json**ファイルとして CMake ターゲットの任意の数のような多くのデバッグ構成を作成できます。

## <a name="support-for-cmakesettings-variables"></a>CMakeSettings 変数のサポート

 **Launch.vs.json**で宣言されている変数をサポートしている**CMakeSettings.json** (下記参照)、現在選択されている構成に適用されるとします。 という名前のキーも`currentDir`、ローカルのプロジェクトを起動したアプリの現在のディレクトリを設定します。

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

'Cwd' キーは、プロジェクトのリモート起動のアプリの現在のディレクトリを設定します。 既定値は '${debugInfo.defaultWorkingDirectory}' に評価されます。 

```cmd
/var/tmp/src/bfc6f7f4-4f0f-8b35-80d7-9198fa973fb9/Linux-Debug
```

## <a name="see-also"></a>関連項目

[Visual Studio で CMake プロジェクト](cmake-projects-in-visual-studio.md)<br/>
[Linux CMake プロジェクトを構成する](../linux/cmake-linux-project.md)<br/>
[リモートの Linux コンピューターに接続する](../linux/connect-to-your-remote-linux-computer.md)<br/>
[CMake のビルド設定をカスタマイズする](customize-cmake-settings.md)<br/>
[CMake デバッグ セッションを構成する](configure-cmake-debugging-sessions.md)<br/>
[Linux プロジェクトのデプロイ、実行、デバッグ](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake 定義済み構成リファレンス](cmake-predefined-configuration-reference.md)<br/>
