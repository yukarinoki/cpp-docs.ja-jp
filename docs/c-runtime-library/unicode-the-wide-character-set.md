---
title: 'Unicode: ワイド文字セット | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.international
dev_langs:
- C++
helpviewer_keywords:
- Unicode [C++], wide character set
- wide characters [C++], Unicode
ms.assetid: b6a05a21-59a5-4d30-8c85-2dbe185f7a74
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4fcd1c874c1701f471026deec73ab596971d3ad4
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2018
---
# <a name="unicode-the-wide-character-set"></a>Unicode: ワイド文字セット

ワイド文字は、2 バイトの多言語文字コードです。 現代のコンピューティングにおいて世界中で使用されているすべての文字は、技術的な記号や特殊な出版用の文字も含め、ワイド文字としての Unicode 仕様に従って表現できます。 Microsoft も参加している巨大なコンソーシアムによって開発され管理されている Unicode 標準は、今や広く受け入れられています。

ワイド文字は **wchar_t** 型です。 ワイド文字列は **wchar_t[]** 配列として表現され、`wchar_t*` ポインターで指し示されます。 すべての ASCII 文字は、先頭に文字 **L** を付けることで、ワイド文字として表現できます。 たとえば、L'\0' はワイド文字 (16 ビット) の終端の null 文字です。 同様に、すべての ASCII 文字列リテラルは、ASCII リテラルの先頭に文字 L を付ける (L"Hello") だけで、ワイド文字列リテラルとして表現できます。

通常、ワイド文字はマルチバイト文字よりもメモリ内の領域を多く必要としますが、処理は速くなります。 また、マルチバイト エンコードで一度に表現できるロケールは 1 つのみですが、Unicode 表現では世界中のすべての文字セットを同時に表現できます。

## <a name="see-also"></a>参照

[国際化](../c-runtime-library/internationalization.md)<br/>
[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)<br/>
