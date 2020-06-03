---
title: メンバーアクセス演算子:。 および-&gt;
ms.date: 11/04/2016
f1_keywords:
- .
- ->
helpviewer_keywords:
- member access, expressions
- operators [C++], member access
- dot operator (.)
- -> operator
- member access, operators
- postfix operators [C++]
- . operator
- member access
ms.assetid: f8fc3df9-d728-40c5-b384-276927f5f1b3
ms.openlocfilehash: 05bab55e1646783e0f8ab9b414d608c912f60a0f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178016"
---
# <a name="member-access-operators--and--gt"></a>メンバーアクセス演算子:。 および-&gt;

## <a name="syntax"></a>構文

```
postfix-expression . name
postfix-expression -> name
```

## <a name="remarks"></a>解説

メンバーアクセス演算子 **。** および **->** は、構造体、共用体、およびクラスのメンバーを参照するために使用されます。 メンバー アクセス式は、選択したメンバーの値と型を持ちます。

メンバー アクセス式には、次の 2 つの形式があります。

1. 最初の形式では、*後置式*は構造体、クラス、または共用体型の値を表し、 *name*は指定された構造体、共用体、またはクラスのメンバーに名前を指定します。 操作の値は*name*の値で、*後置式*が左辺値の場合は左辺値になります。

1. 2番目の形式では、*後置式*は構造体、共用体、またはクラスへのポインターを表し、 *name*は指定された構造体、共用体、またはクラスのメンバーに名前を指定します。 値は、 *name*の値で、左辺値です。 **->** 演算子はポインターを逆参照します。 したがって、式 `e->member` および `(*e).member` ( *e*はポインターを表します) は同一の結果を生成します (演算子 **->** または<strong>\*</strong>がオーバーロードされている場合を除きます)。

## <a name="example"></a>例

次の例に、メンバー アクセス演算子の両方の形式を示します。

```cpp
// expre_Selection_Operator.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

struct Date {
   Date(int i, int j, int k) : day(i), month(j), year(k){}
   int month;
   int day;
   int year;
};

int main() {
   Date mydate(1,1,1900);
   mydate.month = 2;
   cout  << mydate.month << "/" << mydate.day
         << "/" << mydate.year << endl;

   Date *mydate2 = new Date(1,1,2000);
   mydate2->month = 2;
   cout  << mydate2->month << "/" << mydate2->day
         << "/" << mydate2->year << endl;
   delete mydate2;
}
```

```Output
2/1/1900
2/1/2000
```

## <a name="see-also"></a>参照

[後置式](../cpp/postfix-expressions.md)<br/>
[C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[クラスと構造体](../cpp/classes-and-structs-cpp.md)<br/>
[構造体と共用体のメンバー](../c-language/structure-and-union-members.md)
