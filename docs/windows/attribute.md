---
title: 属性 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.attribute
dev_langs:
- C++
helpviewer_keywords:
- __typeof keyword
- custom attributes, creating
- attribute attribute
- attributes [C++], custom
ms.assetid: 8cb3489f-65c4-44ea-b0aa-3c3c6b15741d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9826b689e2b8a640efe66e8625b97b3cec347acf
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="attribute"></a>属性
カスタム属性を作成できます。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ attribute(  
   AllowOn,  
   AllowMultiple=boolean,  
   Inherited=boolean  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *AllowOn*  
 カスタム属性の適用先の言語要素を指定します。 既定値は**System::AttributeTargets::All** (を参照してください[値](https://msdn.microsoft.com/en-us/library/system.attributetargets.aspx))。  
  
 `AllowMultiple`  
 カスタム属性を構成要素に繰り返し適用できるかどうかを指定します。 既定値は**FALSE**です。  
  
 `Inherited`  
 属性をサブクラスに継承するかどうかを示します。 コンパイラです。 この機能を特別なサポートはありません。この情報を処理する属性コンシューマー (リフレクションの使用例) のジョブには。 場合`Inherited`は**TRUE**属性を継承します。 場合`AllowMultiple`は**TRUE**、属性が派生メンバーであるに蓄積される場合`AllowMultiple`は**FALSE**属性はオーバーライド (または 置換) で継承します。 場合`Inherited`は**FALSE**属性は継承できません。 既定値は**TRUE**です。  
  
## <a name="remarks"></a>コメント  
  
> [!NOTE]
>  `attribute`属性は推奨されなくなりました。  共通言語ランタイム属性 System.Attribute に直接を使用すると、子のユーザー定義属性を作成できます。  詳細については、次を参照してください。[ユーザー定義の属性](../windows/user-defined-attributes-cpp-component-extensions.md)です。  
  
 定義する、[カスタム属性](../windows/custom-attributes-cpp.md)配置することによって、`attribute`マネージ クラスまたは構造体定義の属性です。 クラスの名前は、カスタム属性です。 例えば:  
  
```  
[ attribute(Parameter) ]  
public ref class MyAttr {};  
```  
  
 myattr 関数パラメーターに適用できる属性を定義します。 クラスは、属性が他のアセンブリで使用する場合はパブリックである必要があります。  
  
> [!NOTE]
>  名前空間の競合を防ぐためには、すべての属性名に暗黙的に付いて"Attribute"です。この例では、属性とクラスの名前が MyAttrAttribute 実際には、MyAttr と MyAttrAttribute を置き換えて使用することができます。  
  
 クラスのパブリック コンス トラクターは、属性の名前のないパラメーターを定義します。 オーバー ロードされたコンス トラクターは、複数の方法は、そのカスタム属性には、次の方法が定義されているため、属性を指定するを許可します。  
  
```  
// cpp_attr_ref_attribute.cpp  
// compile with: /c /clr  
using namespace System;  
[ attribute(AttributeTargets::Class) ]   // apply attribute to classes  
public ref class MyAttr {  
public:  
   MyAttr() {}   // Constructor with no parameters  
   MyAttr(int arg1) {}   // Constructor with one parameter  
};  
  
[MyAttr]  
ref class ClassA {};   // Attribute with no parameters  
  
[MyAttr(123)]  
ref class ClassB {};   // Attribute with one parameter  
```  
  
 クラスのパブリック データ メンバーおよびプロパティは、属性の省略可能な名前付きパラメーターには。  
  
```  
// cpp_attr_ref_attribute_2.cpp  
// compile with: /c /clr  
using namespace System;  
[ attribute(AttributeTargets::Class) ]  
ref class MyAttr {  
public:  
   // Property Priority becomes attribute's named parameter Priority  
    property int Priority {  
       void set(int value) {}  
       int get() { return 0;}  
   }  
   // Data member Version becomes attribute's named parameter Version  
   int Version;  
   MyAttr() {}   // constructor with no parameters  
   MyAttr(int arg1) {}   // constructor with one parameter  
};  
  
[MyAttr(123, Version=2)]   
ref class ClassC {};  
```  
  
 可能な属性パラメーター型の一覧は、次を参照してください。[カスタム属性](../windows/custom-attributes-cpp.md)です。  
  
 参照してください[ユーザー定義の属性](../windows/user-defined-attributes-cpp-component-extensions.md)属性の対象の詳細についてはします。  
  
 `attribute`属性が、`AllowMultiple`カスタム属性が 1 つ使用するかどうかを指定するパラメーターまたは multiuse (が複数回表示される同じエンティティで)。  
  
```  
// cpp_attr_ref_attribute_3.cpp  
// compile with: /c /clr  
using namespace System;  
[ attribute(AttributeTargets::Class, AllowMultiple = true) ]  
ref struct MyAttr {  
   MyAttr(){}  
};   // MyAttr is a multiuse attribute  
  
[MyAttr, MyAttr()]  
ref class ClassA {};  
```  
  
 カスタム属性クラスの派生直接的または間接的にから<xref:System.ComponentModel.AttributeCollection.%23ctor%2A>メタデータの高速で簡単に属性の定義を識別するため、します。 `attribute`属性は、明示的な派生が必要ではないために、system::attribute から継承を意味します。  
  
```  
[ attribute(Class) ]  
ref class MyAttr  
```  
  
 上記の式は、次の式と同じです。  
  
```  
[ attribute(Class) ]  
ref class MyAttr : System::Attribute   // OK, but redundant.  
```  
  
 `attribute` エイリアス<xref:System.AttributeUsageAttribute?displayProperty=fullName>(AttributeAttribute されません。 これは、属性の名前付け規則の例外)。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`ref` **クラス**、 **ref 構造体**|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// cpp_attr_ref_attribute_4.cpp  
// compile with: /c /clr  
using namespace System;  
[attribute(AttributeTargets::Class)]  
ref struct ABC {  
   ABC(Type ^) {}  
};  
  
[ABC(String::typeid)]   // typeid operator yields System::Type ^  
ref class MyClass {};  
```  
  
## <a name="example"></a>例  
 `Inherited`名前付き引数には、基本クラスに適用されるカスタム属性が派生クラスのリフレクションで示されるかどうかを指定します。  
  
```  
// cpp_attr_ref_attribute_5.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Reflection;  
  
[attribute( AttributeTargets::Method, Inherited=false )]  
ref class BaseOnlyAttribute { };  
  
[attribute( AttributeTargets::Method, Inherited=true )]  
ref class DerivedTooAttribute { };  
  
ref struct IBase {  
public:  
   [BaseOnly, DerivedToo]  
   virtual void meth() {}  
};  
  
// Reflection on Derived::meth will show DerivedTooAttribute   
// but not BaseOnlyAttribute.  
ref class Derived : public IBase {  
public:  
   virtual void meth() override {}  
};  
  
int main() {  
   IBase ^ pIB = gcnew Derived;  
  
   MemberInfo ^ pMI = pIB->GetType( )->GetMethod( "meth" );  
   array<Object ^> ^ pObjs = pMI->GetCustomAttributes( true );  
   Console::WriteLine( pObjs->Length ) ;  
}  
```  
  
```Output  
2  
```  
  
## <a name="see-also"></a>関連項目  
 [属性のアルファベット順リファレンス](../windows/attributes-alphabetical-reference.md)   
 [カスタム属性](http://msdn.microsoft.com/en-us/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)