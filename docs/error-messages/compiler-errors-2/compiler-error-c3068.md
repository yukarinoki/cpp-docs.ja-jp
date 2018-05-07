---
title: コンパイラ エラー C3068 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3068
dev_langs:
- C++
helpviewer_keywords:
- C3068
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f378a60c79defed4fb1738515ca5b65b2851056
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3068"></a>コンパイラ エラー C3068
'function': 'naked' 関数が C++ 例外が発生した場合に、アンワインディングを必要とするオブジェクトを含めることはできません  
  
 コンパイラでのスタックがアンワインドを実行できなかった、 [naked](../../cpp/naked-cpp.md)を一時オブジェクトは、関数と C++ 例外処理で作成されたために、例外をスローした関数 ([/EHsc](../../build/reference/eh-exception-handling-model.md)) が指定されました。  
  
 このエラーを解決するには、次の少なくとも 1 つの操作を行います。  
  
-   /EHsc をコンパイルしません。  
  
-   関数としてのマークを付けないでください`naked`です。  
  
-   関数では、一時オブジェクトを作成できません。  
  
 関数は、関数は、例外をスローし、C++ 例外処理が有効になっている場合、スタックで、一時オブジェクトを作成する場合は、例外がスローされた場合、スタックをコンパイラがクリーンアップされます。  
  
 例外がスローされます、コンパイラで生成されたコード、プロローグと呼ばれるエピローグとするが、naked 関数でなくては、関数に対して実行されます。  
  
## <a name="example"></a>例  
 次の例では、C3068 が生成されます。  
  
```  
// C3068.cpp  
// compile with: /EHsc  
// processor: x86  
class A {  
public:  
   A(){}  
   ~A(){}  
};  
  
void b(A){}  
  
__declspec(naked) void c() {  
   b(A());   // C3068   
};  
```