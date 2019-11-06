---
title: 以前C++のバージョンの Visual Studio からのプロジェクトのアップグレード
description: 旧バージョンの Visual Studio からの Microsoft C++ プロジェクトのアップグレード方法。
ms.date: 10/29/2019
helpviewer_keywords:
- 32-bit code porting
- upgrading Visual C++ applications, 32-bit code
ms.assetid: 18cdacaa-4742-43db-9e4c-2d9e73d8cc84
ms.openlocfilehash: b317271a9cd0873e60a6dd9acd1b73a766aaea19
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627163"
---
# <a name="upgrade-c-projects-from-earlier-versions-of-visual-studio"></a>以前C++のバージョンの Visual Studio からのプロジェクトのアップグレード

Visual Studio 2008 以前で作成されたプロジェクトをアップグレードするには、最初に Visual Studio 2010 を使用して、プロジェクトを VCBuild 形式 (.vcproj) から MSBuild 形式 (.vcxproj) に変換する必要があります。 詳細については、「 [Visual Studio 2008 の手順](use-native-multi-targeting.md#instructions-for-visual-studio-2008)」を参照してください。

Visual Studio 2010 以降で作成されたプロジェクトをアップグレードするには、Visual Studio の最新バージョンでプロジェクトを開くだけです。 Visual Studio では、プロジェクトを現在のスキーマにアップグレードすることができます。 **[いいえ]** を選択し、コンピューターに以前のバージョンの visual studio がインストールされている場合は、新しいバージョンの visual studio でプロジェクトを操作して、古いツールセットを対象にすることができます。 たとえば、プロジェクトを引き続き Windows XP で実行する必要がある場合は、Visual Studio 2019 にアップグレードすることができますが、v141 以前のツールセットを指定する必要があります。 詳細については、「[Visual Studio でネイティブ マルチ ターゲットを利用し、古いプロジェクトを作成する](use-native-multi-targeting.md)」を参照してください。 **[はい]** を選択した場合、プロジェクトは変換され、以前のバージョンに変換することはできません。 そのため、アップグレードシナリオでは、既存のプロジェクトファイルとソリューションファイルのコピーを作成することをお勧めします。

## <a name="upgrade-reports"></a>レポートのアップグレード

プロジェクトをアップグレードするときは、UpgradeLog.htm としてプロジェクト フォルダーにも保存されているアップグレード レポートを受け取ります。 アップグレードレポートには、発生した問題の概要と、次のような変更に関する情報が表示されます。

1. プロジェクト プロパティ

2. インクルード ファイル

3. コンパイラ準拠の改善または標準における変更により、正常にコンパイルされなくなったコード

4. Visual Studio または Windows の利用できなくなった機能に依存するコードや、Visual Studio の既定のインストールに含まれなくなった、または製品から削除されたヘッダー ファイルに依存するコード

5. API の名前変更、関数シグネチャの変更、非推奨の関数など、API の変更によってコンパイルされなくなったコード

6. 警告がエラーになるなど、診断の変更によってコンパイルされなくなったコード

7. 特に /NODEFAULTLIB が使用される場合の、変更されたライブラリによるリンカー エラー

8. 動作の変更による実行時エラーまたは予期しない結果

9. ツールで導入されたエラー。 問題が発生した場合には、通常のサポート チャネルを通じて、または [Visual Studio C++ 開発者コミュニティ](https://developercommunity.visualstudio.com/spaces/62/index.html) ページを使用して、Visual C++ チームに報告してください。

アップグレードされたプロジェクトおよびソリューションの中には、変更せずに正常にビルドできるものがあります。 ただし、ほとんどのプロジェクトでは、ソースコードに加えて、プロジェクト設定の変更が必要になる可能性があります。 これらを修正する方法は1つではありませんが、段階的なアプローチをお勧めします。 作業を開始する前に、さまざまな種類の一般的なエラーの詳細について、[アップグレードに関する潜在的な問題の概要](../porting/overview-of-potential-upgrade-issues-visual-cpp.md)を確認してください。

 1. プラットフォームツールセット、 C++言語標準、および Windows SDK バージョン (該当する場合) を目的のバージョンに設定します。 (**プロジェクト** > **プロパティ** > **構成プロパティ** > **全般**)
 1. 多数のエラーが発生した場合は、[寛容](../build/reference/permissive-standards-conformance.md)オプション (**プロジェクト** > **プロパティ** > **構成プロパティ** > **C/C++**  > **言語**) および[コード分析をオフにします。](/visualstudio/code-quality/code-analysis-for-c-cpp-overview)(**Project** > **プロパティ** > **構成プロパティ** > **コード分析**) オプションを一時的に選択して、エラー数を減らします。
 1. すべての依存関係が存在し、インクルードパスまたはライブラリの場所が正しいことを確認します。 (**プロジェクト** > **プロパティ** > **VC + + ディレクトリ** > の**構成プロパティ**)
 1. 存在しなくなった Api への参照により、エラーを特定して修正します。
 1. コンパイルを妨げる残りのエラーを修正します。 一般的なエラーの修正については、 [「アップグレードに関する潜在的な問題の概要」](../porting/overview-of-potential-upgrade-issues-visual-cpp.md)を参照してください。
 1. MSVC で以前にコンパイルされた、準拠していないコードが原因で発生した新しいエラーがあれ**ば、それを無効に**して修正します。
 1. コード分析を有効にして、許容できない可能性がある潜在的な問題または古くなったコーディングパターンを特定します。 コード分析によって多くのエラーにフラグが設定されている場合は、いくつかの警告をオフにして、最も重要なものを最初に絞り込むことができます。 IDE は、いくつかの種類の問題をすばやく修正するのに役立ちます。
 1. たとえば、カスタムデータ構造とアルゴリズムをC++標準ライブラリやブーストオープンソースライブラリのものに置き換えるなどして、コードを最新化する他の機会を検討してください。 標準の機能を使用することにより、他のユーザーがコードを保守しやすくなり、コードが十分にテストされており、多くの専門家によって標準化委員会C++と広範なコミュニティによってレビューされていることも確実になります。

修復エラーが発生した場合は、Stack Overflow または[ C++開発者コミュニティ](https://developercommunity.visualstudio.com/spaces/62/index.html)で質問を検索または投稿してみてください。

## <a name="in-this-section"></a>このセクションの内容

[アップグレード時の潜在的な問題の概要](overview-of-potential-upgrade-issues-visual-cpp.md)<br/>
[Universal CRT へのコードのアップグレード](upgrade-your-code-to-the-universal-crt.md)<br/>
[WINVER と _WIN32_WINNT の更新](modifying-winver-and-win32-winnt.md)<br/>
[ライブラリ内部の依存関係を修正する](fix-your-dependencies-on-library-internals.md)<br/>
[浮動小数点の移行に関する問題](floating-point-migration-issues.md)<br/>
[C++Visual Studio 2019 で非推奨の機能](features-deprecated-in-visual-studio.md)<br/>
[VCBuild と MSBuild の比較](build-system-changes.md)<br/>
[ポートサードパーティライブラリ](porting-third-party-libraries.md)<br/>

## <a name="see-also"></a>関連項目

[Visual Studio における Visual C++ の新機能](../overview/what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
[2003 から 2015 の Visual C++ の履歴の変更](../porting/visual-cpp-change-history-2003-2015.md)<br/>
[非標準動作](../cpp/nonstandard-behavior.md)<br/>
[ポートデータアプリケーション](../data/data-access-programming-mfc-atl.md)<br/>
