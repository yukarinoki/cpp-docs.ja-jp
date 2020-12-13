---
description: '詳細情報: pointer_to_unary_function クラス'
title: pointer_to_unary_function クラス
ms.date: 02/21/2019
f1_keywords:
- functional/std::pointer_to_unary
helpviewer_keywords:
- pointer_to_unary_function function
- pointer_to_unary_function class
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
ms.openlocfilehash: 45a927add90915bcbd8791eeba5561027b7e9217
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340698"
---
# <a name="pointer_to_unary_function-class"></a>pointer_to_unary_function クラス

単項関数ポインターを適応性のある単項関数に変換します。 C++ 11 では非推奨となりました。 C++ 17 では削除されています。

## <a name="syntax"></a>構文

```cpp
template <class Arg, class Result>
class pointer_to_unary_function
    : public unary_function<Arg, Result>
{
    explicit pointer_to_unary_function(Result(*pfunc)(Arg));
    Result operator()(Arg left) const;
};
```

### <a name="parameters"></a>パラメーター

*pfunc*\
変換する二項関数。

*左側*\
*\* Pfunc* が呼び出されるオブジェクト。

## <a name="return-value"></a>戻り値

クラステンプレートには、のコピーが格納され `pfunc` ます。 そのメンバー関数 `operator()` は (\* **pfunc**)(_ *Left*) を返すように定義されています。

## <a name="remarks"></a>解説

単項関数ポインターは関数オブジェクトであり、パラメーターとして単項関数を想定する C++ 標準ライブラリの任意のアルゴリズムに渡される場合がありますが、適合性はありません。 これをアダプターで使用するには (値をバインドする、negator で使用するなど)、入れ子になった型を指定し、そのような適合を可能にする必要があり `argument_type` `result_type` ます。 `pointer_to_unary_function` による変換によって、関数アダプターを二項関数ポインターと共に使用できるようになります。

## <a name="example"></a>例

`pointer_to_unary_function` のコンストラクターが直接使用されることはほとんどありません。 `pointer_to_unary_function` アダプターの述語を宣言および使用する方法の例については、ヘルパー関数 [ptr_fun](../standard-library/functional-functions.md#ptr_fun) をご覧ください。
