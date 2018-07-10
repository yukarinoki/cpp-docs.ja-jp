---
title: const_mem_fun1_t クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::const_mem_fun1_t
dev_langs:
- C++
helpviewer_keywords:
- const_mem_fun1_t class
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5fe5c06dd3017e867e73cf1107e619ec2c1edaf
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33843796"
---
# <a name="constmemfun1t-class"></a>const_mem_fun1_t クラス

ポインター引数による初期化を行うときに、1 つの引数を使用する **const** メンバー関数を二項関数オブジェクトとして呼び出せるようにするアダプター クラス。

## <a name="syntax"></a>構文

```cpp
template <class Result, class Type, class Arg>
class const_mem_fun1_t
 : public binary_function<const Type *, Arg, Result>
{
    explicit const_mem_fun1_t(Result (Type::* _Pm)(Arg) const);
    Result operator()(const Type* _Pleft, Arg right) const;
 };
```

### <a name="parameters"></a>パラメーター

`_Pm` クラスのメンバー関数へのポインター**型**関数オブジェクトに変換します。

`_Pleft` **Const**オブジェクトを`_Pm`でメンバー関数が呼び出されます。

`right` 指定された引数`_Pm`です。

## <a name="return-value"></a>戻り値

適合可能な二項関数。

## <a name="remarks"></a>コメント

このテンプレート クラスは `_Pm` のコピーをプライベート メンバー オブジェクトに格納します。これは、**Type** クラスのメンバー関数へのポインターである必要があります。 そのメンバー関数を定義 `operator()` を返すよう ( **_Pleft**->\* *Pm)(***右**) **const** です。

## <a name="example"></a>例

`const_mem_fun1_t` のコンストラクターは通常は直接使用されません。ヘルパー関数 `mem_fun` を使用してメンバー関数を適合させます。 メンバー関数アダプターの使用例については、「[mem_fun](../standard-library/functional-functions.md#mem_fun)」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** \<functional>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
