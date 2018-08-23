---
title: ジェネリック クラス (C +/cli CLI) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- classes [C++], generic
- generic classes [C++], about generic classes
- data types [C++], generic
- generic classes
- generics [C++], declaring generic classes
ms.assetid: 0beb99e1-1ec4-4fee-9836-ce9657d67a3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 76dc54662fac3dc769e0bbf72c672908196ef351
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598248"
---
# <a name="generic-classes-ccli"></a>ジェネリック クラス (C++/CLI)

ジェネリック クラスは、次の形式を使用して宣言されます。

## <a name="syntax"></a>構文

```cpp
[attributes]
generic <class-key type-parameter-identifier(s)>
[constraint-clauses]
[accessibility-modifiers] ref class identifier  [modifiers]
[: base-list]
{
class-body
} [declarators] [;]
```

## <a name="remarks"></a>Remarks

上記の構文では、次の用語が使用されます。

*属性*(省略可能)  
追加の宣言情報。 属性と属性クラスの詳細については、属性を参照してください。

*クラス キー*  
いずれか**クラス**または**typename**

*型のパラメーターの識別子*、型パラメーターの名前を指定する識別子のコンマ区切りのリスト。

*制約句*  
リスト (コンマ区切りされません)**場所**句の型パラメーター制約を指定します。 形式をとります。

`where`  *型の識別子パラメーター*`:`*制約リスト*  `...`

*制約リスト*  
*クラスまたはインターフェイス*[`,` *.*]

*アクセシビリティ修飾子*  
ジェネリック クラスのアクセシビリティ修飾子。 唯一の許容修飾子は、Windows ランタイムの**プライベート**します。 使用できる修飾子には、共通言語ランタイムの**プライベート**と**パブリック**します。

*identifier*  
ジェネリックのクラスでは、任意の有効な C++ 識別子の名前。

*修飾子*(省略可能)  
修飾子は、許可されている**シール**と**抽象**します。

*基本リスト*  
1 つの基本クラスとそのいずれかを含むリストには、インターフェイス、コンマで区切ってが実装されています。

*クラス本体*  
フィールド、メンバー関数などを含む、クラスの本文。

*宣言子*  
この型の任意の変数の宣言。 例: `^`*識別子*[`,` ...]

これらなどのジェネリック クラスを宣言することができます (なお、キーワード**クラス**の代わりに使用することがあります**typename**)。 この例で`ItemType`、`KeyType`と`ValueType`ポイントで指定されている種類は不明なは、種類。 `HashTable<int, int>` 構築されたジェネリック型の型は、`HashTable<KeyType, ValueType>`します。 1 つのジェネリック型から別の構築された型の数値を構築できます。 ジェネリック クラスから構築された構築された型は、他の ref クラス型のように扱われます。

```cpp
// generic_classes_1.cpp
// compile with: /clr
using namespace System;
generic <typename ItemType>
ref struct Stack {
   // ItemType may be used as a type here
   void Add(ItemType item) {}
};

generic <typename KeyType, typename ValueType>
ref class HashTable {};

// The keyword class may be used instead of typename:
generic <class ListItem>
ref class List {};

int main() {
   HashTable<int, Decimal>^ g1 = gcnew HashTable<int, Decimal>();
}
```

両方の値の型 (などのいずれかの組み込み型**int**または**二重**、またはユーザー定義の値の型) と参照型をジェネリック型引数として使用することがあります。 ジェネリックの定義内での構文は、同じかに関係なくです。 構文上、不明な型は参照型の場合と同様に扱われます。 ただし、ランタイムは、実際に使用される型が値型であると判断し、メンバーに直接アクセスするための適切な生成されたコードに置き換えてください。 ジェネリック型引数として使用される値型はボックス化されていないと、ためボックス化に関連付けられているパフォーマンスが低下することはありません。 ジェネリックの本文内で使用されている構文にする必要があります`T^`と`->`の代わりに`.`します。 使用されるすべての[ref new、gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)型のパラメーターは適切として解釈されます、ランタイムによって値型の単純な作成、型引数が値型の場合。

ジェネリック クラスを宣言することもできます。[ジェネリック型パラメーターの制約 (C +/cli CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md) 、型パラメーターに対して使用できる型にします。 次の例で任意の型の使用の`ItemType`実装する必要があります、`IItem`インターフェイス。 使用しようとしています。 **int**、これを実装しませんなど`IItem`、型引数が、制約を満たしていないため、コンパイル時エラーが生成します。

```cpp
// generic_classes_2.cpp
// compile with: /clr /c
interface class IItem {};
generic <class ItemType>
where ItemType : IItem
ref class Stack {};
```

同じ名前空間のジェネリック クラスは、数または型パラメーターの型を変更するだけでオーバー ロードできません。 ただし、各クラスは、別の名前空間では場合、オーバー ロードできます。 たとえば、次の 2 つのクラス`MyClass`と`MyClass<ItemType>`、名前空間の`A`と`B`します。 2 つのクラスが 3 つ目の名前空間 c: でオーバー ロードすることができますし、

```cpp
// generic_classes_3.cpp
// compile with: /clr /c
namespace A {
   ref class MyClass {};
}

namespace B {
   generic <typename ItemType>
   ref class MyClass2 { };
}

namespace C {
   using namespace A;
   using namespace B;

   ref class Test {
      static void F() {
         MyClass^ m1 = gcnew MyClass();   // OK
         MyClass2<int>^ m2 = gcnew MyClass2<int>();   // OK
      }
   };
}
```

基底クラスと基底インターフェイスには、型パラメーターを指定できません。 ただし、基底クラスでは、次の例のように、引数として型パラメーターを伴うことができます。

```cpp
// generic_classes_4.cpp
// compile with: /clr /c
generic <typename ItemType>
interface class IInterface {};

generic <typename ItemType>
ref class MyClass : IInterface<ItemType> {};
```

コンス トラクターとデストラクターは 1 回オブジェクトのインスタンスごとに (通常どおり実行)。静的コンス トラクターは、構築された種類ごとに 1 回実行されます。

## <a name="fields-in-generic-classes"></a>ジェネリック クラスのフィールド

このセクションでは、インスタンス、およびジェネリック クラスの静的フィールドの使用を示します。

### <a name="instance-variables"></a>インスタンス変数

ジェネリック クラスのインスタンス変数には、型と、外側のクラスからの型パラメーターを含む変数の初期化子を持つことができます。

## <a name="example"></a>例

次の例では、ジェネリック クラス、MyClass の 3 つの異なるインスタンス\<ItemType >、適切な型引数を使用して作成されます (**int**、**二重**、および**文字列**)。

```cpp
// generics_instance_fields1.cpp
// compile with: /clr
// Instance fields on generic classes
using namespace System;

generic <typename ItemType>
ref class MyClass {
// Field of the type ItemType:
public :
   ItemType field1;
   // Constructor using a parameter of the type ItemType:
   MyClass(ItemType p) {
   field1 = p;
   }
};

int main() {
   // Instantiate an instance with an integer field:
   MyClass<int>^ myObj1 = gcnew MyClass<int>(123);
   Console::WriteLine("Integer field = {0}", myObj1->field1);

   // Instantiate an instance with a double field:
   MyClass<double>^ myObj2 = gcnew MyClass<double>(1.23);
   Console::WriteLine("Double field = {0}", myObj2->field1);

   // Instantiate an instance with a String field:
   MyClass<String^>^ myObj3 = gcnew MyClass<String^>("ABC");
   Console::WriteLine("String field = {0}", myObj3->field1);
   }
```

```Output
Integer field = 123
Double field = 1.23
String field = ABC
```

## <a name="static-variables"></a>静的変数

新しいジェネリック型の作成は、静的変数の新しいインスタンスを作成され、その型の任意の静的コンス トラクターが実行されます。

静的変数は、外側のクラスからの型パラメーターを使用できます。

## <a name="example"></a>例

次の例では、静的フィールドと汎用クラス内で静的コンス トラクターの使用を示します。

```cpp
// generics_static2.cpp
// compile with: /clr
using namespace System;

interface class ILog {
   void Write(String^ s);
};

ref class DateTimeLog : ILog {
public:
   virtual void Write(String^ s) {
      Console::WriteLine( "{0}\t{1}", DateTime::Now, s);
   }
};

ref class PlainLog : ILog {
public:
   virtual void Write(String^ s) { Console::WriteLine(s); }
};

generic <typename LogType>
where LogType : ILog
ref class G {
   static LogType s_log;

public:
   G(){}
   void SetLog(LogType log) { s_log = log; }
   void F() { s_log->Write("Test1"); }
   static G() { Console::WriteLine("Static constructor called."); }
};

int main() {
   G<PlainLog^>^ g1 = gcnew G<PlainLog^>();
   g1->SetLog(gcnew PlainLog());
   g1->F();

   G<DateTimeLog^>^ g2 = gcnew G<DateTimeLog^>();
   g2->SetLog(gcnew DateTimeLog());

   // prints date
   // g2->F();
}
```

```Output
Static constructor called.
Static constructor called.
Static constructor called.
Test1
```

## <a name="methods-in-generic-classes"></a>ジェネリック クラスのメソッド

ジェネリック クラスのメソッドをジェネリックにすることができます。クラスの型パラメーターによって、非ジェネリック メソッドを暗黙的にパラメーター化されます。

ジェネリック クラス内のメソッドに次の特別な規則が適用されます。

- ジェネリック クラスのメソッドは、パラメーター、戻り値の型、またはローカル変数として型パラメーターを使用できます。

- ジェネリック クラスのメソッドは、パラメーター、戻り値の型、またはローカル変数としてオープンかクローズ構築型を使用できます。

### <a name="non-generic-methods-in-generic-classes"></a>ジェネリック クラスの非ジェネリック メソッド

追加の型パラメーターを持たないジェネリック クラスのメソッドは通常、外側のジェネリック クラスで暗黙的にパラメーター化されたに非ジェネリックとして呼ばれます。

非ジェネリック メソッドのシグネチャは、直接またはオープン構築型で外側のクラスの 1 つまたは複数の型パラメーターを含めることができます。 例えば:

`void MyMethod(MyClass<ItemType> x) {}`

このようなメソッドの本文には、これらの型パラメーターも使用できます。

## <a name="example"></a>例

次の例は、非ジェネリック メソッドを宣言`ProtectData`、ジェネリックのクラスの内部`MyClass<ItemType>`します。 メソッドはクラス型のパラメーターを使用して`ItemType`オープン構築型では、そのシグニチャにします。

```cpp
// generics_non_generic_methods1.cpp
// compile with: /clr
// Non-generic methods within a generic class.
using namespace System;

generic <typename ItemType>
ref class MyClass {
public:
   String^ name;
   ItemType data;

   MyClass(ItemType x) {
      data = x;
   }

   // Non-generic method using the type parameter:
   virtual void ProtectData(MyClass<ItemType>^ x) {
      data = x->data;
   }
};

// ItemType defined as String^
ref class MyMainClass: MyClass<String^> {
public:
   // Passing "123.00" to the constructor:
   MyMainClass(): MyClass<String^>("123.00") {
      name = "Jeff Smith";
   }

   virtual void ProtectData(MyClass<String^>^ x) override {
      x->data = String::Format("${0}**", x->data);
   }

   static void Main() {
      MyMainClass^ x1 = gcnew MyMainClass();

      x1->ProtectData(x1);
      Console::WriteLine("Name: {0}", x1->name);
      Console::WriteLine("Amount: {0}", x1->data);
   }
};

int main() {
   MyMainClass::Main();
}
```

```Output
Name: Jeff Smith
Amount: $123.00**  
```

## <a name="generic-methods-in-generic-classes"></a>ジェネリック クラスのジェネリック メソッド

ジェネリックと非ジェネリック クラスのジェネリック メソッドを宣言することができます。 例えば:

## <a name="example"></a>例

```cpp
// generics_method2.cpp
// compile with: /clr /c
generic <typename Type1>
ref class G {
public:
   // Generic method having a type parameter
   // from the class, Type1, and its own type
   // parameter, Type2
   generic <typename Type2>
   void Method1(Type1 t1, Type2 t2) { F(t1, t2); }

   // Non-generic method:
   // Can use the class type param, Type1, but not Type2.
   void Method2(Type1 t1) { F(t1, t1); }

   void F(Object^ o1, Object^ o2) {}
};
```

非ジェネリック メソッドでは、クラスの型パラメーターでパラメーター化が、追加の型のパラメーターを持たないことの意味ではまだジェネリック。

ジェネリック クラスのメソッドのすべての種類など、ジェネリックの静的なインスタンス、および仮想メソッドを使用できます。

## <a name="example"></a>例

次の例では、ジェネリック クラス内でのジェネリック メソッドの宣言とを示しています。

```cpp
// generics_generic_method2.cpp
// compile with: /clr
using namespace System;
generic <class ItemType>
ref class MyClass {
public:
   // Declare a generic method member.
   generic <class Type1>
   String^ MyMethod(ItemType item, Type1 t) {
      return String::Concat(item->ToString(), t->ToString());
   }
};

int main() {
   // Create instances using different types.
   MyClass<int>^ myObj1 = gcnew MyClass<int>();
   MyClass<String^>^ myObj2 = gcnew MyClass<String^>();
   MyClass<String^>^ myObj3 = gcnew MyClass<String^>();

   // Calling MyMethod using two integers.
   Console::WriteLine("MyMethod returned: {0}",
            myObj1->MyMethod<int>(1, 2));

   // Calling MyMethod using an integer and a string.
   Console::WriteLine("MyMethod returned: {0}",
            myObj2->MyMethod<int>("Hello #", 1));

   // Calling MyMethod using two strings.
   Console::WriteLine("MyMethod returned: {0}",
       myObj3->MyMethod<String^>("Hello ", "World!"));

   // generic methods can be called without specifying type arguments
   myObj1->MyMethod<int>(1, 2);
   myObj2->MyMethod<int>("Hello #", 1);
   myObj3->MyMethod<String^>("Hello ", "World!");
}
```

```Output
MyMethod returned: 12
MyMethod returned: Hello #1
MyMethod returned: Hello World!
```

## <a name="using-nested-types-in-generic-classes"></a>ジェネリック クラスの入れ子にされた型を使用します。

通常のクラスと同様、ジェネリック クラスは、その他の種類を宣言できます。 入れ子になったクラス宣言は、外側のクラス宣言の型パラメーターで暗黙的にパラメーター化されます。 そのため、個別の入れ子になったクラスは、構築された外部種類ごとに定義されます。 たとえば、宣言で

```cpp
// generic_classes_5.cpp
// compile with: /clr /c
generic <typename ItemType>
ref struct Outer {
   ref class Inner {};
};
```

型`Outer<int>::Inner`型と同じではない`Outer<double>::Inner`します。

ジェネリック クラスのジェネリック メソッドと同様には、入れ子にされた型の追加の型パラメーターを定義することができます。 内側と外側のクラスで同じ型パラメーター名を使用する場合、内部の型パラメーターには、外側の型パラメーターが非表示になります。

```cpp
// generic_classes_6.cpp
// compile with: /clr /c
generic <typename ItemType>
ref class Outer {
   ItemType outer_item;   // refers to outer ItemType

   generic <typename ItemType>
   ref class Inner {
      ItemType inner_item;   // refers to Inner ItemType
   };
};
```

外側の型パラメーターを参照する手段がないため、コンパイラによってこのような状況で警告が生成されます。

構築された入れ子になったジェネリック型は名前がある場合に、内部の型が暗黙的に外側の型の型パラメーターでパラメーター化された場合でも外側の型の型パラメーターは、内部の型の型パラメーター リストに含まれません。 上記のように構築された型の名前になります`Outer<int>::Inner<string>`します。

次の例では、ビルドと、ジェネリック クラスの入れ子にされた型を使用してリンクされたリストを読み取ってを示します。

## <a name="example"></a>例

```cpp
// generics_linked_list.cpp
// compile with: /clr
using namespace System;
generic <class ItemType>
ref class LinkedList {
// The node class:
public:
   ref class Node {
   // The link field:
   public:
      Node^ next;
      // The data field:
      ItemType item;
   } ^first, ^current;
};

ref class ListBuilder {
public:
   void BuildIt(LinkedList<double>^ list) {
      /* Build the list */
      double m[5] = {0.1, 0.2, 0.3, 0.4, 0.5};
      Console::WriteLine("Building the list:");

      for (int n=0; n<=4; n++) {
         // Create a new node:
         list->current = gcnew LinkedList<double>::Node();

         // Assign a value to the data field:
         list->current->item = m[n];

         // Set the link field "next" to be the same as
         // the "first" field:
         list->current->next = list->first;

         // Redirect "first" to the new node:
         list->first = list->current;

         // Display node's data as it builds:
         Console::WriteLine(list->current->item);
      }
   }

   void ReadIt(LinkedList<double>^ list) {
      // Read the list
      // Make "first" the "current" link field:
      list->current = list->first;
      Console::WriteLine("Reading nodes:");

      // Read nodes until current == null:
      while (list->current != nullptr) {
         // Display the node's data field:
         Console::WriteLine(list->current->item);

         // Move to the next node:
         list->current = list->current->next;
      }
   }
};

int main() {
   // Create a list:
   LinkedList<double>^ aList = gcnew LinkedList<double>();

   // Initialize first node:
   aList->first = nullptr;

   // Instantiate the class, build, and read the list:
   ListBuilder^ myListBuilder = gcnew ListBuilder();
   myListBuilder->BuildIt(aList);
   myListBuilder->ReadIt(aList);
}
```

```Output
Building the list:
0.1
0.2
0.3
0.4
0.5
Reading nodes:
0.5
0.4
0.3
0.2
0.1
```

## <a name="properties-events-indexers-and-operators-in-generic-classes"></a>プロパティ、イベント、インデクサー、およびジェネリック クラスの演算子

- プロパティ、イベント、インデクサー、演算子は、戻り値、パラメーター、または場合などのローカル変数として外側のジェネリック クラスの型パラメーターを使用できます`ItemType`クラスの型パラメーターです。

    ```cpp
    public ItemType MyProperty {}
    ```

- プロパティ、イベント、インデクサー、演算子自体パラメーター化できません。

## <a name="example"></a>例

この例では、ジェネリック クラス内でインスタンス プロパティの宣言を示します。

```cpp
// generics_generic_properties1.cpp
// compile with: /clr
using namespace System;

generic <typename ItemType>
ref class MyClass {
private:
   property ItemType myField;

public:
   property ItemType MyProperty {
      ItemType get() {
         return myField;
      }
      void set(ItemType value) {
         myField = value;
      }
   }
};

int main() {
   MyClass<String^>^ c = gcnew MyClass<String^>();
   MyClass<int>^ c1 = gcnew MyClass<int>();

   c->MyProperty = "John";
   c1->MyProperty = 234;

   Console::Write("{0}, {1}", c->MyProperty, c1->MyProperty);
}
```

```Output
John, 234
```

## <a name="example"></a>例

次の例では、イベントを持つジェネリック クラスを示します。

```cpp
// generics_generic_with_event.cpp
// compile with: /clr
// Declare a generic class with an event and
// invoke events.
using namespace System;

// declare delegates
generic <typename ItemType>
delegate void ClickEventHandler(ItemType);

// generic class that defines events
generic <typename ItemType>
ref class EventSource {
public:
   // declare the event OnClick
   event ClickEventHandler<ItemType>^ OnClick;
   void FireEvents(ItemType item) {
      // raises events
      OnClick(item);
   }
};

// generic class that defines methods that will called when
// event occurs
generic <typename ItemType>
ref class EventReceiver {
public:
   void OnMyClick(ItemType item) {
   Console::WriteLine("OnClick: {0}", item);
   }
};

int main() {
   EventSource<String^>^ MyEventSourceString =
                   gcnew EventSource<String^>();
   EventSource<int>^ MyEventSourceInt = gcnew EventSource<int>();
   EventReceiver<String^>^ MyEventReceiverString =
                   gcnew EventReceiver<String^>();
   EventReceiver<int>^ MyEventReceiverInt = gcnew EventReceiver<int>();

   // hook handler to event
   MyEventSourceString->OnClick += gcnew ClickEventHandler<String^>(
       MyEventReceiverString, &EventReceiver<String^>::OnMyClick);
   MyEventSourceInt->OnClick += gcnew ClickEventHandler<int>(
             MyEventReceiverInt, &EventReceiver<int>::OnMyClick);

   // invoke events
   MyEventSourceString->FireEvents("Hello");
   MyEventSourceInt->FireEvents(112);

   // unhook handler to event
   MyEventSourceString->OnClick -= gcnew ClickEventHandler<String^>(
        MyEventReceiverString, &EventReceiver<String^>::OnMyClick);
   MyEventSourceInt->OnClick -= gcnew ClickEventHandler<int>(
        MyEventReceiverInt, &EventReceiver<int>::OnMyClick);
}
```

## <a name="generic-structs"></a>ジェネリック構造体

ジェネリック構造体の宣言との規則は、Visual C の言語リファレンスに記載されている相違点を除いて、ジェネリック クラスのものと同じです。

## <a name="example"></a>例

次の例は、ジェネリック構造体を宣言`MyGenStruct`、1 つのフィールド`myField`、さまざまな種類の値を割り当てます (**int**、**二重**、 `String^`) このフィールドにします。

```cpp
// generics_generic_struct1.cpp
// compile with: /clr
using namespace System;

generic <typename ItemType>
ref struct MyGenStruct {
public:
   ItemType myField;

   ItemType AssignValue(ItemType item) {
      myField = item;
      return myField;
   }
};

int main() {
   int myInt = 123;
   MyGenStruct<int>^ myIntObj = gcnew MyGenStruct<int>();
   myIntObj->AssignValue(myInt);
   Console::WriteLine("The field is assigned the integer value: {0}",
            myIntObj->myField);

   double myDouble = 0.123;
   MyGenStruct<double>^ myDoubleObj = gcnew MyGenStruct<double>();
   myDoubleObj->AssignValue(myDouble);
   Console::WriteLine("The field is assigned the double value: {0}",
            myDoubleObj->myField);

   String^ myString = "Hello Generics!";
   MyGenStruct<String^>^ myStringObj = gcnew MyGenStruct<String^>();
   myStringObj->AssignValue(myString);
   Console::WriteLine("The field is assigned the string: {0}",
            myStringObj->myField);
}
```

```Output
The field is assigned the integer value: 123
The field is assigned the double value: 0.123
The field is assigned the string: Hello Generics!
```

## <a name="see-also"></a>関連項目

[ジェネリック](../windows/generics-cpp-component-extensions.md)