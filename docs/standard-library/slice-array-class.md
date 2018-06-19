---
title: slice_array クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- valarray/std::slice_array
dev_langs:
- C++
helpviewer_keywords:
- slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67ffb39df8f02df233a31cfffeea5ab5ddcdf933
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855443"
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

## <a name="remarks"></a>コメント

このクラスは、**valarray\<Type>** オブジェクトから選択する要素のシーケンスを説明するクラス [slice](../standard-library/slice-class.md) のオブジェクトとともに、クラス [valarray](../standard-library/valarray-class.md)**\<Type>** のオブジェクトへの参照を格納するオブジェクトを表します。

テンプレート クラスは、特定の valarray 操作によって間接的に作成されており、プログラムで直接使用することはできません。 スライスの添字演算子によって使用される、内部の補助テンプレート クラス。

`slice_array`\< **Type**> `valarray`< **Type**:: `operator[]` ( `slice`)

**slice_array\<Type>** オブジェクトの構築は、valarray **va** のスライス **sl** に対して [va&#91;ba&#93;](../standard-library/valarray-class.md#op_at) という形式の式を記述するだけです。 クラス slice_array のメンバー関数は **valarray\<Type>** に対して定義された対応する関数のシグネチャのように動作しますが、選択された要素のシーケンスだけが影響を受けるという点が異なります。 slice_array によって制御されるシーケンスは、スライスのコンストラクターの 3 つのパラメーター (スライス内の最初の要素のインデックス、要素の数、要素間の距離) によって定義されます。 **va**[ `slice`(2, 5, 3)] によって宣言された valarray **va** から切り取られた slice_array は、インデックス 2、5、8、11、および 14 を含む要素を **va** から選択します。 これらのインデックスは、有効にする手順に対して有効である必要があります。

## <a name="example"></a>例

slice_array の宣言方法や使用方法の例については、[slice::slice](../standard-library/slice-class.md#slice) の例を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** \<valarray>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
