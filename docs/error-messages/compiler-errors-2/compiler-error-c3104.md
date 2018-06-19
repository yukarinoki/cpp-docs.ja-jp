---
title: コンパイラ エラー C3104 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3104
dev_langs:
- C++
helpviewer_keywords:
- C3104
ms.assetid: b5648d47-e5d3-4b45-a3c0-f46e04eae731
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ded5185e3f87ce7f1b5a4a7015ce3c4476c949b5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246468"
---
# <a name="compiler-error-c3104"></a>コンパイラ エラー C3104
無効な属性引数  
  
 属性に無効な引数を指定したとします。  
  
 参照してください[属性パラメーター型](../../windows/attribute-parameter-types-cpp-component-extensions.md)詳細についてはします。  
  
 このエラーは、Visual C 2005 で行ったコンパイラ準拠作業の結果として生成されることができます。 カスタム属性をマネージ配列を渡すときに、配列の型は、集約の初期化リストからは推測不要になった。 今すぐ、コンパイラでは初期化子リストと同様に、配列の型を指定する必要があります。  
  
## <a name="example"></a>例  
 次の例では、C3104 を生成します。  
  
```  
// C3104a.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::Class)]  
public ref struct ABC : public Attribute {  
   ABC(array<int>^){}  
   array<double> ^ param;  
};  
  
[ABC( {1,2,3}, param = {2.71, 3.14})]   // C3104  
// try the following line instead  
// [ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]   
ref struct AStruct{};  
```  
  
## <a name="example"></a>例  
 次の例では、C3104 を生成します。  
  
```  
// C3104b.cpp  
// compile with: /clr /c  
// C3104 expected  
using namespace System;  
  
int func() {  
   return 0;   
}  
  
[attribute(All)]  
ref class A {  
public:   
   A(int) {}  
};  
  
// Delete the following 2 lines to resolve.  
[A(func())]  
ref class B {};  
  
// OK  
[A(0)]  
ref class B {};  
```  
