---
title: '方法: interior_ptr キーワードを含む値の型を宣言 (C + + CLI) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- _ptr keyword
- value types, declaring
ms.assetid: 49eea66e-eeba-49bd-95b0-ba297be436e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6015d5a61589b8ed2d38b6491392fd42e4f38ef1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879478"
---
# <a name="how-to-declare-value-types-with-the-interiorptr-keyword-ccli"></a>方法: interior_ptr キーワードを含む値型を宣言する (C++/CLI)
`interior_ptr`値型で使用できます。  
  
> [!IMPORTANT]
>  この言語機能をサポートに、 **/clr**コンパイラ オプションがなく、 **/ZW**コンパイラ オプション。  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 次の C + + CLI サンプルを使用する方法を示します、`interior_ptr`値型を持つ。  
  
### <a name="code"></a>コード  
  
```  
// interior_ptr_value_types.cpp  
// compile with: /clr  
value struct V {  
   V(int i) : data(i){}  
   int data;  
};  
  
int main() {  
   V v(1);  
   System::Console::WriteLine(v.data);  
  
   // pointing to a value type  
   interior_ptr<V> pv = &v;  
   pv->data = 2;  
  
   System::Console::WriteLine(v.data);  
   System::Console::WriteLine(pv->data);  
  
   // pointing into a value type  
   interior_ptr<int> pi = &v.data;  
   *pi = 3;  
   System::Console::WriteLine(*pi);  
   System::Console::WriteLine(v.data);  
   System::Console::WriteLine(pv->data);  
}  
```  
  
### <a name="output"></a>出力  
  
```  
1  
2  
2  
3  
3  
3  
```  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 値の型で、`this`ポインターが、interior_ptr に評価します。  
  
 値型の非静的メンバー関数の本体で`V`、`this`型の式は、`interior_ptr<V>`値が、関数が呼び出された対象のオブジェクトのアドレス。  
  
### <a name="code"></a>コード  
  
```  
// interior_ptr_value_types_this.cpp  
// compile with: /clr /LD  
value struct V {  
   int data;  
   void f() {  
      interior_ptr<V> pv1 = this;  
      // V* pv2 = this;   error  
   }  
};  
```  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 次の例では、静的メンバーとアドレス演算子を使用する方法を示します。  
  
 Visual C 型の静的メンバーのアドレスは、ネイティブ ポインターを生成します。  静的な値型のメンバーのアドレスは、値型のメンバーがランタイム ヒープに割り当てられているし、ガベージ コレクターが移動できるため、マネージ ポインターです。  
  
### <a name="code"></a>コード  
  
```  
// interior_ptr_value_static.cpp  
// compile with: /clr  
using namespace System;  
value struct V { int i; };  
  
ref struct G {  
   static V v = {22};   
   static int i = 23;   
   static String^ pS = "hello";   
};  
  
int main() {  
   interior_ptr<int> p1 = &G::v.i;  
   Console::WriteLine(*p1);  
  
   interior_ptr<int> p2 = &G::i;  
   Console::WriteLine(*p2);  
  
   interior_ptr<String^> p3 = &G::pS;  
   Console::WriteLine(*p3);  
}  
```  
  
### <a name="output"></a>出力  
  
```  
22  
23  
hello  
```  
  
## <a name="see-also"></a>関連項目  
 [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)