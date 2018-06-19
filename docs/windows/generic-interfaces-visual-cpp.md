---
title: ジェネリック インターフェイス (Visual C) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- generic interfaces
- interfaces, generic [C++}
ms.assetid: f3da788a-ba83-4db7-9dcf-9b95a8fb9d1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8e16a2ab8a1ee0c9255f394d033bda2a7afc2b7e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878698"
---
# <a name="generic-interfaces-visual-c"></a>ジェネリック インターフェイス (Visual C++)
クラスの型パラメーターに適用される制限は、インターフェイスの型パラメーターに適用されるものと同じです (を参照してください[ジェネリック クラス (C + + CLI)](../windows/generic-classes-cpp-cli.md))。  
  
 関数のオーバー ロードを制御するルールは、関数のジェネリック クラスまたはジェネリック インターフェイス内で同じです。  
  
 明示的なインターフェイス メンバーの実装がシンプルなインターフェイスの種類 (次の例を参照してください) と同じ方法での構築されたインターフェイス型を使用します。  
  
 インターフェイスの詳細については、次を参照してください。[インターフェイス クラス](../windows/interface-class-cpp-component-extensions.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
[attributes] generic <class-key type-parameter-identifier[, ...]>  
[type-parameter-constraints-clauses][accesibility-modifiers] interface class identifier [: base-list] {   interface-body} [declarators] ;  
```  
  
## <a name="remarks"></a>コメント  
 *属性*(省略可能)  
 追加の宣言情報。 属性と属性クラスの詳細については、属性を参照してください。  
  
 *クラス キー*  
 **クラス**または**typename**  
  
 `type-parameter-identifier(s)`  
 識別子のコンマ区切りの一覧です。  
  
 `type-parameter-constraints-clauses`  
 指定された形式の[ジェネリック型パラメーターの制約 (C + + CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md)  
  
 *アクセシビリティ修飾子*(省略可能)  
 アクセシビリティ修飾子 (例:**パブリック、プライベート**)。  
  
 *identifier*  
 インターフェイスの名前。  
  
 *情報リスト*(省略可能)  
 含む 1 つまたは複数明示的な基本インターフェイス コンマで区切られたリスト。  
  
 *インターフェイス本体*  
 インターフェイス メンバーの宣言。  
  
 *宣言子*(省略可能)  
 この型に基づく変数の宣言。  
  
## <a name="example"></a>例  
 次の例では、宣言して、ジェネリック インターフェイスをインスタンス化する方法を示します。 例では、ジェネリック インターフェイス`IList<ItemType>`が宣言されています。 2 つの汎用クラスによって実装される`List1<ItemType>`と`List2<ItemType>`、異なる実装を使用します。  
  
```  
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
 この例は、ジェネリック インターフェイスを宣言`IMyGenIface`、および 2 つの非ジェネリック インターフェイス`IMySpecializedInt`と`ImySpecializedString`、specialize を`IMyGenIface`です。 2 つの特殊なインターフェイスを実装する 2 つのクラス、`MyIntClass`と`MyStringClass`です。 この例では、ジェネリック インターフェイスを特化、ジェネリックと非ジェネリックのインターフェイスをインスタンス化およびインターフェイスで明示的に実装されたメンバーを呼び出す方法を示します。  
  
```  
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