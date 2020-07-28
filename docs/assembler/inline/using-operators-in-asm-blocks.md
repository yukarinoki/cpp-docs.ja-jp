---
title: __asm ブロックでの演算子の使用
ms.date: 08/30/2018
helpviewer_keywords:
- brackets [ ]
- brackets [ ], __asm blocks
- __asm keyword [C++], operators
- square brackets [ ], __asm blocks
- operators [C++], using in __asm blocks
- square brackets [ ]
ms.assetid: a26ccfd4-40ae-4a61-952f-c417982aa8dd
ms.openlocfilehash: cdcfee20cfdc5a6dc315d00ef024d1616900a2e8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87191106"
---
# <a name="using-operators-in-__asm-blocks"></a>__asm ブロックでの演算子の使用

**Microsoft 固有の仕様**

ブロックは、 **`__asm`** 演算子など、C または C++ の特定の演算子を使用できません **<<** 。 ただし、演算子など、C および MASM によって共有 \* される演算子は、アセンブリ言語の演算子として解釈されます。 たとえば、ブロックの外側で **`__asm`** は、角かっこ (**[]**) は、配列の要素のサイズに自動的にスケーリングする配列の添字として解釈されます。 ブロック内で **`__asm`** は、これらは MASM の index 演算子として表示されます。これにより、(配列だけでなく) 任意のデータオブジェクトまたはラベルからのバイトオフセットがスケーリングされません。 次のコードはその違いを示しています。

```cpp
int array[10];

__asm mov array[6], bx ;  Store BX at array+6 (not scaled)

array[6] = 0;         /* Store 0 at array+24 (scaled) */
```

への最初の参照 `array` はスケーリングされませんが、2番目の参照はになります。 **型**演算子を使用すると、定数に基づいてスケーリングを実現できます。 たとえば、次のステートメントは互いに対応しています。

```cpp
__asm mov array[6 * TYPE int], 0 ; Store 0 at array + 24

array[6] = 0;                   /* Store 0 at array + 24 */
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__Asm ブロックでの C または C++ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>
