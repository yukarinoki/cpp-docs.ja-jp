---
title: コンパイラ エラー C3899 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3899
dev_langs:
- C++
helpviewer_keywords:
- C3899
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f40f1065514437463be06a89f01e067c4324cd2e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3899"></a>コンパイラ エラー C3899
'var': クラス 'class' の並行領域内で直接 initonly データ メンバーの左辺値の使用が許可されていません  
  
 [Initonly (C + + CLI)](../../dotnet/initonly-cpp-cli.md)内にあるコンス トラクターの部分の内部データ メンバーを初期化することはできません、[並列](../../parallel/openmp/reference/parallel.md)領域。  これは、コンパイラがそのコードの内部に従った再配置、コンス トラクターの一部では実質的に不要になったことなどです。  
  
 を解決するのには、initonly データ メンバーが、そのコンス トラクターが、並列領域の外を初期化します。  
  
## <a name="example"></a>例  
 次の例では、C3899 を生成します。  
  
```  
// C3899.cpp  
// compile with: /clr /openmp  
#include <omp.h>   
  
public ref struct R {  
   initonly int x;  
   R() {  
      x = omp_get_thread_num() + 1000;   // OK  
      #pragma omp parallel num_threads(5)  
      {  
         // cannot assign to 'x' here  
         x = omp_get_thread_num() + 1000;   // C3899  
         System::Console::WriteLine("thread {0}", omp_get_thread_num());  
      }  
      x = omp_get_thread_num() + 1000;   // OK  
   }  
};  
  
int main() {  
   R^ r = gcnew R;  
   System::Console::WriteLine(r->x);  
}  
```