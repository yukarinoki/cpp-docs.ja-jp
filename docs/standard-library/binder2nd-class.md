---
title: binder2nd クラス
ms.date: 02/21/2019
f1_keywords:
- functional/std::binder2nd
helpviewer_keywords:
- binder2nd class
ms.assetid: b2a9c1d1-dfc4-4ca9-a10e-ae84e195a62d
ms.openlocfilehash: 5f59887e6c9d2965a6c8680f17a40c5bd93869c0
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68243349"
---
# <a name="binder2nd-class"></a>binder2nd クラス

指定した値に二項関数の 2 番目の引数をバインドして二項関数オブジェクトを単項関数オブジェクトに変換するコンストラクターを提供するテンプレート クラス。 C++ 11、c++ 17 では削除では、非推奨とされます。

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
        const Operation& Func,
        const typename Operation::second_argument_type& right);

    result_type operator()(const argument_type& left) const;
    result_type operator()(argument_type& left) const;
};
```

### <a name="parameters"></a>パラメーター

*Func*\
単項関数オブジェクトに変換する二項関数オブジェクト。

*そうです*\
二項関数オブジェクトの 2 つ目の引数がバインドされている値。

*左*\
調整後の二項オブジェクトが 2 つ目の引数の固定値と比較する引数の値。

## <a name="return-value"></a>戻り値

値に二項関数オブジェクトの 2 番目の引数をバインドに起因する単項関数オブジェクト*右*します。

## <a name="remarks"></a>Remarks

テンプレート クラスは、二項関数オブジェクト _ のコピーを格納*Func*で`op`のコピーと*右*で`value`します。 そのメンバー関数`operator()`返すよう**op**(`left`、**値**)。

場合`Func`型のオブジェクトは、 `Operation` c は定数、 [bind2nd](../standard-library/functional-functions.md#bind2nd) (`Func`、 `c`) と同じですが、`binder2nd`クラスのコンス トラクター `binder2nd` \< **操作**> (`Func`、 `c`) でより便利です。

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
