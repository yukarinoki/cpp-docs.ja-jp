---
title: add_rvalue_reference クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_rvalue_reference
helpviewer_keywords:
- add_rvalue_reference Class
ms.assetid: 76b0cb7c-1031-45d0-b409-f03ab0297580
ms.openlocfilehash: 6d7cc1d45ed3b963de0a0a004c1696ddbf0af440
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623920"
---
# <a name="add_rvalue_reference-class"></a>add_rvalue_reference クラス

テンプレート パラメーターがオブジェクトまたは関数の型の場合に、その右辺値参照型を作成します。 それ以外の場合、参照縮小のセマンティクスのため、型はテンプレート パラメーターと同じです。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct add_rvalue_reference;

template <class T>
using add_rvalue_reference_t = typename add_rvalue_reference<T>::type;
```

### <a name="parameters"></a>パラメーター

*\T*\
変更する型。

## <a name="remarks"></a>Remarks

クラスには `add_rvalue_reference` 、という名前のメンバーがあり `type` ます。これは、テンプレートパラメーター *T*への右辺値参照の型のエイリアスです。参照の縮小のセマンティクスは、非オブジェクト型と非関数型*t*の場合、 `T&&` *t*です。たとえば、 *T*が左辺値参照型の場合、 `add_rvalue_reference<T>::type` は右辺値参照ではなく左辺値参照型です。

便宜上、は、 \<type_traits> `add_rvalue_reference_t` のメンバーにエイリアスを使用するヘルパーテンプレートを定義し `type` `add_rvalue_reference` ます。

## <a name="example"></a>例

このコード例では、static_assert を使用して、右辺値参照型を `add_rvalue_reference` と`add_rvalue_reference_t` を使用して作成する方法、および左辺値参照型での `add_rvalue_reference` の結果を右辺値参照ではなく左辺値参照型に縮小する方法を示します。

```cpp
// ex_add_rvalue_reference.cpp
// Build by using: cl /EHsc /W4 ex_add_rvalue_reference.cpp
#include <type_traits>
#include <iostream>
#include <string>

using namespace std;
int main()
{
    static_assert(is_same<add_rvalue_reference<string>::type, string&&>::value,
        "Expected add_rvalue_reference_t<string> to be string&&");
    static_assert(is_same<add_rvalue_reference_t<string*>, string*&&>::value,
        "Expected add_rvalue_reference_t<string*> to be string*&&");
    static_assert(is_same<add_rvalue_reference<string&>::type, string&>::value,
        "Expected add_rvalue_reference_t<string&> to be string&");
    static_assert(is_same<add_rvalue_reference_t<string&&>, string&&>::value,
        "Expected add_rvalue_reference_t<string&&> to be string&&");
    cout << "All static_assert tests of add_rvalue_reference passed." << endl;
    return 0;
}

/*Output:
All static_assert tests of add_rvalue_reference passed.
*/
```

## <a name="requirements"></a>必要条件

ヘッダー: \<type_traits>

名前空間: std

## <a name="see-also"></a>関連項目

[<type_traits>](type-traits.md)\
[add_lvalue_reference クラス](add-lvalue-reference-class.md)\
[is_rvalue_reference クラス](is-rvalue-reference-class.md)
