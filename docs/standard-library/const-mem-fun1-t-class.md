---
title: const_mem_fun1_t クラス
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun1_t
helpviewer_keywords:
- const_mem_fun1_t class
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
ms.openlocfilehash: df984d90f8b632f8e3e3b183943343952d45b8be
ms.sourcegitcommit: 4299caac2dc9e806c74ac833d856a3838b0f52a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "57006358"
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

*member_ptr*<br/>
関数オブジェクトに変換されるクラス `Type` のメンバー関数へのポインター。

*left*<br/>
**Const**オブジェクトを*member_ptr*でメンバー関数が呼び出されます。

*right*<br/>
渡される引数*member_ptr*します。

## <a name="return-value"></a>戻り値

適合可能な二項関数。

## <a name="remarks"></a>Remarks

テンプレート クラスのコピーを格納する*member_ptr*、クラスのメンバー関数へのポインターでなければならない`Type`、プライベート メンバー オブジェクトにします。 そのメンバー関数`operator()`返すよう`(left->member_ptr)(right) const`します。

## <a name="example"></a>例

`const_mem_fun1_t` のコンストラクターが直接使用されることはほとんどありません。 `mem_fn` メンバー関数の調整に使用されます。 参照してください[mem_fn](../standard-library/functional-functions.md#mem_fn)メンバー関数アダプターを使用する方法の例についてはします。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<functional>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
