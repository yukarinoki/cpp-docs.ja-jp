---
description: '詳細情報: 文字列リテラルの格納'
title: 文字列リテラルの格納
ms.date: 11/04/2016
helpviewer_keywords:
- string literals, storage
ms.assetid: ba5e4d2c-d456-44b3-a8ca-354af547ac50
ms.openlocfilehash: 5139d480af6b808b5b2e008500794d95d63a9980
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205266"
---
# <a name="storage-of-string-literals"></a>文字列リテラルの格納

リテラル文字列の各文字は、連続するメモリ位置に順番に格納されます。 文字列リテラル内のエスケープ シーケンス ( **\\\\** や **\\"** など) は、それぞれ 1 文字としてカウントされます。 ( **\0** エスケープ シーケンスによって表される) null 文字は各文字列リテラルに自動的に追加され、その最後を示します (これは[変換フェーズ](../preprocessor/phases-of-translation.md) 7 で発生します)。2 つの同じ文字列が別々のアドレスに保存されない場合があることに注意してください。 [/GF](../build/reference/gf-eliminate-duplicate-strings.md) を指定すると、同じ文字列が複数ある場合に、その 1 つだけが実行可能ファイルに追加されます。

## <a name="remarks"></a>Remarks

**Microsoft 固有の仕様**

文字列には、静的ストレージ存続期間があります。 ストレージ存続期間については、「[ストレージ クラス](../c-language/c-storage-classes.md)」をご覧ください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[C 文字列リテラル](../c-language/c-string-literals.md)
