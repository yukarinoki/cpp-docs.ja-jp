---
title: '&lt;complex&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <complex>
- std::<complex>
dev_langs:
- C++
helpviewer_keywords:
- complex header
ms.assetid: 5e728995-3059-496a-9ce9-61d1bfbe4f2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a29dfc976ca29405814bbae81f42a02a74300d74
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33847625"
---
# <a name="ltcomplexgt"></a>&lt;complex&gt;

コンテナー テンプレート クラスを定義**複雑な**とそのサポート用テンプレート。

## <a name="syntax"></a>構文

```cpp
#include <complex>
```

## <a name="remarks"></a>コメント

複素数は、順序付けされた実数のペアです。 純粋に幾何学的な見地からすれば、複素平面は実数からなる 2 次元平面です。 複素平面には代数構造が加えられているため、実数平面とは異なる特殊な性質を持ちます。 この代数構造には次の 2 つの基本的な演算が含まれます。

- として定義されている加算 (*、*、 *b*) + (*c*、 *d*) = (*、* + *c*、 *b* + *d*)

- 定義される乗算 (*、*、 *b*) \* (*c*、 *d*) = (*ac*  -  *bd*、 *ad* + *bc*)

複素数の加算や乗算を伴う複素数の集合は、標準の代数学的な意味での体 (field) です。

- 実数の体 (field) における実数の加算や乗算と全く同様、加算や乗算の演算には交換法則や結合法則が成り立ち、加法に対する乗法の分配法則も成り立ちます。

- 複素数 (0, 0) が加法と (1, 0) が乗法です。

- 複素数の加法に関する逆元 (*、*、 *b*) は (-*、*、-*b*)、および、このようなすべての複素数の乗法の逆関数除く (0, 0) が

   (*、*/(*、*<sup>2</sup> + *b*<sup>2</sup>)、-*b*/(*、*<sup>2</sup> + *b*<sup>2</sup>))

複素数を表す*z* = (*、*、 *b*) 形式で*z* = *、*  + *bi*ここで、*すれば*<sup>2</sup> =-1 で、規則の複素数のセットとそのコンポーネントは、実数の集合の代数を適用することができます。 例えば:

   (1 + 2*すれば*) \* (2 + 3*すれば*)  
   = 1 \* (2 + 3*すれば*) + 2*すれば* \* (2 + 3*すれば*)  
   = (2 + 3*すれば*) + (4*すれば*6 +*すれば*<sup>2</sup>)  
   = (2 - 6) + (3 + 4)*i*  
   = -4 + 7*i*

複素数系は体 (field) ですが、順序体 (ordered field) ではありません。 あるため、実数とそのサブセットのフィールドのような不等式には実数複素数には適用できませんの複素数の順序がありません。

複素数 *z* を表す形式としては、次の 3 つが一般的です。

- デカルト形式: *z* = *、* + *bi*

- 極形式: *z* = *r* (cos *p* + *すれば*sin *p*)

- 指数近似: *z* = *r* \* *e*<sup>*ip*</sup>

これらの標準的な複素数の表現で使用される用語は、次のように呼ばれます。

- デカルト形式の実数要素、または実数部 *a*。

- デカルト形式の虚数要素、または虚数部 *b*。

- 係数、もしくは複素数の絶対値*r*です。

- 偏角または位相角*p* (ラジアン単位)。

複数の値を返すことができる関数は - π より大きく、その引数としての主値を返すときに必要でない限りよりまたは等しい + π 一価にしています。 すべての角度をラジアン単位で表す必要がありますが、円で囲んだ 2 π ラジアン (360 °) がある場合。

### <a name="functions"></a>関数

|関数|説明|
|-|-|
|[abs](../standard-library/complex-functions.md#abs)|複素数の係数を計算します。|
|[arg](../standard-library/complex-functions.md#arg)|複素数から偏角を抽出します。|
|[conj](../standard-library/complex-functions.md#conj)|複素数の複素共役を返します。|
|[cos](../standard-library/complex-functions.md#cos)|複素数のコサインを返します。|
|[cosh](../standard-library/complex-functions.md#cosh)|複素数のハイパーボリック コサインを返します。|
|[exp](../standard-library/complex-functions.md#exp)|複素数の指数関数を返します。|
|[imag](../standard-library/complex-functions.md#imag)|複素数の虚数部を抽出します。|
|[log](../standard-library/complex-functions.md#log)|複素数の自然対数を返します。|
|[log10](../standard-library/complex-functions.md#log10)|複素数の底 10 の対数を返します。|
|[norm](../standard-library/complex-functions.md#norm)|複素数のノルムを抽出します。|
|[polar](../standard-library/complex-functions.md#polar)|デカルト形式で、指定した係数と偏角に対応する複素数を返します。|
|[pow](../standard-library/complex-functions.md#pow)|複素数の底を、別の複素数で累乗することによって得られる複素数を評価します。|
|[real](../standard-library/complex-functions.md#real)|複素数の実数部を抽出します。|
|[sin](../standard-library/complex-functions.md#sin)|複素数のサインを返します。|
|[sinh](../standard-library/complex-functions.md#sinh)|複素数のハイパーボリック サインを返します。|
|[sqrt](../standard-library/complex-functions.md#sqrt)|複素数の平方根を返します。|
|[tan](../standard-library/complex-functions.md#tan)|複素数のタンジェントを返します。|
|[tanh](../standard-library/complex-functions.md#tanh)|複素数のハイパーボリック タンジェントを返します。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator!=](../standard-library/complex-operators.md#op_neq)|2 つの複素数の間の非同等性をテストします。その一方または両方が実数部と虚数部の型のサブセットに属している場合があります。|
|[operator*](../standard-library/complex-operators.md#op_star)|2 つの複素数を乗算します。その一方または両方が実数部と虚数部の型のサブセットに属している場合があります。|
|[operator+](../standard-library/complex-operators.md#op_add)|2 つの複素数を加算します。その一方または両方が実数部と虚数部の型のサブセットに属している場合があります。|
|[operator-](../standard-library/complex-operators.md#operator-)|2 つの複素数を減算します。その一方または両方が実数部と虚数部の型のサブセットに属している場合があります。|
|[operator/](../standard-library/complex-operators.md#op_div)|2 つの複素数を除算します。その一方または両方が実数部と虚数部の型のサブセットに属している場合があります。|
|[operator<\<](../standard-library/complex-operators.md#op_lt_lt)|出力ストリームに複素数を挿入するテンプレート関数。|
|[operator==](../standard-library/complex-operators.md#op_eq_eq)|2 つの複素数の間の同等性をテストします。その一方または両方が実数部と虚数部の型のサブセットに属している場合があります。|
|[operator>>](../standard-library/complex-operators.md#op_gt_gt)|入力ストリームから複素数を抽出するテンプレート関数。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[complex\<double>](../standard-library/complex-double.md)|明示的に特化したテンプレート クラスは両方の種類のオブジェクトの順序付けされたペアを格納するオブジェクトを表します**二重**複素数の実数部を表し、次の虚数部を表します。|
|[complex\<float>](../standard-library/complex-float.md)|明示的に特化したテンプレート クラスは両方の種類のオブジェクトの順序付けされたペアを格納するオブジェクトを表します**float**複素数の実数部を表し、次の虚数部を表します。|
|[complex\<long double>](../standard-library/complex-long-double.md)|明示的に特化したテンプレート クラスは両方の種類のオブジェクトの順序付けされたペアを格納するオブジェクトを表します**long double**複素数の実数部を表し、次の虚数部を表します。|
|[complex](../standard-library/complex-class.md)|このテンプレート クラスは、複素数の算術演算に使用する複素数系を表すオブジェクトを記述します。|

### <a name="literals"></a>リテラル

\<complex> ヘッダーでは次の[ユーザー定義リテラル](../cpp/user-defined-literals-cpp.md)が定義されており、実数部が 0 および虚数部が入力パラメーターの値である複素数を作成します。

|||
|-|-|
|`constexpr complex<long double> operator""il(long double d)`<br /><br /> `constexpr complex<long double> operator""il(unsigned long long d)`|返します。 `complex<long double>{0.0L, static_cast<long double>(d)}`|
|`constexpr complex<double> operator""i(long double d)`<br /><br /> `constexpr complex<double> operator""i(unsigned long long d)`|`complex<double>{0.0, static_cast<double>(d)}` を返します。|
|`constexpr complex<float> operator""if(long double d)`<br /><br /> `constexpr complex<float> operator""if(unsigned long long d)`|`complex<float>{0.0f, static_cast<float>(d)}` を返します。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
