---
title: CMakeSettings.json スキーマ リファレンス
ms.date: 03/05/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: d80829b1475e8718e1c4188ff4fb7d42a1d4b3b9
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827708"
---
# <a name="cmakesettingsjson-schema-reference"></a>CMakeSettings.json スキーマ リファレンス

`cmakesettings.json` ファイルには、指定したプラットフォームのプロジェクトをビルドするために、Visual Studio と CMake との対話方法を指定する情報が含まれています。 このファイルを使用して、cmake.exe 環境の環境変数や引数などの情報を格納します。

## <a name="environments"></a>環境

`environments` 配列には、"環境" を定義する `object` 型の `items` のリストが含まれます。 環境は変数のセットを `configuration` に適用するのに使用できます。 `environments` 配列内の各項目は以下で構成されています。

- `namespace`: フォーム `namespace.variable` 内の構成から環境変数を参照できるように環境に名前を付けます。 既定の環境オブジェクトは `env` と呼ばれ、`%USERPROFILE%` などの特定のシステム環境変数で設定されます。
- `environment`: この変数グループを一意に識別します。 後で `inheritEnvironments` エントリでグループが継承できるようにします。
- `groupPriority`:これらの変数を評価するときの優先順位を指定する整数。 数字が大きい大きい項目が最初に評価されます。
- `inheritEnvironments`:このグループによって継承される環境セットを指定する値の配列。 任意のカスタム環境を使用することも、次の定義済みの環境を使用することもできます。
 
  - linux_arm:ARM Linux をリモートでターゲットにします。
  - linux_x64:x64 Linux をリモートでターゲットにします。
  - linux_x86:x86 Linux をリモートでターゲットにします。
  - msvc_arm:MSVC コンパイラを使用して ARM Windows をターゲットとします。
  - msvc_arm_x64:64 ビットの MSVC コンパイラを使用して ARM Windows をターゲットとします。
  - msvc_arm64:MSVC コンパイラを使用して ARM64 Windows をターゲットとします。
  - msvc_arm64_x64:64 ビットの MSVC コンパイラを使用して ARM64 Windows をターゲットとします。
  - msvc_x64:MSVC コンパイラを使用して x64 Windows をターゲットとします。
  - msvc_x64_x64:64 ビットの MSVC コンパイラを使用して x64 Windows をターゲットとします。
  - msvc_x86:MSVC コンパイラを使用して x86 Windows をターゲットとします。
  - msvc_x86_x64:64 ビットの MSVC コンパイラを使用して x86 Windows をターゲットとします。

## <a name="configurations"></a>構成

`configurations` 配列は、同じフォルダー内の CMakeLists.txt ファイルに適用される CMake 構成を表すオブジェクトで構成されます。 これらのオブジェクトを使用して、複数のビルド構成を定義して、IDE 内でそれらを簡単に切り替えることもできます。 

`configuration` には次のプロパティがあります。
- `name`: 構成に名前を付けます。
- `description`: メニューに表示されるこの構成の説明。
- `generator`: この構成に使用する CMake ジェネレーターを指定します。 次のいずれかを指定できます。

  - Visual Studio 15 2017
  - Visual Studio 15 2017 Win64
  - Visual Studio 15 2017 ARM
  - Visual Studio 14 2015
  - Visual Studio 14 2015 Win64
  - Visual Studio 14 2015 ARM
  - UNIX メイクファイル
  - Ninja

- `configurationType`: 選択したジェネレーターにビルドの種類の構成を指定します。 次のいずれかを指定できます。
 
  - デバッグ
  - 解放
  - MinSizeRel
  - RelWithDebInfo
 
- `inheritEnvironments`: この構成が依存している 1 つまたは複数の環境を指定します。 任意のカスタム環境を使用することも、定義済みの環境を使用することもできます。
- `buildRoot`: 選択したジェネレーターに CMake がビルド スクリプトを生成するディレクトリを指定します。 サポートされているマクロには、`${workspaceRoot}`、`${workspaceHash}`、`${projectFile}`、`${projectDir}`、`${thisFile}`、`${thisFileDir}`、`${name}`、`${generator}`、`${env.VARIABLE}` などがあります。
- `installRoot`: 選択したジェネレーターに CMake がインストール ターゲットを生成するディレクトリを指定します。 サポートされているマクロには、`${workspaceRoot}`、`${workspaceHash}`、`${projectFile}`、`${projectDir}`、`${thisFile}`、`${thisFileDir}`、`${name}`、`${generator}`、`${env.VARIABLE}` などがあります。
- `cmakeCommandArgs`: キャッシュを生成するために呼び出す場合に CMake に渡す追加のコマンド ライン オプションを指定します。
- `cmakeToolchain`: toolchain ファイルを指定します。 これは、-DCMAKE_TOOLCHAIN_FILE を使用して CMake に渡されます。
- `buildCommandArgs`: --ビルド-- の後に CMake に渡されるネイティブ ビルド スイッチを指定します。
- `ctestCommandArgs`: テストの実行中に CTest に渡す追加のコマンド ライン オプションを指定します。
- `codeAnalysisRuleset`: コード分析を実行しているときに使用するルールセットを指定します。 Visual Studio によってインストールされたルールセット ファイルの完全なパスまたはファイル名を指定できます。
- `intelliSenseMode`: IntelliSense の情報を計算するために使用するモードを指定します。 次のいずれかを指定できます。
 
  - windows-msvc-x86
  - windows-msvc-x64
  - windows-msvc-arm
  - windows-msvc-arm64
  - android-clang-x86
  - android-clang-x64
  - android-clang-arm
  - android-clang-arm64
  - ios-clang-x86
  - ios-clang-x64
  - ios-clang-arm
  - ios-clang-arm64
  - windows-clang-x86
  - windows-clang-x64
  - windows-clang-arm
  - windows-clang-arm64
  - linux-gcc-x86
  - linux-gcc-x64
  - linux-gcc-arm

- `cacheRoot`: CMake キャッシュへのパスを指定します。 このディレクトリには、既存の CMakeCache.txt ファイルを含める必要があります。
- `remoteMachineName`: CMake、ビルド、およびデバッガーをホストするリモートの Linux マシンの名前を指定します。 新しい Linux マシンを追加するには、接続マネージャーを使用します。 サポートされているマクロには、`${defaultRemoteMachineName}` が含まれます。
- `remoteCopySourcesOutputVerbosity`: リモート マシンへのソース コピー操作の詳細レベルを指定します。 "ノーマル"、"詳細"、"診断" のいずれかを指定できます。
- `remoteCopySourcesConcurrentCopies`: ソースからリモート マシンへの同期中に使用される同時コピー数を指定します。
- `remoteCopySourcesMethod`: リモート マシンにファイルをコピーするメソッドを指定します。 "rsync" または "sftp" のいずれかを指定できます。
- `remoteCMakeListsRoot`: CMake プロジェクトを含むリモート マシン上のディレクトリを指定します。 サポートされているマクロには、`${workspaceRoot}`、`${workspaceHash}`、`${projectFile}`、`${projectDir}`、`${thisFile}`、`${thisFileDir}`、`${name}`、`${generator}`、`${env.VARIABLE}` などがあります。
- `remoteBuildRoot`: 選択したジェネレーターに CMake がビルド スクリプトを生成するリモート マシン上のディレクトリを指定します。 サポートされているマクロには、`${workspaceRoot}`、`${workspaceHash}`、`${projectFile}`、`${projectDir}`、`${thisFile}`、`${thisFileDir}`、`${name}`、`${generator}`、`${env.VARIABLE}` などがあります。
- `remoteInstallRoot`: 選択したジェネレーターに CMake がインストール ターゲットを生成するリモート マシン上のディレクトリを指定します。 サポートされているマクロには、`${workspaceRoot}`、`${workspaceHash}`、`${projectFile}`、`${projectDir}`、`${thisFile}`、`${thisFileDir}`、`${name}`、`${generator}`、`${env.VARIABLE}` などがあります。`VARIABLE` は、システム、ユーザー、またはセッション レベルで定義されている変数です。
- `remoteCopySources`:Visual Studio がリモート マシンにソース ファイルをコピーするかどうかを指定する `boolean`。 既定値は true です。 自分でファイルの同期を管理する場合は、false に設定します。
- `remoteCopyBuildOutput`:リモート システムからビルド出力をコピーするかどうかを指定する `boolean`。
- `rsyncCommandArgs`: rsync に渡される追加のコマンド ライン オプションのセットを指定します。
- `remoteCopySourcesExclusionList`:ソース ファイルのコピー中に除外するパスの一覧を指定する `array`: パスには、ファイルまたはディレクトリの名前か、コピーのルートに対する相対パスを指定できます。 glob パターン マッチング用のワイルドカード \\\"*\\\" および \\\"?\\\" を使用できます。
- `cmakeExecutable`: CMake プログラムの実行可能ファイルへの完全なパスを指定します。ファイル名と拡張子を含めます。
- `remotePreGenerateCommand`: CMakeLists.txt ファイルを解析するために CMake の実行前に実行するコマンドを指定します。
- `remotePrebuildCommand`: ビルド前にリモート マシン上で実行するコマンドを指定します。
- `remotePostbuildCommand`: ビルド後にリモート マシン上で実行するコマンドを指定します。
- `variables`:-Dname1=value1 -Dname2=value2 などのように CMake に渡される変数を指定する `array`。 


