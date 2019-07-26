---
title: gslice_array クラス
ms.date: 11/04/2016
f1_keywords:
- valarray/std::gslice_array
helpviewer_keywords:
- gslice_array class
ms.assetid: ad1b4514-b14a-4baf-a293-d5a8e8674c75
ms.openlocfilehash: 37c54d09fdfe920c832c4baa7984fee4e090d04a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448926"
---
# <a name="gslicearray-class"></a>gslice_array クラス

valarray の一般的なスライスで定義されるサブセット配列間の演算を実行して一般的なスライス オブジェクトをサポートする、内部の補助テンプレート クラス。

## <a name="syntax"></a>構文

```cpp
template <class Type>
class gslice_array : public gsplice {
public:
    typedef Type value_type;
    void operator=(const valarray<Type>& x) const;

    void operator=(const Type& x) const;

    void operator*=(const valarray<Type>& x) const;

    void operator/=(const valarray<Type>& x) const;

    void operator%=(const valarray<Type>& x) const;

    void operator+=(const valarray<Type>& x) const;

    void operator-=(const valarray<Type>& x) const;

    void operator^=(const valarray<Type>& x) const;

    void operator&=(const valarray<Type>& x) const;

    void operator|=(const valarray<Type>& x) const;

    void operator<<=(const valarray<Type>& x) const;

    void operator>>=(const valarray<Type>& x) const;

// The rest is private or implementation defined
}
```

## <a name="remarks"></a>Remarks

クラスは、> クラス`va` [valarray](../standard-library/valarray-class.md) **\<型**のオブジェクトへの参照、および選択する要素のシーケンスを記述する`gs`クラス[gslice](../standard-library/gslice-class.md)のオブジェクトへの参照を格納するオブジェクトを表します。`valarray<Type>`オブジェクト。

オブジェクトを`gslice_array<Type>`構築するには、 [va&#91;g&#93;](../standard-library/valarray-class.md#op_at)の形式の式を記述する必要があります。 クラス gslice_array のメンバー関数は、に対し`valarray<Type>`て定義されている対応する関数シグネチャのように動作します。ただし、選択した要素のシーケンスのみが影響を受けます。

テンプレート クラスは、特定の valarray 操作によって間接的に作成されており、プログラムで直接使用することはできません。 代わりに、スライスの添字演算子によって、内部の補助テンプレート クラスが使用されます。

`gslice_array`\< **Type**> `valarray`\< **Type**>:: `operator[]` ( **constgslice&** )

オブジェクトを`gslice_array<Type>`構築するには、valarray `va`のスライス`gsl`に`va[gsl]`対してフォームの式を記述する必要があります。 クラス gslice_array のメンバー関数は、に対し`valarray<Type>`て定義されている対応する関数シグネチャのように動作します。ただし、選択した要素のシーケンスのみが影響を受けます。 gslice_array によって制御されるシーケンスは、スライスのコンストラクターの 3 つのパラメーター (最初のスライス内の最初の要素のインデックス、各スライス内の要素の数、各スライス内の要素間の距離) によって定義されます。

次に例を示します。

```cpp
const size_t lv[] = {2, 3};
const size_t dv[] = {7, 2};
const valarray<size_t> len(lv, 2), str(dv, 2);

// va[gslice(3, len, str)] selects elements with
//   indices 3, 5, 7, 10, 12, 14
```

プロシージャが有効であるためには、これらのインデックスが有効である必要があります。

## <a name="example"></a>例

slice_array の宣言方法や使用例については、[gslice::gslice](../standard-library/gslice-class.md#gslice) の例を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<valarray>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
