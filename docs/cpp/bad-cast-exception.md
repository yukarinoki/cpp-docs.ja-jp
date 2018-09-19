---
title: bad_cast 例外 |Microsoft Docs
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
ms.openlocfilehash: 3bd5bb63e075303856d444cb08c2c1f3abe990b0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46083939"
---
# <a name="badcast-exception"></a>bad_cast 例外

**Bad_cast**によって例外がスローされた、 **dynamic_cast**参照型へのキャストが失敗の結果として演算子。

## <a name="syntax"></a>構文

```
catch (bad_cast)
   statement
```

## <a name="remarks"></a>Remarks

インターフェイスを**bad_cast**は。

```cpp
class bad_cast : public exception {
public:
   bad_cast(const char * _Message = "bad cast");
   bad_cast(const bad_cast &);
   virtual ~bad_cast();
};
```

次のコードは、失敗した例を含む**dynamic_cast**がスローされます、 **bad_cast**例外。

```cpp
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

```cpp
Circle circle_instance;
Circle& ref_circle = circle_instance;
```

キャストの意味を反転し、**お試しください**ようブロックします。

```cpp
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);
```

## <a name="see-also"></a>関連項目

[dynamic_cast 演算子](../cpp/dynamic-cast-operator.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[C++ 例外処理](../cpp/cpp-exception-handling.md)