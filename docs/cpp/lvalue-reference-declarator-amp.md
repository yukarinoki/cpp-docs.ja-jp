---
title: '左辺値参照宣言子: &amp;'
ms.date: 11/04/2016
f1_keywords:
- '&'
helpviewer_keywords:
- reference operator
- '& operator [C++], reference operator'
ms.assetid: edf0513d-3dcc-4663-b276-1269795dda51
ms.openlocfilehash: 595f2b683d2abb4cdc8a328dc6e86338ab90f214
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178068"
---
# <a name="lvalue-reference-declarator-amp"></a>左辺値参照宣言子: &amp;

オブジェクトのアドレスを保持しますが、オブジェクトのように構文的に実行されます。

## <a name="syntax"></a>構文

```
type-id & cast-expression
```

## <a name="remarks"></a>解説

lvalue 参照は、オブジェクトの別名と考えることができます。 左辺値参照の宣言は、参照宣言子が続く指定子のオプションのリストから構成されます。 参照は初期化する必要があり、変更できません。

アドレスを特定のポインター型に変換できるオブジェクトは、類似した参照型にも変換できます。 たとえば、アドレスを `char *` 型に変換できるオブジェクトは、`char &` 型にも変換できます。

参照宣言を[アドレス演算子](../cpp/address-of-operator-amp.md)の使用と混同しないようにしてください。 `&`*識別子*の前に**int**や**char**などの型がある場合は、*識別子*が型への参照として宣言されます。 `&`*識別子*の前に型がない場合は、アドレス演算子の使用法が使用されます。

## <a name="example"></a>例

次の例は、`Person` オブジェクトの宣言による参照宣言子と、そのオブジェクトへの参照を示します。 `rFriend` は `myFriend` への参照であるため、いずれかの変数を更新すると同じオブジェクトが変更されます。

```cpp
// reference_declarator.cpp
// compile with: /EHsc
// Demonstrates the reference declarator.
#include <iostream>
using namespace std;

struct Person
{
    char* Name;
    short Age;
};

int main()
{
   // Declare a Person object.
   Person myFriend;

   // Declare a reference to the Person object.
   Person& rFriend = myFriend;

   // Set the fields of the Person object.
   // Updating either variable changes the same object.
   myFriend.Name = "Bill";
   rFriend.Age = 40;

   // Print the fields of the Person object to the console.
   cout << rFriend.Name << " is " << myFriend.Age << endl;
}
```

```Output
Bill is 40
```

## <a name="see-also"></a>参照

[参照](../cpp/references-cpp.md)<br/>
[参照型関数の引数](../cpp/reference-type-function-arguments.md)<br/>
[参照型関数の戻り値](../cpp/reference-type-function-returns.md)<br/>
[ポインターへの参照](../cpp/references-to-pointers.md)
