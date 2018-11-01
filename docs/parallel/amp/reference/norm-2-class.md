---
title: norm_2 クラス
ms.date: 11/04/2016
f1_keywords:
- amp_short_vectors/Concurrency::graphics::norm_2::set_x
- amp_short_vectors/Concurrency::graphics::norm_2::set_xy
- amp_short_vectors/Concurrency::graphics::norm_2::g
- amp_short_vectors/Concurrency::graphics::norm_2::get_yx
- amp_short_vectors/Concurrency::graphics::norm_2::set_yx
- amp_short_vectors/Concurrency::graphics::norm_2::operator-=
- amp_short_vectors/Concurrency::graphics::norm_2::operator/=
- amp_short_vectors/Concurrency::graphics::norm_2::operator*=
- amp_short_vectors/Concurrency::graphics::norm_2::yx
- amp_short_vectors/Concurrency::graphics::norm_2::y
- amp_short_vectors/Concurrency::graphics::norm_2::xy
- amp_short_vectors/Concurrency::graphics::norm_2::operator++
- amp_short_vectors/Concurrency::graphics::norm_2::operator-
- amp_short_vectors/Concurrency::graphics::norm_2::rg
- amp_short_vectors/Concurrency::graphics::norm_2::operator=
- amp_short_vectors/Concurrency::graphics::norm_2::get_y
- amp_short_vectors/Concurrency::graphics::norm_2::r
- amp_short_vectors/Concurrency::graphics::norm_2::get_x
- amp_short_vectors/Concurrency::graphics::norm_2::get_xy
- amp_short_vectors/Concurrency::graphics::norm_2::gr
- amp_short_vectors/Concurrency::graphics::norm_2::set_y
- amp_short_vectors/Concurrency::graphics::norm_2::x
- amp_short_vectors/Concurrency::graphics::norm_2::operator+=
- amp_short_vectors/Concurrency::graphics::norm_2
- amp_short_vectors/Concurrency::graphics::norm_2::operator--
ms.assetid: 80703f9b-61f4-414a-93fd-bc774f7d3393
ms.openlocfilehash: ebf1a80a695f1d25652f239f66d8d40c0e1099ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542218"
---
# <a name="norm2-class"></a>norm_2 クラス

2 個の正規数の short ベクターを表します。

## <a name="syntax"></a>構文

```
class norm_2;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`value_type`||

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[norm_2 コンス トラクター](#ctor)|オーバーロードされます。 既定のコンストラクター。すべての要素を 0 で初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|norm_2::get_x||
|norm_2::get_xy||
|norm_2::get_y||
|norm_2::get_yx||
|norm_2::ref_g||
|norm_2::ref_r||
|norm_2::ref_x||
|norm_2::ref_y||
|norm_2::set_x||
|norm_2::set_xy||
|norm_2::set_y||
|norm_2::set_yx||

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|norm_2::operator-||
|norm_2::operator--||
|norm_2::operator*=||
|norm_2::operator/=||
|norm_2::operator++||
|norm_2::operator+=||
|norm_2::operator=||
|norm_2::operator-=||

### <a name="public-constants"></a>パブリック定数

|名前|説明|
|----------|-----------------|
|[定数のサイズ](#norm_2__size)||

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|norm_2::g||
|norm_2::gr||
|norm_2::r||
|norm_2::rg||
|norm_2::x||
|norm_2::xy||
|norm_2::y||
|norm_2::yx||

## <a name="inheritance-hierarchy"></a>継承階層

`norm_2`

## <a name="requirements"></a>必要条件

**ヘッダー:** amp_short_vectors.h

**Namespace:** concurrency::graphics

##  <a name="ctor"></a> norm_2

既定のコンストラクター。すべての要素を 0 で初期化します。

```
norm_2() restrict(amp,
    cpu);

norm_2(
    norm _V0,
    norm _V1) restrict(amp,
    cpu);

norm_2(
    float _V0,
    float _V1) restrict(amp,
    cpu);

norm_2(
    unorm _V0,
    unorm _V1) restrict(amp,
    cpu);

norm_2(
    norm _V) restrict(amp,
    cpu);

explicit norm_2(
    float _V) restrict(amp,
    cpu);

norm_2(
    const norm_2& _Other) restrict(amp,
    cpu);

explicit inline norm_2(
    const uint_2& _Other) restrict(amp,
    cpu);

explicit inline norm_2(
    const int_2& _Other) restrict(amp,
    cpu);

explicit inline norm_2(
    const float_2& _Other) restrict(amp,
    cpu);

explicit inline norm_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

explicit inline norm_2(
    const double_2& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>パラメーター

*_V0*<br/>
0 の要素を初期化する値。

*_V1*<br/>
1 要素を初期化する値。

*(_V).*<br/>
初期化の値。

*_Other*<br/>
初期化するために使用するオブジェクト。

##  <a name="norm_2__size"></a> サイズ

```
static const int size = 2;
```

## <a name="see-also"></a>関連項目

[Concurrency::graphics 名前空間](concurrency-graphics-namespace.md)
