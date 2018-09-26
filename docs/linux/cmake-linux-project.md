---
title: Visual Studio で Linux CMake プロジェクトを構成する | Microsoft Docs
description: Visual Studio で Linux CMake プロジェクトを構成する方法
ms.custom: ''
ms.date: 07/20/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 88f5ef5379d597a81456dab7f3dd28a73a4df84b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394921"
---
# <a name="configure-a-linux-cmake-project"></a>Linux CMake プロジェクトを構成する

**Visual Studio 2017 バージョン 15.4 以降**<br/>
Visual Studio に Linux C++ ワークロードをインストールすると、Linux の CMake サポートが既定で選択されます。 Visual Studio プロジェクトに変換しなくても、CMake を利用する既存のコード ベースで作業できるようになりました。 コード ベースがクロス プラットフォームの場合、Visual Studio 内から Windows と Linux の両方をターゲット設定できます。

このトピックは、Visual Studio の CMake サポートに関する基本的な知識が読者にあるものとして作成されています。 詳細については、「[CMake Tools for Visual C++](../ide/cmake-tools-for-visual-cpp.md)」 (Visual C++ の CMake ツール) をご覧ください。 CMake 自体の詳細については、「[Build, Test and Package Your Software With CMake](https://cmake.org/)」 (CMake でソフトウェアをビルド、テスト、パッケージ化する) を参照してください。

> [!NOTE]  
> Visual Studio で CMake を利用するには、CMake 3.8 で導入されたサーバー モードに対応する必要があります。 Visual Studio で [CMake ターゲット ビュー](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/cmake-support-in-visual-studio-targets-view-single-file-compilation-and-cache-generation-settings/) ウィンドウをサポートする、Microsoft 提供の CMake バリアントの場合は、[https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases) で最新のビルド済みバイナリをダウンロードします。 パッケージ マネージャーで 3.8 より古いバージョンの CMake が提供される場合は、[ソースから CMake をビルドする](#build-a-supported-cmake-release-from-source)か、標準の CMake の使用が好ましい場合、公式の [CMake ダウンロード ページ](https://cmake.org/download/)からダウンロードすることで、これを回避できます。 

## <a name="open-a-folder"></a>フォルダーを開く

最初に、メイン メニューから **[ファイル]** > **[開く]** > **[フォルダー]** の順に選択するか、コマンド ラインに「`devenv.exe <foldername>`」と入力します。 開いたフォルダーには、ソース コードと共に CMakeLists.txt ファイルが入っているはずです。
次のサンプルでは、単純な CMakeLists.txt ファイルと .cpp ファイルを確認できます。

```cpp
// hello.cpp

#include <iostream>

int main(int argc, char* argv[])
{
    std::cout << "Hello from Linux CMake" << std::endl;
}
```

CMakeLists.txt:

```cmd
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="choose-a-linux-target"></a>Linux ターゲットを選ぶ

フォルダーを開くとすぐに、Visual Studio によって CMakeLists.txt ファイルが解析され、**x86-Debug** の Windows ターゲットが指定されます。 Linux を対象とするには、プロジェクト設定を **Linux-Debug** または **Linux-Release** に変更します。

既定では、**[ツール]** > **[オプション]** > **[クロス プラットフォーム]** > **[接続マネージャー]** の下にある一覧の、最初のリモート システムが選ばれます。 リモート接続が見つからない場合、リモート接続を作成するように求められます。

Linux ターゲットを指定すると、ソースが Linux マシンにコピーされます。 次に、Linux マシンで CMake が実行され、プロジェクトの CMake キャッシュが生成されます。

![Linux で CMake キャッシュを生成する](media/cmake-linux-1.png "Linux で CMake キャッシュを生成する")

**Visual Studio 2017 バージョン 15.7 以降:**<br/>
リモート ヘッダーの IntelliSense サポートを提供するため、Visual Studio によってローカルの Windows コンピューター上のディレクトリに自動的にコピーされます。 詳細については、[リモート ヘッダーの IntelliSense](configure-a-linux-project.md#remote_intellisense) のセクションを参照してください。

## <a name="debug-the-project"></a>プロジェクトをデバッグする

リモート システムでコードをデバッグするには、ブレークポイントを設定し、プロジェクト設定の隣にあるツール バー メニューのスタートアップ項目として CMake ターゲットを選び、ツール バーの **[&#x23f5; 実行]** を選択するか、F5 キーを押します。

プログラムのコマンド ライン引数をカスタマイズするには、**ソリューション エクスプローラー**で実行可能ファイルを右クリックし、**[デバッグ設定と起動設定]** を選びます。 これにより、プログラムに関する情報を含んだ launch.vs.json 構成ファイルが開かれるか、作成されます。 追加の引数を指定するには、`args` JSON 配列に引数を追加します。 詳細については、「[Open Folder projects in Visual C++ (Visual C++ の [フォルダーを開く] プロジェクト)](https://docs.microsoft.com/en-us/cpp/ide/non-msbuild-projects)」をご覧ください。

## <a name="configure-cmake-settings-for-linux"></a>Linux の CMake 設定を構成する

既定の CMake 設定を変更するには、メイン メニューで **[CMake]、[CMake の設定の変更]、[CMakeLists.txt]** の順に選ぶか、**[ソリューション エクスプローラー]** の CMakeSettings.txt を右クリックし、**[CMake の設定の変更]** を選びます。 次に、`CMakeSettings.json` という名称のフォルダーに新しいファイルが作成されます。このファイルには、プロジェクト設定のメニュー項目の一覧にある既定の構成が入力されます。 次のサンプルでは、前のコード サンプルに基づく、Linux デバッグの既定の構成を確認できます。

```json
{
      "name": "Linux-Debug",
      "generator": "Unix Makefiles",
      "remoteMachineName": "${defaultRemoteMachineName}",
      "configurationType": "Debug",
      "remoteCMakeListsRoot": "/var/tmp/src/${workspaceHash}/${name}",
      "cmakeExecutable": "/usr/local/bin/cmake",
      "buildRoot": "${env.LOCALAPPDATA}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.LOCALAPPDATA}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "remoteBuildRoot": "/var/tmp/build/${workspaceHash}/build/${name}",
      "remoteInstallRoot": "/var/tmp/build/${workspaceHash}/install/${name}",
      "remoteCopySources": true,
      "remoteCopySourcesOutputVerbosity": "Normal",
      "remoteCopySourcesConcurrentCopies": "10",
      "remoteCopySourcesMethod": "rsync",
      "remoteCopySourcesExclusionList": [".vs", ".git"],
      "rsyncCommandArgs" : "-t --delete --delete-excluded",
      "remoteCopyBuildOutput" : "false",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "",
      "ctestCommandArgs": "",
      "inheritEnvironments": [ "linux-x64" ]
}
```

`name` 値には、任意の値を指定できます。 リモート システムが複数存在する場合、`remoteMachineName` 値によって、ターゲットとなるリモート システムが指定されます。 このフィールドには IntelliSense が有効になっており、適切なシステムの選択を支援します。 フィールド `remoteCMakeListsRoot` によって、リモート システム上にある、プロジェクト ソースのコピー先が指定されます。 フィールド `remoteBuildRoot` は、リモート システムでビルド出力が生成される場所です。 その出力は、`buildRoot` によって指定される場所にもローカル コピーされます。 cmake インストールを行うときに適用されることを除き、`remoteInstallRoot` フィールドと `installRoot` フィールドは `remoteBuildRoot` と `buildRoot` に似ています。 `remoteCopySources` エントリにより、ローカル ソースがリモート コンピューターにコピーされるかどうかが制御されます。 ファイルが大量にあり、自分で既にソースを同期している場合、これを false に設定することがあります。 `remoteCopyOutputVerbosity` 値により、エラーを診断する必要がある場合のコピー ステップの詳細度が制御されます。 `remoteCopySourcesConcurrentCopies` エントリにより、コピーのために生成されるプロセスの数が制御されます。 `remoteCopySourcesMethod` 値は rsync または sftp になります。 `remoteCopySourcesExclusionList` フィールドでは、リモート コンピューターにコピーされる内容を制御できます。 `rsyncCommandArgs` 値では、コピーの rsync メソッドを制御できます。 `remoteCopyBuildOutput` フィールドにより、リモート ビルド出力がローカル ビルド フォルダーにコピーされるかどうかが制御されます。

さらに制御するためのオプション設定もいくつかあります。

```json
{
      "remotePreBuildCommand": "",
      "remotePreGenerateCommand": "",
      "remotePostBuildCommand": "",
}
```

そうしたオプションでは、ビルドの前後や CMake 生成の前にリモート ボックスでコマンドを実行できます。 リモート ボックスで有効なコマンドになります。 出力はパイプで Visual Studio に戻されます。

## <a name="build-a-supported-cmake-release-from-source"></a>サポートされている CMake リリースをソースからビルドする

Linux マシンで必須となる CMake の最小バージョンは 3.8 です。サーバー モードにも対応している必要があります。 確認するには、次のコマンドを実行します。

```cmd
cmake --version
```

サーバー モードが有効になっていることを確認するには、次を実行します。

```cmd
cmake -E capabilities
```

出力の中から **“serverMode”:true** を探します。 下の説明のようにソースから CMake をコンパイルするときでも、完了時に機能を確認してください。 サーバー モードの有効化を禁止する制約がお使いの Linux システムに存在する場合があります。

Linux システムのシェルでソースから CMake のビルドを始めるには、パッケージ マネージャーが最新の状態であることと、git と cmake が利用できることを確認してください。

最初に、Visual Studio の CMake サポート用のフォークが保持されている [Microsoft CMake リポジトリ](https://github.com/Microsoft/CMake)から、CMake のソースを複製します。

```cmd
sudo apt-get update
sudo apt-get install -y git cmake
git clone https://github.com/Microsoft/CMake.git
cd CMake
```

次に、CMake の現行リリースを /usr/local/bin にビルドしてインストールするために、以下のコマンドを実行します。

```cmd
mkdir out
cd out
cmake ../
make
sudo make install
```

次に、以下のコマンドを実行して、バージョンが 3.8 以上であることと、サーバー モードが有効になっていることを確認します。

```cmd
/usr/local/bin/cmake –version
cmake -E capabilities
```

## <a name="see-also"></a>参照

[プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)<br/>
[Visual C++ 用の CMake ツール](../ide/cmake-tools-for-visual-cpp.md)  
