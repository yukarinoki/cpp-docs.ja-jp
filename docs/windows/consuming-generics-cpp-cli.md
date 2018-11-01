---
title: ジェネリックの使用 (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- generics [C++], consuming from .NET languages
ms.assetid: e6330ef5-e907-432e-b527-7a22f5899639
ms.openlocfilehash: 3fa63ae0e75f4c754c8ff2dbdeb0d662246f00dc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551737"
---
# <a name="consuming-generics-ccli"></a>ジェネリックの使用 (C++/CLI)

.NET (または UWP) の 1 つの言語で作成されたジェネリックは、他の言語で使用することがあります。 テンプレートとは異なり、コンパイル済みアセンブリのジェネリックはまだジェネリックは残ります。 したがって、ジェネリック型が定義されているアセンブリとは異なる言語であっても、別のアセンブリでは、ジェネリック型をインスタンス化いずれかの可能性があります。

## <a name="example"></a>例

### <a name="description"></a>説明

この例では、c# で定義されたジェネリック クラスを使用します。

### <a name="code"></a>コード

```cs
// consuming_generics_from_other_NET_languages.cs
// compile with: /target:library
// a C# program
public class CircularList<ItemType> {
   class ListNode    {
      public ItemType m_item;
      public ListNode next;
      public ListNode(ItemType item) {
         m_item = item;
      }
   }

   ListNode first, last;

   public CircularList() {}

   public void Add(ItemType item) {
      ListNode newnode = new ListNode(item);
      if (first == null) {
         first = last = newnode;
         first.next = newnode;
         last.next = first;
      }
      else {
         newnode.next = first;
         first = newnode;
         last.next = first;
      }
   }

   public void Remove(ItemType item) {
      ListNode iter = first;
      if (first.m_item.Equals( item )) {
         first =
         last.next = first.next;
      }
      for ( ; iter != last ; iter = iter.next )
         if (iter.next.m_item.Equals( item )) {
              if (iter.next == last)
                  last = iter;
              iter.next = iter.next.next;
              return;
          }
   }

   public void PrintAll() {
      ListNode iter = first;
      do {
         System.Console.WriteLine( iter.m_item );
         iter = iter.next;
      } while (iter != last);
   }
}
```

## <a name="example"></a>例

### <a name="description"></a>説明

この例では、c# で作成されたアセンブリを使用します。

### <a name="code"></a>コード

```cpp
// consuming_generics_from_other_NET_languages_2.cpp
// compile with: /clr
#using <consuming_generics_from_other_NET_languages.dll>
using namespace System;
class NativeClass {};
ref class MgdClass {};

int main() {
   CircularList<int>^ circ1 = gcnew CircularList<int>();
   CircularList<MgdClass^>^ circ2 = gcnew CircularList<MgdClass^>();

   for (int i = 0 ; i < 100 ; i += 10)
      circ1->Add(i);
   circ1->Remove(50);
   circ1->PrintAll();
}
```

```Output
90
80
70
60
40
30
20
10
```

## <a name="see-also"></a>関連項目

[ジェネリック](../windows/generics-cpp-component-extensions.md)