---
description: '詳細情報: mem_fun1_ref_t クラス'
title: mem_fun1_ref_t クラス
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun1_ref_t
helpviewer_keywords:
- mem_fun1_ref_t class
ms.assetid: 7d6742f6-19ba-4523-b3c8-0e5b8f11464f
ms.openlocfilehash: 6418812fb4c924c8d67ba4fc09d4595455ad73c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149124"
---
# <a name="mem_fun1_ref_t-class"></a>mem_fun1_ref_t クラス

`non_const`参照引数で初期化するときに、1つの引数を受け取るメンバー関数を二項関数オブジェクトとして呼び出すことができるようにするアダプタークラス。 C++ 11 では非推奨となりました。 C++ 17 では削除されています。

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

*_Pm*\
関数オブジェクトに変換されるクラス `Type` のメンバー関数へのポインター。

*左側*\
*_Pm* メンバー関数が呼び出されるオブジェクト。

*そうです*\
*_Pm* に指定される引数。

## <a name="return-value"></a>戻り値

適合可能な二項関数。

## <a name="remarks"></a>解説

クラステンプレートには *_Pm* のコピーが格納されます。このコピーは、プライベートメンバーオブジェクト内のクラスのメンバー関数へのポインターである必要があり `Type` ます。 そのメンバー関数は `operator()` (**left**. \* `_Pm` ) を返すように定義されています。(**right**)。

## <a name="example"></a>例

`mem_fun1_ref_t` のコンストラクターは通常は直接使用されません。ヘルパー関数 `mem_fun_ref` を使用してメンバー関数を適合させます。 メンバー関数アダプターの使用例については、「[mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref)」を参照してください。
