---
title: コンパイラ エラー C3764 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3764
dev_langs:
- C++
helpviewer_keywords:
- C3764
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c214fcf40f442c35d754db64c8443c328d50ae10
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273629"
---
# <a name="compiler-error-c3764"></a>コンパイラ エラー C3764
'override_function': 基底クラス メソッド 'base_class_function' をオーバーライドすることはできません  
  
 正しくない形式の上書きが検出されました。 たとえば、基底クラス関数が`virtual`です。 詳細については、次を参照してください。[オーバーライド](../../windows/override-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3764 を生成します。  
  
```  
// C3764.cpp  
// compile with: /clr /c  
public ref struct A {  
   void g(int);  
   virtual void h(int);  
};  
  
public ref struct B : A {  
   virtual void g(int) override {}   // C3764  
   virtual void h(int) override {}   // OK  
};  
```  
  
## <a name="example"></a>例  
 C3764 は基底クラスのメソッドは、両方を明示的にはときも発生し、名前付きオーバーライドします。 次の例では、C3764 を生成します。  
  
```  
// C3764_b.cpp  
// compile with: /clr /c  
ref struct A {  
   virtual void Test() {}  
};  
  
ref struct B : public A {  
   virtual void Test() override {}  
   virtual void Test2() = A::Test {}   // C3764  
};  
```