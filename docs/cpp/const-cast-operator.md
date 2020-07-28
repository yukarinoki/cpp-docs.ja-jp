---
title: const_cast 演算子
ms.date: 11/04/2016
f1_keywords:
- const_cast_cpp
helpviewer_keywords:
- const_cast keyword [C++]
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
ms.openlocfilehash: d2711142e4aa73cc0119949876e7e593067cd45d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180343"
---
# <a name="const_cast-operator"></a>const_cast 演算子

クラスから**const**、 **volatile**、および **__unaligned**属性を削除します。

## <a name="syntax"></a>構文

```
const_cast <type-id> (expression)
```

## <a name="remarks"></a>解説

オブジェクト型へのポインターまたはデータメンバーへのポインターは、 **const**、 **volatile**、および **__unaligned**修飾子を除き、同じである型に明示的に変換できます。 ポインターと参照の場合、結果は元のオブジェクトを参照します。 データ メンバーへのポインターの場合、結果は元の (キャストされていない) ポインターが指していたデータ メンバーと同じメンバーを参照します。 参照されるオブジェクトの型によっては、結果のポインター、参照、またはデータ メンバーへのポインターを通じた書き込み操作で未定義の動作が発生する可能性があります。

**Const_cast**演算子を使用して、定数変数の定数状態を直接オーバーライドすることはできません。

**Const_cast**演算子は、null ポインター値を変換先の型の null ポインター値に変換します。

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

**Const_cast**が含まれている行では、**この**ポインターのデータ型は `const CCTest *`です。 **Const_cast**演算子は、**この**ポインターのデータ型を `CCTest *`に変更して、メンバー `number` を変更できるようにします。 キャストは、そのキャストが発生したステートメントの残り時間の間だけ持続します。

## <a name="see-also"></a>参照

[キャスト演算子](../cpp/casting-operators.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
