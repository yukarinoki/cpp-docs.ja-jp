---
title: ジェネリック関数 (C +/cli CLI) |Microsoft Docs
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], generic
- generic methods
- generics [C++], functions
- methods [C++], generic
- generic functions
ms.assetid: 8e409364-58f9-4360-b486-e7d555e0c218
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4e5305aaa35064c26a78cbd4654c27a0d608d70c
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50067905"
---
# <a name="generic-functions-ccli"></a>ジェネリック関数 (C++/CLI)

ジェネリック関数は、型パラメーターで宣言された関数です。 呼び出されると、型パラメーターではなく実際の型が使用されます。

## <a name="all-platforms"></a>すべてのプラットフォーム

### <a name="remarks"></a>Remarks

この機能は、すべてのプラットフォームには適用されません。

## <a name="windows-runtime"></a>Windows ランタイム

### <a name="remarks"></a>Remarks

この機能は、Windows ランタイムでサポートされていません。

### <a name="requirements"></a>必要条件

コンパイラ オプション: `/ZW`

## <a name="common-language-runtime"></a>共通言語ランタイム

ジェネリック関数は、型パラメーターで宣言された関数です。 呼び出されると、型パラメーターではなく実際の型が使用されます。

### <a name="syntax"></a>構文

```cpp
[attributes] [modifiers]
return-type identifier<type-parameter identifier(s)>
[type-parameter-constraints clauses]

([formal-parameters])
{function-body}
```

### <a name="parameters"></a>パラメーター

*属性*<br/>
(省略可能)追加の宣言情報。 属性と属性クラスの詳細については、属性を参照してください。

*修飾子*<br/>
(省略可能)静的などの関数の修飾子です。  **仮想**仮想メソッドをジェネリックにすることはできないためには許可されません。

*戻り値の型*<br/>
メソッドによって返される型。 戻り値の型が void の場合は、戻り値は必要ありません。

*identifier*<br/>
関数名。

*型パラメーターの識別子*<br/>
識別子のコンマ区切りリスト。

*仮パラメーター*<br/>
(省略可能)パラメーター リストです。

*型パラメーター制約句*<br/>
これは、型の引数として使用できる型での制限を指定しますで指定された形式の[ジェネリック型パラメーターの制約 (C +/cli CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md)します。

*関数本体*<br/>
型パラメーターの識別子を参照する、メソッドの本体。

### <a name="remarks"></a>Remarks

ジェネリック関数は、ジェネリック型パラメーターで宣言された関数です。 クラスまたは構造体、またはスタンドアロン関数内のメソッドがあります。 1 つのジェネリック宣言には、ジェネリック型パラメーターのさまざまな実際の型の置換だけが異なる関数のファミリが暗黙的に宣言します。

クラスまたは構造体のコンス トラクターを宣言して、ジェネリック型パラメーターを持つことはできません。

呼び出されると、ジェネリック型パラメーターは、実際の型に置換されます。 テンプレート関数の呼び出しに似た構文を使用して、山かっこでは、実際の型を明示的に指定することがあります。 型のパラメーターなしで呼び出すと、コンパイラは関数呼び出しで指定されたパラメーターから実際の型を推測しようとします。 目的の型引数は、使用されるパラメーターから推測できない、コンパイラでエラーが報告されます。

### <a name="requirements"></a>必要条件

コンパイラ オプション: `/clr`

### <a name="examples"></a>使用例

次のコード サンプルでは、ジェネリック関数を示します。

```cpp
// generics_generic_function_1.cpp
// compile with: /clr
generic <typename ItemType>
void G(int i) {}

ref struct A {
   generic <typename ItemType>
   void G(ItemType) {}

   generic <typename ItemType>
   static void H(int i) {}
};

int main() {
   A myObject;

   // generic function call
   myObject.G<int>(10);

   // generic function call with type parameters deduced
   myObject.G(10);

   // static generic function call
   A::H<int>(10);

   // global generic function call
   G<int>(10);
}
```

ジェネリック関数は、署名またはアリティ、関数の型パラメーターの数に基づいてオーバー ロードできます。 また、ジェネリック関数オーバー ロードできます、同じ名前の非ジェネリック関数と関数がいくつかの型パラメーターが異なる限り、します。 たとえば、次の関数をオーバー ロードできます。

```cpp
// generics_generic_function_2.cpp
// compile with: /clr /c
ref struct MyClass {
   void MyMythod(int i) {}

   generic <class T>
   void MyMythod(int i) {}

   generic <class T, class V>
   void MyMythod(int i) {}
};
```

次の例では、ジェネリック関数を使用して、配列内の最初の要素を検索します。 宣言`MyClass`、基底クラスから継承される`MyBaseClass`します。 `MyClass` ジェネリック関数を含む`MyFunction`、もう 1 つの汎用関数を呼び出し`MyBaseClassFunction`、基底クラス内で。 `main`、ジェネリックの関数では、 `MyFunction`、別の型引数を使用すると呼びます。

```cpp
// generics_generic_function_3.cpp
// compile with: /clr
using namespace System;

ref class MyBaseClass {
protected:
   generic <class ItemType>
   ItemType MyBaseClassFunction(ItemType item) {
      return item;
   }
};

ref class MyClass: public MyBaseClass {
public:
   generic <class ItemType>
   ItemType MyFunction(ItemType item) {
      return MyBaseClass::MyBaseClassFunction<ItemType>(item);
   }
};

int main() {
   MyClass^ myObj = gcnew MyClass();

   // Call MyFunction using an int.
   Console::WriteLine("My function returned an int: {0}",
                           myObj->MyFunction<int>(2003));

   // Call MyFunction using a string.
   Console::WriteLine("My function returned a string: {0}",
   myObj->MyFunction<String^>("Hello generic functions!"));
}
```

```Output
My function returned an int: 2003
My function returned a string: Hello generic functions!
```

## <a name="see-also"></a>関連項目

[Component Extensions for .NET と UWP](../windows/component-extensions-for-runtime-platforms.md)<br/>
[ジェネリック](../windows/generics-cpp-component-extensions.md)
