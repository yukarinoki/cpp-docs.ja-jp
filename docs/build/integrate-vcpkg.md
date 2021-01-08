---
title: vcpkg と Visual Studio または Visual Studio Code を統合する
description: vcpkg を Windows 上の Visual Studio、または macOS と Linux 上の Visual Studio Code と統合する方法について説明します。
ms.date: 12/11/2020
ms.technology: cpp-ide
ms.openlocfilehash: b6f092313dde14b10a05d4cff0904adf5174b264
ms.sourcegitcommit: 2b2c3fa9244e31db35ea33554dea0efcab490f3c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/18/2020
ms.locfileid: "97684119"
---
# <a name="integrate-vcpkg-with-visual-studio-or-visual-studio-code"></a>vcpkg と Visual Studio または Visual Studio Code を統合する

vcpkg は、C および C++ のライブラリのクロスプラットフォームのコマンドライン パッケージ マネージャーです。 Windows 上の Visual Studio、または Linux と macOS 上の Visual Studio Code と統合できます。

## <a name="integrate-with-visual-studio-on-windows"></a>Windows 上の Visual Studio と統合する

### <a name="integrate-per-user"></a>ユーザーごとに統合する

vcpkg ルート ディレクトリから **`vcpkg integrate install`** を実行して、ユーザーごとにすべての vcpkg ヘッダー ファイルとバイナリを検索するように Visual Studio を構成します。 Visual Studio で VC++ ディレクトリ パスを編集する必要はありません。 vcpkg のクローンが複数ある場合、このコマンドを実行するクローンが新しい既定の場所となります。

これで、フォルダーまたはヘッダーの名前を入力してヘッダーをインクルードできるようになりました。オートコンプリートを利用できます。 ライブラリにリンクしたり、プロジェクト参照を追加したりする追加の手順は必要ありません。 次の図は、Visual Studio によってどのように *`azure-storage-cpp`* ヘッダーが検出されるかを示しています。 vcpkg は、ターゲット プラットフォームでパーティション分割される、 *`/installed`* サブフォルダーにそのヘッダーを配置します。 以下の図は、ライブラリの *`/was`* サブフォルダーにあるインクルード ファイルのリストを示しています。

![Visual Studio エディターの IntelliSense オートコンプリートのポップアップ ウィンドウ](media/vcpkg-intellisense.png "vcpkg と IntelliSense")

### <a name="integrate-per-project"></a>プロジェクトごとに統合する

アクティブになっている vcpkg インスタンスのバージョンとは異なる特定のバージョンのライブラリを使用する必要がある場合は、次の手順に従います。

1. vcpkg の新しいクローンを作成します。 詳細については、「[vcpkg をインストールする](install-vcpkg.md)」を参照してください。

1. 新しい vcpkg ルート ディレクトリに移動します。

1. ライブラリの portfile を変更して、必要なバージョンを取得します。

1. **`vcpkg install <library>`** を実行します。 詳細については、「[vcpkg を使用してライブラリを管理する](manage-libraries-with-vcpkg.md)」を参照してください。

1. **`vcpkg integrate project`** を使用して、プロジェクトごとにそのライブラリを参照する NuGet パッケージを作成します。

## <a name="integrate-with-visual-studio-code-on-linux-or-macos"></a>Linux または macOS 上の Visual Studio Code と統合する

シェルまたはターミナル ウィンドウで、ディレクトリを vcpkg ルート ディレクトリに変更します。 次に **`./vcpkg integrate install`** を実行して、Linux または macOS 上の Visual Studio Code を構成します。 このコマンドを使用して vcpkg ツールとライブラリの場所を設定し、ソース ファイルで IntelliSense を有効にします。

## <a name="remove-vcpkg-integration"></a>vcpkg の統合を削除する

**`integrate`** オプションを使用した場合は、vcpkg インスタンスを削除する前に統合を削除する必要があります。 統合を削除してクリーンアップするには、ディレクトリを vcpkg ルート ディレクトリに変更します。 Windows 上の場合、統合を確実にクリーンアップするには **`vcpkg integrate remove`** を実行します。 Linux または macOS 上の場合は、 **`./vcpkg integrate remove`** コマンドを実行します。

## <a name="see-also"></a>関連項目

[vcpkg: Windows、Linux、および macOS 用の C++ パッケージ マネージャー](./vcpkg.md)\
[GitHub 上の vcpkg](https://github.com/Microsoft/vcpkg)\
[vcpkg をインストールする](install-vcpkg.md)\
[vcpkg を使用してライブラリを管理する](manage-libraries-with-vcpkg.md)\
[vcpkg コマンドライン リファレンス](vcpkg-command-line-reference.md)\
[クイック スタート](https://github.com/microsoft/vcpkg/blob/master/docs/index.md)\
[よく寄せられる質問](https://github.com/microsoft/vcpkg/blob/master/docs/about/faq.md)
