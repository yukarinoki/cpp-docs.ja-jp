---
title: gslice_array クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- valarray/std::gslice_array
dev_langs:
- C++
helpviewer_keywords:
- gslice_array class
ms.assetid: ad1b4514-b14a-4baf-a293-d5a8e8674c75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff44a91b4916092e319c7acc0520c49aeb9a5fa4
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953076"
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

クラスは、オブジェクトへの参照を格納するオブジェクトを表します`va`クラスの[valarray](../standard-library/valarray-class.md)**\<型 >**、オブジェクトと共に`gs`クラスの[gslice](../standard-library/gslice-class.md)から選択する要素のシーケンスを説明する、`valarray<Type>`オブジェクト。

構築する、`gslice_array<Type>`オブジェクト形式の式を記述するだけ[va&#91;gs&#93;](../standard-library/valarray-class.md#op_at)します。 クラス gslice_array のメンバー関数に対して定義された対応する関数のシグネチャのように動作します`valarray<Type>`選択した要素のシーケンスだけが影響を受けることを除いて、します。

テンプレート クラスは、特定の valarray 操作によって間接的に作成されており、プログラムで直接使用することはできません。 代わりに、スライスの添字演算子によって、内部の補助テンプレート クラスが使用されます。

`gslice_array`\< **Type**> `valarray`\< **Type**>:: `operator[]` ( **constgslice&**)

構築する、`gslice_array<Type>`オブジェクト形式の式を記述するだけ`va[gsl]`、スライスの`gsl`valarray の`va`します。 クラス gslice_array のメンバー関数に対して定義された対応する関数のシグネチャのように動作します`valarray<Type>`選択した要素のシーケンスだけが影響を受けることを除いて、します。 gslice_array によって制御されるシーケンスは、スライスのコンストラクターの 3 つのパラメーター (最初のスライス内の最初の要素のインデックス、各スライス内の要素の数、各スライス内の要素間の距離) によって定義されます。

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

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
