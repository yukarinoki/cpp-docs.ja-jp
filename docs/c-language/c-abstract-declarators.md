---
title: C 抽象宣言子
ms.date: 11/04/2016
helpviewer_keywords:
- declarators, abstract
- abstract declarations
ms.assetid: 6a556ad7-0555-421a-aa02-294d77cda8b5
ms.openlocfilehash: 196eb39d901b38ab7b005b03a933827ec4288218
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335059"
---
# <a name="c-abstract-declarators"></a>C 抽象宣言子

抽象宣言子は、1 つ以上のポインター、配列、または関数修飾子で構成される、識別子のない宣言子です。 ポインター修飾子 (<strong>\*</strong>) は、宣言子の識別子の前に常に置きます。配列 (**[ ] )** および関数 ( ( **)** ) 修飾子は識別子に従います。 これがわかっていれば、抽象宣言子内のどこに識別子があると想定されているかを判断し、それに従って宣言子を解釈できます。 複雑な宣言子の詳細と例については「[さらに複雑な宣言子の解釈](../c-language/interpreting-more-complex-declarators.md)」を参照してください。 通常は、`typedef` を使用して宣言子を簡素化できます。 「[typedef 宣言](../c-language/typedef-declarations.md)」を参照してください。

抽象宣言子は複雑になる場合があります。 複雑な抽象宣言子内のかっこは、宣言内の複雑な宣言子の場合と同様に、特定の解釈を指定します。

以下の各例に、抽象宣言子を示します。

```
int *         // The type name for a pointer to type int:

int *[3]      // An array of three pointers to int

int (*) [5]   // A pointer to an array of five int

int *()       // A function with no parameter specification
              // returning a pointer to int

// A pointer to a function taking no arguments and
// returning an int

int (*) ( void )

// An array of an unspecified number of constant pointers to
// functions each with one parameter that has type unsigned int
// and an unspecified number of other parameters returning an int

int (*const []) ( unsigned int, ... )
```

> [!NOTE]
> 1 組の空のかっこで構成される抽象宣言子 **( )** は、あいまいであるため、使用できません。 暗黙的な識別子がかっこ内にある (この場合は修飾されていない型になる) のか、かっこの前にある (この場合は関数型になる) のか、判断することはできません。

## <a name="see-also"></a>関連項目

[宣言子と変数宣言](../c-language/declarators-and-variable-declarations.md)
