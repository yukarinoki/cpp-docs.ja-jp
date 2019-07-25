---
title: slice_array クラス
ms.date: 11/04/2016
f1_keywords:
- valarray/std::slice_array
helpviewer_keywords:
- slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
ms.openlocfilehash: cf33c5f627a88698c84947f9b803edaebccf5566
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450402"
---
# <a name="slicearray-class"></a>slice_array クラス

valarray のスライスで定義されるサブセット配列間の演算を提供することによりスライス オブジェクトをサポートする、内部の補助テンプレート クラス。

## <a name="syntax"></a>構文

```cpp
template <class Type>
class slice_array : public slice {
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

このクラスは、**valarray\<Type>** オブジェクトから選択する要素のシーケンスを説明するクラス [slice](../standard-library/slice-class.md) のオブジェクトとともに、クラス [valarray](../standard-library/valarray-class.md) **\<Type>** のオブジェクトへの参照を格納するオブジェクトを表します。

テンプレート クラスは、特定の valarray 操作によって間接的に作成されており、プログラムで直接使用することはできません。 スライスの添字演算子によって使用される、内部の補助テンプレート クラス。

`slice_array`\< **Type**> `valarray`< **Type**:: `operator[]` ( `slice`)

オブジェクトを`slice_array<Type>`構築するには、valarray `va`のスライス`sl`に対して、 [va&#91;sl&#93;](../standard-library/valarray-class.md#op_at)という形式の式を記述する必要があります。 クラス slice_array のメンバー関数は、に対し`valarray<Type>`て定義されている対応する関数シグネチャのように動作します。ただし、選択した要素のシーケンスのみが影響を受けます。 slice_array によって制御されるシーケンスは、スライスのコンストラクターの 3 つのパラメーター (スライス内の最初の要素のインデックス、要素の数、要素間の距離) によって定義されます。 `va` **Va**[ `va`(2, 5, 3)] によって宣言された valarray からの slice_array cut は、インデックス2、5、8、11、および14の要素をから選択します。 `slice` プロシージャが有効であるためには、これらのインデックスが有効である必要があります。

## <a name="example"></a>例

slice_array の宣言方法や使用方法の例については、[slice::slice](../standard-library/slice-class.md#slice) の例を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<valarray>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
