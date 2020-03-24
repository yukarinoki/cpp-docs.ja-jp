---
title: '論理 OR 演算子: ||'
ms.date: 06/14/2018
f1_keywords:
- '||'
helpviewer_keywords:
- OR operator [C++], logical
- '|| operator'
- OR operator
- logical OR operator
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
ms.openlocfilehash: 94b2bc024dd7223ac7adacc72924f5ee289bab37
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178081"
---
# <a name="logical-or-operator-"></a>論理 OR 演算子: ||

## <a name="syntax"></a>構文

> 論理式*または式* **||** の*論理 and 式*

## <a name="remarks"></a>解説

論理 OR 演算子 ( **||** ) は、両方のオペランドが true の場合はブール値 true を返し、それ以外の場合は FALSE を返します。 オペランドは、評価の前に**ブール**型に暗黙的に変換され、結果は**bool**型になります。 論理 OR の結合規則は左から右です。

論理 OR 演算子のオペランドが同じ型である必要はありませんが、整数型またはポインター型である必要があります。 オペランドは一般に関係式または等価式です。

最初のオペランドが完全に評価され、すべての副作用が完了した後で、論理 OR 式の評価が続行されます。

2 番目のオペランドは、最初のオペランドが false (0) と評価された場合にのみ、評価されます。 これにより、論理 OR 式が true の場合に 2 番目のオペランドの無駄な評価が行われないようになっています。

```cpp
printf( "%d" , (x == w || x == y || x == z) );
```

上の例では、`x` が `w`、`y`、または `z` と等しい場合、`printf` 関数の 2 番目の引数が true に評価され、値 1 が出力されます。 それ以外の場合は、false と評価され、値 0 が出力されます。 条件の 1 つが true と評価されると、直ちに評価が終了します。

## <a name="operator-keyword-for-124124"></a>の Operator キーワード&#124;&#124;

**Or**演算子は **||** に相当するテキストです。 プログラムで**or**演算子にアクセスするには、次の2つの方法があります。ヘッダーファイル \<iso646 > を含めるか、または[/za](../build/reference/za-ze-disable-language-extensions.md) (言語拡張機能を無効にする) コンパイラオプションを指定してコンパイルします。

## <a name="example"></a>例

```cpp
// expre_Logical_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate logical OR
#include <iostream>
using namespace std;
int main() {
   int a = 5, b = 10, c = 15;
   cout  << boolalpha
         << "The true expression "
         << "a < b || b > c yields "
         << (a < b || b > c) << endl
         << "The false expression "
         << "a > b || b > c yields "
         << (a > b || b > c) << endl;
}
```

## <a name="see-also"></a>参照

[C++組み込み演算子の優先順位と結合規則](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 論理演算子](../c-language/c-logical-operators.md)
