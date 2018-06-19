---
title: pointer_to_binary_function クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::pointer_to_binary
dev_langs:
- C++
helpviewer_keywords:
- pointer_to_binary_function function
- pointer_to_binary_function class
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39549a277a203d9daa894f48437224caf50a0521
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853379"
---
# <a name="pointertobinaryfunction-class"></a>pointer_to_binary_function クラス

二項関数ポインターを適応性のある二項関数に変換します。

## <a name="syntax"></a>構文

```cpp
template <class Arg1, class Arg2, class Result>
class pointer_to_binary_function
    : public binary_function <Arg1, Arg2, Result>
{
public:
    explicit pointer_to_binary_function(
        Result(*pfunc)(Arg1, Arg2));
    Result operator()(Arg1 left, Arg2 right) const;
};
```

### <a name="parameters"></a>パラメーター

`pfunc` 変換する二項関数。

`left` 左側のオブジェクトを *\*pfunc*で呼び出されるとします。

`right` 右側のオブジェクトを *\*pfunc*で呼び出されるとします。

## <a name="return-value"></a>戻り値

テンプレート クラスは **pfunc** のコピーを格納します。 そのメンバー関数 `operator()` は (\* **pfunc**)(_ *Left*, \_ *Right*) を返すように定義されています。

## <a name="remarks"></a>コメント

二項関数ポインターは関数オブジェクトであり、パラメーターとして二項関数を想定する C++ 標準ライブラリの任意のアルゴリズムに渡される場合がありますが、適応性はありません。 二項関数ポインターをアダプターと共に使用する (値をバインドしたり否定子と共に使用するなど) には、このような適応を可能にする、入れ子にされた型 (**first_argument_type**、**second_argument_type**、および **result_type**) と共に指定する必要があります。 `pointer_to_binary_function` による変換によって、関数アダプターを二項関数ポインターと共に使用できるようになります。

## <a name="example"></a>例

`pointer_to_binary_function` のコンストラクターが直接使用されることはほとんどありません。 `pointer_to_binary_function` アダプターの述語を宣言および使用する方法の例については、ヘルパー関数 [ptr_fun](../standard-library/functional-functions.md#ptr_fun) をご覧ください。

## <a name="requirements"></a>要件

**ヘッダー:** \<functional>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
