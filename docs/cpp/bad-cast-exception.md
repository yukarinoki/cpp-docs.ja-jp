---
title: bad_cast 例外 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- bad_cast
- bad_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- exceptions [C++], bad_cast
- bad_cast keyword [C++]
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c09754e44b2cf1d7bda4bde35b8d76335d96711
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="badcast-exception"></a>bad_cast 例外
`bad_cast` 例外は、参照型へのキャストが失敗した結果として `dynamic_cast` 演算子によってスローされます。  
  
## <a name="syntax"></a>構文  
  
```  
catch (bad_cast)  
   statement  
```  
  
## <a name="remarks"></a>コメント  
 `bad_cast` のインターフェイスは次のとおりです。  
  
```  
class bad_cast : public exception {  
public:  
   bad_cast(const char * _Message = "bad cast");  
   bad_cast(const bad_cast &);  
   virtual ~bad_cast();  
};  
```  
  
 次のコードには、`dynamic_cast` 例外をスローする、失敗した `bad_cast` の例が含まれます。  
  
```  
// expre_bad_cast_Exception.cpp  
// compile with: /EHsc /GR  
#include <typeinfo.h>  
#include <iostream>  
  
class Shape {  
public:  
   virtual void virtualfunc() const {}  
};  
  
class Circle: public Shape {  
public:  
   virtual void virtualfunc() const {}  
};  
  
using namespace std;  
int main() {  
   Shape shape_instance;  
   Shape& ref_shape = shape_instance;  
   try {  
      Circle& ref_circle = dynamic_cast<Circle&>(ref_shape);   
   }  
   catch (bad_cast b) {  
      cout << "Caught: " << b.what();  
   }  
}  
```  
  
 キャストされているオブジェクト (Shape) が、指定したキャスト型 (Circle) から派生していないため、例外がスローされます。 例外を回避するには、`main` に次の宣言を追加します。  
  
```  
Circle circle_instance;  
Circle& ref_circle = circle_instance;  
```  
  
 次に、`try` ブロックのキャストの意味を次のように反転させます。  
  
```  
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);  
```  
  
## <a name="see-also"></a>関連項目  
 [dynamic_cast 演算子](../cpp/dynamic-cast-operator.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [C++ 例外処理](../cpp/cpp-exception-handling.md)