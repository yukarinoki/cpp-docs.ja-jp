---
title: Unicode のサポート
ms.date: 1/09/2018
helpviewer_keywords:
- globalization [C++], character sets
- portable data types [MFC]
- Unicode [C++]
- wide characters [C++], about wide characters
- character sets [C++], Unicode
- localization [C++], character sets
- Unicode [C++], installing support
ms.openlocfilehash: fea49bff2a4563b8617e19636e27afbae1c55811
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410552"
---
# <a name="support-for-unicode"></a>Unicode のサポート

Unicode は、1 バイト (つまり、ほとんどの) で表すことができないものも含めて、すべての文字セットをサポートするための仕様です。 いずれかの Unicode を使用することをお勧め国際市場向けプログラミングしている場合、または[マルチバイト文字セット](../text/support-for-multibyte-character-sets-mbcss.md)(MBCS)、またはスイッチを変更することでいずれかをビルドできるように、プログラムのコードします。

ワイド文字は、2 バイトの多言語文字コードです。 数万文字、技術的な記号や発行の特殊文字を含むほぼすべての文字で、現代のコンピューティングが世界中で使用を構成するは、全体の 1 つとしての Unicode 仕様に従って表現できる文字をエンコードしてutf-16 を使用します。 Unicode サロゲート ペアの機能を使用して、1 つだけのワイド文字では表現できない文字を Unicode のペアで表現できます。 一般的に使用されるほとんどすべての文字は、1 つの 16 ビットのワイド文字の utf-16 で表される、ためには、国際文字セットを使用したプログラミングのワイド文字を使用して簡略化します。 による UTF 16LE (リトル エンディアン) でエンコードされたワイド文字とは、Windows のネイティブ文字形式です。

ワイド文字列は `wchar_t[]` 配列として表現され、`wchar_t*` ポインターで指し示されます。 ASCII 文字は、先頭に文字 L を付けることで、ワイド文字として表現できます。 たとえば、L '\0' はワイド (16 ビット) の終端の NULL 文字です。 同様に、ASCII 文字列リテラルは、ASCII リテラルの先頭に文字 L を付けることで、ワイド文字列リテラルとして表現できます (L"Hello")。

通常、ワイド文字はマルチバイト文字よりもメモリ内の領域を多く必要としますが、処理は速くなります。 さらに、1 つだけのロケールは、マルチバイト エンコードで一度に表現できる、Unicode 表現でに、世界中のすべての文字セットは、同時に表されます。

MFC フレームワークは Unicode に完全に対応しており、MFC では、次の表に示すように、移植性のあるマクロを使用することで Unicode 対応を実現しています。

## <a name="portable-data-types-in-mfc"></a>MFC での移植性のあるデータ型

|移植性のないデータ型|置き換えに使うマクロ|
|-----------------------------|----------------------------|
|`char`, `wchar_t`|`_TCHAR`|
|`char*`、 `LPSTR` (Win32 データ型) `LPWSTR`|`LPTSTR`|
|`const char*`、 `LPCSTR` (Win32 データ型) `LPCWSTR`|`LPCTSTR`|

クラス`CString`使用`_TCHAR`をベースとの簡単な変換コンス トラクターと演算子を提供します。 Unicode の文字列操作のほとんどは、操作の基本単位が 8 ビット バイトではなく 16 ビット文字であることを除き、Windows の ANSI 文字セットの操作に使用するのと同じロジックを使用して記述できます。 マルチバイト文字セットの操作と異なり、1 つの Unicode 文字を 2 つの個別のバイトのように扱う必要はなく、また、そのような処理は適切ではありません。 ワイド文字のサロゲート ペアが表す単一の文字の可能性に対処する必要は、ただし、します。 一般に、文字列の長さは、文字数と同じ幅の狭いまたは広いが含まれているかどうかが想定するコードを書き込みません。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [MFC の Unicode とマルチバイト文字セット (MBCS) のサポートを使用します。](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)

- [Unicode をプログラムで有効にします。](../text/international-enabling.md)

- [プログラムで Unicode と MBCS の両方を有効にします。](../text/internationalization-strategies.md)

- [Unicode を使用して、国際化のプログラムを作成するには](../text/unicode-programming-summary.md)

- [Unicode の利点について説明します](../text/benefits-of-character-set-portability.md)

- [ワイド文字引数をプログラムに渡すためにの wmain を使用します。](../text/support-for-using-wmain.md)

- [Unicode プログラミングの概要を参照してください。](../text/unicode-programming-summary.md)

- [バイト幅の移植性に対する汎用テキスト マッピングについて説明します](../text/generic-text-mappings-in-tchar-h.md)

## <a name="see-also"></a>関連項目

[テキストと文字列](../text/text-and-strings-in-visual-cpp.md)<br/>
[wmain の使用](../text/support-for-using-wmain.md)