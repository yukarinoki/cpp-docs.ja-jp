---
title: コンパイラ エラー C3485 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3485
dev_langs:
- C++
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4cd9de6f300fed673d588df60d7acca15b104b61
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3485"></a>コンパイラ エラー C3485
ラムダ定義に cv 修飾子は使用できません  
  
 ラムダ式の定義の一部として `const` 修飾子または `volatile` 修飾子を使用することはできません。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   ラムダ式の定義から `const` 修飾子または `volatile` 修飾子を削除します。  
  
## <a name="example"></a>例  
 次の例では、ラムダ式の定義の一部として `const` 修飾子を使用しているため、C3485 が生成されます。  
  
```  
// C3485.cpp  
  
int main()  
{  
   auto x = []() const mutable {}; // C3485  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)