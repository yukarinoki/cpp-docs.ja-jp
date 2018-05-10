---
title: Visual Studio で Linux CMake プロジェクトを構成する | Microsoft Docs
ms.custom: ''
ms.date: 10/25/2107
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-linux
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 961419e9ffcd5dede0db01f81e1b1eedc3290436
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="configure-a-linux-cmake-project"></a>Linux CMake プロジェクトを構成する
  
**Visual Studio 2017 バージョン 15.4** Linux C++ ワークロードをインストールすると、Linux の CMake サポートが既定で選択されます。 Visual Studio プロジェクトに変換しなくても、CMake を利用する既存のコード ベースで作業できるようになりました。 コード ベースがクロス プラットフォームの場合、Visual Studio 内から Windows と Linux の両方をターゲット設定できます。 

このトピックは、Visual Studio の CMake サポートに関する基本的な知識が読者にあるものとして作成されています。 詳細については、「[CMake Tools for Visual C++](../ide/cmake-tools-for-visual-cpp.md)」 (Visual C++ の CMake ツール) をご覧ください。 CMake 自体の詳細については、「[Build, Test and Package Your Software With CMake](https://cmake.org/)」 (CMake でソフトウェアをビルド、テスト、パッケージ化する) を参照してください。

> [!NOTE] 
> Visual Studio で CMake を利用するには、CMake 3.8 で導入されたサーバー モードに対応する必要があります。 パッケージ マネージャーから古いバージョンの CMake が提供される場合、ソースから CMake 3.8 をビルドすることでそれを回避できます。



## <a name="open-a-folder"></a>フォルダーを開く
最初に、メイン メニューから **[ファイル]、[開く]、[フォルダー]** の順に選択するか、コマンド ラインに「`devenv.exe <foldername>`」と入力します。 開いたフォルダーには、ソース コードと共に CMakeLists.txt ファイルが入っているはずです。
次のサンプルでは、単純な CMakeLists.txt ファイルと .cpp ファイルを確認できます。

```cpp
// Hello.cpp

#include <iostream>;
 
int main(int argc, char* argv[])
{
    std::cout << "Hello" << std::endl;
}
```

CMakeLists.txt: 
```cmd
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="choose-a-linux-target"></a>Linux ターゲットを選ぶ
フォルダーを開くとすぐに、CMakeLists.txt ファイルが解析され、x86 デバッグの Windows ターゲットが指定されます。 Linux を対象とするには、Linux デバッグまたは Linux リリースにプロジェクト設定を変更します。

既定では、一覧の最初にあるリモート システムが選ばれます (**[ツール]、[オプション]、[クロス プラットフォーム]、[接続マネージャー]** の下で)。 リモート接続が見つからない場合、リモート接続を作成するように求められます。

Linux ターゲットを指定すると、ソースが Linux マシンにコピーされます。 次に、Linux マシンで CMake が実行され、プロジェクトの CMake キャッシュが生成されます。  

![Linux で CMake キャッシュを生成する](media/cmake-linux-1.png "Linux で CMake キャッシュを生成する")  

## <a name="debug-the-project"></a>プロジェクトをデバッグする  
リモート システムでコードをデバッグするには、ブレークポイントを設定し、プロジェクト設定の隣にあるツール バー メニューのスタートアップ項目として CMake ターゲットを選び、[実行] をクリックします (あるいは、F5 を押します)。

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
      "remoteBuildRoot": "/var/tmp/build/${workspaceHash}/build/${name}",
      "remoteCopySources": true,
      "remoteCopySourcesOutputVerbosity": "Normal",
      "remoteCopySourcesConcurrentCopies": "10",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "",
      "ctestCommandArgs": "",
      "inheritEnvironments": [ "linux-x64" ]
}
```
`name` 値には、任意の値を指定できます。 リモート システムが複数存在する場合、`remoteMachineName` 値によって、ターゲットとなるリモート システムが指定されます。 このフィールドには IntelliSense が有効になっており、適切なシステムの選択を支援します。 フィールド `remoteCMakeListsRoot` によって、リモート システム上にある、プロジェクト ソースのコピー先が指定されます。 フィールド `remoteBuildRoot` は、リモート システムでビルド出力が生成される場所です。 その出力は、`buildRoot` によって指定される場所にもローカル コピーされます。

## <a name="building-a-supported-cmake-release-from-source"></a>サポートされている CMake リリースをソースからビルドする
Linux マシンで必須となる CMake の最小バージョンは 3.8 です。サーバー モードにも対応している必要があります。 確認するには、次のコマンドを実行します。

```cmd
cmake --version
```

サーバー モードが有効になっていることを確認するには、次を実行します。

```cmd
cmake -E capabilities
```

出力の中から “serverMode”:true を探します。 下の説明のようにソースから CMake をコンパイルするときでも、完了時に機能を確認してください。 サーバー モードの有効化を禁止する制約がお使いの Linux システムに存在する場合があります。

お使いの Linux システムのためにシェルのソースからビルドを始めるには、パッケージ マネージャーが最新の状態であることと、git と cmake が利用できることを確認してください。 最初に、Visual Studio の CMake サポート用に使用しているリポジトリから CMake ソースを複製します。

```cmd
sudo apt-get update
sudo apt-get install -y git cmake
git clone https://github.com/Microsoft/CMake.git
cd CMake
```

次に、次のコマンドを実行します。

```cmd
mkdir out
cd out
cmake ../
make
sudo make install
```

上のコマンドで CMake の現行リリースがビルドされ、/usr/local/bin にリリースされます。 バージョンが 3.8 以上であることとサーバー モードが有効になっていることを確認するには、次のコマンドを実行します。

```cmd
/usr/local/bin/cmake –version
cmake -E capabilities
```

## <a name="see-also"></a>参照
[プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)  
[Visual C++ 用の CMake ツール](../ide/cmake-tools-for-visual-cpp.md)
