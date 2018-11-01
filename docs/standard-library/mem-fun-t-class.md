---
title: mem_fun_t クラス
ms.date: 11/04/2016
f1_keywords:
- xfunctional/std::mem_fun_t
helpviewer_keywords:
- mem_fun_t class
ms.assetid: 242566d4-750c-4c87-9d63-2e2c9d19ca2a
ms.openlocfilehash: 32c66eb20215bc68efd0f0bb43c30f951da1bae9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456369"
---
# <a name="memfunt-class"></a>mem_fun_t クラス

使用するアダプター クラスを`non_const`ポインター引数による初期化時に、単項関数オブジェクトとして呼び出せるようにする引数を受け取らないメンバー関数。

## <a name="syntax"></a>構文

```cpp
template <class Result, class Type>
class mem_fun_t : public unary_function<Type *, Result> {
    explicit mem_fun_t(Result (Type::* _Pm)());

    Result operator()(Type* _Pleft) const;

};
```

### <a name="parameters"></a>パラメーター

*_Pm*<br/>
関数オブジェクトに変換されるクラス `Type` のメンバー関数へのポインター。

*_Pleft*<br/>
オブジェクトを *_Pm*でメンバー関数が呼び出されます。

## <a name="return-value"></a>戻り値

適合可能な単項関数。

## <a name="remarks"></a>Remarks

テンプレート クラスのコピーを格納する *_Pm*、クラスのメンバー関数へのポインターでなければならない`Type`、プライベート メンバー オブジェクトにします。 そのメンバー関数 `operator()` は ( `_Pleft`->* `_Pm`)( ) を返すように定義されています。

## <a name="example"></a>例

`mem_fun_t` のコンストラクターは通常は直接使用されません。ヘルパー関数 `mem_fun` を使用してメンバー関数を適合させます。 メンバー関数アダプターの使用例については、「[mem_fun](../standard-library/functional-functions.md#mem_fun)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<functional>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<functional>](../standard-library/functional.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
