---
title: コンパイラの警告 (レベル 1) C4488 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4488
dev_langs:
- C++
helpviewer_keywords:
- C4488
ms.assetid: 55625e46-ddb5-4c7c-99c7-cd4aa9f879bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a3c5fc64637d989066acfa90715c50504664231
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4488"></a>コンパイラの警告 (レベル 1) C4488
'function': インターフェイス メソッド 'interface_method' を実装する 'keyword' キーワードが必要です  
  
 クラスは、その直接の継承元インターフェイスのすべてのメンバーを実装する必要があります。 実装されるメンバーは、パブリック アクセシビリティが必要し、virtual に指定する必要があります。  
  
## <a name="example"></a>例  
 C4488 は実装されているメンバーがパブリックでない場合に発生します。 次の例では、C4488 を生成します。  
  
```  
// C4488.cpp  
// compile with: /clr /c /W1 /WX  
interface struct MyI {  
   void f1();  
};  
  
// implemented member not public  
ref class B : MyI { virtual void f1() {} };  // C4488  
  
// OK  
ref class C : MyI {  
public:  
   virtual void f1() {}  
};  
```  
  
## <a name="example"></a>例  
 C4488 は、実装されるメンバーが仮想にマークされていない場合に発生することができます。 次の例では、C4488 を生成します。  
  
```  
// C4488_b.cpp  
// compile with: /clr /c /W1 /WX  
interface struct MyI {  
   void f1();  
};  
  
ref struct B : MyI { void f1() {} };   // C4488  
ref struct C : MyI { virtual void f1() {} };   // OK  
```