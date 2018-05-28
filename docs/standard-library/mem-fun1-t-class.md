---
title: mem_fun1_t クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::mem_fun1_t
dev_langs:
- C++
helpviewer_keywords:
- mem_fun1_t class
ms.assetid: 01a8c2c2-b2f7-4e3f-869c-5b5b9f06ea54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2c90838bf4ae49e372b35ca2e9a2f0feede4eb9b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="memfun1t-class"></a>mem_fun1_t クラス

ポインター引数による初期化を行うときに、1 つの引数を使用する **non_const** メンバー関数を二項関数オブジェクトとして呼び出せるようにするアダプター クラス。

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

`_Pm` クラスのメンバー関数へのポインター**型**関数オブジェクトに変換します。

`_Pleft` オブジェクトを`_Pm`でメンバー関数が呼び出されます。

`right` 指定された引数`_Pm`です。

## <a name="return-value"></a>戻り値

適合可能な二項関数。

## <a name="remarks"></a>コメント

このテンプレート クラスは `_Pm` のコピーをプライベート メンバー オブジェクトに格納します。これは、**Type** クラスのメンバー関数へのポインターである必要があります。 そのメンバー関数 `operator()` は ( **_Pleft**->\* `_Pm`)( **right**) を返すように定義されています。

## <a name="example"></a>例

`mem_fun1_t` のコンストラクターは通常は直接使用されません。ヘルパー関数 `mem_fun` を使用してメンバー関数を適合させます。 メンバー関数アダプターの使用例については、「[mem_fun](../standard-library/functional-functions.md#mem_fun)」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** \<functional>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
