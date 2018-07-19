---
title: コンパイラの警告 (レベル 3) C4316 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4316
dev_langs:
- C++
helpviewer_keywords:
- C4316
ms.assetid: 10371f01-aeb8-40ac-a290-59e63efa5ad4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 609f3bbe9f338c5d53491190512ce2b9c290cdb8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298383"
---
# <a name="compiler-warning-level-3-c4316"></a>コンパイラの警告 (レベル 3) C4316
ヒープで割り当てられているオブジェクトが、この型にアラインされていない可能性があります。  
  
 `operator new` を使用して割り当てられたオブジェクトがオーバーアラインされている場合は、このオブジェクトにアラインメントが指定されていない可能性があります。 オーバーライド[new 演算子](../../c-runtime-library/operator-new-crt.md)と[演算子 delete](../../c-runtime-library/operator-delete-crt.md)の配置された割り当てルーチンを使用するように、型をオーバーアラインメント — たとえば、 [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md)と[_aligned_free](../../c-runtime-library/reference/aligned-free.md)です。 次の例では、C4316 が生成されます。  
  
```cpp  
// C4316.cpp  
// Test: cl /W3 /c C4316.cpp  
  
__declspec(align(32)) struct S {}; // C4324  
  
int main() {  
    new S; // C4316  
}  
```