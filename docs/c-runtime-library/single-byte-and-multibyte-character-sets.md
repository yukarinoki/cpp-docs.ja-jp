---
title: 1 バイト文字セットとマルチバイト文字セット
description: Microsoft ランタイムライブラリの1バイト文字セットとマルチバイト文字セットの概要を説明します。
ms.topic: conceptual
ms.date: 11/04/2016
helpviewer_keywords:
- SBCS (single byte character set)
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- character sets [C++], single byte
ms.assetid: 2cbc78ea-33c0-4cfb-b0df-7ce2458431ce
ms.openlocfilehash: 6668285915ab9f1939c1baf8a2d3da2d00543528
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "91590174"
---
# <a name="single-byte-and-multibyte-character-sets"></a>1 バイト文字セットとマルチバイト文字セット

ASCII 文字セットでは、0x00 から 0x7F までの範囲の文字を定義しています。 そのほかに、ASCII 文字セットと同じ 0x00 から 0x7F までの範囲の文字に加え、0x80 から 0xFF までの拡張文字セットも定義している、主にヨーロッパ向けのさまざまな文字セットがあります。  ASCII 文字セットだけでなく、多くのヨーロッパ言語の文字セットを表すには、8ビットの1バイト文字セット (SBCS) で十分です。 ただし、日本語の漢字など、ヨーロッパ以外の文字セットには、1バイトのコード体系で表現できる文字数よりも多くの文字が含まれているため、マルチバイト文字セット (MBCS) エンコーディングが必要になります。

> [!NOTE]
> Microsoft ランタイム ライブラリの多くの SBCS ルーチンでマルチバイト、文字、文字列が必要に応じて処理されます。 多くのマルチバイト文字セットでは、ASCII 文字セットをサブセットとして定義しています。 多くのマルチバイト文字セットでは、0x00 から 0x7F の範囲内の各文字が、ASCII 文字セットで同じ値を持つ文字と一致します。 たとえば、ASCII 文字列でも MBCS 文字列でも、1 バイトの null 文字 (\0) の値は 0x00 で、終端の null 文字を意味します。

マルチバイト文字セットは、1バイト文字と2バイト文字の両方で構成されます。 マルチバイト文字の文字列には、1バイト文字と2バイト文字の組み合わせを含めることができます。 2 バイト文字には、先行バイトと後続バイトがあります。 特殊なマルチバイト文字セットでは、先行バイトが後続バイトと同じ範囲の値を持っている場合があります。 これらの範囲が重複している場合は、指定されたバイトが先行バイトまたは後続バイトとして機能しているかどうかを判断するために、コンテキストの評価が必要になることがあります。

## <a name="see-also"></a>関連項目

[国際化](../c-runtime-library/internationalization.md)<br/>
[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)<br/>
