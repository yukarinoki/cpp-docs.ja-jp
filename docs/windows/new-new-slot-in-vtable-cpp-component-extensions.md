---
title: 新しい (新しい vtable のスロット) (C++ コンポーネント拡張) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 1a9a5704-f02f-46ae-ad65-f0f2b6dbabc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7189909f3cff84d2bb1a767e4ddeda817bcd6128
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879784"
---
# <a name="new-new-slot-in-vtable--c-component-extensions"></a>new (vtable の新しいスロット) (C++ コンポーネント拡張)
`new` キーワードは、仮想メンバーが vtable の新しいスロットを取得することを示します。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
 (この言語機能にはランタイムに適用される特記事項がありません。)  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 Windows ランタイムでサポートされていません。  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
 **解説**  
  
 **/Clr**コンパイル、`new`仮想メンバーが vtable の新しいスロットを取得する以外の場合は、関数が基底クラスのメソッドをオーバーライドしていないことを示します。  
  
 `new` を指定すると、関数の IL に newslot 修飾子が追加されます。  newslot の詳細については、次のトピックを参照してください。  
  
-   [MethodInfo.GetBaseDefinition メソッド](https://msdn.microsoft.com/en-us/library/system.reflection.methodinfo.getbasedefinition.aspx)  
  
-   [MethodAttributes 列挙体](https://msdn.microsoft.com/en-us/library/system.reflection.methodattributes.aspx)  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/clr**  
  
### <a name="examples"></a>使用例  
 **例**  
  
 `new` の効果の例を次に示します。  
  
```  
// newslot.cpp  
// compile with: /clr  
ref class C {  
public:  
   virtual void f() {  
      System::Console::WriteLine("C::f() called");  
   }  
  
   virtual void g() {  
      System::Console::WriteLine("C::g() called");  
   }  
};  
  
ref class D : public C {  
public:  
   virtual void f() new {  
      System::Console::WriteLine("D::f() called");  
   }  
  
   virtual void g() override {  
      System::Console::WriteLine("D::g() called");  
   }  
};  
  
ref class E : public D {  
public:  
   virtual void f() override {  
      System::Console::WriteLine("E::f() called");  
   }  
};  
  
int main() {  
   D^ d = gcnew D;  
   C^ c = gcnew D;  
  
   c->f();   // calls C::f  
   d->f();   // calls D::f  
  
   c->g();   // calls D::g  
   d->g();   // calls D::g  
  
   D ^ e = gcnew E;  
   e->f();   // calls E::f  
}  
```  
  
 **出力**  
  
```Output  
C::f() called  
  
D::f() called  
  
D::g() called  
  
D::g() called  
  
E::f() called  
```  
  
## <a name="see-also"></a>関連項目  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)   
 [オーバーライド指定子](../windows/override-specifiers-cpp-component-extensions.md)