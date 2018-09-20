---
title: tiled_index クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- tiled_index class
ms.assetid: 0ce2ae26-f1bb-4436-b473-a9e1b619bb38
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5ad67a806bae53234661c19d3f405a526ce5f87
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440772"
---
# <a name="tiledindex-class"></a>tiled_index クラス

インデックスを提供する[tiled_extent](tiled-extent-class.md)オブジェクト。 このクラスには、ローカル タイルの原点およびグローバル原点を基準として要素にアクセスするためのプロパティがあります。 タイル スペースの詳細については、次を参照してください。[を使用してタイル](../../../parallel/amp/using-tiles.md)します。

## <a name="syntax"></a>構文

```
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

#### <a name="parameters"></a>パラメーター

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
|[tiled_index コンス トラクター](#ctor)|`tile_index` クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[get_tile_extent](#tiled_index__get_tile_extent)|返します、[エクステント](extent-class.md)オブジェクトの値を持つ、`tiled_index`テンプレート引数`_Dim0`、 `_Dim1`、および`_Dim2`します。|

### <a name="public-constants"></a>パブリック定数

|名前|説明|
|----------|-----------------|
|[barrier 定数](#tiled_index__barrier)|ストア、 [tile_barrier](tile-barrier-class.md)スレッドの現在のタイルのバリアを表すオブジェクト。|
|||
|[グローバル定数](#tiled_index__global)|ストア、[インデックス](index-class.md)グリッド オブジェクトのグローバル インデックスを表すランク 1、2、または 3 のオブジェクト。|
|[ローカル定数](#tiled_index__local)|ストア、`index`の現在のタイルで、相対パスを表すランク 1、2、または 3 のインデックスのオブジェクトを[tiled_extent](tiled-extent-class.md)オブジェクト。|
|[rank 定数](#tiled_index__rank)|`tiled_index` オブジェクトのランクを格納します。|
|[tile 定数](#tiled_index__tile)|`index` オブジェクトの現在のタイルの座標を表すランク 1、2、または 3 の `tiled_extent` オブジェクトを格納します。|
|[tile_dim0 定数](#tiled_index__tile_dim0)|最上位の次元の長さを格納します。|
|[tile_dim1 定数](#tiled_index__tile_dim1)|最上位の次の次元の長さを格納します。|
|[tile_dim2 定数](#tiled_index__tile_dim2)|最下位の次元の長さを格納します。|
|[tile_origin 定数](#tiled_index__tile_origin)|`index` オブジェクトの現在のタイルの原点のグローバル座標を表すランク 1、2、または 3 の `tiled_extent` オブジェクトを格納します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[tile_extent](#tile_extent)|取得、[エクステント](extent-class.md)オブジェクトの値を持つ、`tiled_index`テンプレート引数`tiled_index`テンプレート引数`_Dim0`、 `_Dim1`、および`_Dim2`します。|

## <a name="inheritance-hierarchy"></a>継承階層

`_Tiled_index_base`

`tiled_index`

## <a name="requirements"></a>要件

**ヘッダー:** amp.h

**名前空間:** Concurrency

## <a name="tiled_index__ctor"></a>  tiled_index コンス トラクター

`tiled_index` クラスの新しいインスタンスを初期化します。

## <a name="syntax"></a>構文

```
tiled_index(
    const index<rank>& _Global,
    const index<rank>& _Local,
    const index<rank>& _Tile,
    const index<rank>& _Tile_origin,
    const tile_barrier& _Barrier ) restrict(amp,cpu);

tiled_index(
    const tiled_index& _Other ) restrict(amp,cpu);
```

#### <a name="parameters"></a>パラメーター

*_Global*<br/>
グローバル[インデックス](index-class.md)の構築された`tiled_index`します。

*(_L)*<br/>
ローカル[インデックス](index-class.md)の構築されました。 `tiled_index`

*_Tile*<br/>
タイル[インデックス](index-class.md)の構築されました。 `tiled_index`

*_Tile_origin*<br/>
タイルの原点[インデックス](index-class.md)の構築されました。 `tiled_index`

*_Barrier*<br/>
[Tile_barrier](tile-barrier-class.md)オブジェクトの構築された`tiled_index`します。

*_Other*<br/>
構築された `tile_index` にコピーされる `tiled_index` オブジェクトです。

## <a name="overloads"></a>Overloads

|||
|-|-|
|名前|説明|
|`tiled_index(const index<rank>& _Global, const index<rank>& _Local, const index<rank>& _Tile, const index<rank>& _Tile_origin, const tile_barrier& _Barrier restrict(amp,cpu);`|グローバル座標のタイルのインデックスおよびローカル座標のタイルの相対位置から `tile_index` クラスの新しいインスタンスを初期化します。 `_Global` パラメーターおよび `_Tile_origin` パラメーターが計算されます。|
|`tiled_index(    const tiled_index& _Other) restrict(amp,cpu);`|指定した `tile_index` オブジェクトをコピーして、`tiled_index` クラスの新しいインスタンスを初期化します。|

## <a name="tiled_index__get_tile_extent"></a>  get_tile_extent

返します、[エクステント](extent-class.md)オブジェクトの値を持つ、`tiled_index`テンプレート引数`_Dim0`、 `_Dim1`、および`_Dim2`します。

## <a name="syntax"></a>構文

```
extent<rank> get_tile_extent()restrict(amp,cpu);
```

## <a name="return-value"></a>戻り値

`extent`オブジェクトの値を持つ、`tiled_index`テンプレート引数`_Dim0`、 `_Dim1`、および`_Dim2`します。

## <a name="tiled_index__barrier"></a>  バリア

ストア、 [tile_barrier](tile-barrier-class.md)スレッドの現在のタイルのバリアを表すオブジェクト。

## <a name="syntax"></a>構文

```
const tile_barrier barrier;
```

## <a name="tiled_index__global"></a>  global

ストア、[インデックス](index-class.md)オブジェクトのグローバル インデックスを表すランク 1、2、または 3 のオブジェクト。

## <a name="syntax"></a>構文

```
const index<rank> global;
```

## <a name="tiled_index__local"></a>  地元の

ストア、[インデックス](index-class.md)の現在のタイルで、相対パスを表すランク 1、2、または 3 のインデックスのオブジェクトを[tiled_extent](tiled-extent-class.md)オブジェクト。

## <a name="syntax"></a>構文

```
const index<rank> local;
```

## <a name="tiled_index__rank"></a>  ランク

`tiled_index` オブジェクトのランクを格納します。

## <a name="syntax"></a>構文

```
static const int rank = _Rank;
```

## <a name="tiled_index__tile"></a>  タイル

ストア、[インデックス](index-class.md)ランク 1、2、または 3 の現在のタイルの座標を表すオブジェクトを[tiled_extent](tiled-extent-class.md)オブジェクト。

## <a name="syntax"></a>構文

```
const index<rank> tile;
```

## <a name="tiled_index__tile_dim0"></a>  tile_dim0

最上位の次元の長さを格納します。

## <a name="syntax"></a>構文

```
static const int tile_dim0 = _Dim0;
```

## <a name="tiled_index__tile_dim1"></a>  tile_dim1

最上位の次の次元の長さを格納します。

## <a name="syntax"></a>構文

```
static const int tile_dim1 = _Dim1;
```
## <a name="tiled_index__tile_dim2"></a>  tile_dim2

最下位の次元の長さを格納します。

## <a name="syntax"></a>構文

```
static const int tile_dim2 = _Dim2;
```
## <a name="tiled_index__tile_origin"></a>  tile_origin

ストア、[インデックス](index-class.md)内で現在のタイルの原点のグローバル表すランク 1、2、または 3 の座標のオブジェクトを[tiled_extent](tiled-extent-class.md)オブジェクト。

## <a name="syntax"></a>構文

```
const index<rank> tile_origin
```
## <a name="tile_extent"></a>  tile_extent
  取得、[エクステント](extent-class.md)オブジェクトの値を持つ、`tiled_index`テンプレート引数`tiled_index`テンプレート引数`_Dim0`、 `_Dim1`、および`_Dim2`します。

## <a name="syntax"></a>構文

```
__declspec(property(get= get_tile_extent)) extent<rank> tile_extent;
```

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
