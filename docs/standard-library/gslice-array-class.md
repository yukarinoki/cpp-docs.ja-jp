---
description: '詳細情報: gslice_array クラス'
title: gslice_array クラス
ms.date: 11/04/2016
f1_keywords:
- valarray/std::gslice_array
helpviewer_keywords:
- gslice_array class
ms.assetid: ad1b4514-b14a-4baf-a293-d5a8e8674c75
ms.openlocfilehash: 2c3cf29cd80d874265ec86d5c31a10e5c8359b8e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232032"
---
# <a name="gslice_array-class"></a>gslice_array クラス

Valarray の一般的なスライスによって定義されたサブセット配列間の演算を提供することによって一般的なスライスオブジェクトをサポートする、内部の補助クラステンプレート。

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

## <a name="remarks"></a>解説

クラスは、クラス valarray のオブジェクトへの参照を、 `va` [](../standard-library/valarray-class.md) **\<Type>** `gs` オブジェクトから選択する要素のシーケンスを記述するクラス [gslice](../standard-library/gslice-class.md)のオブジェクトと共に格納するオブジェクトを表し `valarray<Type>` ます。

オブジェクトを構築するには、 `gslice_array<Type>` [va&#91;gs&#93;](../standard-library/valarray-class.md#op_at)の形式の式を記述する必要があります。 クラス gslice_array のメンバー関数は、に対して定義されている対応する関数シグネチャと同様に動作し `valarray<Type>` ますが、選択された要素のシーケンスのみが影響を受けます。

クラステンプレートは、特定の valarray 操作によって間接的に作成され、プログラムで直接使用することはできません。 代わりに、内部補助クラステンプレートがスライスの添字演算子によって使用されます。

`gslice_array`\< **Type**>`valarray` \< **Type**> :: `operator[]` ( **ssisdb&**)。

オブジェクトを構築する `gslice_array<Type>` には `va[gsl]` 、valarray のスライスに対してフォームの式を記述する必要が `gsl` `va` あります。 クラス gslice_array のメンバー関数は、に対して定義されている対応する関数シグネチャと同様に動作し `valarray<Type>` ますが、選択された要素のシーケンスのみが影響を受けます。 gslice_array によって制御されるシーケンスは、スライスのコンストラクターの 3 つのパラメーター (最初のスライス内の最初の要素のインデックス、各スライス内の要素の数、各スライス内の要素間の距離) によって定義されます。

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

## <a name="requirements"></a>要件

**ヘッダー:**\<valarray>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
