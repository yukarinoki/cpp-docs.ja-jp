---
title: Concurrency::direct3d 名前空間関数 (AMP)
ms.date: 08/31/2018
f1_keywords:
- amp/Concurrency::direct3d::abs
- amp/Concurrency::direct3d::countbits
- amp/Concurrency::direct3d::create_accelerator_view
- amp/Concurrency::direct3d::d3d_access_lock
- amp/Concurrency::direct3d::d3d_access_unlock
- amp/Concurrency::direct3d::firstbithigh
- amp/Concurrency::direct3d::get_buffer
- amp/Concurrency::direct3d::get_device
- amp/Concurrency::direct3d::imax
- amp/Concurrency::direct3d::is_timeout_disabled
- amp/Concurrency::direct3d::mad
- amp/Concurrency::direct3d::noise
- amp/Concurrency::direct3d::radians
- amp/Concurrency::direct3d::reversebits
- amp/Concurrency::direct3d::saturate
- amp/Concurrency::direct3d::smoothstep
- amp/Concurrency::direct3d::step
- amp/Concurrency::direct3d::umin
ms.assetid: 28943b62-52c9-42dc-baf1-ca7b095c1a19
ms.openlocfilehash: e21b1f2869ab81973b341abc5371714fbf8580e2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375929"
---
# <a name="concurrencydirect3d-namespace-functions-amp"></a>Concurrency::direct3d 名前空間関数 (AMP)

||||
|-|-|-|
|[Abs](#abs)|[クランプ](#clamp)|[カウントビット](#countbits)|
|[create_accelerator_view](#create_accelerator_view)|[d3d_access_lock](#d3d_access_lock)||
|[d3d_access_try_lock](#d3d_access_try_lock)|[d3d_access_unlock](#d3d_access_unlock)|[ファーストビトハイ](#firstbithigh)|
|[ファーストビットロー](#firstbitlow)|[get_buffer](#get_buffer)|[get_device](#get_device)|
|[Imax](#imax)|[イミン](#imin)|[is_timeout_disabled](#is_timeout_disabled)|
|[怒って](#mad)|[make_array](#make_array)|[ノイズ](#noise)|
|[ラジアン](#radians)|[rcp](#rcp)|[リバースビット](#reversebits)|
|[飽和](#saturate)|[署名](#sign)|[スムーズステップ](#smoothstep)|
|[ステップ](#step)|[uマックス](#umax)|[ウミン](#umin)|

## <a name="requirements"></a>必要条件

**ヘッダー:** amp.h**名前空間:** 同時実行

## <a name="abs"></a><a name="abs"></a>Abs

引数の絶対値を返します。

```cpp
inline int abs(int _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
整数値

### <a name="return-value"></a>戻り値

引数の絶対値を返します。

## <a name="clamp"></a><a name="clamp"></a>クランプ

2 番目および 3 番目に指定された引数によって定義される範囲に固定される 1 番目に指定された引数の値を計算します。

```cpp
inline float clamp(
    float _X,
    float _Min,
    float _Max) restrict(amp);

inline int clamp(
    int _X,
    int _Min,
    int _Max) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
固定される値。

*_Min*<br/>
固定される範囲の下限。

*_Max*<br/>
固定される範囲の上限。

### <a name="return-value"></a>戻り値

`_X` の固定された値。

## <a name="countbits"></a><a name="countbits"></a>カウントビット

_X 内で設定されているビットの数をカウントします。

```cpp
inline unsigned int countbits(unsigned int _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
符号なし整数値

### <a name="return-value"></a>戻り値

_Xのセットビット数を返します。

## <a name="create_accelerator_view"></a><a name="create_accelerator_view"></a>create_accelerator_view

Direct3D デバイス インターフェイスへのポインターから[accelerator_view](accelerator-view-class.md)オブジェクトを作成します。

## <a name="syntax"></a>構文

```cpp
accelerator_view create_accelerator_view(
    IUnknown * _D3D_device
    queuing_mode _Qmode = queuing_mode_automatic);

accelerator_view create_accelerator_view(
    accelerator& _Accelerator,
    bool _Disable_timeout
    queuing_mode _Qmode = queuing_mode_automatic);
```

### <a name="parameters"></a>パラメーター

*_Accelerator*<br/>
新しい accelerator_view が作成されるアクセラレータ。

*_D3D_device*<br/>
Direct3D デバイス インターフェイスへのポインター。

*_Disable_timeout*<br/>
新しく作成された accelerator_view に対してタイムアウトを無効にする必要があるかどうかを指定するブール値パラメーター。 これは、Direct3D デバイス作成のための D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT フラグに対応し、オペレーティング システムが Windows のタイムアウトの検出と回復機構ごとにデバイスをリセットせずに、実行するために 2 秒より長くかかる負荷を許可するかどうかを示すために使用されます。 このフラグの使用は、accelerator_view で時間のかかるタスクを実行する必要がある場合にお勧めします。

*_Qmode*<br/>
新しく作成されたaccelerator_viewに使用する[queuing_mode。](concurrency-namespace-enums-amp.md#queuing_mode) このパラメーターには `queuing_mode_automatic` の既定値があります。

## <a name="return-value"></a>戻り値

渡された Direct3D デバイス インターフェイスから作成された `accelerator_view` オブジェクト。

## <a name="remarks"></a>解説

この関数は、Direct3D デバイス インターフェイスへの既存のポインターから新しい `accelerator_view` オブジェクトを作成します。 関数呼び出しが成功した場合、パラメーターの参照カウントはインターフェイスに対する `AddRef` 呼び出しを使用してインクリメントされます。 DirectX コードで不要になった場合は、オブジェクトを安全に解放できます。 メソッドの呼び出しが失敗すると[、runtime_exception](runtime-exception-class.md)がスローされます。

この関数を使用して作成する `accelerator_view` オブジェクトはスレッド セーフです。 `accelerator_view` オブジェクトの同時使用を同期する必要があります。 `accelerator_view` オブジェクトと生の ID3D11Device インターフェイスを非同期で同時に使用すると、未定義の動作が発生します。

C++ AMP ランタイムは、`D3D11_CREATE_DEVICE_DEBUG` フラグを使用すると D3D デバッグ レイヤーを使用してデバッグ モードで詳細なエラー情報を提供します。

## <a name="d3d_access_lock"></a><a name="d3d_access_lock"></a>d3d_access_lock

accelerator_view と共有されるリソースに対して安全に D3D 演算を実行する目的で、accelerator_view のロックを取得します。 accelerator_view および内部でこの accelerator_view に関連付けられているすべての C++ AMP リソースは、演算を実行するときにこのロックを取得し、別のスレッドが D3D アクセス ロックを保持している間はブロックします。 このロックは非再帰的です。既にロックを保持しているスレッドからこの関数を呼び出したときの動作は定義されていません。 D3D のアクセスのロックを保持しているスレッドから、accelerator_view または accelerator_view に関連付けられているデータ コンテナーに対して演算を実行したときの動作は定義されていません。 スコープ ベースの D3D アクセス ロックの RAII スタイル クラスである、scoped_d3d_access_lock も参照してください。

```cpp
void __cdecl d3d_access_lock(accelerator_view& _Av);
```

### <a name="parameters"></a>パラメーター

*_Av*<br/>
ロックする accelerator_view。

## <a name="d3d_access_try_lock"></a><a name="d3d_access_try_lock"></a>d3d_access_try_lock

ブロックせずに、accelerator_view に対する D3D アクセスのロックを取得します。

```cpp
bool __cdecl d3d_access_try_lock(accelerator_view& _Av);
```

### <a name="parameters"></a>パラメーター

*_Av*<br/>
ロックする accelerator_view。

### <a name="return-value"></a>戻り値

ロックが取得された場合は true。現在、別のスレッドによって保持されている場合は false。

## <a name="d3d_access_unlock"></a><a name="d3d_access_unlock"></a>d3d_access_unlock

指定された accelerator_view に対する D3D アクセスのロックを解除します。 呼び出し元スレッドが accelerator_view のロックを保持しない場合、結果は未定義になります。

```cpp
void __cdecl d3d_access_unlock(accelerator_view& _Av);
```

### <a name="parameters"></a>パラメーター

*_Av*<br/>
ロックが解放される accelerator_view。

## <a name="firstbithigh"></a><a name="firstbithigh"></a>ファーストビトハイ

最上位ビットから最下位ビットに移動する、最初に設定されたビットの位置を取得します。

```cpp
inline int firstbithigh(int _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
整数値

### <a name="return-value"></a>戻り値

最初に設定されたビットの位置

## <a name="firstbitlow"></a><a name="firstbitlow"></a>ファーストビットロー

最下位ビットから上位ビットに向かって操作し、_X 内で最初に設定されたビットの位置を取得します。

```cpp
inline int firstbitlow(int _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
整数値

### <a name="return-value"></a>戻り値

最初に設定されたビットの位置を返します

## <a name="get_buffer"></a><a name="get_buffer"></a>get_buffer

指定した配列を基にする Direct3D バッファー インターフェイスを取得します。

```cpp
template<
    typename value_type,
    int _Rank
>
IUnknown *get_buffer(
    const array<value_type, _Rank>& _Array)  ;
```

### <a name="parameters"></a>パラメーター

*Value_type*<br/>
配列内の要素の型。

*_Rank*<br/>
配列のランク。

*_Array*<br/>
基になる Direct3D バッファー インターフェイスが返される Direct3D accelerator_view の配列。

### <a name="return-value"></a>戻り値

配列の基になる Direct3D バッファーに対応する IUnknown インターフェイス ポインター。

## <a name="a-nameget_device-get_device"></a><a name="get_device">get_device

accelerator_viewの基になる D3D デバイス インターフェイスを取得します。

```cpp
IUnknown* get_device(const accelerator_view Av);
```

### <a name="parameters"></a>パラメーター

*Av*<br/>
基になる D3D デバイス インターフェイスが返される D3D accelerator_view。

### <a name="return-value"></a>戻り値

accelerator_view`IUnknown`の基になる D3D デバイスのインターフェイス ポインター。

## <a name="imax"></a><a name="imax"></a>Imax

引数の最大数値を判断します。

```cpp
inline int imax(
    int _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
整数値

*_y*<br/>
整数値

### <a name="return-value"></a>戻り値

引数の最大数値を返します。

## <a name="imin"></a><a name="imin"></a>イミン

引数の最小数値を判断します。

```cpp
inline int imin(
    int _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
整数値

*_y*<br/>
整数値

### <a name="return-value"></a>戻り値

引数の最小数値を返します。

## <a name="is_timeout_disabled"></a><a name="is_timeout_disabled"></a>is_timeout_disabled

指定された accelerator_view についてタイムアウトが無効であるかどうかを示すブール型のフラグを返します。 これは、Direct3D デバイス作成のための D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT フラグに対応します。

```cpp
bool __cdecl is_timeout_disabled(const accelerator_view& _Accelerator_view);
```

### <a name="parameters"></a>パラメーター

*_Accelerator_view*<br/>
タイムアウト無効の設定を照会する対象の accelerator_view。

### <a name="return-value"></a>戻り値

指定された accelerator_view についてタイムアウトが無効であるかどうかを示すブール型のフラグ。

## <a name="mad"></a><a name="mad"></a>怒って

1 番目と 2 番目の指定された引数の積を計算し、3 番目の指定された引数を加算します。

```cpp
inline float mad(
    float _X,
    float _Y,
    float _Z) restrict(amp);

inline double mad(
    double _X,
    double _Y,
    double _Z) restrict(amp);

inline int mad(
    int _X,
    int _Y,
    int _Z) restrict(amp);

inline unsigned int mad(
    unsigned int _X,
    unsigned int _Y,
    unsigned int _Z) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
1 番目の指定された引数。

*_y*<br/>
2 番目の指定された引数。

*_Z*<br/>
3 番目の指定された引数。

### <a name="return-value"></a>戻り値

`_X`\*`_Y`の + 結果`_Z`です。

## <a name="make_array"></a><a name="make_array"></a>make_array

Direct3D バッファーのインターフェイス ポインターから配列を作成します。

```cpp
template<
    typename value_type,
    int _Rank
>
array<value_type, _Rank> make_array(
    const extent<_Rank>& _Extent,
    const Concurrency::accelerator_view& _Rv,
    IUnknown* _D3D_buffer)  ;
```

### <a name="parameters"></a>パラメーター

*Value_type*<br/>
作成される配列の要素型。

*_Rank*<br/>
作成される配列のランク。

*_Extent*<br/>
配列の集合の図形を記述する範囲。

*_Rv*<br/>
配列が作成される D3D アクセラレータ ビュー。

*_D3D_buffer*<br/>
配列を作成する基になる D3D バッファーの IUnknown インターフェイス ポインター。

### <a name="return-value"></a>戻り値

用意された Direct3D バッファーを使用して作成された配列。

## <a name="noise"></a><a name="noise"></a>ノイズ

Perlinノイズアルゴリズムを使用してランダム値を生成します。

```cpp
inline float noise(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
パーリンノイズを生成する浮動小数点値

### <a name="return-value"></a>戻り値

1 ~ 1 の範囲内の Perlin ノイズ値を返します。

## <a name="radians"></a><a name="radians"></a>ラジアン

_X を角度からラジアンに変換します。

```cpp
inline float radians(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

度からラジアンに変換_Xを返します。

## <a name="rcp"></a><a name="rcp"></a>Rcp

高速近似計算を使用して指定された引数の逆数を計算します。

```cpp
inline float rcp(float _X) restrict(amp);

inline double rcp(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
逆数を計算する値。

### <a name="return-value"></a>戻り値

指定された引数の逆数。

## <a name="reversebits"></a><a name="reversebits"></a>リバースビット

_X 内のビットの順序を反転させます。

```cpp
inline unsigned int reversebits(unsigned int _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
符号なし整数値

### <a name="return-value"></a>戻り値

ビットの順序が逆の値を返_X

## <a name="saturate"></a><a name="saturate"></a>飽和

0 ～ 1 の範囲内で _X をクランプします。

```cpp
inline float saturate(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

0 から 1 の範囲内でクランプされた_Xを返します。

## <a name="sign"></a><a name="sign"></a>署名

指定された引数の符号を確認します。

```cpp
inline int sign(int _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
整数値

### <a name="return-value"></a>戻り値

引数の符号。

## <a name="smoothstep"></a><a name="smoothstep"></a>スムーズステップ

_X が [_Min, _Max] の範囲内にある場合、0 ～ 1 の滑らかなエルミート補間を返します。

```cpp
inline float smoothstep(
    float _Min,
    float _Max,
    float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_Min*<br/>
浮動小数点値

*_Max*<br/>
浮動小数点値

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xが _Min 未満の場合は 0 を返します。_Xが_Maxより大きい場合は 1。それ以外の場合、_Xが [_Min、_Max] の範囲内にある場合は、0 から 1 の間の値を返します。

## <a name="step"></a><a name="step"></a>ステップ

2 つの値を比較し、どちらの値が大きいかに応じて 0 または 1 を返します。

```cpp
inline float step(
    float _Y,
    float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_y*<br/>
浮動小数点値

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xが_Y以上の場合は 1 を返します。それ以外の場合は 0

## <a name="umax"></a><a name="umax"></a>uマックス

引数の最大数値を判断します。

```cpp
inline unsigned int umax(
    unsigned int _X,
    unsigned int _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
整数値

*_y*<br/>
整数値

### <a name="return-value"></a>戻り値

引数の最大数値を返します。

## <a name="umin"></a><a name="umin"></a>ウミン

引数の最小数値を判断します。

```cpp
inline unsigned int umin(
    unsigned int _X,
    unsigned int _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
整数値

*_y*<br/>
整数値

### <a name="return-value"></a>戻り値

引数の最小数値を返します。

## <a name="see-also"></a>関連項目

[Concurrency::direct3d 名前空間](concurrency-direct3d-namespace.md)
