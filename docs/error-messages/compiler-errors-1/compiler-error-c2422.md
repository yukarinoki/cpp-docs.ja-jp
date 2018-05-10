---
title: コンパイラ エラー C2422 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2422
dev_langs:
- C++
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 89a808e4b324b11c88be38ae7d8815bee4e232cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2422"></a>コンパイラ エラー C2422
'のオペランド' で誤ったセグメント オーバーライド  
  
 インライン アセンブラー コードで、オペランドに対してセグメント オーバーライド演算子 (:)  以下の原因が考えられます。  
  
-   演算子の直前のレジスタは、セグメント レジスタではありません。  
  
-   演算子の直前のレジスタは、オペランド内の唯一のセグメント レジスタではありません。  
  
-   間接演算子 (かっこ) 内のセグメント オーバーライド演算子が表示されます。  
  
-   セグメント オーバーライド演算子の後の式は、イミディ エイトのオペランドまたはメモリ オペランドではありません。  
  
 次の例では、C2422 が生成されます。  
  
```  
// C2422.cpp  
// processor: x86  
int main() {  
   _asm {  
      mov AX, [BX:ES]   // C2422  
      mov AX, ES   // OK  
   }  
}  
```