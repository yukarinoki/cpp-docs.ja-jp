---
title: bad_typeid 例外
ms.date: 10/04/2019
f1_keywords:
- bad_typeid
- bad_typeid_cpp
helpviewer_keywords:
- bad_typeid exception
- exceptions [C++], bad_typeid
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
ms.openlocfilehash: 3e01f97c67803408c9ce5bf056e3e9ed4746d259
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229169"
---
# <a name="bad_typeid-exception"></a>bad_typeid 例外

のオペランドが NULL ポインターの場合、 [typeid 演算子](../cpp/typeid-operator.md)によって**bad_typeid**例外がスローされ **`typeid`** ます。

## <a name="syntax"></a>構文

```
catch (bad_typeid)
   statement
```

## <a name="remarks"></a>解説

**Bad_typeid**のインターフェイスは次のとおりです。

```cpp
class bad_typeid : public exception
{
public:
   bad_typeid();
   bad_typeid(const char * _Message = "bad typeid");
   bad_typeid(const bad_typeid &);
   virtual ~bad_typeid();

   bad_typeid& operator=(const bad_typeid&);
   const char* what() const;
};
```

次の例は、 **`typeid`** **bad_typeid**例外をスローする演算子を示しています。

```cpp
// expre_bad_typeid.cpp
// compile with: /EHsc /GR
#include <typeinfo>
#include <iostream>

class A{
public:
   // object for class needs vtable
   // for RTTI
   virtual ~A();
};

using namespace std;
int main() {
A* a = NULL;

try {
   cout << typeid(*a).name() << endl;  // Error condition
   }
catch (bad_typeid){
   cout << "Object is NULL" << endl;
   }
}
```

## <a name="output"></a>出力

```Output
Object is NULL
```

## <a name="see-also"></a>関連項目

[実行時の型情報](../cpp/run-time-type-information.md)\
[キーワード](../cpp/keywords-cpp.md)
