---
title: 旧バージョンの Visual C++ からのプロジェクトのアップグレード
ms.date: 11/04/2016
helpviewer_keywords:
- 32-bit code porting
- upgrading Visual C++ applications, 32-bit code
ms.assetid: 18cdacaa-4742-43db-9e4c-2d9e73d8cc84
ms.openlocfilehash: 8848dca10a75bec6f5ff6251a3af5be8e9a7b6e6
ms.sourcegitcommit: 9e85c2e029d06b4c1c69837437468718b4d54908
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2019
ms.locfileid: "57816374"
---
# <a name="upgrading-projects-from-earlier-versions-of-visual-c"></a>旧バージョンの Visual C++ からのプロジェクトのアップグレード

ほとんどの場合、旧バージョンの Visual Studio で作成されたプロジェクトを開くことができます。 ただし、こうしたプロジェクトは、開くときにアップグレードされます。 アップグレードされたプロジェクトを保存すると、旧バージョンの Visual Studio では開くことができなくなります。

> [!IMPORTANT]
> 既に変換されたプロジェクトを変換しようとすると、再変換によって既存のファイルが削除されるため、その旨を確認するメッセージが表示されます。

アップグレードされたプロジェクトおよびソリューションの多くが、変更なしで正常にビルドできます。 ただし、一部のプロジェクトについては、設定、ソース コード、またはその両方に対する変更が必要になる可能性があります。 まず、次のガイドラインを使用して、設定に関する問題に対処することをお勧めします。その後、プロジェクトをまだビルドできない場合は、コードの問題に対処します。 詳細については、「[Overview of potential upgrade issues](../porting/overview-of-potential-upgrade-issues-visual-cpp.md)」 (アップグレードの潜在的な問題の概要) を参照してください。

1. 既存のプロジェクトおよびソリューション ファイルのコピーを作成します。 必要に応じてファイルのバージョンを比較できるように、現在のバージョンと旧バージョンの Visual Studio を並行してインストールします。

2. 現在のバージョンの Visual Studio で、プロジェクトまたはソリューションのコピーを開いてアップグレードし、保存します。

3. 変換されたプロジェクトごとに、ショートカット メニューを開き、 **[プロパティ]** を選択します。 **[構成プロパティ]** で **[全般]** を選択し、 **[プラットフォーム ツールセット]** で現在のバージョンを選択します (たとえば、Visual Studio 2017 の場合は **v141** を選択)。

4. ソリューションをビルドします。 ビルドに失敗した場合は、設定を変更し、リビルドします。

ストアド プロシージャをデータ ソースで簡単に変更してデバッグできるように、そのソースは個別のデータベース プロジェクトに含まれています。 データ ソースが含まれる C++ プロジェクトをアップグレードすると、個別のデータベース プロジェクトが自動的に作成されます。

対象となる Windows のバージョンを更新する方法については、「[WINVER および _WIN32_WINNT の変更](../porting/modifying-winver-and-win32-winnt.md)」を参照してください。

## <a name="in-this-section"></a>このセクションの内容

[Universal CRT へのコードのアップグレード](upgrade-your-code-to-the-universal-crt.md)<br/>
[WINVER および _WIN32_WINNT の変更](modifying-winver-and-win32-winnt.md)<br/>
[ライブラリ内部の依存関係を修正する](fix-your-dependencies-on-library-internals.md)<br/>
[浮動小数点の移行に関する問題](floating-point-migration-issues.md)<br/>
[Visual Studio でネイティブ マルチ ターゲットを利用し、古いプロジェクトを作成する](use-native-multi-targeting.md)<br/>
[Visual Studio 2019 プレビューでの非推奨の Visual C++ 機能](features-deprecated-in-visual-studio.md)<br/>
[ビルド システムの変更点](build-system-changes.md)<br/>

## <a name="see-also"></a>関連項目

[Visual Studio 2017 の Visual C++ の新機能](../what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
[2003 から 2015 の Visual C++ の履歴の変更](../porting/visual-cpp-change-history-2003-2015.md)<br/>
[非標準動作](../cpp/nonstandard-behavior.md)
