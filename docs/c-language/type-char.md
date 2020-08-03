---
title: char 型
ms.date: 11/04/2016
helpviewer_keywords:
- type char
- unsigned char keyword [C]
- char keyword [C]
ms.assetid: a5da0866-e780-4793-be87-15a8426e7ea0
ms.openlocfilehash: 5b60af4becb3fa496a0b54c3702eac247bd75d5e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231443"
---
# <a name="type-char"></a>char 型

**`char`** 型は、表現できる文字セットのメンバーの整数値を格納するために使用されます。 この整数値は、特定の文字に対応する ASCII コードです。

**Microsoft 固有の仕様**

**`unsigned char`** 型の文字値の範囲は、16 進数で 0 から 0xFF までです。 **`signed char`** の範囲は 0x80 から 0x7F までです。 これらの範囲は、0 から 255 の 10 進数と -128 から +127 の 10 進数にそれぞれ変換されます。 /J コンパイラ オプションを使用すると、既定値が **`signed`** から **`unsigned`** に変更されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[基本型の格納](../c-language/storage-of-basic-types.md)
