---
title: const_mem_fun1_t クラス
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun1_t
helpviewer_keywords:
- const_mem_fun1_t class
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
ms.openlocfilehash: 8ccd9d7e58b9cadec83b64df5553564db20a5745
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244525"
---
# <a name="constmemfun1t-class"></a>const_mem_fun1_t クラス

ポインター引数による初期化を行うときに、1 つの引数を使用する **const** メンバー関数を二項関数オブジェクトとして呼び出せるようにするアダプター クラス。 C++ 11、c++ 17 では削除では、非推奨とされます。

## <a name="syntax"></a>構文

```cpp
template <class Result, class Type, class Arg>
class const_mem_fun1_t : public binary_function<const Type *, Arg, Result>
{
    explicit const_mem_fun1_t(Result (Type::* member_ptr)(Arg) const);
    Result operator()(const Type* left, Arg right) const;
};
```

### <a name="parameters"></a>パラメーター

*member_ptr*\
関数オブジェクトに変換されるクラス `Type` のメンバー関数へのポインター。

*左*\
**Const**オブジェクトを*member_ptr*でメンバー関数が呼び出されます。

*そうです*\
渡される引数*member_ptr*します。

## <a name="return-value"></a>戻り値

適合可能な二項関数。

## <a name="remarks"></a>Remarks

テンプレート クラスのコピーを格納する*member_ptr*、クラスのメンバー関数へのポインターでなければならない`Type`、プライベート メンバー オブジェクトにします。 そのメンバー関数`operator()`返すよう`(left->member_ptr)(right) const`します。

## <a name="example"></a>例

`const_mem_fun1_t` のコンストラクターが直接使用されることはほとんどありません。 `mem_fn` メンバー関数の調整に使用されます。 参照してください[mem_fn](../standard-library/functional-functions.md#mem_fn)メンバー関数アダプターを使用する方法の例についてはします。
