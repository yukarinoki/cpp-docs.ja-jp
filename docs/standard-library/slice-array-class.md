---
description: '詳細情報: slice_array クラス'
title: slice_array クラス
ms.date: 11/04/2016
f1_keywords:
- valarray/std::slice_array
helpviewer_keywords:
- slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
ms.openlocfilehash: 580a09d99b08bc563c64571247d74a980eb229f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153981"
---
# <a name="slice_array-class"></a>slice_array クラス

Valarray のスライスによって定義されたサブセット配列間の演算を提供することによってスライスオブジェクトをサポートする、内部の補助クラステンプレート。

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

## <a name="remarks"></a>解説

クラスは、valarray クラスのオブジェクトへの参照 [を、](../standard-library/valarray-class.md) **\<Type>** **valarray \<Type>** オブジェクトから選択する要素のシーケンスを記述するクラス [スライス](../standard-library/slice-class.md)のオブジェクトと共に格納するオブジェクトを表します。

クラステンプレートは、特定の valarray 操作によって間接的に作成され、プログラムで直接使用することはできません。 スライスの添字演算子によって使用される、内部の補助クラステンプレート。

`slice_array`\< **Type**>`valarray` <  **「**: ()」と入力 `operator[]` `slice` します。

オブジェクトを構築する `slice_array<Type>` には、valarray のスライスに対して、 [va&#91;sl&#93;](../standard-library/valarray-class.md#op_at)の形式の式を記述する必要が `sl` `va` あります。 クラス slice_array のメンバー関数は、に対して定義されている対応する関数シグネチャと同様に動作し `valarray<Type>` ますが、選択された要素のシーケンスのみが影響を受けます。 slice_array によって制御されるシーケンスは、スライスのコンストラクターの 3 つのパラメーター (スライス内の最初の要素のインデックス、要素の数、要素間の距離) によって定義されます。 Va によって宣言された valarray からの slice_array 切り取り `va` [  `slice` (2, 5, 3)] は、インデックス2、5、8、11、および14の要素をから選択し `va` ます。 プロシージャが有効であるためには、これらのインデックスが有効である必要があります。

## <a name="example"></a>例

slice_array の宣言方法や使用方法の例については、[slice::slice](../standard-library/slice-class.md#slice) の例を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:**\<valarray>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
