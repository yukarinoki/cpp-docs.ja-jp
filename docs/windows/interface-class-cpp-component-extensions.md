---
title: インターフェイス クラス (C++ コンポーネント拡張) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- interface_CPP
dev_langs:
- C++
helpviewer_keywords:
- interface class keyword
- interface struct keyword
ms.assetid: 3ccea701-f50b-4da7-ad6b-f0ee1203e2b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 74b4ea6b82de65f691d5d0350e161725625e4e1f
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604487"
---
# <a name="interface-class--c-component-extensions"></a>インターフェイス クラス (C++ コンポーネント拡張)
インターフェイスを宣言します。  ネイティブ インターフェイスについては、次を参照してください。 [_ _interface](../cpp/interface.md)します。  
  
## <a name="all-runtimes"></a>すべてのランタイム  

### <a name="syntax"></a>構文  
  
```  
interface_access  
interface class  
 name :  inherit_accessbase_interface{};interface_accessinterface structname :  inherit_accessbase_interface{};  
```  
  
### <a name="parameters"></a>パラメーター  
  
 *interface_access*  
 アセンブリの外部インターフェイスのアクセシビリティ。  指定できる値は**パブリック**と**プライベート**します。  **プライベート**既定値です。 入れ子になったインターフェイスを持つことはできません、 *interface_access*指定子。  
  
 *name*  
 インターフェイスの名前。  
  
 *inherit_access*  
 ユーザー補助*base_interface*します。  許可されるユーザー補助の基底インターフェイスが**パブリック**(既定)。  
  
 *base_interface* (省略可能)  
 インターフェイスの基本インターフェイス*名前*します。  
  
### <a name="remarks"></a>Remarks  
  
 **構造体をインターフェイス**と等価**インターフェイス クラス**します。  
  
 インターフェイスは、関数、イベント、およびプロパティの宣言を含めることができます。  すべてのインターフェイス メンバーは、パブリック アクセシビリティを持ちます。 静的データ メンバー、関数、イベント、およびプロパティが、インターフェイスに含めることもでき、インターフェイスでこれらの静的メンバーを定義する必要があります。  
  
 インターフェイスは、クラスを実装する方法を定義します。 インターフェイスはクラスではないと、クラスは、インターフェイスにのみ実装できます。 クラスは、インターフェイスで宣言された関数を定義、オーバーライドされていない、関数が実装されます。 そのため、名前の参照では、インターフェイス メンバーは含まれません。  
  
 クラスまたは構造体、インターフェイスから派生したインターフェイスのすべてのメンバーを実装する必要があります。 インターフェイスを実装するときに*名前*でインターフェイスを実装することも必要があります、`base_interface`一覧。  
  
 詳細については次を参照してください:  
  
-   [インターフェイス静的コンス トラクター](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md)  
  
-   [ジェネリック インターフェイス (Visual C++)](../windows/generic-interfaces-visual-cpp.md)  
  
 他の CLR 型については、次を参照してください。[クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)します。  
  
 型がインターフェイスの場合、コンパイル時に検出できます`__is_interface_class(type)`します。 詳細については、次を参照してください。[型の特徴のコンパイラ サポート](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)します。  
  
 開発環境で取得できますの F1 ヘルプでこれらのキーワードをキーワードを強調表示 (`interface class`など) f1 キーを押します。  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 **解説**  
  
 (この言語機能には Windows ランタイムのみに適用される特記事項がありません。)  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: `/ZW`  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
 **解説**  
  
 (この言語機能には共通言語ランタイムのみに適用される特記事項がありません。)  
  
### <a name="requirements"></a>必要条件  
 コンパイラ オプション: `/clr`  
  
### <a name="examples"></a>使用例  
  
 次のコード例では、インターフェイスが clock 関数の動作を定義する方法を示します。  
  
```cpp  
// mcppv2_interface_class.cpp  
// compile with: /clr  
using namespace System;  
  
public delegate void ClickEventHandler(int, double);  
  
// define interface with nested interface  
public interface class Interface_A {  
   void Function_1();  
  
   interface class Interface_Nested_A {  
      void Function_2();  
   };  
};  
  
// interface with a base interface  
public interface class Interface_B : Interface_A {  
   property int Property_Block;  
   event ClickEventHandler^ OnClick;     
   static void Function_3() { Console::WriteLine("in Function_3"); }  
};  
  
// implement nested interface  
public ref class MyClass : public Interface_A::Interface_Nested_A {  
public:  
   virtual void Function_2() { Console::WriteLine("in Function_2"); }  
};  
  
// implement interface and base interface  
public ref class MyClass2 : public Interface_B {  
private:  
   int MyInt;  
  
public:  
   // implement non-static function  
   virtual void Function_1() { Console::WriteLine("in Function_1"); }  
  
   // implement property  
   property int Property_Block {  
      virtual int get() { return MyInt; }  
      virtual void set(int value) { MyInt = value; }  
   }  
   // implement event  
   virtual event ClickEventHandler^ OnClick;  
  
   void FireEvents() {  
      OnClick(7, 3.14159);  
   }  
};  
  
// class that defines method called when event occurs  
ref class EventReceiver {  
public:  
   void OnMyClick(int i, double d) {  
      Console::WriteLine("OnClick: {0}, {1}", i, d);  
   }  
};  
  
int main() {  
   // call static function in an interface  
   Interface_B::Function_3();  
  
   // instantiate class that implements nested interface  
   MyClass ^ x = gcnew MyClass;  
   x->Function_2();  
  
   // instantiate class that implements interface with base interface  
   MyClass2 ^ y = gcnew MyClass2;  
   y->Function_1();  
   y->Property_Block = 8;  
   Console::WriteLine(y->Property_Block);  
  
   EventReceiver^ MyEventReceiver = gcnew EventReceiver();  
  
   // hook handler to event  
   y->OnClick += gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);  
  
   // invoke events  
   y->FireEvents();  
  
   // unhook handler to event  
   y->OnClick -= gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);  
  
   // call implemented function via interface handle  
   Interface_A^ hi = gcnew MyClass2();  
   hi->Function_1();  
}  
```  
  
 **出力**  
  
```Output  
in Function_3  
  
in Function_2  
  
in Function_1  
  
8  
  
OnClick: 7, 3.14159  
  
in Function_1  
```  
  
 次のコード サンプルでは、宣言で複数のインターフェイスとクラスによってそれらのインターフェイスが使用されている同じシグネチャを持つ関数を実装する 2 つの方法を示します。  
  
```cpp  
// mcppv2_interface_class_2.cpp  
// compile with: /clr /c  
interface class I {  
   void Test();  
   void Test2();  
};  
  
interface class J : I {  
   void Test();  
   void Test2();  
};  
  
ref struct R : I, J {  
   // satisfies the requirement to implement Test in both interfaces  
   virtual void Test() {}  
  
   // implement both interface functions with explicit overrides  
   virtual void A() = I::Test2 {}  
   virtual void B() = J::Test2 {}  
};  
```  
  
## <a name="see-also"></a>関連項目  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)