---
title: コンパイラ エラー C2472 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2472
dev_langs:
- C++
helpviewer_keywords:
- C2472
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d89a6d6b10fa76c7fbf1bf11c4ebe2ecff5f98ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2472"></a>コンパイラ エラー C2472
'function' を 'message' マネージ コードで生成できません。混合イメージを生成するには、/clr と共にコンパイルしてください  
  
 このエラーは、純粋な共通言語ランタイム (CLR) の環境内で、マネージ コードでサポートされていない型を使用すると発生します。 エラーを解決するには、 **/clr** を使用してコンパイルします。  
  
 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で非推奨とされています。  
  
## <a name="example"></a>例  
 次の例では警告 C2472 が生成されます。  
  
```  
// C2472.cpp  
// compile with: /clr:pure  
// C2472 expected  
  
#include <cstdlib>  
  
int main()  
{  
   int * __ptr32 p32;  
   int * __ptr64 p64;  
  
   p32 = (int * __ptr32)malloc(4);  
   p64 = p32;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)