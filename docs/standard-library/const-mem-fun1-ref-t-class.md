---
title: const_mem_fun1_ref_t クラス
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun1_ref_t
helpviewer_keywords:
- const_mem_fun1_ref_t class
ms.assetid: 8220d373-fa1c-44be-a21d-96d49b3ea6bb
ms.openlocfilehash: f9f426b7280872846695e204f2c9843d2622fe19
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228337"
---
# <a name="const_mem_fun1_ref_t-class"></a>const_mem_fun1_ref_t クラス

**`const`** 参照引数で初期化するときに、1つの引数を受け取るメンバー関数を二項関数オブジェクトとして呼び出すことができるようにするアダプタークラス。 C++ 11 では非推奨となりました。 C++ 17 では削除されています。

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

*Pm*\
関数オブジェクトに変換されるクラス `Type` のメンバー関数へのポインター。

*左側*\
**`const`** *Pm*メンバー関数が呼び出されるオブジェクト。

*そうです*\
*Pm*に渡される引数。

## <a name="return-value"></a>戻り値

適合可能な二項関数。

## <a name="remarks"></a>解説

クラステンプレートは、 *Pm* `Type` プライベートメンバーオブジェクト内のクラスのメンバー関数へのポインターである必要がある Pm のコピーを格納します。 そのメンバー関数は `operator()` ( `left` \* *Pm*) () を返すように定義さ `right` れて **`const`** います。

## <a name="example"></a>例

`const_mem_fun1_ref_t` のコンストラクターは通常は直接使用されません。ヘルパー関数 `mem_fun_ref` を使用してメンバー関数を適合させます。 メンバー関数アダプターの使用例については、「[mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref)」を参照してください。
