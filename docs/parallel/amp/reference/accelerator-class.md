---
description: '詳細情報: accelerator クラス'
title: accelerator クラス
ms.date: 11/04/2016
f1_keywords:
- AMPRT/accelerator
- AMPRT/Concurrency::accelerator::accelerator
- AMPRT/Concurrency::accelerator::create_view
- AMPRT/Concurrency::accelerator::get_all
- AMPRT/Concurrency::accelerator::get_auto_selection_view
- AMPRT/Concurrency::accelerator::get_dedicated_memory
- AMPRT/Concurrency::accelerator::get_default_cpu_access_type
- AMPRT/Concurrency::accelerator::get_default_view
- AMPRT/Concurrency::accelerator::get_description
- AMPRT/Concurrency::accelerator::get_device_path
- AMPRT/Concurrency::accelerator::get_has_display
- AMPRT/Concurrency::accelerator::get_is_debug
- AMPRT/Concurrency::accelerator::get_is_emulated
- AMPRT/Concurrency::accelerator::get_supports_cpu_shared_memory
- AMPRT/Concurrency::accelerator::get_supports_double_precision
- AMPRT/Concurrency::accelerator::get_supports_limited_double_precision
- AMPRT/Concurrency::accelerator::get_version
- AMPRT/Concurrency::accelerator::set_default
- AMPRT/Concurrency::accelerator::set_default_cpu_access_type
- AMPRT/Concurrency::accelerator::cpu_accelerator
- AMPRT/Concurrency::accelerator::dedicated_memory
- AMPRT/Concurrency::accelerator::default_accelerator
- AMPRT/Concurrency::accelerator::default_cpu_access_type
- AMPRT/Concurrency::accelerator::default_view
- AMPRT/Concurrency::accelerator::description
- AMPRT/Concurrency::accelerator::device_path
- AMPRT/Concurrency::accelerator::direct3d_ref
- AMPRT/Concurrency::accelerator::direct3d_warp
- AMPRT/Concurrency::accelerator::has_display
- AMPRT/Concurrency::accelerator::is_debug
- AMPRT/Concurrency::accelerator::is_emulated
- AMPRT/Concurrency::accelerator::supports_cpu_shared_memory
- AMPRT/Concurrency::accelerator::supports_double_precision
- AMPRT/Concurrency::accelerator::supports_limited_double_precision
- AMPRT/Concurrency::accelerator::version
helpviewer_keywords:
- accelerator class
ms.assetid: 37eed593-cf87-4611-9cdc-e98df6c2377a
ms.openlocfilehash: 3f5c8ba2d68049097acb89e90caf83d92be6f7e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254535"
---
# <a name="accelerator-class"></a>accelerator クラス

アクセラレータは、データ並列計算用に最適化されたハードウェアの機能です。 アクセラレータは、PCIe バス (GPU など) にアタッチされているデバイスである場合や主要 CPU の拡張命令セットである場合があります。

## <a name="syntax"></a>構文

```cpp
class accelerator;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[accelerator コンストラクター](#ctor)|`accelerator` クラスの新しいインスタンスを初期化します。|
|[~ accelerator デストラクター](#ctor)|`accelerator` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[create_view](#create_view)|このアクセラレータの `accelerator_view` オブジェクトを作成して返します。|
|[get_all](#get_all)|使用可能なすべてのアクセラレータを表す `accelerator` オブジェクトのベクターを返します。|
|[get_auto_selection_view](#get_auto_selection_view)|自動選択 `accelerator_view` を返します。|
|[get_dedicated_memory](#get_dedicated_memory)|`accelerator` の専用のメモリ (KB 単位) を返します。|
|[get_default_cpu_access_type](#get_default_cpu_access_type)|このアクセラレータで作成されたバッファーの既定の [access_type](concurrency-namespace-enums-amp.md#access_type) を返します。|
|[get_default_view](#get_default_view)|`accelerator_view` に関連付けられている既定の `accelerator` オブジェクトを返します。|
|[get_description](#get_description)|`accelerator` デバイスの短い説明を返します。|
|[get_device_path](#get_device_path)|デバイスのパスを返します。|
|[get_has_display](#get_has_display)|`accelerator` がディスプレイにアタッチされるかどうかを決定します。|
|[get_is_debug](#get_is_debug)|`accelerator` が広範なエラー レポートに有効なデバッグ レイヤーを持つかどうかを決定します。|
|[get_is_emulated](#get_is_emulated)|`accelerator` がエミュレートされるかどうかを決定します。|
|[get_supports_cpu_shared_memory](#get_supports_cpu_shared_memory)|`accelerator` が共有メモリをサポートするかどうかを決定します|
|[get_supports_double_precision](#get_supports_double_precision)|`accelerator` がディスプレイにアタッチされるかどうかを決定します。|
|[get_supports_limited_double_precision](#get_supports_limited_double_precision)|`accelerator` が倍精度サポートを制限するかどうかを決定します。|
|[get_version](#get_version)|`accelerator` のバージョンを返します。|
|[set_default](#set_default)|既定のアクセラレータのパスを返します。|
|[set_default_cpu_access_type](#set_default_cpu_access_type)|このに対して行われた配列および暗黙のメモリ割り当ての既定の CPU [access_type](concurrency-namespace-enums-amp.md#access_type)を設定し `accelerator` ます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[operator! =](#operator_neq)|このオブジェクトと別のオブジェクトを比較 `accelerator` し、同じである場合はを返します **`false`** 。それ以外の場合はを返し **`true`** ます。|
|[operator =](#operator_eq)|指定された `accelerator` オブジェクトの内容をこのオブジェクトにコピーします。|
|[operator = =](#operator_eq_eq)|このオブジェクトと別のオブジェクトを比較 `accelerator` し、同じである場合はを返します **`true`** 。それ以外の場合はを返し **`false`** ます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[cpu_accelerator](#cpu_accelerator)|CPU `accelerator` の文字列定数を取得します。|
|[dedicated_memory](#dedicated_memory)|`accelerator` の専用のメモリ (KB 単位) を取得します。|
|[default_accelerator](#default_accelerator)|既定の `accelerator` の文字列定数を取得します。|
|[default_cpu_access_type](#default_cpu_access_type)|このに対して行われた配列および暗黙のメモリ割り当ての既定の CPU [access_type](concurrency-namespace-enums-amp.md#access_type)を取得または設定し `accelerator` ます。|
|[default_view](#default_view)|`accelerator_view` に関連付けられている既定の `accelerator` オブジェクトを取得します。|
|[description](#description)|`accelerator` デバイスの短い説明を取得します。|
|[device_path](#device_path)|デバイスのパスを取得します。|
|[direct3d_ref](#direct3d_ref)|Direct3D 参照 `accelerator` の文字列定数を取得します。|
|[direct3d_warp](#direct3d_warp)|`accelerator`STREAMING SIMD 拡張 (SSE) を使用するマルチコア cpu で C++ AMP コードを実行するために使用できるオブジェクトの文字列定数を取得します。|
|[has_display](#has_display)|`accelerator` がディスプレイにアタッチされているかどうかを示すブール値を取得します。|
|[is_debug](#is_debug)|`accelerator` に、広範なエラー レポートに有効なデバッグ レイヤーがあるかどうかを示します。|
|[is_emulated](#is_emulated)|`accelerator` がエミュレートされるかどうかを示します。|
|[supports_cpu_shared_memory](#supports_cpu_shared_memory)|`accelerator` が共有メモリをサポートするかどうかを示します。|
|[supports_double_precision](#supports_double_precision)|アクセラレータが倍精度数値演算をサポートするかどうかを示します。|
|[supports_limited_double_precision](#supports_limited_double_precision)|アクセラレータの倍精度数値演算のサポートが制限されているかどうかを示します。|
|[version](#version)|`accelerator` のバージョンを取得します。|

## <a name="inheritance-hierarchy"></a>継承階層

`accelerator`

## <a name="remarks"></a>解説

アクセラレータは、データ並列計算用に最適化されたハードウェアの機能です。 多くの場合、アクセラレータは独立した GPU ですが、DirectX REF デバイス、WARP (SSE 命令で加速される CPU 側のデバイス)、または CPU 自体などの仮想ホスト側のエンティティでもあることがあります。

使用できるデバイスをエミュレートすることによって、または既定のデバイス、参照デバイス、または WARP デバイスを取得することによって、`accelerator` オブジェクトを構築することができます。

## <a name="requirements"></a>要件

**ヘッダー:** amprt. h

**名前空間:** Concurrency

## <a name="a-accelerator"></a><a name="dtor"></a></a> ~ accelerator

`accelerator` オブジェクトを破棄します。

```cpp
~accelerator();
```

### <a name="return-value"></a>戻り値

## <a name="accelerator"></a><a name="ctor"></a> アクセラレーター

[Accelerator クラス](accelerator-class.md)の新しいインスタンスを初期化します。

```cpp
accelerator();

explicit accelerator(const std::wstring& _Device_path);

accelerator(const accelerator& _Other);
```

### <a name="parameters"></a>パラメーター

*_Device_path*<br/>
物理デバイスのパスです。

*_Other*<br/>
コピーするアクセラレータです。

## <a name="cpu_accelerator"></a><a name="cpu_accelerator"></a> cpu_accelerator

CPU アクセラレータの文字列定数を取得します。

```cpp
static const wchar_t cpu_accelerator[];
```

## <a name="create_view"></a><a name="create_view"></a> create_view

`accelerator_view`指定されたキューモードを使用して、このアクセラレータにオブジェクトを作成して返します。 キューモードが指定されていない場合、新しいは `accelerator_view` [queuing_mode:: 即時](concurrency-namespace-enums-amp.md#queuing_mode) キューモードを使用します。

```cpp
accelerator_view create_view(queuing_mode qmode = queuing_mode_automatic);
```

### <a name="parameters"></a>パラメーター

*qmode*<br/>
キューモード。

### <a name="return-value"></a>戻り値

`accelerator_view`指定されたキューモードを使用する、このアクセラレータの新しいオブジェクト。

## <a name="dedicated_memory"></a><a name="dedicated_memory"></a> dedicated_memory

`accelerator` の専用のメモリ (KB 単位) を取得します。

```cpp
__declspec(property(get= get_dedicated_memory)) size_t dedicated_memory;
```

## <a name="default_accelerator"></a><a name="default_accelerator"></a> default_accelerator

既定の `accelerator` の文字列定数を取得します。

```cpp
static const wchar_t default_accelerator[];
```

## <a name="default_cpu_access_type"></a><a name="default_cpu_access_type"></a> default_cpu_access_type

配列の既定の cpu [access_type](concurrency-namespace-enums-amp.md#access_type)と、このに対して行われた暗黙のメモリ割り当て `accelerator` 。

```cpp
__declspec(property(get= get_default_cpu_access_type)) access_type default_cpu_access_type;
```

## <a name="default_view"></a><a name="default_view"></a> default_view

に関連付けられている既定のアクセラレータビューを取得し `accelerator` ます。

```cpp
__declspec(property(get= get_default_view)) accelerator_view default_view;
```

## <a name="description"></a><a name="description"></a> 記述

`accelerator` デバイスの短い説明を取得します。

```cpp
__declspec(property(get= get_description)) std::wstring description;
```

## <a name="device_path"></a><a name="device_path"></a> device_path

アクセラレータのパスを取得します。 パスはシステム上で一意です。

```cpp
__declspec(property(get= get_device_path)) std::wstring device_path;
```

## <a name="direct3d_ref"></a><a name="direct3d_ref"></a> direct3d_ref

Direct3D 参照アクセラレータの文字列定数を取得します。

```cpp
static const wchar_t direct3d_ref[];
```

## <a name="direct3d_warp"></a><a name="direct3d_warp"></a> direct3d_warp

`accelerator`STREAMING SIMD 拡張 (SSE) を使用してマルチコア cpu で C++ AMP コードを実行するために使用できるオブジェクトの文字列定数を取得します。

```cpp
static const wchar_t direct3d_warp[];
```

## <a name="get_all"></a><a name="get_all"></a> get_all

使用可能なすべてのアクセラレータを表す `accelerator` オブジェクトのベクターを返します。

```cpp
static inline std::vector<accelerator> get_all();
```

### <a name="return-value"></a>戻り値

使用可能なアクセラレータのベクター

## <a name="get_auto_selection_view"></a><a name="get_auto_selection_view"></a> get_auto_selection_view

ランタイムによって自動的に選択される parallel_for_each カーネルを実行するためにターゲットの accelerator_view で parallel_for_each ターゲット結果として指定される場合、自動選択の accelerator_view を返します。 その他のすべての目的については、このメソッドで返される accelerator_view は、既定のアクセラレータの既定の accelerator_view と同じです。

```cpp
static accelerator_view __cdecl get_auto_selection_view();
```

### <a name="return-value"></a>戻り値

自動選択の accelerator_view。

## <a name="get_dedicated_memory"></a><a name="get_dedicated_memory"></a> get_dedicated_memory

`accelerator` の専用のメモリ (KB 単位) を返します。

```cpp
size_t get_dedicated_memory() const;
```

### <a name="return-value"></a>戻り値

の専用メモリ ( `accelerator` kb 単位)。

## <a name="get_default_cpu_access_type"></a><a name="get_default_cpu_access_type"></a> get_default_cpu_access_type

このアクセラレータで作成されるバッファーの既定の CPU access_type を取得します

```cpp
access_type get_default_cpu_access_type() const;
```

### <a name="return-value"></a>戻り値

このアクセラレータで作成されるバッファーの既定の CPU access_type。

## <a name="get_default_view"></a><a name="get_default_view"></a> get_default_view

`accelerator_view` に関連付けられている既定の `accelerator` オブジェクトを返します。

```cpp
accelerator_view get_default_view() const;
```

### <a name="return-value"></a>戻り値

に関連付けられている既定の `accelerator_view` オブジェクト `accelerator` 。

## <a name="get_description"></a><a name="get_description"></a> get_description

`accelerator` デバイスの短い説明を返します。

```cpp
std::wstring get_description() const;
```

### <a name="return-value"></a>戻り値

デバイスの簡単な説明 `accelerator` 。

## <a name="get_device_path"></a><a name="get_device_path"></a> get_device_path

アクセラレータのパスを返します。 パスはシステム上で一意です。

```cpp
std::wstring get_device_path() const;
```

### <a name="return-value"></a>戻り値

システム全体で一意のデバイスインスタンスパス。

## <a name="get_has_display"></a><a name="get_has_display"></a> get_has_display

がディスプレイに出力できるかどうかを示すブール値を返し `accelerator` ます。

```cpp
bool get_has_display() const;
```

### <a name="return-value"></a>戻り値

**`true`** が `accelerator` ディスプレイに出力できる場合は。それ以外の場合は **`false`** 。

## <a name="get_is_debug"></a><a name="get_is_debug"></a> get_is_debug

`accelerator` が広範なエラー レポートに有効なデバッグ レイヤーを持つかどうかを決定します。

```cpp
bool get_is_debug() const;
```

### <a name="return-value"></a>戻り値

**`true`** で `accelerator` 広範なエラー報告が有効になっているデバッグ層がの場合。 それ以外の場合は **`false`** 。

## <a name="get_is_emulated"></a><a name="get_is_emulated"></a> get_is_emulated

`accelerator` がエミュレートされるかどうかを決定します。

```cpp
bool get_is_emulated() const;
```

### <a name="return-value"></a>戻り値

**`true`** がエミュレートされている場合は `accelerator` 。 それ以外の場合は **`false`** 。

## <a name="get_supports_cpu_shared_memory"></a><a name="get_supports_cpu_shared_memory"></a> get_supports_cpu_shared_memory

アクセラレータがアクセラレータと CPU の両方からアクセスできるメモリをサポートするかどうかを示すブール値を返します。

```cpp
bool get_supports_cpu_shared_memory() const;
```

### <a name="return-value"></a>戻り値

**`true`** アクセラレータが CPU 共有メモリをサポートする場合は、それ以外の場合は **`false`** 。

## <a name="get_supports_double_precision"></a><a name="get_supports_double_precision"></a> get_supports_double_precision

アクセラレータが倍精度の数値演算をサポートしているかどうかを示すブール値を返します。これには、との間の、ヒューズ乗算 (FMA)、除算、逆数、およびキャストが含まれます。 **`int`****`double`**

```cpp
bool get_supports_double_precision() const;
```

### <a name="return-value"></a>戻り値

**`true`** アクセラレータで倍精度数値演算がサポートされている場合は、それ以外の場合は **`false`** 。

## <a name="get_supports_limited_double_precision"></a><a name="get_supports_limited_double_precision"></a> get_supports_limited_double_precision

アクセラレータの倍精度数値演算のサポートが制限されているかどうかを示すブール値を返します。 アクセラレータのサポートが制限されている場合、との間の重複する加算 (FMA)、除算、逆数、 **`int`** およびキャスト **`double`** はサポートされていません。

```cpp
bool get_supports_limited_double_precision() const;
```

### <a name="return-value"></a>戻り値

**`true`** アクセラレータで倍精度数値演算のサポートが制限されている場合は。それ以外の場合は **`false`** 。

## <a name="get_version"></a><a name="get_version"></a> get_version

`accelerator` のバージョンを返します。

```cpp
unsigned int get_version() const;
```

### <a name="return-value"></a>戻り値

`accelerator` のバージョン。

## <a name="has_display"></a><a name="has_display"></a> has_display

がディスプレイに出力できるかどうかを示すブール値を取得し `accelerator` ます。

```cpp
__declspec(property(get= get_has_display)) bool has_display;
```

## <a name="is_debug"></a><a name="is_debug"></a> is_debug

に `accelerator` 広範なエラー報告が有効になっているデバッグ層があるかどうかを示すブール値を取得します。

```cpp
__declspec(property(get= get_is_debug)) bool is_debug;
```

## <a name="is_emulated"></a><a name="is_emulated"></a> is_emulated

がエミュレートされるかどうかを示すブール値を取得し `accelerator` ます。

```cpp
__declspec(property(get= get_is_emulated)) bool is_emulated;
```

## <a name="operator"></a><a name="operator_neq"></a> operator! =

このオブジェクトと別のオブジェクトを比較 `accelerator` し、同じである場合はを返します **`false`** 。それ以外の場合はを返し **`true`** ます。

```cpp
bool operator!= (const accelerator& _Other) const;
```

### <a name="parameters"></a>パラメーター

*_Other*<br/>
`accelerator`このと比較するオブジェクト。

### <a name="return-value"></a>戻り値

**`false`** 2つの `accelerator` オブジェクトが同一である場合は。それ以外の場合は **`true`** 。

## <a name="operator"></a><a name="operator_eq"></a> operator =

指定された `accelerator` オブジェクトの内容をこのオブジェクトにコピーします。

```cpp
accelerator& operator= (const accelerator& _Other);
```

### <a name="parameters"></a>パラメーター

*_Other*<br/>
コピー元の `accelerator` オブジェクト。

### <a name="return-value"></a>戻り値

この `accelerator` オブジェクトへの参照。

## <a name="operator"></a><a name="operator_eq_eq"></a> operator = =

このオブジェクトと別のオブジェクトを比較 `accelerator` し、同じである場合はを返します **`true`** 。それ以外の場合はを返し **`false`** ます。

```cpp
bool operator== (const accelerator& _Other) const;
```

### <a name="parameters"></a>パラメーター

*_Other*<br/>
`accelerator`このと比較するオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 他の `accelerator` オブジェクトがこのオブジェクトと同じ場合は `accelerator` 。それ以外の場合は **`false`** 。

## <a name="set_default"></a><a name="set_default"></a> set_default

暗黙的に既定のアクセラレータを使用するすべての操作に使用する既定のアクセラレータを設定します。 このメソッドは、ランタイムによって選択された既定のアクセラレータが暗黙的に既定のアクセラレータを使用する操作で既に使用されていない場合にのみ正常に終了します

```cpp
static inline bool set_default(std::wstring _Path);
```

### <a name="parameters"></a>パラメーター

*_Path*<br/>
アクセラレータへのパス。

### <a name="return-value"></a>戻り値

**`true`** 既定のアクセラレータの設定時に呼び出しが成功した場合は。 それ以外の場合は **`false`** 。

## <a name="set_default_cpu_access_type"></a><a name="set_default_cpu_access_type"></a> set_default_cpu_access_type

このアクセラレータで作成された配列の既定の cpu access_type、またはこのアクセラレータでアクセスされる array_views の一部としての暗黙的なメモリ割り当てに設定します。 このメソッドは、アクセラレータの default_cpu_access_type がこのメソッドの以前の呼び出しによってオーバーライドされていない場合にのみ成功します。また、このアクセラレータに対して選択された default_cpu_access_type ランタイムは、配列の割り当てにまだ使用されていないか、このアクセラレータでアクセスされる array_view をバッキングするメモリ割り当てに対してまだ使用されていませ

```cpp
bool set_default_cpu_access_type(access_type _Default_cpu_access_type);
```

### <a name="parameters"></a>パラメーター

*_Default_cpu_access_type*<br/>
このアクセラレータの array/array_view メモリ割り当てに使用される既定の CPU access_type。

### <a name="return-value"></a>戻り値

アクセラレータの既定の CPU access_type が正常に設定されたかどうかを示すブール値。

## <a name="supports_cpu_shared_memory"></a><a name="supports_cpu_shared_memory"></a> supports_cpu_shared_memory

`accelerator` が共有メモリをサポートしているかどうか示すブール値を取得します。

```cpp
__declspec(property(get= get_supports_cpu_shared_memory)) bool supports_cpu_shared_memory;
```

## <a name="supports_double_precision"></a><a name="supports_double_precision"></a> supports_double_precision

アクセラレータで倍精度数値演算がサポートされているかどうかを示すブール値を取得します。

```cpp
__declspec(property(get= get_supports_double_precision)) bool supports_double_precision;
```

## <a name="supports_limited_double_precision"></a><a name="supports_limited_double_precision"></a> supports_limited_double_precision

アクセラレータの倍精度数値演算のサポートが制限されているかどうかを示すブール値を取得します。 アクセラレータのサポートが制限されている場合、との間の重複する加算 (FMA)、除算、逆数、 **`int`** およびキャスト **`double`** はサポートされていません。

```cpp
__declspec(property(get= get_supports_limited_double_precision)) bool supports_limited_double_precision;
```

## <a name="version"></a><a name="version"></a> のバージョン

`accelerator` のバージョンを取得します。

```cpp
__declspec(property(get= get_version)) unsigned int version;
```

## <a name="see-also"></a>関連項目

[Concurrency 名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
