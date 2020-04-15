---
title: Concurrency::graphics::direct3d 名前空間関数
ms.date: 11/04/2016
f1_keywords:
- amp_graphics/Concurrency::graphics::direct3d::get_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_texture
ms.assetid: 11ee1d42-333e-4ae9-95ac-4cf68c06d13d
ms.openlocfilehash: 330c1aa94b1d122901fc23576686032400249d31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376384"
---
# <a name="concurrencygraphicsdirect3d-namespace-functions"></a>Concurrency::graphics::direct3d 名前空間関数

||||
|-|-|-|
|[get_sampler](#get_sampler)|[get_texture](#get_texture)|[make_sampler](#make_sampler)|
|[make_texture](#make_texture)|[ムサド4](#msad4)|

## <a name="get_sampler"></a><a name="get_sampler"></a>get_sampler

指定されたサンプラー オブジェクトを表す特定のアクセラレータ ビューについて、D3D サンプラーの状態インターフェイスを取得します。

```cpp
IUnknown* get_sampler(
    const Concurrency::accelerator_view& _Av,
    const sampler& _Sampler) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_Av*<br/>
D3D サンプラーの状態が作成される D3D アクセラレータ ビュー。

*_Sampler*<br/>
基になる D3D サンプラーの状態インターフェイスが作成されるサンプラー オブジェクト。

### <a name="return-value"></a>戻り値

特定のサンプラーを表す D3D サンプラーの状態に対応する IUnknown インターフェイス ポインター。

## <a name="get_texture"></a><a name="get_texture"></a>get_texture

指定したテクスチャ オブジェクトの基になる Direct3D[テクスチャ](texture-class.md)インターフェイスを取得します。

```cpp
template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const texture<value_type, _Rank>& _Texture) restrict(cpu);

template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const writeonly_texture_view<value_type, _Rank>& _Texture) restrict(cpu);

template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const texture_view<value_type, _Rank>& _Texture) restrict(cpu);
```

### <a name="parameters"></a>パラメーター

*Value_type*<br/>
テクスチャの要素型。

*_Rank*<br/>
テクスチャのランク。

*_Texture*<br/>
基になる Direct3D テクスチャ インターフェイスが返される accelerator_view に関連付けられているテクスチャまたはテクスチャ ビュー。

### <a name="return-value"></a>戻り値

テクスチャの基になる Direct3D テクスチャに対応する IUnknown インターフェイス ポインター。

## <a name="make_sampler"></a><a name="make_sampler"></a>make_sampler

D3D サンプラーの状態インターフェイス ポインターからサンプラーを作成します。

```cpp
sampler make_sampler(_In_ IUnknown* _D3D_sampler) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_D3D_sampler*<br/>
サンプラーを作成する基になる D3D サンプラーの状態の IUnknown インターフェイス ポインター。

### <a name="return-value"></a>戻り値

サンプラーは、指定された D3D サンプラーの状態を表します。

## <a name="make_texture"></a><a name="make_texture"></a>make_texture

指定したパラメータを使用して[テクスチャ](texture-class.md)オブジェクトを作成します。

```cpp
template<
    typename value_type,
    int _Rank
>
texture<value_type, _Rank> make_texture(
    const Concurrency::accelerator_view& _Av,
    _In_ IUnknown* _D3D_texture,
    DXGI_FORMAT _View_format = DXGI_FORMAT_UNKNOWN) restrict(cpu);
```

### <a name="parameters"></a>パラメーター

*Value_type*<br/>
テクスチャの要素の型。

*_Rank*<br/>
テクスチャのランク。

*_Av*<br/>
テクスチャが作成される D3D アクセラレータ ビュー。

*_D3D_texture*<br/>
テクスチャを作成する基になる D3D テクスチャの IUnknown インターフェイス ポインター。

*_View_format*<br/>
このテクスチャから作成されるビューに使用する DXGI 形式。 DXGI_FORMAT_UNKNOWN渡す (既定値) _D3D_textureの基になる形式とこのテンプレートのvalue_typeから形式を派生します。 用意された形式は、_D3D_texture の基になる形式との互換性が必要です。

### <a name="return-value"></a>戻り値

用意された D3D テクスチャを使用するテクスチャ。

## <a name="msad4"></a><a name="msad4"></a>ムサド4

4 バイトの参照値と 8 バイトのソース値を比較し、4 個の合計値のベクターを累積します。 各合計は、参照値とソース値の異なるバイト アラインメントの差の絶対値のマスク合計に対応します。

```cpp
inline uint4 msad4(
    uint _Reference,
    uint2 _Source,
    uint4 _Accum) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_Reference*<br/>
1 個の uint 値の 4 バイトの参照配列。

*_Source*<br/>
2 個の uint 値のベクター内の 8 バイトのソース配列。

*_Accum*<br/>
参照値とソース値の異なるバイト アラインメントの差の絶対値のマスク合計に加算される 4 個の値のベクター。

### <a name="return-value"></a>戻り値

4 つの合計のベクターを返します。 各合計は、参照値とソース値の異なるバイト アラインメントの差の絶対値のマスク合計に対応します。

## <a name="requirements"></a>必要条件

**ヘッダー:** amp_graphics.h

**名前空間:** 同時実行::グラフィックス::direct3d

## <a name="see-also"></a>関連項目

[同時実行::グラフィックス::direct3d名前空間](concurrency-graphics-direct3d-namespace.md)
