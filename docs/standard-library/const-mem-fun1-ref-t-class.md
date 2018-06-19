---
title: const_mem_fun1_ref_t クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::const_mem_fun1_ref_t
dev_langs:
- C++
helpviewer_keywords:
- const_mem_fun1_ref_t class
ms.assetid: 8220d373-fa1c-44be-a21d-96d49b3ea6bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c465ce95ecbf2ecb50e79e6e4cbaafce8cf7a407
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33843679"
---
# <a name="constmemfun1reft-class"></a>const_mem_fun1_ref_t クラス

参照引数による初期化を行うときに、1 つの引数を使用する **const** メンバー関数を二項関数オブジェクトとして呼び出せるようにするアダプター クラス。

## <a name="syntax"></a>構文

```cpp
template <class Result, class Type, class Arg>
class const_mem_fun1_ref_t
 : public binary_function<Type, Arg, Result>
 {
    explicit const_mem_fun1_ref_t(Result (Type::* Pm)(Arg) const);
    Result operator()(const Type& left, Arg right) const;
 };
```

### <a name="parameters"></a>パラメーター

`Pm` クラスのメンバー関数へのポインター**型**関数オブジェクトに変換します。

`left` **Const**オブジェクトを`Pm`でメンバー関数が呼び出されます。

`right` 指定された引数`Pm`です。

## <a name="return-value"></a>戻り値

適合可能な二項関数。

## <a name="remarks"></a>コメント

このテンプレート クラスは `Pm` のコピーをプライベート メンバー オブジェクトに格納します。これは、**Type** クラスのメンバー関数へのポインターである必要があります。 そのメンバー関数 `operator()` は、(`left`.\**Pm*)(`right`) **const** を返すように定義されています。

## <a name="example"></a>例

`const_mem_fun1_ref_t` のコンストラクターは通常は直接使用されません。ヘルパー関数 `mem_fun_ref` を使用してメンバー関数を適用します。 メンバー関数アダプターの使用例については、「[mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref)」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** \<functional>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
