---
title: mem_fun1_t クラス
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun1_t
helpviewer_keywords:
- mem_fun1_t class
ms.assetid: 01a8c2c2-b2f7-4e3f-869c-5b5b9f06ea54
ms.openlocfilehash: 822de97849750a72948137ba8fe23beab8554ff5
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245097"
---
# <a name="memfun1t-class"></a>mem_fun1_t クラス

使用するアダプター クラスを`non_const`メンバー関数を 1 つの引数のポインター引数による初期化時に、二項関数オブジェクトとして呼び出せるようにします。 C++ 11、c++ 17 では削除では、非推奨とされます。

## <a name="syntax"></a>構文

```cpp
template <class Result, class Type, class Arg>
class mem_fun1_t : public binary_function<Type *, Arg, Result> {
    explicit mem_fun1_t(
    Result (Type::* _Pm)(Arg));

    Result operator()(
    Type* _Pleft,
    Arg right) const;
};
```

### <a name="parameters"></a>パラメーター

*_Pm*\
関数オブジェクトに変換されるクラス `Type` のメンバー関数へのポインター。

*_Pleft*\
オブジェクトを *_Pm*でメンバー関数が呼び出されます。

*そうです*\
渡される引数 *_Pm*します。

## <a name="return-value"></a>戻り値

適合可能な二項関数。

## <a name="remarks"></a>Remarks

テンプレート クラスのコピーを格納する *_Pm*、クラスのメンバー関数へのポインターでなければならない`Type`、プライベート メンバー オブジェクトにします。 そのメンバー関数`operator()`返すよう ( **_Pleft** -> \* `_Pm`) (**右**)。

## <a name="example"></a>例

`mem_fun1_t` のコンストラクターは通常は直接使用されません。ヘルパー関数 `mem_fun` を使用してメンバー関数を適合させます。 メンバー関数アダプターの使用例については、「[mem_fun](../standard-library/functional-functions.md#mem_fun)」を参照してください。
