---
title: new (新規のスロット vtable) (C++ コンポーネント拡張) |Microsoft Docs
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
ms.openlocfilehash: 7ef754c380353716c923f6d5f404106cebc163c9
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011882"
---
# <a name="new-new-slot-in-vtable--c-component-extensions"></a>new (vtable の新しいスロット) (C++ コンポーネント拡張)
**新しい**キーワードは、仮想メンバーが vtable の新しいスロットを取得することを示します。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
 (この言語機能にはランタイムに適用される特記事項がありません。)  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 Windows ランタイムでサポートされていません。  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
### <a name="remarks"></a>Remarks  
  
 `/clr`コンパイル、**新しい**仮想メンバーが vtable の新しいスロットを取得するは、関数が基底クラスのメソッドをオーバーライドしていないことを示します。  
  
 **新しい**により、関数の IL に追加する newslot 修飾子。  newslot の詳細については、次のトピックを参照してください。  
  
-   [MethodInfo.GetBaseDefinition メソッド](https://msdn.microsoft.com/library/system.reflection.methodinfo.getbasedefinition.aspx)  
  
-   [MethodAttributes 列挙体](https://msdn.microsoft.com/library/system.reflection.methodattributes.aspx)  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: `/clr`  
  
### <a name="examples"></a>使用例  
  
 次の例は、の効果を示しています。**新しい**します。  
  
```cpp  
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
  
```Output  
C::f() called  
  
D::f() called  
  
D::g() called  
  
D::g() called  
  
E::f() called  
```  
  
## <a name="see-also"></a>関連項目  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)   
 [オーバーライド指定子](../windows/override-specifiers-cpp-component-extensions.md)