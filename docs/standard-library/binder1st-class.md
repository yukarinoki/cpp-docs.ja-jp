---
title: binder1st クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::binder1st
dev_langs:
- C++
helpviewer_keywords:
- binder1st class
ms.assetid: 6b8ee343-c82f-48f8-867d-06f9d1d324c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a9e53d9344e56f9efc4f20b834ce31bcb05f9fbb
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44103987"
---
# <a name="binder1st-class"></a>binder1st クラス

指定した値に二項関数の 1 番目の引数をバインドして二項関数オブジェクトを単項関数オブジェクトに変換するコンストラクターを提供するテンプレート クラス。

## <a name="syntax"></a>構文

```cpp
template <class Operation>
class binder1st
    : public unaryFunction <typename Operation::second_argument_type,
                             typename Operation::result_type>
{
public:
    typedef typename Operation::argument_type argument_type;
    typedef typename Operation::result_type result_type;
    binder1st(
        const Operation& Func,
        const typename Operation::first_argument_type& left);

    result_type operator()(const argument_type& right) const;
    result_type operator()(const argument_type& right) const;

protected:
    Operation op;
    typename Operation::first_argument_type value;
};
```

### <a name="parameters"></a>パラメーター

*Func*<br/>
単項関数オブジェクトに変換する二項関数オブジェクト。

*left*<br/>
二項関数オブジェクトの最初の引数がバインドされている値。

*right*<br/>
調整後の二項オブジェクトが 2 つ目の引数の固定値と比較する引数の値。

## <a name="return-value"></a>戻り値

単項関数オブジェクト、値に二項関数オブジェクトの最初の引数をバインドに起因する*左*します。

## <a name="remarks"></a>Remarks

テンプレート クラスは、二項関数オブジェクトのコピーを格納する*Func*で`op`のコピーと*左*で`value`します。 そのメンバー関数 `operator()` は **op**( **value**, `right`) を返すように定義されています。

場合*Func*型のオブジェクトは、`Operation`と`c`が定数の場合、 [bind1st](../standard-library/functional-functions.md#bind1st) ( `Func`、 `c` ) と同じですが、`binder1st`クラスのコンス トラクター`binder1st` \< **操作**> ( `Func`、 `c` ) でより便利です。

## <a name="example"></a>例

```cpp
// functional_binder1st.cpp
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
        binder1st<less<int> >(less<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    // Compare use of binder2nd fixing 2nd argument:
    // count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(),
        binder2nd<less<int> >(less<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
\* Output:
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 less than 10 is: 2.
*\
```

## <a name="requirements"></a>要件

**ヘッダー:** \<functional>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
