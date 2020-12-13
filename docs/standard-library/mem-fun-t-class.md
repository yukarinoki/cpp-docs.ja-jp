---
description: '詳細情報: mem_fun_t クラス'
title: mem_fun_t クラス
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun_t
helpviewer_keywords:
- mem_fun_t class
ms.assetid: 242566d4-750c-4c87-9d63-2e2c9d19ca2a
ms.openlocfilehash: 53c3103c8f2c855d8d6ff9a2861ace4f2c69c787
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149150"
---
# <a name="mem_fun_t-class"></a>mem_fun_t クラス

`non_const`ポインター引数を使用して初期化するときに、引数を取らないメンバー関数を単項関数オブジェクトとして呼び出すことができるようにするアダプタークラス。 C++ 11 では非推奨となりました。 C++ 17 では削除されています。

## <a name="syntax"></a>構文

```cpp
template <class Result, class Type>
class mem_fun_t : public unary_function<Type *, Result> {
    explicit mem_fun_t(Result (Type::* _Pm)());

    Result operator()(Type* _Pleft) const;
};
```

### <a name="parameters"></a>パラメーター

*_Pm*\
関数オブジェクトに変換されるクラス `Type` のメンバー関数へのポインター。

*_Pleft*\
*_Pm* メンバー関数が呼び出されるオブジェクト。

## <a name="return-value"></a>戻り値

適合可能な単項関数。

## <a name="remarks"></a>解説

クラステンプレートには *_Pm* のコピーが格納されます。このコピーは、プライベートメンバーオブジェクト内のクラスのメンバー関数へのポインターである必要があり `Type` ます。 そのメンバー関数は `operator()` () () を返すように定義さ `_Pleft` ->*  `_Pm` れています。

## <a name="example"></a>例

`mem_fun_t` のコンストラクターは通常は直接使用されません。ヘルパー関数 `mem_fun` を使用してメンバー関数を適合させます。 メンバー関数アダプターの使用例については、「[mem_fun](../standard-library/functional-functions.md#mem_fun)」を参照してください。
