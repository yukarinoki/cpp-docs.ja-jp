---
description: 詳細については、「インラインアセンブリでの型と変数のサイズ」を参照してください。
title: インライン アセンブリでの型と変数サイズ
ms.date: 08/30/2018
ms.topic: reference
helpviewer_keywords:
- variables, length
- size, getting in inline assembly
- size
- LENGTH operator
- TYPE operator
- SIZE operator
- inline assembly, operators
- variables, type
- variables, size
ms.assetid: b62c2f2b-a7ad-4145-bae4-d890db86d348
ms.openlocfilehash: 0d6822537f542c159c40c0ed6f14dca93aa36525
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122019"
---
# <a name="type-and-variable-sizes-in-inline-assembly"></a>インライン アセンブリでの型と変数サイズ

**Microsoft 固有の仕様**

**長さ**、**サイズ**、および **型** の演算子の意味は、インラインアセンブリでは制限されています。 これらを演算子で使用することはできません `DUP` (MASM ディレクティブや演算子を使用してデータを定義することはできません)。 ただし、これらを使用して、C または C++ の変数または型のサイズを調べることができます。

- **LENGTH** 演算子は、配列内の要素の数を返すことができます。 非配列変数の値1が返されます。

- **Size** 演算子は、C または C++ 変数のサイズを返すことができます。 変数のサイズは、その **長さ** と **型** の積です。

- **型** 演算子は、c または C++ の型または変数のサイズを返すことができます。 変数が配列の場合、 **TYPE** は配列の1つの要素のサイズを返します。

たとえば、プログラムに8要素の配列がある場合、 **`int`**

```cpp
int arr[8];
```

次の C およびアセンブリ式は、とその要素のサイズを生成し `arr` ます。

|__asm|C|サイズ|
|-------------|-------|----------|
|**長さ** arr|`sizeof(arr)/sizeof(arr[0])`|8|
|**サイズ** arr|`sizeof(arr)`|32|
|**「** Arr」と入力します。|`sizeof(arr[0])`|4|

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__Asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
