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
ms.openlocfilehash: 9d295093031eaee0a2d4dd83aa931060e6eebc07
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832271"
---
# <a name="tiled_index-class"></a>tiled_index クラス

[Tiled_extent](tiled-extent-class.md)オブジェクトのインデックスを提供します。 このクラスには、ローカル タイルの原点およびグローバル原点を基準として要素にアクセスするためのプロパティがあります。 並べて表示するスペースの詳細については、「 [タイルの使用](../../../parallel/amp/using-tiles.md)」を参照してください。

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
|[tiled_index コンストラクター](#ctor)|`tile_index` クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[get_tile_extent](#tiled_index__get_tile_extent)|テンプレート引数、、およびの値を持つ [extent](extent-class.md) オブジェクトを返し `tiled_index` `_Dim0` `_Dim1` `_Dim2` ます。|

### <a name="public-constants"></a>パブリック定数

|名前|説明|
|----------|-----------------|
|[バリア定数](#tiled_index__barrier)|スレッドの現在のタイルのバリアを表す [tile_barrier](tile-barrier-class.md) オブジェクトを格納します。|
|[グローバル定数](#tiled_index__global)|Grid オブジェクトのグローバルインデックスを表すランク1、2、または3の [インデックス](index-class.md) オブジェクトを格納します。|
|[ローカル定数](#tiled_index__local)|`index` [Tiled_extent](tiled-extent-class.md)オブジェクトの現在のタイルの相対インデックスを表すランク1、2、または3のオブジェクトを格納します。|
|[rank 定数](#tiled_index__rank)|`tiled_index` オブジェクトのランクを格納します。|
|[タイル定数](#tiled_index__tile)|`index` オブジェクトの現在のタイルの座標を表すランク 1、2、または 3 の `tiled_extent` オブジェクトを格納します。|
|[tile_dim0 定数](#tiled_index__tile_dim0)|最上位の次元の長さを格納します。|
|[tile_dim1 定数](#tiled_index__tile_dim1)|最上位の次の次元の長さを格納します。|
|[tile_dim2 定数](#tiled_index__tile_dim2)|最下位の次元の長さを格納します。|
|[tile_origin 定数](#tiled_index__tile_origin)|`index` オブジェクトの現在のタイルの原点のグローバル座標を表すランク 1、2、または 3 の `tiled_extent` オブジェクトを格納します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[tile_extent](#tile_extent)|[extent](extent-class.md) `tiled_index` テンプレート引数テンプレート引数、、およびの値を持つ extent オブジェクトを取得し `tiled_index` `_Dim0` `_Dim1` `_Dim2` ます。|

## <a name="inheritance-hierarchy"></a>継承階層

`_Tiled_index_base`

`tiled_index`

## <a name="requirements"></a>必要条件

**ヘッダー:** amp.h

**名前空間:** Concurrency

## <a name="tiled_index-constructor"></a><a name="ctor"></a> tiled_index コンストラクター

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
構築されたのグローバル [インデックス](index-class.md) `tiled_index` 。

*_Local*<br/>
構築されたのローカル[インデックス](index-class.md)`tiled_index`

*_Tile*<br/>
構築されたのタイル[インデックス](index-class.md)`tiled_index`

*_Tile_origin*<br/>
構築されたのタイルの原点の[インデックス](index-class.md)`tiled_index`

*_Barrier*<br/>
構築されたの [tile_barrier](tile-barrier-class.md) オブジェクト `tiled_index` 。

*_Other*<br/>
構築された `tile_index` にコピーされる `tiled_index` オブジェクトです。

### <a name="overloads"></a>オーバーロード

|名前|説明|
|-|-|
|`tiled_index(const index<rank>& _Global, const index<rank>& _Local, const index<rank>& _Tile, const index<rank>& _Tile_origin, const tile_barrier& _Barrier restrict(amp,cpu);`|グローバル座標のタイルのインデックスおよびローカル座標のタイルの相対位置から `tile_index` クラスの新しいインスタンスを初期化します。 `_Global` パラメーターおよび `_Tile_origin` パラメーターが計算されます。|
|`tiled_index(    const tiled_index& _Other) restrict(amp,cpu);`|指定した `tile_index` オブジェクトをコピーして、`tiled_index` クラスの新しいインスタンスを初期化します。|

## <a name="get_tile_extent"></a><a name="tiled_index__get_tile_extent"></a> get_tile_extent

テンプレート引数、、およびの値を持つ [extent](extent-class.md) オブジェクトを返し `tiled_index` `_Dim0` `_Dim1` `_Dim2` ます。

### <a name="syntax"></a>構文

```cpp
extent<rank> get_tile_extent()restrict(amp,cpu);
```

### <a name="return-value"></a>戻り値

`extent` `tiled_index` テンプレート引数の値 `_Dim0` ( `_Dim1` 、、および) を持つオブジェクト `_Dim2` 。

## <a name="barrier"></a><a name="tiled_index__barrier"></a> 壁

スレッドの現在のタイルのバリアを表す [tile_barrier](tile-barrier-class.md) オブジェクトを格納します。

### <a name="syntax"></a>構文

```cpp
const tile_barrier barrier;
```

## <a name="global"></a><a name="tiled_index__global"></a> 全体

オブジェクトのグローバルインデックスを表すランク1、2、または3の [インデックス](index-class.md) オブジェクトを格納します。

### <a name="syntax"></a>構文

```cpp
const index<rank> global;
```

## <a name="local"></a><a name="tiled_index__local"></a> 地元の

[Tiled_extent](tiled-extent-class.md)オブジェクトの現在のタイルの相対インデックスを表すランク1、2、または3の[インデックス](index-class.md)オブジェクトを格納します。

### <a name="syntax"></a>構文

```cpp
const index<rank> local;
```

## <a name="rank"></a><a name="tiled_index__rank"></a> ランク

`tiled_index` オブジェクトのランクを格納します。

### <a name="syntax"></a>構文

```cpp
static const int rank = _Rank;
```

## <a name="tile"></a><a name="tiled_index__tile"></a> タイル

[Tiled_extent](tiled-extent-class.md)オブジェクトの現在のタイルの座標を表すランク1、2、または3の[インデックス](index-class.md)オブジェクトを格納します。

### <a name="syntax"></a>構文

```cpp
const index<rank> tile;
```

## <a name="tile_dim0"></a><a name="tiled_index__tile_dim0"></a> tile_dim0

最上位の次元の長さを格納します。

### <a name="syntax"></a>構文

```cpp
static const int tile_dim0 = _Dim0;
```

## <a name="tile_dim1"></a><a name="tiled_index__tile_dim1"></a> tile_dim1

最上位の次の次元の長さを格納します。

### <a name="syntax"></a>構文

```cpp
static const int tile_dim1 = _Dim1;
```

## <a name="tile_dim2"></a><a name="tiled_index__tile_dim2"></a> tile_dim2

最下位の次元の長さを格納します。

### <a name="syntax"></a>構文

```cpp
static const int tile_dim2 = _Dim2;
```

## <a name="tile_origin"></a><a name="tiled_index__tile_origin"></a> tile_origin

[Tiled_extent](tiled-extent-class.md)オブジェクト内の現在のタイルの原点のグローバル座標を表すランク1、2、または3の[インデックス](index-class.md)オブジェクトを格納します。

### <a name="syntax"></a>構文

```cpp
const index<rank> tile_origin
```

## <a name="tile_extent"></a><a name="tile_extent"></a> tile_extent

[extent](extent-class.md) `tiled_index` テンプレート引数テンプレート引数、、およびの値を持つ extent オブジェクトを取得し `tiled_index` `_Dim0` `_Dim1` `_Dim2` ます。

### <a name="syntax"></a>構文

```cpp
__declspec(property(get= get_tile_extent)) extent<rank> tile_extent;
```

## <a name="see-also"></a>関連項目

[Concurrency 名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
