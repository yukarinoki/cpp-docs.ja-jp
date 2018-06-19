---
title: _ _Asm ブロック内の演算子を使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- brackets [ ]
- brackets [ ], __asm blocks
- __asm keyword [C++], operators
- square brackets [ ], __asm blocks
- operators [C++], using in __asm blocks
- square brackets [ ]
ms.assetid: a26ccfd4-40ae-4a61-952f-c417982aa8dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2e1c7c4b8415655aff36327db9c6a9f866d82683
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32051131"
---
# <a name="using-operators-in-asm-blocks"></a>__asm ブロックでの演算子の使用
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 `__asm`ブロックがなど C または C++ の特定の演算子を使用することはできません、 **<<** 演算子。 ただし、演算子とで共有される C MASM、ように、\*演算子は、アセンブリ言語の演算子として解釈されます。 たとえば、外部、`__asm`ブロック、角かっこ (**[]**) C は、配列内の要素のサイズを自動的にスケーリング配列の添字を囲むとして解釈されます。 内部、`__asm`ブロック、任意のデータ オブジェクトまたはラベル (配列だけでなく) から、スケールなしのバイト オフセットを生成、MASM インデックス演算子見なされます。 次のコードは、違いを示しています。  
  
```  
int array[10];  
  
__asm mov array[6], bx ;  Store BX at array+6 (not scaled)  
  
array[6] = 0;         /* Store 0 at array+24 (scaled) */  
```  
  
 最初に参照`array`拡大縮小されませんが、2 つ目はします。 使用できるに注意してください、**型**定数に基づいてスケーリングを実現するために演算子。 たとえば、次のステートメントは同等です。  
  
```  
__asm mov array[6 * TYPE int], 0 ; Store 0 at array + 24  
  
array[6] = 0;                   /* Store 0 at array + 24 */  
```  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__asm ブロックでの C または C++ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)