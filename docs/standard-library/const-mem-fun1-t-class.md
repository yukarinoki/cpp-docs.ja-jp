---
description: '詳細情報: const_mem_fun1_t クラス'
title: const_mem_fun1_t クラス
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun1_t
helpviewer_keywords:
- const_mem_fun1_t class
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
ms.openlocfilehash: 998826bbd78745913caf76ad6b152aac490956fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233657"
---
# <a name="const_mem_fun1_t-class"></a>const_mem_fun1_t クラス

ポインター引数を使用して **`const`** 初期化するときに、1つの引数を取るメンバー関数を二項関数オブジェクトとして呼び出すことができるようにするアダプタークラス。 C++ 11 では非推奨となりました。 C++ 17 では削除されています。

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

*左側*\
**`const`** *Member_ptr* メンバー関数が呼び出されるオブジェクト。

*そうです*\
*Member_ptr* に指定される引数。

## <a name="return-value"></a>戻り値

適合可能な二項関数。

## <a name="remarks"></a>解説

クラステンプレートには *member_ptr* のコピーが格納されます。このコピーは、プライベートメンバーオブジェクト内のクラスのメンバー関数へのポインターである必要があり `Type` ます。 そのメンバー関数は、 `operator()` を返すように定義さ `(left->member_ptr)(right) const` れています。

## <a name="example"></a>例

`const_mem_fun1_t` のコンストラクターが直接使用されることはほとんどありません。 `mem_fn` は、メンバー関数を調整するために使用されます。 メンバー関数アダプターの使用方法の例については、「 [mem_fn](../standard-library/functional-functions.md#mem_fn) 」を参照してください。
