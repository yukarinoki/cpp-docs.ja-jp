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
ms.openlocfilehash: b6ac9f7174baf1e0ebe41181c6a6f43e7bb3f5d1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169098"
---
# <a name="using-operators-in-__asm-blocks"></a>__asm ブロックでの演算子の使用

**Microsoft 固有の仕様**

`__asm` ブロックは、C またはC++特定の演算子 ( **<<** 演算子など) を使用できません。 ただし、C および MASM によって共有される演算子 (\* 演算子など) は、アセンブリ言語の演算子として解釈されます。 たとえば、`__asm` ブロックの外側では、角かっこ ( **[]** ) は配列添字として解釈され、C は配列内の要素のサイズに自動的にスケーリングします。 `__asm` ブロック内では、MASM の index 演算子として表示されます。これにより、配列だけでなく、任意のデータオブジェクトまたはラベルからのバイトオフセットがスケーリングされません。 次のコードはその違いを示しています。

```cpp
int array[10];

__asm mov array[6], bx ;  Store BX at array+6 (not scaled)

array[6] = 0;         /* Store 0 at array+24 (scaled) */
```

`array` への最初の参照はスケーリングされませんが、2番目の参照はになります。 **型**演算子を使用すると、定数に基づいてスケーリングを実現できます。 たとえば、次のステートメントは互いに対応しています。

```cpp
__asm mov array[6 * TYPE int], 0 ; Store 0 at array + 24

array[6] = 0;                   /* Store 0 at array + 24 */
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[__asm ブロックでの C または C++ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>
