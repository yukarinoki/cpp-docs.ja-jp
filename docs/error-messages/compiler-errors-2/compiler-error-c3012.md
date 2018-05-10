---
title: コンパイラ エラー C3012 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3012
dev_langs:
- C++
helpviewer_keywords:
- C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d30a7fbb50a984c8cec6b45a0ab4759a0578de7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3012"></a>コンパイラ エラー C3012
  
> '*組み込み*': 組み込み関数は、並行領域内で直接使用できません  
  
 A[コンパイラ組み込み関数](../../intrinsics/compiler-intrinsics.md)で関数が許可されていません、`omp parallel`領域。 この問題を解決するには、地域からの組み込みを移動または組み込みで非対応に置き換えます。   
  
## <a name="example"></a>例  
  
 次の例では、C3012 を生成し、その修正方法を示しています。  
  
```cpp  
// C3012.cpp  
// compile with: /openmp  
#ifdef __cplusplus  
extern "C" {  
#endif  
void* _ReturnAddress();  
#ifdef __cplusplus  
}  
#endif  
  
int main()  
{  
   #pragma omp parallel  
   {  
      _ReturnAddress();   // C3012  
   }  
   _ReturnAddress();      // OK  
}  
```