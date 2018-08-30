---
title: コンパイラの警告 (レベル 1) C4312 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4312
dev_langs:
- C++
helpviewer_keywords:
- C4312
ms.assetid: 541906ed-4f62-4bcb-947f-cf9ae7411bcb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b30d020532935c925b1ecab25d17cd43a7e8663
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205903"
---
# <a name="compiler-warning-level-1-c4312"></a>コンパイラの警告 (レベル 1) C4312
'操作' :  'type1' からより大きいサイズの 'type2' へ変換します。  
  
 この警告は、32 ビット値を 64 ビット ポインター型に割り当てようとしたことを検出します。たとえば、32 ビット `int` または `long` を 64 ビット ポインターにキャストした場合などです。  
  
 この変換は、符号拡張が発生する場合、32 ビットに収まるポインター値であっても安全でないことがあります。 負の 32 ビット整数が 64 ビット ポインター型に割り当てられる場合、符号拡張によって、ポインター値が整数の値とは異なるメモリ アドレスを参照するようになります。  
  
 この警告は、64 ビット コンパイル ターゲットに対してのみ発行されます。 詳細については、次を参照してください。[ポインターの使用規則](/windows/desktop/WinProg64/rules-for-using-pointers)します。  
  
 次のコード例は、64 ビットのターゲットのコンパイル時に C4312 を生成します。  
  
```  
// C4312.cpp  
// compile by using: cl /W1 /LD C4312.cpp  
void* f(int i) {  
   return (void*)i;   // C4312 for 64-bit targets  
}  
  
void* f2(__int64 i) {  
   return (void*)i;   // OK  
}  
```