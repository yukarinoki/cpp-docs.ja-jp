---
title: bad_cast 例外
ms.date: 11/04/2016
f1_keywords:
- bad_cast
- bad_cast_cpp
helpviewer_keywords:
- exceptions [C++], bad_cast
- bad_cast keyword [C++]
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
ms.openlocfilehash: b40f64671e7c259b7dc04b31a11d20d0fc76c5c4
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68242389"
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
class bad_cast : public exception
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

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[bad_cast](#bad_cast)|`bad_cast` 型のオブジェクトのコンストラクター。|

### <a name="functions"></a>関数

|関数|説明|
|-|-|
|[どのような](#what)|TBD|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator=](#op_eq)|代入演算子を 1 つ割り当てる`bad_cast`を別のオブジェクト。|

## <a name="bad_cast"></a> bad_cast

`bad_cast` 型のオブジェクトのコンストラクター。

```cpp
bad_cast(const char * _Message = "bad cast");
bad_cast(const bad_cast &);
```

## <a name="op_eq"></a> 演算子 =

代入演算子を 1 つ割り当てる`bad_cast`を別のオブジェクト。

```cpp
bad_cast& operator=(const bad_cast&) noexcept;
```

## <a name="what"></a> どのような

```cpp
const char* what() const noexcept override;
```

## <a name="see-also"></a>関連項目

[dynamic_cast 演算子](../cpp/dynamic-cast-operator.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[C++ 例外処理](../cpp/cpp-exception-handling.md)