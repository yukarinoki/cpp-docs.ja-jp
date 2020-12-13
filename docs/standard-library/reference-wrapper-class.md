---
description: '詳細情報: reference_wrapper クラス'
title: reference_wrapper クラス
ms.date: 11/04/2016
f1_keywords:
- functional/std::reference_wrapper
- type_traits/std::reference_wrapper
- xrefwrap/std::reference_wrapper
- type_traits/std::reference_wrapper::get
- type_traits/std::reference_wrapper::operator()
- functional/std::reference_wrapper::result_type
- functional/std::reference_wrapper::type
- functional/std::reference_wrapper::get
- functional/std::reference_wrapper::operator()
helpviewer_keywords:
- std::reference_wrapper [C++]
- std::reference_wrapper [C++]
- std::reference_wrapper [C++], result_type
- std::reference_wrapper [C++], type
- std::reference_wrapper [C++], get
ms.assetid: 90b8ed62-e6f1-44ed-acc7-9619bd58865a
ms.openlocfilehash: 5d3550a6ff579ea1e4174459d3ab1eab07b8a5d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337860"
---
# <a name="reference_wrapper-class"></a>reference_wrapper クラス

参照をラップします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
class reference_wrapper
{
    typedef Ty type;

    reference_wrapper(Ty&) noexcept;
    operator Ty&() const noexcept;
    Ty& get() const noexcept;

    template <class... Types>
    auto operator()(Types&&... args) const ->
        decltype(std::invoke(get(), std::forward<Types>(args)...));
};
```

## <a name="remarks"></a>解説

`reference_wrapper<Ty>` は、構築可能で、オブジェクトまたは `Ty` 型の関数への参照の周りの割り当て可能なラッパーのコピーであり、その型のオブジェクトを指すポインターを保持します。 `reference_wrapper` を使用して参照を標準コンテナーに格納できるほか、`std::bind` への参照によってオブジェクトを渡すことができます。

`Ty` 型は、オブジェクトの種類または関数の型である必要があります。それ以外の場合はコンパイル時に静的アサートに失敗します。

ヘルパー関数 [std::ref](functional-functions.md#ref) および [std::cref](functional-functions.md#cref) は、`reference_wrapper` オブジェクトの作成に使用できます。

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|名前|説明|
|-|-|
|[reference_wrapper](#reference_wrapper)|`reference_wrapper` を構築します。|

### <a name="typedefs"></a>Typedefs

|名前|説明|
|-|-|
|[result_type](#result_type)|ラップされた参照の弱い結果型。|
|[type](#type)|ラップされた参照の型。|

### <a name="functions"></a>関数

|名前|説明|
|-|-|
|[get](#get)|ラップされた参照を取得します。|

### <a name="operators"></a>オペレーター

|名前|説明|
|-|-|
|[演算子 Ty&amp;](#op_ty_amp)|ラップされた参照へのポインターを取得します。|
|[operator ()](#op_call)|ラップされた参照を呼び出します。|

## <a name="get"></a><a name="get"></a> 取得

ラップされた参照を取得します。

```cpp
Ty& get() const noexcept;
```

### <a name="remarks"></a>解説

このメンバー関数はラップされた参照を返します。

### <a name="example"></a>例

```cpp
// std__functional__reference_wrapper_get.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int main() {
    int i = 1;
    std::reference_wrapper<int> rwi(i);

    std::cout << "i = " << i << std::endl;
    std::cout << "rwi = " << rwi << std::endl;
    rwi.get() = -1;
    std::cout << "i = " << i << std::endl;

    return (0);
}
```

```Output
i = 1
rwi = 1
i = -1
```

## <a name="operator-tyamp"></a><a name="op_ty_amp"></a> 演算子 Ty&amp;

ラップされた参照を取得します。

```cpp
operator Ty&() const noexcept;
```

### <a name="remarks"></a>解説

このメンバー演算子は、 `*ptr`を返します。

### <a name="example"></a>例

```cpp
// std__functional__reference_wrapper_operator_cast.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int main() {
    int i = 1;
    std::reference_wrapper<int> rwi(i);

    std::cout << "i = " << i << std::endl;
    std::cout << "(int)rwi = " << (int)rwi << std::endl;

    return (0);
}
```

```Output
i = 1
(int)rwi = 1
```

## <a name="operator"></a><a name="op_call"></a> operator ()

ラップされた参照を呼び出します。

```cpp
template <class... Types>
auto operator()(Types&&... args);
```

### <a name="parameters"></a>パラメーター

*な*\
引数リストの型。

*value*\
引数リスト。

### <a name="remarks"></a>解説

テンプレート メンバー `operator()` は `std::invoke(get(), std::forward<Types>(args)...)` を返します。

### <a name="example"></a>例

```cpp
// std__functional__reference_wrapper_operator_call.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val) {
    return (-val);
}

int main() {
    std::reference_wrapper<int (int)> rwi(neg);

    std::cout << "rwi(3) = " << rwi(3) << std::endl;

    return (0);
}
```

```Output
rwi(3) = -3
```

## <a name="reference_wrapper"></a><a name="reference_wrapper"></a> reference_wrapper

`reference_wrapper` を構築します。

```cpp
reference_wrapper(Ty& val) noexcept;
```

### <a name="parameters"></a>パラメーター

*~*\
ラップする型。

*val*\
ラップする値。

### <a name="remarks"></a>解説

このコンストラクターは、`ptr` の格納された値を `&val` に設定します。

### <a name="example"></a>例

```cpp
// std__functional__reference_wrapper_reference_wrapper.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val) {
    return (-val);
}

int main() {
    int i = 1;
    std::reference_wrapper<int> rwi(i);

    std::cout << "i = " << i << std::endl;
    std::cout << "rwi = " << rwi << std::endl;
    rwi.get() = -1;
    std::cout << "i = " << i << std::endl;

    return (0);
}
```

```Output
i = 1
rwi = 1
i = -1
```

## <a name="result_type"></a><a name="result_type"></a> result_type

ラップされた参照の弱い結果型。

```cpp
typedef R result_type;
```

### <a name="remarks"></a>解説

`result_type` typedef は、ラップされた関数の弱い結果型のシノニムです。 この typedef は、関数型に対してのみ意味があります。

### <a name="example"></a>例

```cpp
// std__functional__reference_wrapper_result_type.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val) {
    return (-val);
}

int main() {
    typedef std::reference_wrapper<int (int)> Mywrapper;
    Mywrapper rwi(neg);
    Mywrapper::result_type val = rwi(3);

    std::cout << "val = " << val << std::endl;

    return (0);
}
```

```Output
val = -3
```

## <a name="type"></a><a name="type"></a> 型

ラップされた参照の型。

```cpp
typedef Ty type;
```

### <a name="remarks"></a>解説

この typedef は、テンプレート引数 `Ty` のシノニムです。

### <a name="example"></a>例

```cpp
// std__functional__reference_wrapper_type.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val) {
    return (-val);
}

int main() {
    int i = 1;
    typedef std::reference_wrapper<int> Mywrapper;
    Mywrapper rwi(i);
    Mywrapper::type val = rwi.get();

    std::cout << "i = " << i << std::endl;
    std::cout << "rwi = " << val << std::endl;

    return (0);
}
```

```Output
i = 1
rwi = 1
```
