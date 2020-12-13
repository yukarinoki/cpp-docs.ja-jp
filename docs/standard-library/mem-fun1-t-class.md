---
description: '詳細情報: mem_fun1_t クラス'
title: mem_fun1_t クラス
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun1_t
helpviewer_keywords:
- mem_fun1_t class
ms.assetid: 01a8c2c2-b2f7-4e3f-869c-5b5b9f06ea54
ms.openlocfilehash: a0fd8f060757c7dc5004ad753fd168c9e644e1b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149085"
---
# <a name="mem_fun1_t-class"></a>mem_fun1_t クラス

ポインター引数を使用して `non_const` 初期化するときに、1つの引数を取るメンバー関数を二項関数オブジェクトとして呼び出すことができるようにするアダプタークラス。 C++ 11 では非推奨となりました。 C++ 17 では削除されています。

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

*_Pm*\
関数オブジェクトに変換されるクラス `Type` のメンバー関数へのポインター。

*_Pleft*\
*_Pm* メンバー関数が呼び出されるオブジェクト。

*そうです*\
*_Pm* に指定される引数。

## <a name="return-value"></a>戻り値

適合可能な二項関数。

## <a name="remarks"></a>解説

クラステンプレートには *_Pm* のコピーが格納されます。このコピーは、プライベートメンバーオブジェクト内のクラスのメンバー関数へのポインターである必要があり `Type` ます。 そのメンバー関数は、 `operator()` (**_Pleft** -> \* `_Pm` ) (**right**) を返すように定義されています。

## <a name="example"></a>例

`mem_fun1_t` のコンストラクターは通常は直接使用されません。ヘルパー関数 `mem_fun` を使用してメンバー関数を適合させます。 メンバー関数アダプターの使用例については、「[mem_fun](../standard-library/functional-functions.md#mem_fun)」を参照してください。
