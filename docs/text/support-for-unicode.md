---
title: Unicode のサポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 1/09/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- globalization [C++], character sets
- portable data types [MFC]
- Unicode [C++]
- wide characters [C++], about wide characters
- character sets [C++], Unicode
- localization [C++], character sets
- Unicode [C++], installing support
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b9d5a435339e366d70749d64e5aae9264fe12b1f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858407"
---
# <a name="support-for-unicode"></a>Unicode のサポート

Unicode は、1 バイト (つまり、それらのほとんどでは表現できないものも含めて、すべての文字セットをサポートするための仕様です。 いずれかの Unicode を使用することをお勧め国際市場向けプログラミングしている場合、または[マルチバイト文字セット](../text/support-for-multibyte-character-sets-mbcss.md)(MBCS)、またはそれをビルドするには、スイッチを変更することでいずれかのように、プログラムをコードします。

ワイド文字は、2 バイトの多言語文字コードです。 全体の 1 つとしての Unicode 仕様に従って表現できる万文字、技術的な記号や発行の特殊文字を含むほぼすべての文字現代のコンピューティングが、世界中で使用される文字をエンコードしてutf-16 を使用します。 Unicode サロゲート ペアの機能を使用して Unicode のペアで 1 つのワイド文字では表現できない文字を表すことができます。 一般的な用途のほとんどすべての文字は、1 つの 16 ビットのワイド文字の utf-16 で表される、ためには、国際文字セットを使用したプログラミングのワイド文字を使用して簡略化します。 使用して UTF 16LE (リトル エンディアン) でエンコードされたワイド文字とは、Windows のネイティブ文字形式です。

ワイド文字列は `wchar_t[]` 配列として表現され、`wchar_t*` ポインターで指し示されます。 ASCII 文字は、先頭に文字 L を付けることで、ワイド文字として表現できます。 たとえば、L'\0' はワイド文字 (16 ビット) の終端の **NULL** 文字です。 同様に、ASCII 文字列リテラルは、ASCII リテラルの先頭に文字 L を付けることで、ワイド文字列リテラルとして表現できます (L"Hello")。

通常、ワイド文字はマルチバイト文字よりもメモリ内の領域を多く必要としますが、処理は速くなります。 さらに、1 つだけのロケールは、マルチバイト エンコードで一度に表現できる、世界中のすべての文字セットが、Unicode 表現で同時に表現します。

MFC フレームワークは Unicode に完全に対応しており、MFC では、次の表に示すように、移植性のあるマクロを使用することで Unicode 対応を実現しています。

## <a name="portable-data-types-in-mfc"></a>MFC での移植性のあるデータ型

|移植性のないデータ型|置き換えに使うマクロ|
|-----------------------------|----------------------------|
|`char`, `wchar_t`|`_TCHAR`|
|`char*`、 `LPSTR` (Win32 データ型) `LPWSTR`|`LPTSTR`|
|`const char*`、 `LPCSTR` (Win32 データ型) `LPCWSTR`|`LPCTSTR`|

クラス`CString`使用`_TCHAR`をベースとし、簡単な変換コンス トラクターと演算子を提供します。 Unicode の文字列操作のほとんどは、操作の基本単位が 8 ビット バイトではなく 16 ビット文字であることを除き、Windows の ANSI 文字セットの操作に使用するのと同じロジックを使用して記述できます。 マルチバイト文字セットの操作と異なり、1 つの Unicode 文字を 2 つの個別のバイトのように扱う必要はなく、また、そのような処理は適切ではありません。 ワイド文字のサロゲート ペアで表される単一文字の可能性に対処する必要は、ただし。 一般に、文字列の長さは、文字の数と同じ前提とナローとワイドが含まれているかどうかのコードを書き込みません。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [MFC の Unicode およびマルチバイト文字セット (MBCS) のサポートを使用します。](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)

- [プログラムで Unicode を有効にします。](../text/international-enabling.md)

- [プログラムで Unicode と MBCS の両方を有効にします。](../text/internationalization-strategies.md)

- [Unicode を使用して、国際化プログラムを作成するには](../text/unicode-programming-summary.md)

- [Unicode の利点を説明します](../text/benefits-of-character-set-portability.md)

- [ワイド文字の引数をプログラムに渡すためにの wmain を使用します。](../text/support-for-using-wmain.md)

- [Unicode プログラミングの概要を参照してください。](../text/unicode-programming-summary.md)

- [バイト幅の移植性に対する汎用テキスト マップの詳細します。](../text/generic-text-mappings-in-tchar-h.md)

## <a name="see-also"></a>関連項目

[テキストと文字列](../text/text-and-strings-in-visual-cpp.md)  
[wmain の使用](../text/support-for-using-wmain.md)  
