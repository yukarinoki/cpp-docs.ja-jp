---
title: 'Unicode: ワイド文字セット'
description: Microsoft C ランタイムでの Unicode ワイド文字セットの概要。
ms.topic: conceptual
ms.date: 11/04/2016
helpviewer_keywords:
- Unicode [C++], wide character set
- wide characters [C++], Unicode
ms.assetid: b6a05a21-59a5-4d30-8c85-2dbe185f7a74
ms.openlocfilehash: 7cd170ae43223f1e8e61d9fc576e49baa2164b23
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765331"
---
# <a name="unicode-the-wide-character-set"></a>Unicode: ワイド文字セット

ワイド文字は、2 バイトの多言語文字コードです。 現代のコンピューティングにおいて世界中で使用されているすべての文字は、技術的な記号や特殊な出版用の文字も含め、ワイド文字としての Unicode 仕様に従って表現できます。 Microsoft も参加している巨大なコンソーシアムによって開発され管理されている Unicode 標準は、今や広く受け入れられています。

ワイド文字の型は **`wchar_t`** です。 ワイド文字列は、配列として表現され **`wchar_t[]`** ます。 ポインターを使用して、配列をポイントし `wchar_t*` ます。

文字の前にプレフィックスを付けることで、任意の ASCII 文字をワイド文字として表すことができ `L` ます。 たとえば、 `L'\0'` は、全角 (16 ビット) の終端の null 文字です。

文字をプレフィックスとして使用すると、ASCII 文字列リテラルをワイド文字列リテラルとして表すことができ `L` ます。 たとえば、`L"Hello"` のようにします。

一般に、ワイド文字では、マルチバイト文字よりもメモリ内の領域が多く使用されます。 しかし、ワイド文字は処理が速くなります。 マルチバイトエンコードで一度に表現できるロケールは1つだけです。 世界中のすべての文字セットは、Unicode 表現によって同時に表現されます。

## <a name="see-also"></a>関連項目

[プロパティー](../c-runtime-library/internationalization.md)\
[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)
