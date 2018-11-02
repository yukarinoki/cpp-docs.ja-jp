---
title: ジェネリック型パラメーターの制約 (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- where
helpviewer_keywords:
- where keyword [C++]
- constraints, C++
ms.assetid: eb828cc9-684f-48a3-a898-b327700c0a63
ms.openlocfilehash: c0ad5a22adec0d93019e9ea5c81cc8329d1607f8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533706"
---
# <a name="constraints-on-generic-type-parameters-ccli"></a>ジェネリック型パラメーターの制約 (C++/CLI)

ジェネリック型またはメソッドの宣言では、制約と型パラメーターを修飾することができます。 制約は、型引数として使用される型が満たす必要がある要件です。 たとえば、型引数が特定のインターフェイスを実装または特定のクラスから継承する必要があります、制約があります。

制約は、省略可能です。そのパラメーターの制約と同じですが、パラメーターの制約を指定していない<xref:System.Object>します。

## <a name="syntax"></a>構文

```cpp
where type-parameter: constraint list
```

### <a name="parameters"></a>パラメーター

*型パラメーター*<br/>
制約が適用される、型パラメーターの 1 つ。

*制約リスト*<br/>
*制約リスト*制約の仕様のコンマ区切りの一覧を示します。 一覧には、型パラメーターによって実装されるインターフェイスを含めることができます。

一覧には、クラスを含めることもできます。 基底クラスの制約を満たすために、型引数の制約と同じクラスまたはください制約から派生します。

指定することも**gcnew()** ; パブリック コンス トラクターを型引数が必要かを示すまたは**ref クラス**を示す、型引数は任意のクラスを含む、参照型である必要がありますインターフェイス、デリゲート、または配列型。または**値クラス**引数型を示す値型である必要があります。 値は null 値以外の型\<T > を指定できます。

制約としてジェネリック パラメーターを指定することもできます。 制約する型指定された型引数は、するか、制約の型から派生する必要があります。 これは、生の型の制約と呼ばれます。

## <a name="remarks"></a>Remarks

制約句から成る**場所**型パラメーター、コロンを続けて (**:**) と、制約は、型パラメーターで制限の内容を指定します。 **場所**状況依存のキーワードを参照してください[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)詳細についてはします。 複数の個別**場所**をスペースで句。

ジェネリック型またはメソッドの引数として使用できる型での制限事項を配置するパラメーターの型に制約が適用されます。

クラスとインターフェイスの制約は、引数の型する必要があるまたは指定したクラスを継承または実装している指定されたインターフェイスを指定します。

ジェネリック型またはメソッドへの制約の適用により、制約付きの型の既知の機能を活用するためにその型またはメソッドのコードです。 型パラメーターを実装するように、ジェネリック クラスを宣言するなど、`IComparable<T>`インターフェイス。

```cpp
// generics_constraints_1.cpp
// compile with: /c /clr
using namespace System;
generic <typename T>
where T : IComparable<T>
ref class List {};
```

この制約は、型引数を使用する必要があります`T`実装`IComparable<T>`コンパイル時にします。 また、インターフェイスのメソッドなど`CompareTo`、呼び出されます。 インターフェイス メソッドを呼び出すための型パラメーター インスタンスのキャストは必要ありません。

型パラメーターを型引数のクラスで静的メソッドを呼び出すことができません。これらは、実際の名前付きの型を介してのみ呼び出すことができます。

制約がなどの組み込み型を含め、値型にすることはできません**int**または**二重**します。 値の型には、クラスを派生できませんが、ため 1 つのクラスができる制約を満たすです。 その場合は、特定の値の型に置き換え、型パラメーターでジェネリックを書き換えることができます。

コンパイラがメソッドの使用またはその他の機能に不明な型の制約を意味不明な型には、メソッドまたはインターフェイスがサポートしている場合を除き、場合によっては制約が必要です。

コンマ区切りの一覧で、同じ型パラメーターに対して複数の制約を指定することができます。

```cpp
// generics_constraints_2.cpp
// compile with: /c /clr
using namespace System;
using namespace System::Collections::Generic;
generic <typename T>
where T : List<T>, IComparable<T>
ref class List {};
```

複数の型パラメーターを持つ 1 つを使用して**場所**型パラメーターごとの句。 例えば:

```cpp
// generics_constraints_3.cpp
// compile with: /c /clr
using namespace System;
using namespace System::Collections::Generic;

generic <typename K, typename V>
   where K: IComparable<K>
   where V: IComparable<K>
ref class Dictionary {};
```

要約すると、次の規則に従って、コード内の制約を使用します。

- 複数の制約がある場合、制約は任意の順序で表示されます。

- 制約は、抽象基本クラスなどのクラス型も可能です。 ただし、制約は、値の型またはクラスをシールすることはできません。

- 自体の制約が、型パラメーターをすることはできませんが、オープン構築型の型パラメーターが含まれることができます。 例えば:

    ```cpp
    // generics_constraints_4.cpp
    // compile with: /c /clr
    generic <typename T>
    ref class G1 {};

    generic <typename Type1, typename Type2>
    where Type1 : G1<Type2>   // OK, G1 takes one type parameter
    ref class G2{};
    ```

## <a name="example"></a>例

次の例では、制約を使用して、型パラメーターでインスタンス メソッドを呼び出すを示します。

```cpp
// generics_constraints_5.cpp
// compile with: /clr
using namespace System;

interface class IAge {
   int Age();
};

ref class MyClass {
public:
   generic <class ItemType> where ItemType : IAge
   bool isSenior(ItemType item) {
      // Because of the constraint,
      // the Age method can be called on ItemType.
      if (item->Age() >= 65)
         return true;
      else
         return false;
   }
};

ref class Senior : IAge {
public:
   virtual int Age() {
      return 70;
   }
};

ref class Adult: IAge {
public:
   virtual int Age() {
      return 30;
   }
};

int main() {
   MyClass^ ageGuess = gcnew MyClass();
   Adult^ parent = gcnew Adult();
   Senior^ grandfather = gcnew Senior();

   if (ageGuess->isSenior<Adult^>(parent))
      Console::WriteLine("\"parent\" is a senior");
   else
      Console::WriteLine("\"parent\" is not a senior");

   if (ageGuess->isSenior<Senior^>(grandfather))
      Console::WriteLine("\"grandfather\" is a senior");
   else
      Console::WriteLine("\"grandfather\" is not a senior");
}
```

```Output
"parent" is not a senior
"grandfather" is a senior
```

## <a name="example"></a>例

制約としてジェネリック型パラメーターを使用すると、生の型の制約と呼ばれます。 生の型制約は、独自の型パラメーターを持つメンバー関数を含んでいる型の型パラメーターに制約する必要がある場合に便利です。

次の例では、`T`生の型制約のコンテキストでは、`Add`メソッド。

生の型制約は、ジェネリック クラス定義にも使用できます。 コンパイラはに関して何も仮定生の型の制約から派生する点を除いてために、ジェネリック クラスで生の型制約の有用性が制限されて<xref:System.Object>します。 2 つの型パラメーターの間の継承関係を適用するシナリオでは、ジェネリック クラスの生の型制約を使用します。

```cpp
// generics_constraints_6.cpp
// compile with: /clr /c
generic <class T>
ref struct List {
   generic <class U>
   where U : T
   void Add(List<U> items)  {}
};

generic <class A, class B, class C>
where A : C
ref struct SampleClass {};
```

## <a name="see-also"></a>関連項目

[ジェネリック](../windows/generics-cpp-component-extensions.md)