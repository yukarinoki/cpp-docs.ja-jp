---
title: コンパイラの警告 (レベル 1) C4946 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4946
dev_langs:
- C++
helpviewer_keywords:
- C4946
ms.assetid: b85cbef0-e053-4de6-9b14-7b0f82d40495
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 072e43f4750d2f64fb0f9dc56478a68699b98c9e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4946"></a>コンパイラの警告 (レベル 1) C4946
reinterpret_cast が関連クラスの間で使用されました : 'class1' と 'class2'  
  
 使用しないでください[reinterpret_cast](../../cpp/reinterpret-cast-operator.md)に関連する型の間でキャストします。 使用して[static_cast](../../cpp/static-cast-operator.md) 、ポリモーフィックな型は、代わりを使用して[dynamic_cast](../../cpp/dynamic-cast-operator.md)です。  
  
 既定では、この警告は off です。 詳細については、「 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。  
  
 次のコード例では、C4946 が生成されます。  
  
```  
// C4946.cpp  
// compile with: /W1  
#pragma warning (default : 4946)  
class a {  
public:  
   a() : m(0) {}  
   int m;  
};  
  
class b : public virtual a {  
};  
  
class b2 : public virtual a {  
};  
  
class c : public b, public b2 {  
};  
  
int main() {  
   c* pC = new c;  
   a* pA = reinterpret_cast<a*>(pC);   // C4946  
   // try the following line instead  
   // a* pA = static_cast<a*>(pC);  
}  
```