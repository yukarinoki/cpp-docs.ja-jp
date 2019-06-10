---
title: 互換性
ms.date: 11/04/2016
f1_keywords:
- c.programs
helpviewer_keywords:
- CRT, compatibility
- compatibility, C run-time libraries
- compatibility
ms.assetid: 346709cb-edda-4909-9a19-3d253eddb6b7
ms.openlocfilehash: 5e9d2edca8da128343bd14ea86a8c1c0023a244b
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446670"
---
# <a name="compatibility"></a>互換性

Universal C Run-Time Library (UCRT) は、C++ に適合するために必要な C 標準ライブラリの大部分をサポートしています。 C99 (ISO/IEC 9899:1999) ライブラリを実装しています (ただし、\<tgmath.h> で定義されている型がジェネリックのマクロと、\<complex.h> での厳密な型の互換性は除きます)。 また、UCRT は、POSIX.1 (ISO/IEC 9945-1:1996、POSIX システム アプリケーション プログラミング インターフェイス) の C ライブラリの大きなサブセットを実装していますが、すべての POSIX 標準に完全に適合しているわけではありません。  さらに、UCRT はいくつかの Microsoft 固有の関数とマクロを実装していますが、これらは標準には含まれていません。

Visual C++ の Microsoft による実装に固有の関数は vcruntime ライブラリ内にあります。  これらの関数の多くは内部で使用されるものであり、ユーザー コードから呼び出すことはできません。 一部の関数は、デバッグでの使用や、実装の互換性の目的でドキュメントに記載されています。

C++ 標準では、グローバル名前空間のアンダースコアで始まる名前は、実装用に予約されています。 POSIX 関数はグローバル名前空間に含まれていますが、標準の C ランタイム ライブラリの一部ではないため、これらの関数の Microsoft 固有の実装では名前の先頭にアンダースコアが付いています。 移植性の目的で、UCRT では既定の名前もサポートされていますが、それらを使用するコードがコンパイルされると、非推奨の警告が Microsoft C++ コンパイラから出されます。 既定の POSIX 名が非推奨とされており、関数そのものは使用できます。 この警告を表示しないようにするには、元の POSIX 名を使用するコードでヘッダーをインクルードする前に `_CRT_NONSTDC_NO_WARNINGS` を定義します。

標準 C ライブラリの関数の中には、パラメーターを誤用した場合やバッファーのチェックを行わない場合、安全に使用できないものがありました。 これらの関数は、多くの場合、コードのセキュリティ問題の発生源になります。 Microsoft では、これらの関数の一連の安全性を高めたバージョンを作成し、パラメーターの使い方を確認するようにしました。また、実行時に問題が検出された場合は、無効パラメーター ハンドラーが呼び出されます。  既定では、より安全で利用可能なバリアントが含まれる関数が使用されると、Microsoft C++ コンパイラから非推奨の警告が出されます。 C++ コードをコンパイルする場合に `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` を 1 に定義すると、ほとんどの警告が解消されます。 こうすると、テンプレートのオーバーロードを使用して安全性の高いバリアントが呼び出されるため、ソース コードの移植性を維持できます。 この警告を表示しないようにするには、これらの関数を使用するコードでヘッダーをインクルードする前に `_CRT_SECURE_NO_WARNINGS` を定義します。 詳細については、「 [Security Features in the CRT](../c-runtime-library/security-features-in-the-crt.md)」を参照してください。

特定の関数に関するドキュメントで別途説明されている場合を除き、UCRT は Windows API と互換性があります。  Windows 8 ストア アプリ、または Windows 10 上のユニバーサル Windows プラットフォーム (UWP) アプリでは、特定の関数がサポートされません。 これらの関数は、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」の一覧に含まれています。この一覧には、Windows ランタイムと [UWP](/uwp) でサポートされない関数が列挙されています。

## <a name="related-articles"></a>関連トピック

|Title|説明|
|-----------|-----------------|
|[UWP アプリ、Windows ランタイム、および C ランタイム](../c-runtime-library/windows-store-apps-the-windows-runtime-and-the-c-run-time.md)|UCRT ルーチンがユニバーサル Windows アプリまたは Microsoft ストア アプリと互換性がないケースについて説明します。|
|[ANSI C 準拠](../c-runtime-library/ansi-c-compliance.md)|UCRT における標準に適合した名前付けについて説明します。|
|[UNIX](../c-runtime-library/unix.md)|プログラムを UNIX に移植するためのガイドラインを提供します。|
|[Windows プラットフォーム (CRT)](../c-runtime-library/windows-platforms-crt.md)|CRT がサポートするオペレーティング システムの一覧を示します。|
|[下位互換性](../c-runtime-library/backward-compatibility.md)|CRT の古い名前が新しい名前にマップされる方法について説明します。|
|[CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)|CRT ライブラリ (.lib) ファイルと、関連するコンパイラ オプションの概要を示します。|