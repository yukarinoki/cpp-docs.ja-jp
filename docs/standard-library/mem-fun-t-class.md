---
title: mem_fun_t クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::mem_fun_t
dev_langs:
- C++
helpviewer_keywords:
- mem_fun_t class
ms.assetid: 242566d4-750c-4c87-9d63-2e2c9d19ca2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32aceae204f50d98e84f1286042854e725917623
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33852547"
---
# <a name="memfunt-class"></a>mem_fun_t クラス

ポインター引数による初期化を行うときに、引数を使用しない **non_const** メンバー関数を単項関数オブジェクトとして呼び出せるようにするアダプター クラス。

## <a name="syntax"></a>構文

```cpp
template <class Result, class Type>
class mem_fun_t : public unary_function<Type *, Result> {
    explicit mem_fun_t(Result (Type::* _Pm)());

    Result operator()(Type* _Pleft) const;

};
```

### <a name="parameters"></a>パラメーター

`_Pm` クラスのメンバー関数へのポインター**型**関数オブジェクトに変換します。

`_Pleft` オブジェクトを`_Pm`でメンバー関数が呼び出されます。

## <a name="return-value"></a>戻り値

適合可能な単項関数。

## <a name="remarks"></a>コメント

このテンプレート クラスは `_Pm` のコピーをプライベート メンバー オブジェクトに格納します。これは、**Type** クラスのメンバー関数へのポインターである必要があります。 そのメンバー関数 `operator()` は ( `_Pleft`->* `_Pm`)( ) を返すように定義されています。

## <a name="example"></a>例

`mem_fun_t` のコンストラクターは通常は直接使用されません。ヘルパー関数 `mem_fun` を使用してメンバー関数を適合させます。 メンバー関数アダプターの使用例については、「[mem_fun](../standard-library/functional-functions.md#mem_fun)」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** \<functional>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<functional>](../standard-library/functional.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
