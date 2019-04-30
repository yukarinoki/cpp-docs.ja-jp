---
title: writeonly_texture_view クラス
ms.date: 11/04/2016
f1_keywords:
- writeonly_texture_view
- AMP_GRAPHICS/writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::rank Constant
ms.assetid: 8d117ad3-0a1c-41ae-b29c-7c95fdd4d04d
ms.openlocfilehash: 5244ae5df99b06c77f4eb27317e5829b21fabf24
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405418"
---
# <a name="writeonlytextureview-class"></a>writeonly_texture_view クラス

テクスチャへの書き込み専用アクセスを提供します。

## <a name="syntax"></a>構文

```
template <
    typename value_type,
    int _Rank
>
class writeonly_texture_view;

template <
    typename value_type,
    int _Rank
>
class writeonly_texture_view<value_type, _Rank> : public details::_Texture_base<value_type, _Rank>;
```

#### <a name="parameters"></a>パラメーター

*value_type*<br/>
テクスチャの要素の型。

*_Rank*<br/>
テクスチャのランク。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`scalar_type`||
|`value_type`|テクスチャの要素の型。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[writeonly_texture_view コンス トラクター](#ctor)|`writeonly_texture_view` クラスの新しいインスタンスを初期化します。|
|[~ writeonly_texture_view デストラクター](#ctor)|`writeonly_texture_view` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[set](#set)|指定されたインデックス位置にある要素の値を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[operator=](#operator_eq)|指定したコピー`writeonly_texture_view`オブジェクトをこのオブジェクト。|

### <a name="public-constants"></a>パブリック定数

|名前|説明|
|----------|-----------------|
|[rank 定数](#rank)|`writeonly_texture_view` オブジェクトのランクを取得します。|

## <a name="inheritance-hierarchy"></a>継承階層

`_Texture_base`

`writeonly_texture_view`

## <a name="requirements"></a>必要条件

**ヘッダー:** amp_graphics.h

**名前空間:** Concurrency::graphics

##  <a name="dtor"></a> ~writeonly_texture_view

`writeonly_texture_view` オブジェクトを破棄します。

```
~writeonly_texture_view() restrict(amp,cpu);
```

##  <a name="operator_eq"></a> 演算子 =

指定したコピー`writeonly_texture_view`オブジェクトをこのオブジェクト。

```
writeonly_texture_view<value_type, _Rank>& operator= (
    const writeonly_texture_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター

*_Other*<br/>
`writeonly_texture_view` コピーするオブジェクト。

### <a name="return-value"></a>戻り値

この `writeonly_texture_view` オブジェクトへの参照。

##  <a name="rank"></a> ランク

`writeonly_texture_view` オブジェクトのランクを取得します。

```
static const int rank = _Rank;
```

##  <a name="set"></a> 設定

指定されたインデックス位置にある要素の値を設定します。

```
void set(
    const index<_Rank>& _Index,
    const value_type& value) const restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_Index*<br/>
要素のインデックス。

*value*<br/>
要素の新しい値。

##  <a name="ctor"></a> writeonly_texture_view

`writeonly_texture_view` クラスの新しいインスタンスを初期化します。

```
writeonly_texture_view(
    texture<value_type,
    _Rank>& _Src) restrict(amp);

writeonly_texture_view(
    const writeonly_texture_view<value_type,
    _Rank>& _Src) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター

*_Rank*<br/>
テクスチャのランク。

*value_type*<br/>
テクスチャの要素の型。

*_Src*<br/>
テクスチャの作成に使用される、`writeonly_texture_view`します。

## <a name="see-also"></a>関連項目

[Concurrency::graphics 名前空間](concurrency-graphics-namespace.md)
