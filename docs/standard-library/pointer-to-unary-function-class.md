---
title: pointer_to_unary_function クラス
ms.date: 02/21/2019
f1_keywords:
- functional/std::pointer_to_unary
helpviewer_keywords:
- pointer_to_unary_function function
- pointer_to_unary_function class
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
ms.openlocfilehash: cff84f1f15eea34c60162f702dfe05350d1383d1
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240465"
---
# <a name="pointertounaryfunction-class"></a>pointer_to_unary_function クラス

単項関数ポインターを適応性のある単項関数に変換します。 C++ 11、c++ 17 では削除では、非推奨とされます。

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

*左*\
*\*pfunc* が呼び出されるオブジェクト。

## <a name="return-value"></a>戻り値

テンプレート クラスのコピーを格納する`pfunc`します。 そのメンバー関数 `operator()` は (\* **pfunc**)(_ *Left*) を返すように定義されています。

## <a name="remarks"></a>Remarks

単項関数ポインターは関数オブジェクトであり、パラメーターとして単項関数を想定する C++ 標準ライブラリの任意のアルゴリズムに渡される場合がありますが、適合性はありません。 値をバインドなど、否定子と共に使用するアダプターを使用して入れ子にされた型で指定する必要があります`argument_type`と`result_type`このような適応を可能にします。 `pointer_to_unary_function` による変換によって、関数アダプターを二項関数ポインターと共に使用できるようになります。

## <a name="example"></a>例

`pointer_to_unary_function` のコンストラクターが直接使用されることはほとんどありません。 `pointer_to_unary_function` アダプターの述語を宣言および使用する方法の例については、ヘルパー関数 [ptr_fun](../standard-library/functional-functions.md#ptr_fun) をご覧ください。
