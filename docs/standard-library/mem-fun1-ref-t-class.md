---
title: mem_fun1_ref_t クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::mem_fun1_ref_t
dev_langs:
- C++
helpviewer_keywords:
- mem_fun1_ref_t class
ms.assetid: 7d6742f6-19ba-4523-b3c8-0e5b8f11464f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d354e469b6b6a19d51ecedbc7f2106c21e82dab
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="memfun1reft-class"></a>mem_fun1_ref_t クラス

参照引数による初期化を行うときに、1 つの引数を使用する **non_const** メンバー関数を二項関数オブジェクトとして呼び出せるようにするアダプター クラス。

## <a name="syntax"></a>構文

```cpp
template <class Result, class Type, class Arg>
class mem_fun1_ref_t : public binary_function<Type, Arg, Result> {
    explicit mem_fun1_ref_t(
    Result (Type::* _Pm)(Arg));

    Result operator()(
    Type& left,
    Arg right) const;

};
```

### <a name="parameters"></a>パラメーター

`_Pm` クラスのメンバー関数へのポインター**型**関数オブジェクトに変換します。

`left` オブジェクトを`_Pm`でメンバー関数が呼び出されます。

`right` 指定された引数`_Pm`です。

## <a name="return-value"></a>戻り値

適合可能な二項関数。

## <a name="remarks"></a>コメント

このテンプレート クラスは `_Pm` のコピーをプライベート メンバー オブジェクトに格納します。これは、**Type** クラスのメンバー関数へのポインターである必要があります。 そのメンバー関数を定義`operator()`を返すよう (**左**.\*`_Pm`) (**右**)。

## <a name="example"></a>例

`mem_fun1_ref_t` のコンストラクターは通常は直接使用されません。ヘルパー関数 `mem_fun_ref` を使用してメンバー関数を適合させます。 メンバー関数アダプターの使用例については、「[mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref)」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** \<functional>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
