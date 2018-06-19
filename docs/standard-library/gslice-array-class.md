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
ms.openlocfilehash: ff9718a98244379fccde78b18fa70ef46c7e7a76
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845646"
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

## <a name="remarks"></a>コメント

このクラスは、クラス [gslice](../standard-library/gslice-class.md) のオブジェクト **gs** と共に、クラス [valarray](../standard-library/valarray-class.md)**\<Type>** のオブジェクト **va** への参照を格納するオブジェクトを表します。これらは **valarray\<Type>** オブジェクトから選択する要素のシーケンスを説明します。

**gslice_array\<Type>** オブジェクトの構築は、[va&#91;gs&#93;](../standard-library/valarray-class.md#op_at) という形式の式を記述するだけです。 クラス gslice_array のメンバー関数は **valarray\<Type>** に対して定義された対応する関数のシグネチャのように動作しますが、選択された要素のシーケンスだけが影響を受けるという点が異なります。

テンプレート クラスは、特定の valarray 操作によって間接的に作成され、プログラムで直接使用することはできません。 代わりに、スライスの添字演算子によって、内部の補助テンプレート クラスが使用されます。

`gslice_array`\< **Type**> `valarray`\< **Type**>:: `operator[]` ( **constgslice&**)

**gslice_array\<Type>** オブジェクトの構築は、valarray **va** のスライス **gsl** に対して **va[gsl]** という形式の式を記述するだけです。 クラス gslice_array のメンバー関数は **valarray\<Type>** に対して定義された対応する関数のシグネチャのように動作しますが、選択された要素のシーケンスだけが影響を受けるという点が異なります。 gslice_array によって制御されるシーケンスは、スライスのコンストラクターの 3 つのパラメーター (最初のスライス内の最初の要素のインデックス、各スライス内の要素の数、各スライス内の要素間の距離) によって定義されます。

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

**ヘッダー:** \<valarray>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
