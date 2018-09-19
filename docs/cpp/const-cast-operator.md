---
title: const_cast 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- const_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- const_cast keyword [C++]
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 314e8363fafa4f2a6649055f2c608cd5b7edd18c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070081"
---
# <a name="constcast-operator"></a>const_cast 演算子

削除、 **const**、**揮発性**、および **_ _unaligned**クラスから属性。

## <a name="syntax"></a>構文

```
const_cast <type-id> (expression)
```

## <a name="remarks"></a>Remarks

任意のオブジェクト型へのポインターまたはデータ メンバーへのポインターを除いて同一である型に明示的に変換できる、 **const**、**揮発性**、および **_ _unaligned**修飾子。 ポインターと参照の場合、結果は元のオブジェクトを参照します。 データ メンバーへのポインターの場合、結果は元の (キャストされていない) ポインターが指していたデータ メンバーと同じメンバーを参照します。 参照されるオブジェクトの型によっては、結果のポインター、参照、またはデータ メンバーへのポインターを通じた書き込み操作で未定義の動作が発生する可能性があります。

使用することはできません、 **const_cast**定数変数の定数のステータスを直接オーバーライドする演算子。

**Const_cast**演算子は、null ポインターの値を変換先の型の null ポインター値に変換します。

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

含む行で、 **const_cast**のデータ型、**この**ポインターが`const CCTest *`します。 **Const_cast**演算子のデータ型を変更する、**この**へのポインター `CCTest *`、メンバーを許可する`number`を変更します。 キャストは、そのキャストが発生したステートメントの残り時間の間だけ持続します。

## <a name="see-also"></a>関連項目

[キャスト演算子](../cpp/casting-operators.md)<br/>
[キーワード](../cpp/keywords-cpp.md)