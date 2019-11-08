---
title: ポインター (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- declarators, pointers
- declarations, pointers
- pointers [C++]
- pointers, declarations
ms.assetid: 595387c5-8e58-4670-848f-344c7caf985e
ms.openlocfilehash: a258a71b8b89643ee98785ee9dfbf30cdf128db7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223067"
---
# <a name="pointers-c"></a>ポインター (C++)

ポインターは次の順序で宣言します。

> \[*storage-class-specifiers*] \[*cv-qualifiers*] *type-specifiers* \[*ms-modifier*] *declarator* **;**

任意の有効なポインター宣言子を使用できます*宣言子*します。 単純なポインター宣言子の構文は、次のとおりです。

> __\*__ \[*cv-qualifiers*] *identifier* \[ **=** *expression*]

1. 宣言指定子:

   - ストレージ クラスの指定子 (省略可能)。 詳細については、次を参照してください。[指定子](../cpp/specifiers.md)します。

   - 省略可能な**const**または**揮発性**指されるオブジェクトの型に適用するキーワード。

   - 型指定子: ポイントされるオブジェクトの型を表す型の名前。

1. 宣言子:

   - オプションの Microsoft 固有の修飾子。 詳細については、次を参照してください。 [Microsoft 固有の修飾子](../cpp/microsoft-specific-modifiers.md)します。

   - __\*__ 演算子。

   - 省略可能な**const**または**揮発性**ポインター自体に適用するキーワード。

   - 識別子。

   - 初期化子 (省略可能)。

関数へのポインターの宣言子は次のようになります。

> __(\*__  \[ *cv 修飾子*]*識別子* **) (** *引数リスト* **)** \[ *cv 修飾子*] \[*例外仕様*] \[ **=** *式*] **;**

ポインターの配列の場合、構文は次のようになります。

> __\*__ *identifier* **\[** \[*constant-expression*] **]**

1 つの宣言内で、宣言指定子の後ろのコンマ区切りリストとして、複数の宣言子とその初期化子をまとめて指定することができます。

ポインター宣言の簡単な例は次のとおりです。

```cpp
char *pch;
```

前の宣言を指定する`pch`型のオブジェクトを指す**char**します。

さらに複雑な例を次に示します。

```cpp
static unsigned int * const ptr;
```

前の宣言を指定する`ptr`型のオブジェクトへの定数ポインターは、**unsigned int**静的ストレージ存続期間。

次の例は、複数のポインターを宣言および初期化する方法を示しています。

```cpp
static int *p = &i, *q = &j;
```

ポインターの p と q が型のオブジェクトへのポイントに前の例では、 **int**されそれぞれ i と j のアドレスに初期化されます。  ストレージ クラス指定子**静的**両方のポインターに適用されます。

## <a name="example"></a>例

```cpp
// pointer.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   int i = 1, j = 2; // local variables on the stack
   int *p;

   // a pointer may be assigned to "point to" the value of
   // another variable using the & (address of) operator
   p = & j;

   // since j was on the stack, this address will be somewhere
   // on the stack.  Pointers are printed in hex format using
   // %p and conventionally marked with 0x.
   printf_s("0x%p\n",  p);

   // The * (indirection operator) can be read as "the value
   // pointed to by".
   // Since p is pointing to j, this should print "2"
   printf_s("0x%p %d\n",  p, *p);

   // changing j will change the result of the indirection
   // operator on p.
   j = 7;
   printf_s("0x%p %d\n",  p, *p );

   // The value of j can also be changed through the pointer
   // by making an assignment to the dereferenced pointer
   *p = 10;
   printf_s("j is %d\n", j); // j is now 10

   // allocate memory on the heap for an integer,
   // initialize to 5
   p = new int(5);

   // print the pointer and the object pointed to
   // the address will be somewhere on the heap
   printf_s("0x%p %d\n",  p, *p);

   // free the memory pointed to by p
   delete p;

   // At this point, dereferencing p with *p would trigger
   // a runtime access violation.

   // Pointer arithmetic may be done with an array declared
   // on the stack or allocated on the heap with new.
   // The increment operator takes into account the size
   // of the objects pointed to.
   p = new int[5];
   for (i = 0; i < 5; i++, p++) {
      *p = i * 10;
      printf_s("0x%p %d\n", p, *p);
   }

   // A common expression seen is dereferencing in combination
   // with increment or decrement operators, as shown here.
   // The indirection operator * takes precedence over the
   // increment operator ++.
   // These are particularly useful in manipulating char arrays.
   char s1[4] = "cat";
   char s2[4] = "dog";
   char* p1 = s1;
   char* p2 = s2;

   // the following is a string copy operation
   while (*p1++ = *p2++);

   // s2 was copied into s1, so now they are both equal to "dog"
   printf_s("%s %s", s1, s2);
}
```

```Output
0x0012FEC8
0x0012FEC8 2
0x0012FEC8 7
j is 10
0x00320850 5
0x00320850 0
0x00320854 10
0x00320858 20
0x0032085C 30
0x00320860 40
dog dog
```

## <a name="example"></a>例

別の例として、データ構造 (この場合、リンク リスト) でのポインターの使用を示します。

```cpp
// pointer_linkedlist.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

struct NewNode {
   NewNode() : node(0){}
   int i;
   NewNode * node;
};

void WalkList(NewNode * ptr) {
   if (ptr != 0) {
      int i = 1;
      while (ptr->node != 0 ) {
         cout << "node " << i++ << " = " << ptr->i << endl;
         ptr = ptr->node;
      }
      cout << "node " << i++ << " = " << ptr->i << endl;
   }
}

void AddNode(NewNode ** ptr) {
   NewNode * walker = 0;
   NewNode * MyNewNode = new NewNode;
   cout << "enter a number: " << endl;
   cin >> MyNewNode->i;

   if (*ptr == 0)
      *ptr = MyNewNode;
   else  {
      walker = *ptr;
      while (walker->node != 0)
         walker = walker->node;

      walker->node = MyNewNode;
   }
}

int main() {
   char ans = ' ';
   NewNode * ptr = 0;
   do {
      cout << "a (add node)  d (display list)  q (quit)" << endl;
      cin >> ans;
      switch (ans) {
      case 'a':
         AddNode(&ptr);
         break;
      case 'd':
         WalkList(ptr);
         break;
      }
   } while (ans != 'q');
}
```

```Output
a
45
d
a
789
d
qa (add node)  d (display list)  q (quit)
enter a number:
a (add node)  d (display list)  q (quit)
node 1 = 45
a (add node)  d (display list)  q (quit)
enter a number:
a (add node)  d (display list)  q (quit)
node 1 = 45
node 2 = 789
a (add node)  d (display list)  q (quit)
```

## <a name="see-also"></a>関連項目

[間接演算子: *](../cpp/indirection-operator-star.md)<br/>
[address-of 演算子: &](../cpp/address-of-operator-amp.md)
