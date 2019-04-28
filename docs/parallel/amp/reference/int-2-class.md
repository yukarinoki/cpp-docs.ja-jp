---
title: int_2 クラス
ms.date: 11/04/2016
f1_keywords:
- amp_short_vectors/Concurrency::graphics::int_2::y
- amp_short_vectors/Concurrency::graphics::int_2::set_x
- amp_short_vectors/Concurrency::graphics::int_2::set_y
- amp_short_vectors/Concurrency::graphics::int_2::get_yx
- amp_short_vectors/Concurrency::graphics::int_2::operator++
- amp_short_vectors/Concurrency::graphics::int_2::x
- amp_short_vectors/Concurrency::graphics::int_2::set_yx
- amp_short_vectors/Concurrency::graphics::int_2::operator/=
- amp_short_vectors/Concurrency::graphics::int_2::get_y
- amp_short_vectors/Concurrency::graphics::int_2::gr
- amp_short_vectors/Concurrency::graphics::int_2::operator*=
- amp_short_vectors/Concurrency::graphics::int_2::r
- amp_short_vectors/Concurrency::graphics::int_2::get_xy
- amp_short_vectors/Concurrency::graphics::int_2::operator=
- amp_short_vectors/Concurrency::graphics::int_2::g
- amp_short_vectors/Concurrency::graphics::int_2::rg
- amp_short_vectors/Concurrency::graphics::int_2::xy
- amp_short_vectors/Concurrency::graphics::int_2::operator-=
- amp_short_vectors/Concurrency::graphics::int_2::get_x
- amp_short_vectors/Concurrency::graphics::int_2::yx
- amp_short_vectors/Concurrency::graphics::int_2
- amp_short_vectors/Concurrency::graphics::int_2::operator-
- amp_short_vectors/Concurrency::graphics::int_2::set_xy
- amp_short_vectors/Concurrency::graphics::int_2::operator+=
- amp_short_vectors/Concurrency::graphics::int_2::operator--
ms.assetid: 258b02e9-f1ee-46c2-8edd-dc9f69184846
ms.openlocfilehash: 3c5aefbfd1a4b06274fac0f56c1e1e45ef9dc5bd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180259"
---
# <a name="int2-class"></a>int_2 クラス

2 個の整数の short ベクターを表します。

## <a name="syntax"></a>構文

```
class int_2;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`value_type`||

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[int_2 コンス トラクター](#ctor)|オーバーロードされます。 既定のコンストラクター。すべての要素を 0 で初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|int_2::get_x||
|int_2::get_xy||
|int_2::get_y||
|int_2::get_yx||
|int_2::ref_g||
|int_2::ref_r||
|int_2::ref_x||
|int_2::ref_y||
|int_2::set_x||
|int_2::set_xy||
|int_2::set_y||
|int_2::set_yx||

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|int_2::operator-||
|int_2::operator--||
|int_2::operator%=||
|int_2::operator&=||
|int_2::operator*=||
|int_2::operator/=||
|int_2::operator^=||
|int_2::operator&#124;=||
|int_2::operator~||
|int_2::operator++||
|int_2::operator+=||
|int_2::operator<\<=||
|int_2::operator=||
|int_2::operator-=||
|int_2::operator>>=||

### <a name="public-constants"></a>パブリック定数

|名前|説明|
|----------|-----------------|
|[定数のサイズ](#int_2__size)||

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|int_2::g||
|int_2::gr||
|int_2::r||
|int_2::rg||
|int_2::x||
|int_2::xy||
|int_2::y||
|int_2::yx||

## <a name="inheritance-hierarchy"></a>継承階層

`int_2`

## <a name="requirements"></a>必要条件

**ヘッダー:** amp_short_vectors.h

**名前空間:** Concurrency::graphics

##  <a name="ctor"></a> int_2

既定のコンストラクター。すべての要素を 0 で初期化します。

```
int_2() restrict(amp,
    cpu);

int_2(
    int _V0,
    int _V1) restrict(amp,
    cpu);

int_2(
    int _V) restrict(amp,
    cpu);

int_2(
    const int_2& _Other) restrict(amp,
    cpu);

explicit inline int_2(
    const uint_2& _Other) restrict(amp,
    cpu);

explicit inline int_2(
    const float_2& _Other) restrict(amp,
    cpu);

explicit inline int_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

explicit inline int_2(
    const norm_2& _Other) restrict(amp,
    cpu);

explicit inline int_2(
    const double_2& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>パラメーター

*_V0*<br/>
0 の要素を初期化する値。

*_V1*<br/>
1 要素を初期化する値。

*_V*<br/>
初期化の値。

*_Other*<br/>
初期化するために使用するオブジェクト。

##  <a name="int_2__size"></a> サイズ

```
static const int size = 2;
```

## <a name="see-also"></a>関連項目

[Concurrency::graphics 名前空間](concurrency-graphics-namespace.md)
