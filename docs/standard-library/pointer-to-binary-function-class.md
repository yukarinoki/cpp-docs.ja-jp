---
title: pointer_to_binary_function クラス
ms.date: 02/21/2019
f1_keywords:
- functional/std::pointer_to_binary
helpviewer_keywords:
- pointer_to_binary_function function
- pointer_to_binary_function class
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
ms.openlocfilehash: 88d38be258c6ceb1054e0d31cc52e4d8d25186ec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370321"
---
# <a name="pointertobinaryfunction-class"></a>pointer_to_binary_function クラス

二項関数ポインターを適応性のある二項関数に変換します。 C++ 11、c++ 17 では削除では、非推奨とされます。

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

*pfunc*<br/>
変換する二項関数。

*left*<br/>
*\*pfunc* が呼び出される左辺のオブジェクト。

*right*<br/>
*\*pfunc* が呼び出される右側のオブジェクト。

## <a name="return-value"></a>戻り値

テンプレート クラスのコピーを格納する`pfunc`します。 そのメンバー関数`operator()`返すよう`(* pfunc)(Left, right)`します。

## <a name="remarks"></a>Remarks

二項関数ポインターは関数オブジェクトであり、パラメーターとして二項関数を想定する C++ 標準ライブラリの任意のアルゴリズムに渡される場合がありますが、適応性はありません。 値をバインドなど、否定子と共に使用するアダプターを使用して入れ子にされた型で指定する必要があります`first_argument_type`、 `second_argument_type`、および`result_type`このような適応を可能にします。 `pointer_to_binary_function` による変換によって、関数アダプターを二項関数ポインターと共に使用できるようになります。

## <a name="example"></a>例

`pointer_to_binary_function` のコンストラクターが直接使用されることはほとんどありません。 `pointer_to_binary_function` アダプターの述語を宣言および使用する方法の例については、ヘルパー関数 [ptr_fun](../standard-library/functional-functions.md#ptr_fun) をご覧ください。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<functional>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
