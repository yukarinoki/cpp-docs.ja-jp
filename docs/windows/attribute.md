---
title: 属性 |Microsoft Docs
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
ms.openlocfilehash: fa6c9dfa36ae753e87f0dd4b8c0fc13d3db6aeba
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679909"
---
# <a name="attribute"></a>属性

カスタム属性を作成することができます。

## <a name="syntax"></a>構文

```cpp
[ attribute(
   AllowOn,
   AllowMultiple=boolean,
   Inherited=boolean
) ]
```

### <a name="parameters"></a>パラメーター

*AllowOn*  
カスタム属性を適用できる言語要素を指定します。 既定値は`System::AttributeTargets::All`(を参照してください[値](https://msdn.microsoft.com/library/system.attributetargets.aspx))。

*AllowMultiple*  
構成要素にカスタム属性を繰り返し適用できるかどうかを指定します。 既定値は FALSE です。

*継承*  
サブクラスに継承される属性を示します。 コンパイラは特別なサポートしていません。 この機能の属性コンシューマーのジョブが (`Reflection`など) にこの情報を処理します。 場合*継承された*が true の場合、この属性を継承します。 場合*AllowMultiple*が true の場合場合に、派生メンバーでは、属性が蓄積されます*AllowMultiple* false で、属性はオーバーライド (または置換) 継承します。 場合*継承された*false で、属性は継承されません。 既定値は TRUE です。

## <a name="remarks"></a>Remarks

> [!NOTE]
> **属性**属性が非推奨となりました。  共通言語ランタイムの属性を使用して、`System.Attribute`に子のユーザー定義属性を作成するには、直接します。 詳細については、次を参照してください。[ユーザー定義の属性](../windows/user-defined-attributes-cpp-component-extensions.md)します。

定義する、[カスタム属性](../windows/custom-attributes-cpp.md)配置することで、**属性**マネージ クラスまたは構造体の定義に対する属性。 クラスの名前は、カスタム属性です。 例えば:

```cpp
[ attribute(Parameter) ]
public ref class MyAttr {};
```

という名前の属性を定義します。`MyAttr`関数パラメーターに適用できます。 クラスは、属性が他のアセンブリで使用する場合は、パブリックである必要があります。

> [!NOTE]
> 名前空間の競合を防ぐためには、すべての属性名に暗黙的に"Attribute"終わる;属性とクラスの名前を実際には、この例では`MyAttrAttribute`が`MyAttr`と`MyAttrAttribute`同じ意味で使用できます。

クラスのパブリック コンス トラクターは、属性の名前のないパラメーターを定義します。 オーバー ロードされたコンス トラクターは、複数の方法であるカスタム属性には、次の方法が定義されているため、属性を指定するを許可します。

```cpp
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

```cpp
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

可能な属性パラメーターの型の一覧は、次を参照してください。[カスタム属性](../windows/custom-attributes-cpp.md)します。

参照してください[ユーザー定義の属性](../windows/user-defined-attributes-cpp-component-extensions.md)属性の対象の詳細についてはします。

**属性**属性が、 *AllowMultiple*カスタム属性が 1 回使用するかどうかを指定するパラメーターまたは multiuse (に表示できる複数回、同じエンティティ)。

```cpp
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

カスタム属性クラスは直接または間接的にから派生<xref:System.ComponentModel.AttributeCollection.%23ctor%2A>、高速かつ簡単にメタデータ内の属性定義を識別するため、します。 **属性**属性からの継承の意味`System::Attribute`ので、明示的な派生が必要ではありません。

```cpp
[ attribute(Class) ]
ref class MyAttr
```

上記の式は、次の式と同じです。

```cpp
[ attribute(Class) ]
ref class MyAttr : System::Attribute   // OK, but redundant.
```

**属性**の別名です<xref:System.AttributeUsageAttribute?displayProperty=fullName>(AttributeAttribute されません。 これは、属性の名前付け規則の例外)。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**ref クラス**、 **ref 構造体**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="example"></a>例

```cpp
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

`Inherited`名前付き引数は基本クラスに適用されるカスタム属性が派生クラスのリフレクションで示されるかどうかを指定します。

```cpp
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

[属性リファレンス (アルファベット順)](../windows/attributes-alphabetical-reference.md)  
