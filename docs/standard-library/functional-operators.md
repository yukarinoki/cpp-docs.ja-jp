---
title: '&lt;functional&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- functional/std::operator!=
- functional/std::operator==
helpviewer_keywords:
- functional operators
ms.assetid: d4b3c760-f3e2-4b65-bdaa-d42e8dd6f5e1
ms.openlocfilehash: b396e5c692129821c0deb9aef9469a5c54e600b0
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78876349"
---
# <a name="ltfunctionalgt-operators"></a>&lt;functional&gt; 演算子

## <a name="op_eq_eq"></a>operator = =

呼び出し可能オブジェクトが空かどうかをテストします。

```cpp
template <class Fty>
    bool operator==(const function<Fty>& f, null_ptr_type npc);

template <class Fty>
    bool operator==(null_ptr_type npc, const function<Fty>& f);
```

### <a name="parameters"></a>パラメーター

*Fty*\
ラップする関数の型。

*f*\
関数オブジェクト

*npc*\
null ポインター

### <a name="remarks"></a>解説

どちらの演算子も、`function` オブジェクトへの参照である引数と null ポインター定数である引数を受け取ります。 `function` オブジェクトが空の場合にのみ、両方とも true を返します。

### <a name="example"></a>例

```cpp
// std__functional__operator_eq.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
{
    return (-val);
}

int main()
{
    std::function<int(int)> fn0;
    std::cout << std::boolalpha << "empty == "
        << (fn0 == 0) << std::endl;

    std::function<int(int)> fn1(neg);
    std::cout << std::boolalpha << "empty == "
        << (fn1 == 0) << std::endl;

    return (0);
}
```

```Output
empty == true
empty == false
```

## <a name="op_neq"></a>operator! =

呼び出し可能オブジェクトが空かどうかをテストします。

```cpp
template <class Fty>
    bool operator!=(const function<Fty>& f, null_ptr_type npc);

template <class Fty>
    bool operator!=(null_ptr_type npc, const function<Fty>& f);
```

### <a name="parameters"></a>パラメーター

*Fty*\
ラップする関数の型。

*f*\
関数オブジェクト

*npc*\
null ポインター

### <a name="remarks"></a>解説

どちらの演算子も、`function` オブジェクトへの参照である引数と null ポインター定数である引数を受け取ります。 `function` オブジェクトが空ではない場合にのみ、両方とも true を返します。

### <a name="example"></a>例

```cpp
// std__functional__operator_ne.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn0;
    std::cout << std::boolalpha << "not empty == "
        << (fn0 != 0) << std::endl;

    std::function<int (int)> fn1(neg);
    std::cout << std::boolalpha << "not empty == "
        << (fn1 != 0) << std::endl;

    return (0);
    }
```

```Output
not empty == false
not empty == true
```
