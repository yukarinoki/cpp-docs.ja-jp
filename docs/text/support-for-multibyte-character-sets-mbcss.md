---
title: マルチバイト文字セット (MBCS) のサポート
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- multibyte characters [C++]
- MBCS [C++]
ms.assetid: b498733c-a1e1-45e3-8f26-d6da3cb5f2dd
ms.openlocfilehash: 0b43168ec4331e99dea7e939b097674cc880804e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375764"
---
# <a name="support-for-multibyte-character-sets-mbcss"></a>マルチバイト文字セット (MBCS) のサポート

マルチバイト文字セット (MBCS: Multibyte Character Set) は、日本語や中国語など、1 バイト文字では表現できない文字セットをサポートするニーズに対する古いアプローチです。 新規開発を行う場合は、エンド ユーザーに対して表示されることのないシステム文字列を除き、すべてのテキスト文字列で Unicode 文字列を使用する必要があります。 MBCS は、レガシ テクノロジであり、新規開発にはお勧めしません。

最も一般的な MBCS の実装は、2 バイト文字セット (DBCS: Double-Byte Character Set) です。 Visual C++ と MFC では、DBCS に完全に対応しています。

サンプルについては、MFC ソース コード ファイルを参照してください。

大きな文字セットを採用している市場に対応したプラットフォームでは、Unicode の代わりとしては MBCS がまず考えられます。 MFC では、国際化に対応できるデータ型と C ランタイム関数を使用することにより MBCS をサポートしています。 プログラム コードでもこれらを使用するようにしてください。

MBCS では、1 バイトまたは 2 バイトのいずれかで文字がエンコードされます。 2 バイト文字では、最初にくる先頭バイトとその後ろに続くバイトの両方で 1 つの文字と解釈されるようになっています。 この最初のバイトは、先行バイト用に予約されている範囲の値をとります。 バイトのどの範囲が先行バイトとなるかは、使用するコード ページによって異なります。 たとえば、日本語のコード ページ 932 では 0x81 から 0x9F までの範囲を先行バイトとして使いますが、韓国語のコード ページ 949 では別の範囲を使っています。

MBCS のプログラミングでは、次の点について考慮する必要があります。

環境内の MBCS 文字は、ファイル名やディレクトリ名などの文字列に含めることができます。

### <a name="editing-operations"></a>編集操作

MBCS アプリケーションでの編集操作は、バイトではなく文字に対して行う必要があります。 キャレットは文字を分割しないようにする必要があり、**右矢印**キーは右に 1 文字移動する必要があります。 **削除**は文字を削除する必要があります。**元に戻す**必要がありますを挿入します。

### <a name="string-handling"></a>文字列操作

MBCS を使うアプリケーションでは、文字列操作で特殊な問題が出てきます。 1 つの文字列の中に 1 バイト幅の文字と 2 バイト幅の文字が混在しているため、先頭バイトがあるかどうかを必ず確認する必要があります。

### <a name="run-time-library-support"></a>ランタイム ライブラリのサポート

C のランタイム ライブラリおよび MFC は、1 バイト文字、MBCS、および Unicode でのプログラミングをそれぞれサポートしています。 1 バイト文字列は、ランタイム関数`str`のファミリで処理され、MBCS 文字列は対応する`_mbs`関数で処理され、Unicode 文字列は対応`wcs`する関数で処理されます。 MFC クラスのメンバー関数では、状況に応じて、通常の `str` ファミリの関数、MBCS の関数、または Unicode の関数に割り当てる移植性の高いランタイム関数を使用しています。

### <a name="mbcsunicode-portability"></a>MBCS と Unicode の移植性

tchar.h ヘッダー ファイルを使用すると、同じソースからシングルバイト、MBCS、および Unicode アプリケーションをビルドできます。 Tchar.h は、_tcs*を付けたマクロ*を`str`定義`_mbs`し、`wcs`適切な 、 、または 関数にマップします。 MBCS でビルドするには、シンボル `_MBCS` を定義します。 Unicode をビルドするには、`_UNICODE`記号 を定義します。 MFC アプリケーションでは、既定で `_UNICODE` が定義されています。 詳細については、 [tchar.h の汎用テキスト マッピングを](../text/generic-text-mappings-in-tchar-h.md)参照してください。

> [!NOTE]
> と の`_UNICODE``_MBCS`両方を定義する場合、動作は定義されません。

Mbctype.h ヘッダー ファイルおよび Mbstring.h ヘッダー ファイルでは、MBCS 固有の関数とマクロが定義されています。この関数とマクロは状況に応じて必要になります。 たとえば `_ismbblead` は、文字列の特定のバイトが先行バイトかどうかを示します。

国際移植性を高めるには[、Unicode](../text/support-for-unicode.md)またはマルチバイト文字セット (MBCD) を使用してプログラムをコーディングします。

## <a name="what-do-you-want-to-do"></a>目的に合ったトピックをクリックしてください

- [国際化対応について](../text/international-enabling.md)

- [プログラムでユニコードと MBCS の両方を有効にする](../text/internationalization-strategies.md)

- [MBCS のプログラミングについて](../text/mbcs-programming-tips.md)

- [MBCS のプログラミングについて](../text/mbcs-programming-tips.md)

- [Tchar.h における汎用テキストのマッピング](../text/generic-text-mappings-in-tchar-h.md)

## <a name="see-also"></a>関連項目

[テキストと文字列](../text/text-and-strings-in-visual-cpp.md)<br/>
[Visual C++ における MBCS のサポート](../text/mbcs-support-in-visual-cpp.md)
