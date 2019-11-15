---
title: Microsoft C++移植およびアップグレードガイド
description: Microsoft C++ code を最新バージョンの Visual Studio にアップグレードします。
ms.date: 11/05/2019
ms.assetid: f5fbcc3d-aa72-41a6-ad9a-a706af2166fb
ms.topic: overview
ms.openlocfilehash: 04c3950d637c01031e78d0d95e13232143ceb232
ms.sourcegitcommit: 4dde7914608508e47c21cae03ac58fe953a0c29b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2019
ms.locfileid: "74119488"
---
# <a name="microsoft-c-porting-and-upgrading-guide"></a>Microsoft C++移植およびアップグレードガイド

このトピックでは、Visual Studio のC++最新バージョンに Microsoft コードをアップグレードするためのガイドを提供します。 Visual Studio 2008 以前で作成されたプロジェクトからアップグレードする場合は、最初に Visual Studio 2010 を使用してプロジェクトを MSBuild 形式に変換してから、Visual Studio 2019 でプロジェクトを開く必要があります。 Visual Studio 2010 から2015で作成されたプロジェクトの場合は、Visual Studio 2019 でプロジェクトを開きます。 詳細な手順については、「[以前のバージョンの Visual Studio からのプロジェクトのアップグレードC++ ](upgrading-projects-from-earlier-versions-of-visual-cpp.md)」を参照してください。

Visual Studio 2015、Visual Studio 2017、および Visual Studio 2019 のツールセットは、バイナリと互換性があります。これにより、ライブラリの依存関係をアップグレードしなくても、より新しいバージョンのコンパイラにアップグレードできます。 詳細については、「 [ C++ 2015 と2019のバイナリ互換性](binary-compat-2015-2017.md)」を参照してください。

オープンソースライブラリを使用するプロジェクトをアップグレードする場合、または複数のプラットフォームで実行する場合は、CMake ベースのプロジェクトに移行することをお勧めします。 詳細については、「 [Visual Studio での Cmake プロジェクト](../build/cmake-projects-in-visual-studio.md)」を参照してください。

## <a name="reasons-to-upgrade-c-code"></a>コードをアップグレードC++する理由

レガシアプリケーションが十分に実行されており、セキュリティで保護された環境で動作していて、アクティブな開発中でない場合は、アップグレードする必要がありません。 ただし、アプリケーションに継続的なメンテナンスが必要な場合、またはパフォーマンスやセキュリティの強化などの新機能の開発が必要な場合は、次のいずれかの理由でコードをアップグレードすることを検討してください。

- コンパイラの最適化が向上しているため、同じコードをより高速に実行できます。

- 最新C++の機能とプログラミング手法により、バグの一般的な原因が多くなくなり、以前の C スタイルの表現よりもはるかに簡単に保守できるコードが生成されます。

- コンパイラとリンカーのパフォーマンスが向上するため、ビルド時間が大幅に短縮されます。

- 標準への準拠の向上。 [/Permissive-](../build/reference/permissive-standards-conformance.md)コンパイラオプションを使用すると、以前は Microsoft C++コンパイラで許可されていたが、現在C++の標準に準拠していないコードを識別できます。

- より安全な[C ランタイムライブラリ]()機能や、[ガードチェック](../build/reference/guard-enable-guard-checks.md)やアドレス sanitizers などのコンパイラ機能 (Visual Studio 2019 バージョン 16.4) など、実行時のセキュリティが向上しました。

## <a name="multitargeting-vs-upgrading"></a>マルチターゲットとアップグレード

コードベースを新しいツールセットにアップグレードすることができない場合でも、最新バージョンの Visual Studio を使用して、以前のツールセットとライブラリでコンパイルされるプロジェクトをビルドおよび編集できます。 Visual Studio 2019 では、次のような機能を利用できます。

- 主要なガイドラインチェッカーや Clang C++ -Tidy などの最新の静的分析ツールを使用すると、ソースコードの潜在的な問題を特定するのに役立ちます。

- 最新のスタイルの選択に応じてオートフォーマットを使用すると、従来のコードをより読みやすくするのに役立ちます。

詳細については、「[Visual Studio でネイティブ マルチ ターゲットを利用し、古いプロジェクトを作成する](use-native-multi-targeting.md)」を参照してください。

## <a name="in-this-section"></a>このセクションの内容

|Title|説明|
|-----------|-----------------|
|[以前C++のバージョンの Visual Studio からのプロジェクトのアップグレード](upgrading-projects-from-earlier-versions-of-visual-cpp.md)|コードベースを Visual Studio 2019 および v142 のコンパイラにアップグレードする方法について説明します。|
|[コードをアップグレードC++するための IDE ツール](ide-tools-for-upgrading-code.md)|アップグレードプロセスに役立つ IDE の便利な機能。|
|[C++2015と2019間のバイナリの互換性](binary-compat-2015-2017.md)|V142 プロジェクトの現状で v140 ライブラリを使用します。|
|[Visual Studio でネイティブ マルチ ターゲットを利用し、古いプロジェクトを作成する](use-native-multi-targeting.md)|以前のコンパイラとライブラリで Visual Studio 2019 を使用します。|
|[2003 から 2015 の Visual C++ の履歴の変更](visual-cpp-change-history-2003-2015.md)|Visual Studio 2003 から2015の Microsoft C++ライブラリおよびビルドツールのすべての変更の一覧。コードの変更が必要になる場合があります。|
|[2003 ～ 2015 年の Visual C++ の新機能](visual-cpp-what-s-new-2003-through-2015.md)|Visual Studio 2003 から Visual studio 2015 までの Microsoft C++の "新機能" のすべての情報。|
|[移植およびアップグレード: 例とケース スタディ](porting-and-upgrading-examples-and-case-studies.md)|このセクションでは、いくつかのサンプルとアプリケーションを移植してアップグレードし、エクスペリエンスと結果について説明しました。 これらを読むと、移植およびプロセスのアップグレードに関係する含意がわかります。 プロセス全体を通して、アップグレードに関するヒントとテクニックについて説明し、特定のエラーを修正する方法を示します。|
|[ユニバーサル Windows プラットフォームへの移植](porting-to-the-universal-windows-platform-cpp.md)|コードを Windows 10 に移植する方法を説明します。|
|[Visual C++ の紹介 (UNIX ユーザー向け)](introduction-to-visual-cpp-for-unix-users.md)|Visual C++ を初めて使用し、生産性を向上したい UNIX ユーザー向けの情報を提供します。|
|[Windows での Linux プログラムの実行](porting-from-unix-to-win32.md)|UNIX アプリケーションを Windows に移行するためのオプションについて説明します。|

## <a name="see-also"></a>関連項目

[Visual Studio での C++](../overview/visual-cpp-in-visual-studio.md)<br/>
[Visual Studio での C++ コンパイラの新機能](../overview/what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
[Visual Studio の C++ 準拠の強化](../overview/cpp-conformance-improvements.md)<br/>
