---
title: tiled_index クラス
ms.date: 03/27/2019
f1_keywords:
- tiled_index
- AMP/tiled_index
- AMP/Concurrency::tiled_index::tiled_index
- AMP/Concurrency::tiled_index::get_tile_extent
- AMP/Concurrency::tiled_index::barrier
- AMP/Concurrency::tiled_index::global
- AMP/Concurrency::tiled_index::local
- AMP/Concurrency::tiled_index::rank
- AMP/Concurrency::tiled_index::tile
- AMP/Concurrency::tiled_index::tile_dim0
- AMP/Concurrency::tiled_index::tile_dim1
- AMP/Concurrency::tiled_index::tile_dim2
- AMP/Concurrency::tiled_index::tile_origin
- AMP/Concurrency::tiled_index::tile_extent
helpviewer_keywords:
- tiled_index class
ms.assetid: 0ce2ae26-f1bb-4436-b473-a9e1b619bb38
ms.openlocfilehash: 46a6b3548526f0917c4e022a12bf859242e70b20
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375481"
---
# <a name="tiled_index-class"></a>tiled_index クラス

[tiled_extent](tiled-extent-class.md)オブジェクトへのインデックスを提供します。 このクラスには、ローカル タイルの原点およびグローバル原点を基準として要素にアクセスするためのプロパティがあります。 タイルスペースの詳細については、「[タイルの使用](../../../parallel/amp/using-tiles.md)」を参照してください。

## <a name="syntax"></a>構文

```cpp
template <
    int _Dim0,
    int _Dim1 = 0,
    int _Dim2 = 0
>
class tiled_index : public _Tiled_index_base<3>;

template <
    int _Dim0,
    int _Dim1
>
class tiled_index<_Dim0, _Dim1, 0> : public _Tiled_index_base<2>;

template <
    int _Dim0
>
class tiled_index<_Dim0, 0, 0> : public _Tiled_index_base<1>;
```

### <a name="parameters"></a>パラメーター

*_Dim0*<br/>
最上位の次元の長さ。

*_Dim1*<br/>
最上位の次の次元の長さ。

*_Dim2*<br/>
最下位の次元の長さ。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[tiled_indexコンストラクタ](#ctor)|`tile_index` クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[get_tile_extent](#tiled_index__get_tile_extent)|`tiled_index`テンプレート引数`_Dim0`、、`_Dim1`および`_Dim2`の値を持つ[範囲](extent-class.md)オブジェクトを返します。|

### <a name="public-constants"></a>パブリック定数

|名前|説明|
|----------|-----------------|
|[バリア定数](#tiled_index__barrier)|現在のスレッド タイルのバリアを表す[tile_barrier](tile-barrier-class.md)オブジェクトを格納します。|
|||
|[グローバルコンスタント](#tiled_index__global)|グリッド オブジェクトのグローバル[インデックス](index-class.md)を表すランク 1、2、または 3 のインデックス オブジェクトを格納します。|
|[ローカル定数](#tiled_index__local)|tiled_extent`index`オブジェクトの現在のタイルの相対インデックスを表すランク 1、2、または 3[tiled_extent](tiled-extent-class.md)のオブジェクトを格納します。|
|[ランク定数](#tiled_index__rank)|`tiled_index` オブジェクトのランクを格納します。|
|[タイル定数](#tiled_index__tile)|`index` オブジェクトの現在のタイルの座標を表すランク 1、2、または 3 の `tiled_extent` オブジェクトを格納します。|
|[tile_dim0定数](#tiled_index__tile_dim0)|最上位の次元の長さを格納します。|
|[tile_dim1定数](#tiled_index__tile_dim1)|最上位の次の次元の長さを格納します。|
|[tile_dim2定数](#tiled_index__tile_dim2)|最下位の次元の長さを格納します。|
|[tile_origin定数](#tiled_index__tile_origin)|`index` オブジェクトの現在のタイルの原点のグローバル座標を表すランク 1、2、または 3 の `tiled_extent` オブジェクトを格納します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[tile_extent](#tile_extent)|テンプレート引数`tiled_index`テンプレート引数`_Dim0`、および`_Dim1``_Dim2`の値`tiled_index`を持つ[範囲](extent-class.md)オブジェクトを取得します。|

## <a name="inheritance-hierarchy"></a>継承階層

`_Tiled_index_base`

`tiled_index`

## <a name="requirements"></a>必要条件

**ヘッダー:** amp.h

**名前空間:** Concurrency

## <a name="tiled_index-constructor"></a><a name="ctor"></a>tiled_indexコンストラクタ

`tiled_index` クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
tiled_index(
    const index<rank>& _Global,
    const index<rank>& _Local,
    const index<rank>& _Tile,
    const index<rank>& _Tile_origin,
    const tile_barrier& _Barrier ) restrict(amp,cpu);

tiled_index(
    const tiled_index& _Other ) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター

*_Global*<br/>
構築された[index](index-class.md)`tiled_index`のグローバル インデックス。

*_Local*<br/>
構築された[ローカルインデックス](index-class.md)`tiled_index`

*_Tile*<br/>
構築されたタイル[インデックス](index-class.md)`tiled_index`

*_Tile_origin*<br/>
構築されたタイルの原点[インデックス](index-class.md)`tiled_index`

*_Barrier*<br/>
構築[tile_barrier](tile-barrier-class.md)された`tiled_index`のtile_barrierオブジェクト。

*_Other*<br/>
構築された `tile_index` にコピーされる `tiled_index` オブジェクトです。

### <a name="overloads"></a>Overloads

|||
|-|-|
|名前|説明|
|`tiled_index(const index<rank>& _Global, const index<rank>& _Local, const index<rank>& _Tile, const index<rank>& _Tile_origin, const tile_barrier& _Barrier restrict(amp,cpu);`|グローバル座標のタイルのインデックスおよびローカル座標のタイルの相対位置から `tile_index` クラスの新しいインスタンスを初期化します。 `_Global` パラメーターおよび `_Tile_origin` パラメーターが計算されます。|
|`tiled_index(    const tiled_index& _Other) restrict(amp,cpu);`|指定した `tile_index` オブジェクトをコピーして、`tiled_index` クラスの新しいインスタンスを初期化します。|

## <a name="get_tile_extent"></a><a name="tiled_index__get_tile_extent"></a>get_tile_extent

`tiled_index`テンプレート引数`_Dim0`、、`_Dim1`および`_Dim2`の値を持つ[範囲](extent-class.md)オブジェクトを返します。

### <a name="syntax"></a>構文

```cpp
extent<rank> get_tile_extent()restrict(amp,cpu);
```

### <a name="return-value"></a>戻り値

テンプレート`extent`引数`_Dim0`、、`_Dim1`および`_Dim2`の`tiled_index`値を持つオブジェクト。

## <a name="barrier"></a><a name="tiled_index__barrier"></a>障壁

現在のスレッド タイルのバリアを表す[tile_barrier](tile-barrier-class.md)オブジェクトを格納します。

### <a name="syntax"></a>構文

```cpp
const tile_barrier barrier;
```

## <a name="global"></a><a name="tiled_index__global"></a>グローバル

オブジェクトのグローバル インデックスを表すランク 1、2、または 3 の[インデックス](index-class.md)オブジェクトを格納します。

### <a name="syntax"></a>構文

```cpp
const index<rank> global;
```

## <a name="local"></a><a name="tiled_index__local"></a>地元の

[tiled_extent](tiled-extent-class.md)オブジェクトの現在のタイルの相対インデックスを表すランク 1、2、または 3 の[インデックス](index-class.md)オブジェクトを格納します。

### <a name="syntax"></a>構文

```cpp
const index<rank> local;
```

## <a name="rank"></a><a name="tiled_index__rank"></a>ランク

`tiled_index` オブジェクトのランクを格納します。

### <a name="syntax"></a>構文

```cpp
static const int rank = _Rank;
```

## <a name="tile"></a><a name="tiled_index__tile"></a>タイル

[tiled_extent](tiled-extent-class.md)オブジェクトの現在のタイルの座標を表す、ランク 1、2、または 3 の[インデックス](index-class.md)オブジェクトを格納します。

### <a name="syntax"></a>構文

```cpp
const index<rank> tile;
```

## <a name="tile_dim0"></a><a name="tiled_index__tile_dim0"></a>tile_dim0

最上位の次元の長さを格納します。

### <a name="syntax"></a>構文

```cpp
static const int tile_dim0 = _Dim0;
```

## <a name="tile_dim1"></a><a name="tiled_index__tile_dim1"></a>tile_dim1

最上位の次の次元の長さを格納します。

### <a name="syntax"></a>構文

```cpp
static const int tile_dim1 = _Dim1;
```

## <a name="tile_dim2"></a><a name="tiled_index__tile_dim2"></a>tile_dim2

最下位の次元の長さを格納します。

### <a name="syntax"></a>構文

```cpp
static const int tile_dim2 = _Dim2;
```

## <a name="tile_origin"></a><a name="tiled_index__tile_origin"></a>tile_origin

[tiled_extent](tiled-extent-class.md)オブジェクト内の現在のタイルの原点のグローバル座標を表す、ランク 1、2、または 3 の[インデックス](index-class.md)オブジェクトを格納します。

### <a name="syntax"></a>構文

```cpp
const index<rank> tile_origin
```

## <a name="tile_extent"></a><a name="tile_extent"></a>tile_extent

テンプレート引数`tiled_index`テンプレート引数`_Dim0`、および`_Dim1``_Dim2`の値`tiled_index`を持つ[範囲](extent-class.md)オブジェクトを取得します。

### <a name="syntax"></a>構文

```cpp
__declspec(property(get= get_tile_extent)) extent<rank> tile_extent;
```

## <a name="see-also"></a>関連項目

[同時実行名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
