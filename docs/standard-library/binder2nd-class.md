---
description: '詳細情報: binder2nd クラス'
title: binder2nd クラス
ms.date: 02/21/2019
f1_keywords:
- functional/std::binder2nd
helpviewer_keywords:
- binder2nd class
ms.assetid: b2a9c1d1-dfc4-4ca9-a10e-ae84e195a62d
ms.openlocfilehash: a3c76fcea22045ee7e723ad3ad51390c39f602ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325493"
---
# <a name="binder2nd-class"></a>binder2nd クラス

二項関数の2番目の引数を指定された値にバインドすることによって、二項関数オブジェクトを単項関数オブジェクトに変換するコンストラクターを提供するクラステンプレート。 C++ 11 では非推奨となりました。 C++ 17 では削除されています。

## <a name="syntax"></a>構文

```cpp
template <class Operation>
class binder2nd
    : public unaryFunction <typename Operation::first_argument_type,
    typename Operation::result_type>
{
    typedef typename Operation::argument_type argument_type;
    typedef typename Operation::result_type result_type;
    binder2nd(
        const Operation& func,
        const typename Operation::second_argument_type& right);

    result_type operator()(const argument_type& left) const;
    result_type operator()(argument_type& left) const;
};
```

### <a name="parameters"></a>パラメーター

*func*\
単項関数オブジェクトに変換する二項関数オブジェクト。

*そうです*\
二項関数オブジェクトの 2 つ目の引数がバインドされている値。

*左側*\
調整後の二項オブジェクトが 2 つ目の引数の固定値と比較する引数の値。

## <a name="return-value"></a>戻り値

二項関数オブジェクトの2番目の引数を値 *right* にバインドした結果として生成される単項関数オブジェクト。

## <a name="remarks"></a>解説

クラステンプレートには、バイナリ関数オブジェクト *func* のコピー `op` と、の *right* のコピーが格納され `value` ます。 そのメンバー関数は、 `operator()` を返すように定義さ `op(left, value)` れています。

*Func* が型のオブジェクトで、 `Operation` c が定数である場合、 [bind2nd](../standard-library/functional-functions.md#bind2nd) `(func, c)` は `binder2nd` クラスコンストラクターに相当し、 `binder2nd<Operation>(func, c)` さらに便利です。

## <a name="example"></a>例

```cpp
// functional_binder2nd.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    // Count the number of integers > 10 in the vector
    vector<int>::iterator::difference_type result1;
    result1 = count_if(v1.begin(), v1.end(),
        binder2nd<greater<int> >(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    // Compare using binder1st fixing 1st argument:
    // count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(),
        binder1st<greater<int> >(greater<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 less than 10 is: 2.
```
