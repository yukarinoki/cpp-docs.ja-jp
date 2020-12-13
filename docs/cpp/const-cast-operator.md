---
description: 詳細については、「const_cast 演算子」を参照してください。
title: const_cast 演算子
ms.date: 11/04/2016
f1_keywords:
- const_cast_cpp
helpviewer_keywords:
- const_cast keyword [C++]
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
ms.openlocfilehash: c0c08402450773368914facb719c4ddf97b7503d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344667"
---
# <a name="const_cast-operator"></a>const_cast 演算子

クラスから、、およびの各属性を削除し **`const`** **`volatile`** **`__unaligned`** ます。

## <a name="syntax"></a>構文

```
const_cast <type-id> (expression)
```

## <a name="remarks"></a>解説

オブジェクト型またはデータメンバーへのポインターへのポインターは、、、および修飾子を除き、同じである型に明示的に変換でき **`const`** **`volatile`** **`__unaligned`** ます。 ポインターと参照の場合、結果は元のオブジェクトを参照します。 データ メンバーへのポインターの場合、結果は元の (キャストされていない) ポインターが指していたデータ メンバーと同じメンバーを参照します。 参照されるオブジェクトの型によっては、結果のポインター、参照、またはデータ メンバーへのポインターを通じた書き込み操作で未定義の動作が発生する可能性があります。

演算子を使用して、 **`const_cast`** 定数変数の定数状態を直接オーバーライドすることはできません。

演算子は、 **`const_cast`** null ポインター値を変換先の型の null ポインター値に変換します。

## <a name="example"></a>例

```cpp
// expre_const_cast_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class CCTest {
public:
   void setNumber( int );
   void printNumber() const;
private:
   int number;
};

void CCTest::setNumber( int num ) { number = num; }

void CCTest::printNumber() const {
   cout << "\nBefore: " << number;
   const_cast< CCTest * >( this )->number--;
   cout << "\nAfter: " << number;
}

int main() {
   CCTest X;
   X.setNumber( 8 );
   X.printNumber();
}
```

を含む行で **`const_cast`** は、ポインターのデータ型 **`this`** は `const CCTest *` です。 演算子は、 **`const_cast`** ポインターのデータ型 **`this`** をに変更 `CCTest *` し、メンバーを変更できるようにし `number` ます。 キャストは、そのキャストが発生したステートメントの残り時間の間だけ持続します。

## <a name="see-also"></a>関連項目

[キャスト演算子](../cpp/casting-operators.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
