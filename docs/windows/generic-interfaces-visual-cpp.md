---
title: ジェネリック インターフェイス (C +/cli CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- generic interfaces
- interfaces, generic [C++}
ms.assetid: f3da788a-ba83-4db7-9dcf-9b95a8fb9d1a
ms.openlocfilehash: 68c5a53d3de38479adbdcb49e823513f295a2095
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50493952"
---
# <a name="generic-interfaces-ccli"></a>ジェネリック インターフェイス (C +/cli CLI)

クラスの型パラメーターに適用される制限はインターフェイスの型パラメーターに適用されるものと同じ (を参照してください[ジェネリック クラス (C +/cli CLI)](../windows/generic-classes-cpp-cli.md))。

関数のオーバー ロードを制御するルールは、ジェネリック クラスまたはジェネリック インターフェイス内の関数のと同じです。

明示的なインターフェイス メンバーの実装は、単純なインターフェイスの種類 (次の例を参照してください) と同じ方法で構築されたインターフェイス型と協力します。

インターフェイスの詳細については、次を参照してください。[インターフェイス クラス](../windows/interface-class-cpp-component-extensions.md)します。

## <a name="syntax"></a>構文

```cpp
[attributes] generic <class-key type-parameter-identifier[, ...]>
[type-parameter-constraints-clauses][accesibility-modifiers] interface class identifier [: base-list] {   interface-body} [declarators] ;
```

## <a name="remarks"></a>Remarks

*属性*<br/>
(省略可能)追加の宣言情報。 属性と属性クラスの詳細については、次を参照してください。**属性**します。

*クラス キー*<br/>
**クラス**または**typename**

*type-parameter-identifier(s)*<br/>
識別子のコンマ区切りリスト。

*型パラメーター制約句*<br/>
指定された形式の[ジェネリック型パラメーターの制約 (C +/cli CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md)

*アクセシビリティ修飾子*<br/>
(省略可能)アクセシビリティ修飾子 (例:**パブリック、プライベート**)。

*identifier*<br/>
インターフェイスの名前。

*基本リスト*<br/>
(省略可能)1 つまたは複数明示的な基本インターフェイス コンマ区切りを含むリスト。

*インターフェイス本体*<br/>
インターフェイス メンバーの宣言。

*宣言子*<br/>
(省略可能)この型に基づいた変数の宣言。

## <a name="example"></a>例

次の例では、宣言して、ジェネリック インターフェイスのインスタンスを作成する方法を示します。 例では、ジェネリック インターフェイスで`IList<ItemType>`は宣言されています。 2 つのジェネリック クラスによって実装される`List1<ItemType>`と`List2<ItemType>`、異なる実装を使用します。

```cpp
// generic_interface.cpp
// compile with: /clr
using namespace System;

// An exception to be thrown by the List when
// attempting to access elements beyond the
// end of the list.
ref class ElementNotFoundException : Exception {};

// A generic List interface
generic <typename ItemType>
public interface class IList {
   ItemType MoveFirst();
   bool Add(ItemType item);
   bool AtEnd();
   ItemType Current();
   void MoveNext();
};

// A linked list implementation of IList
generic <typename ItemType>
public ref class List1 : public IList<ItemType> {
   ref class Node {
      ItemType m_item;

   public:
      ItemType get_Item() { return m_item; };
      void set_Item(ItemType value) { m_item = value; };

      Node^ next;

      Node(ItemType item) {
         m_item = item;
         next = nullptr;
      }
   };

   Node^ first;
   Node^ last;
   Node^ current;

   public:
   List1() {
      first = nullptr;
      last = first;
      current = first;
   }

   virtual ItemType MoveFirst() {
      current = first;
      if (first != nullptr)
        return first->get_Item();
      else
         return ItemType();
   }

   virtual bool Add(ItemType item) {
      if (last != nullptr) {
         last->next = gcnew Node(item);
         last = last->next;
      }
      else {
         first = gcnew Node(item);
         last = first;
         current = first;
      }
      return true;
   }

   virtual bool AtEnd() {
      if (current == nullptr )
        return true;
      else
        return false;
   }

   virtual ItemType Current() {
       if (current != nullptr)
         return current->get_Item();
       else
         throw gcnew ElementNotFoundException();
   }

   virtual void MoveNext() {
      if (current != nullptr)
       current = current->next;
      else
        throw gcnew ElementNotFoundException();
   }
};

// An array implementation of IList
generic <typename ItemType>
ref class List2 : public IList<ItemType> {
   array<ItemType>^ item_array;
   int count;
   int current;

   public:

   List2() {
      // not yet possible to declare an
      // array of a generic type parameter
      item_array = gcnew array<ItemType>(256);
      count = current = 0;
   }

   virtual ItemType MoveFirst() {
      current = 0;
      return item_array[0];
   }

   virtual bool Add(ItemType item) {
      if (count < 256)
         item_array[count++] = item;
      else
        return false;
      return true;
   }

   virtual bool AtEnd() {
      if (current >= count)
        return true;
      else
        return false;
   }

   virtual ItemType Current() {
      if (current < count)
        return item_array[current];
      else
        throw gcnew ElementNotFoundException();
   }

   virtual void MoveNext() {
      if (current < count)
         ++current;
      else
         throw gcnew ElementNotFoundException();
   }
};

// Add elements to the list and display them.
generic <typename ItemType>
void AddStringsAndDisplay(IList<ItemType>^ list, ItemType item1, ItemType item2) {
   list->Add(item1);
   list->Add(item2);
   for (list->MoveFirst(); ! list->AtEnd(); list->MoveNext())
   Console::WriteLine(list->Current());
}

int main() {
   // Instantiate both types of list.

   List1<String^>^ list1 = gcnew List1<String^>();
   List2<String^>^ list2 = gcnew List2<String^>();

   // Use the linked list implementation of IList.
   AddStringsAndDisplay<String^>(list1, "Linked List", "List1");

   // Use the array implementation of the IList.
   AddStringsAndDisplay<String^>(list2, "Array List", "List2");
}
```

```Output
Linked List
List1
Array List
List2
```

## <a name="example"></a>例

この例ではジェネリック インターフェイスを宣言`IMyGenIface`、および 2 つの非ジェネリック インターフェイス`IMySpecializedInt`と`ImySpecializedString`、特化を`IMyGenIface`します。 2 つの特殊なインターフェイスが 2 つのクラスで実装し、`MyIntClass`と`MyStringClass`します。 この例では、ジェネリック インターフェイスを特化、ジェネリックと非ジェネリックのインターフェイスをインスタンス化およびインターフェイスを明示的に実装されたメンバーを呼び出す方法を示します。

```cpp
// generic_interface2.cpp
// compile with: /clr
// Specializing and implementing generic interfaces.
using namespace System;

generic <class ItemType>
public interface class IMyGenIface {
   void Initialize(ItemType f);
};

public interface class IMySpecializedInt: public IMyGenIface<int> {
   void Display();
};

public interface class IMySpecializedString: public IMyGenIface<String^> {
   void Display();
};

public ref class MyIntClass: public IMySpecializedInt {
   int myField;

public:
   virtual void Initialize(int f) {
      myField = f;
   }

   virtual void Display() {
      Console::WriteLine("The integer field contains: {0}", myField);
   }
};

public ref struct MyStringClass: IMySpecializedString {
   String^ myField;

public:
   virtual void Initialize(String^ f) {
      myField = f;
    }

   virtual void Display() {
      Console::WriteLine("The String field contains: {0}", myField);
   }
};

int main() {
   // Instantiate the generic interface.
   IMyGenIface<int>^ myIntObj = gcnew MyIntClass();

   // Instantiate the specialized interface "IMySpecializedInt."
   IMySpecializedInt^ mySpIntObj = (IMySpecializedInt^) myIntObj;

   // Instantiate the generic interface.
   IMyGenIface<String^>^ myStringObj = gcnew MyStringClass();

   // Instantiate the specialized interface "IMySpecializedString."
   IMySpecializedString^ mySpStringObj =
            (IMySpecializedString^) myStringObj;

   // Call the explicitly implemented interface members.
   myIntObj->Initialize(1234);
   mySpIntObj->Display();

   myStringObj->Initialize("My string");
   mySpStringObj->Display();
}
```

```Output
The integer field contains: 1234
The String field contains: My string
```

## <a name="see-also"></a>関連項目

[ジェネリック](../windows/generics-cpp-component-extensions.md)