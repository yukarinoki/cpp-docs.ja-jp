---
title: 'メンバー アクセス演算子: です。 および&gt;|Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- .
- ->
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a4af9fa780aca1bc1c1304b45d226984fbb5eb7e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201446"
---
# <a name="member-access-operators--and--gt"></a>メンバー アクセス演算子: です。 -&gt;
## <a name="syntax"></a>構文  
  
```  
postfix-expression . name  
postfix-expression -> name  
```  
  
## <a name="remarks"></a>Remarks  
 メンバー アクセス演算子**します。** **->** 構造体、共用体、およびクラスのメンバーを参照するために使用します。 メンバー アクセス式は、選択したメンバーの値と型を持ちます。  
  
 メンバー アクセス式には、次の 2 つの形式があります。  
  
1.  最初のフォームでは、*後置式*構造体、クラス、または共用体の型の値を表すと*名前*の指定された構造体、共用体、またはクラス メンバーの名前します。 操作の値はの*名前*が左辺値の場合と*後置式*左辺値です。  
  
2.  2 番目の形式で*後置式*構造体、共用体、またはクラスへのポインターを表しますと*名前*の指定された構造体、共用体、またはクラス メンバーの名前します。 値はの*名前*左辺値です。 **->** 演算子は、ポインターを逆参照します。 したがって、式`e->member`と`(*e).member`(場所*e*ポインターを表します) と同じ結果を生成する (する場合を除く演算子**->** または <strong>\*</strong>オーバー ロードされます)。  
  
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
  
## <a name="see-also"></a>関連項目  
 [後置式](../cpp/postfix-expressions.md)   
 [C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [クラスと構造体](../cpp/classes-and-structs-cpp.md)   
 [構造体と共用体のメンバー](../c-language/structure-and-union-members.md)