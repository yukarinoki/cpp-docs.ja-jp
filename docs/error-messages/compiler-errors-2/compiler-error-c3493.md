---
title: コンパイラ エラー C3493 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3493
dev_langs:
- C++
helpviewer_keywords:
- C3493
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3aec62bfff59396ec73141746193e4e3f16d84fa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33257317"
---
# <a name="compiler-error-c3493"></a>コンパイラ エラー C3493
既定のキャプチャ モードが指定されていないため、'var' を暗黙的にキャプチャできません  
  
 空のラムダ式のキャプチャである `[]`は、ラムダ式が明示的にも暗黙的にも変数をキャプチャしないことを指定します。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   既定のキャプチャ モードを指定するか、または  
  
-   1 つ以上の変数を明示的にキャプチャします。  
  
## <a name="example"></a>例  
 次の例では、外部変数を変更しているが、空のキャプチャ句を指定していないため、C3493 が生成されます。  
  
```  
// C3493a.cpp  
  
int main()  
{  
   int m = 55;  
   [](int n) { m = n; }(99); // C3493  
}  
```  
  
## <a name="example"></a>例  
 次の例では、既定のキャプチャ モードとして参照渡しを指定することによって C3493 を解決しています。  
  
```  
// C3493b.cpp  
  
int main()  
{  
   int m = 55;  
   [&](int n) { m = n; }(99);  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)