---
title: '左辺値参照宣言子: &amp; |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '&'
dev_langs:
- C++
helpviewer_keywords:
- reference operator
- '& operator [C++], reference operator'
ms.assetid: edf0513d-3dcc-4663-b276-1269795dda51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d16ed882b1037123963f105b1a78bf8e1023d332
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943901"
---
# <a name="lvalue-reference-declarator-amp"></a>左辺値参照宣言子: &amp;
オブジェクトのアドレスを保持しますが、オブジェクトのように構文的に実行されます。  
  
## <a name="syntax"></a>構文  
  
```  
  
type-id & cast-expression  
```  
  
## <a name="remarks"></a>Remarks  
 lvalue 参照は、オブジェクトの別名と考えることができます。 左辺値参照の宣言は、参照宣言子が続く指定子のオプションのリストから構成されます。 参照は初期化する必要があり、変更できません。  
  
 アドレスを特定のポインター型に変換できるオブジェクトは、類似した参照型にも変換できます。 たとえば、アドレスを `char *` 型に変換できるオブジェクトは、`char &` 型にも変換できます。  
  
 参照の宣言の使用を混同しないでください、 [address-of 演算子](../cpp/address-of-operator-amp.md)します。 ときに、 `&`*識別子*など、型の前が**int**または**char**、*識別子*への参照として宣言されています型。 ときに`&`*識別子*前がない型で、使用状況は、address-of 演算子の。  
  
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
  
## <a name="see-also"></a>関連項目  
 [参照](../cpp/references-cpp.md)   
 [参照型関数の引数](../cpp/reference-type-function-arguments.md)   
 [参照型関数の戻り値](../cpp/reference-type-function-returns.md)   
 [ポインターへの参照](../cpp/references-to-pointers.md)