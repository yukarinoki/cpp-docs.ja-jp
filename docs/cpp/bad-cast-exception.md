---
description: '詳細情報: bad_cast 例外'
title: bad_cast 例外
ms.date: 10/04/2019
f1_keywords:
- bad_cast
- bad_cast_cpp
helpviewer_keywords:
- exceptions [C++], bad_cast
- bad_cast keyword [C++]
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
ms.openlocfilehash: 40408128bd1c90feff34e8ea1ce8bf7a3c0d56cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255692"
---
# <a name="bad_cast-exception"></a>bad_cast 例外

**Bad_cast** 例外は、 **`dynamic_cast`** 参照型へのキャストが失敗した結果として、演算子によってスローされます。

## <a name="syntax"></a>構文

```
catch (bad_cast)
   statement
```

## <a name="remarks"></a>解説

**Bad_cast** のインターフェイスは次のとおりです。

```cpp
class bad_cast : public exception
```

次のコードには、bad_cast 例外をスローする、失敗したの例が含まれてい **`dynamic_cast`** ます。 

```cpp
// expre_bad_cast_Exception.cpp
// compile with: /EHsc /GR
#include <typeinfo>
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

この例外がスローされるのは、キャストされているオブジェクト (図形) が指定されたキャスト型 (Circle) から派生していないためです。 例外を回避するには、`main` に次の宣言を追加します。

```cpp
Circle circle_instance;
Circle& ref_circle = circle_instance;
```

次に、ブロック内のキャストの意味を次のように逆にし **`try`** ます。

```cpp
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);
```

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[bad_cast](#bad_cast)|`bad_cast` 型のオブジェクトのコンストラクター。|

### <a name="functions"></a>関数

|機能|説明|
|-|-|
|[結果](#what)|TBD|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[operator =](#op_eq)|ある `bad_cast` オブジェクトを別のオブジェクトに代入する代入演算子。|

## <a name="bad_cast"></a><a name="bad_cast"></a> bad_cast

`bad_cast` 型のオブジェクトのコンストラクター。

```cpp
bad_cast(const char * _Message = "bad cast");
bad_cast(const bad_cast &);
```

## <a name="operator"></a><a name="op_eq"></a> operator =

ある `bad_cast` オブジェクトを別のオブジェクトに代入する代入演算子。

```cpp
bad_cast& operator=(const bad_cast&) noexcept;
```

## <a name="what"></a><a name="what"></a> 結果

```cpp
const char* what() const noexcept override;
```

## <a name="see-also"></a>関連項目

[dynamic_cast 演算子](../cpp/dynamic-cast-operator.md)\
[Keywords](../cpp/keywords-cpp.md)\
[例外とエラー処理に関する最新の C++ のベストプラクティス](../cpp/errors-and-exception-handling-modern-cpp.md)
