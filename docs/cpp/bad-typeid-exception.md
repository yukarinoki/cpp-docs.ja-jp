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
ms.openlocfilehash: 6410f27342ed40300ff236ee1c47ada740255f84
ms.sourcegitcommit: c51b2c665849479fa995bc3323a22ebe79d9d7ce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "71998806"
---
# <a name="bad_typeid-exception"></a>bad_typeid 例外

**Typeid**のオペランドが NULL ポインターの場合、 [typeid 演算子](../cpp/typeid-operator.md)によって**bad_typeid**例外がスローされます。

## <a name="syntax"></a>構文

```
catch (bad_typeid)
   statement
```

## <a name="remarks"></a>コメント

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

次の例は、 **bad_typeid**例外をスローする**typeid**演算子を示しています。

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

## <a name="output"></a>[出力]

```Output
Object is NULL
```

## <a name="see-also"></a>関連項目

[ランタイム型情報](../cpp/run-time-type-information.md)\
[キーワード](../cpp/keywords-cpp.md)
