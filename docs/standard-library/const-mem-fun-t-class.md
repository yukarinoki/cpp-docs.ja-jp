---
title: const_mem_fun_t クラス
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun_t
helpviewer_keywords:
- const_mem_fun_t class
ms.assetid: f169d381-019b-4a0e-a9a3-54da6d948270
ms.openlocfilehash: 6b34fb6b20b2aaf2f18fbe8d937e50bdbaa3bdff
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228350"
---
# <a name="const_mem_fun_t-class"></a>const_mem_fun_t クラス

参照引数による初期化を行うときに、引数を使用しない const メンバー関数を単項関数オブジェクトとして呼び出せるようにするアダプター クラス。 C++ 11 では非推奨となりました。 C++ 17 では削除されています。

## <a name="syntax"></a>構文

```cpp
template <class Result, class Type>
class const_mem_fun_t : public unary_function <Type *, Result>
{
    explicit const_mem_fun_t(Result (Type::* Pm)() const);
    Result operator()(const Type* Pleft) const;
};
```

### <a name="parameters"></a>パラメーター

*Pm*\
関数オブジェクトに変換されるクラス `Type` のメンバー関数へのポインター。

*Pleft*\
*Pm*メンバー関数が呼び出されるオブジェクト。

## <a name="return-value"></a>戻り値

適合可能な単項関数。

## <a name="remarks"></a>解説

クラステンプレートは、 *Pm* `Type` プライベートメンバーオブジェクト内のクラスのメンバー関数へのポインターである必要がある Pm のコピーを格納します。 そのメンバー関数は `operator()` () () を返すように定義さ `Pleft` -> \* `Pm` **`const`** れています。

## <a name="example"></a>例

`const_mem_fun_t` のコンストラクターは通常は直接使用されません。ヘルパー関数 `mem_fun` を使用してメンバー関数を適合させます。 メンバー関数アダプターの使用例については、「[mem_fun](../standard-library/functional-functions.md#mem_fun)」を参照してください。
