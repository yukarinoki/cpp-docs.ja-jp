---
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
ms.openlocfilehash: 31008b398d17ac0c226f9359745067c4fefc08a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180436"
---
# <a name="accelerator-class"></a>accelerator クラス

アクセラレータは、データ並列計算用に最適化されたハードウェアの機能です。 アクセラレータは、PCIe バス (GPU など) にアタッチされているデバイスである場合や主要 CPU の拡張命令セットである場合があります。

## <a name="syntax"></a>構文

```
class accelerator;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[アクセラレータ コンス トラクター](#ctor)|`accelerator` クラスの新しいインスタンスを初期化します。|
|[~ accelerator デストラクター](#ctor)|`accelerator` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[create_view](#create_view)|このアクセラレータの `accelerator_view` オブジェクトを作成して返します。|
|[get_all](#get_all)|使用可能なすべてのアクセラレータを表す `accelerator` オブジェクトのベクターを返します。|
|[get_auto_selection_view](#get_auto_selection_view)|自動選択 `accelerator_view` を返します。|
|[get_dedicated_memory](#get_dedicated_memory)|`accelerator` の専用のメモリ (KB 単位) を返します。|
|[get_default_cpu_access_type](#get_default_cpu_access_type)|既定値を返します[access_type](concurrency-namespace-enums-amp.md#access_type)このアクセラレータで作成されるバッファーの。|
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
|[set_default_cpu_access_type](#set_default_cpu_access_type)|既定の CPU 設定[access_type](concurrency-namespace-enums-amp.md#access_type)配列および暗黙的なメモリ割り当てがこれに加えられた`accelerator`します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[operator!=](#operator_neq)|これを比較します`accelerator`と他のオブジェクトを返します**false**は同じである場合を返しますそれ以外の場合、 **true**します。|
|[operator=](#operator_eq)|指定された `accelerator` オブジェクトの内容をこのオブジェクトにコピーします。|
|[operator==](#operator_eq_eq)|これを比較します`accelerator`と他のオブジェクトを返します**true**は同じである場合を返しますそれ以外の場合、 **false**します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[cpu_accelerator](#cpu_accelerator)|CPU `accelerator` の文字列定数を取得します。|
|[dedicated_memory](#dedicated_memory)|`accelerator` の専用のメモリ (KB 単位) を取得します。|
|[default_accelerator](#default_accelerator)|既定の `accelerator` の文字列定数を取得します。|
|[default_cpu_access_type](#default_cpu_access_type)|取得または設定の既定の CPU [access_type](concurrency-namespace-enums-amp.md#access_type)配列および暗黙的なメモリ割り当てがこれに加えられた`accelerator`します。|
|[default_view](#default_view)|`accelerator_view` に関連付けられている既定の `accelerator` オブジェクトを取得します。|
|[description](#description)|`accelerator` デバイスの短い説明を取得します。|
|[device_path](#device_path)|デバイスのパスを取得します。|
|[direct3d_ref](#direct3d_ref)|Direct3D 参照 `accelerator` の文字列定数を取得します。|
|[direct3d_warp](#direct3d_warp)|文字列の定数を取得、`accelerator`ストリーミング SIMD 拡張命令 (SSE) を使用するマルチコア Cpu で C++ AMP コードの実行に使用できるオブジェクトします。|
|[has_display](#has_display)|`accelerator` がディスプレイにアタッチされているかどうかを示すブール値を取得します。|
|[is_debug](#is_debug)|`accelerator` に、広範なエラー レポートに有効なデバッグ レイヤーがあるかどうかを示します。|
|[is_emulated](#is_emulated)|`accelerator` がエミュレートされるかどうかを示します。|
|[supports_cpu_shared_memory](#supports_cpu_shared_memory)|`accelerator` が共有メモリをサポートするかどうかを示します。|
|[supports_double_precision](#supports_double_precision)|アクセラレータが倍精度数値演算をサポートするかどうかを示します。|
|[supports_limited_double_precision](#supports_limited_double_precision)|アクセラレータの倍精度数値演算のサポートが制限されているかどうかを示します。|
|[version](#version)|`accelerator` のバージョンを取得します。|

## <a name="inheritance-hierarchy"></a>継承階層

`accelerator`

## <a name="remarks"></a>Remarks

アクセラレータは、データ並列計算用に最適化されたハードウェアの機能です。 多くの場合、アクセラレータは独立した GPU ですが、DirectX REF デバイス、WARP (SSE 命令で加速される CPU 側のデバイス)、または CPU 自体などの仮想ホスト側のエンティティでもあることがあります。

使用できるデバイスをエミュレートすることによって、または既定のデバイス、参照デバイス、または WARP デバイスを取得することによって、`accelerator` オブジェクトを構築することができます。

## <a name="requirements"></a>必要条件

**ヘッダー:** amprt.h

**名前空間:** コンカレンシー

##  <a name="dtor"></a> </a> ~ accelerator

`accelerator` オブジェクトを破棄します。

```
~accelerator();
```

### <a name="return-value"></a>戻り値

##  <a name="ctor"></a> アクセラレータ

新しいインスタンスを初期化、[アクセラレータ クラス](accelerator-class.md)します。

```
accelerator();

explicit accelerator(const std::wstring& _Device_path);

accelerator(const accelerator& _Other);
```

### <a name="parameters"></a>パラメーター

*_Device_path*<br/>
物理デバイスのパスです。

*_Other*<br/>
コピーするアクセラレータです。

##  <a name="cpu_accelerator"></a> cpu_accelerator

CPU アクセラレータの文字列定数を取得します。

```
static const wchar_t cpu_accelerator[];
```

##  <a name="create_view"></a> create_view

作成して返します、`accelerator_view`指定のキュー モードを使用して、このアクセラレータでのオブジェクト。 キュー モードが指定されていない場合、新しい`accelerator_view`を使用して、 [queuing_mode::immediate](concurrency-namespace-enums-amp.md#queuing_mode)キュー モード。

```
accelerator_view create_view(queuing_mode qmode = queuing_mode_automatic);
```

### <a name="parameters"></a>パラメーター

*qmode*<br/>
キュー モード。

### <a name="return-value"></a>戻り値

新しい`accelerator_view`指定のキュー モードを使用して、このアクセラレータでのオブジェクト。

##  <a name="dedicated_memory"></a> dedicated_memory

`accelerator` の専用のメモリ (KB 単位) を取得します。

```
__declspec(property(get= get_dedicated_memory)) size_t dedicated_memory;
```

##  <a name="default_accelerator"></a> default_accelerator

既定の `accelerator` の文字列定数を取得します。

```
static const wchar_t default_accelerator[];
```

##  <a name="default_cpu_access_type"></a> default_cpu_access_type

既定の cpu [access_type](concurrency-namespace-enums-amp.md#access_type)配列および暗黙的なメモリ割り当てがこれに加えられた`accelerator`します。

```
__declspec(property(get= get_default_cpu_access_type)) access_type default_cpu_access_type;
```

##  <a name="default_view"></a> default_view

関連付けられている既定のアクセラレータ ビューを取得、`accelerator`します。

```
__declspec(property(get= get_default_view)) accelerator_view default_view;
```

##  <a name="description"></a> 説明

`accelerator` デバイスの短い説明を取得します。

```
__declspec(property(get= get_description)) std::wstring description;
```

##  <a name="device_path"></a> device_path

アクセラレータのパスを取得します。 パスは、システム上で一意です。

```
__declspec(property(get= get_device_path)) std::wstring device_path;
```

##  <a name="direct3d_ref"></a> direct3d_ref

Direct3D の参照のアクセラレータの文字列定数を取得します。

```
static const wchar_t direct3d_ref[];
```

##  <a name="direct3d_warp"></a> direct3d_warp

文字列の定数を取得、`accelerator`ストリーミング SIMD 拡張命令 (SSE) を使用するマルチコア Cpu で C++ AMP コードの実行に使用できるオブジェクトします。

```
static const wchar_t direct3d_warp[];
```

##  <a name="get_all"></a> get_all

使用可能なすべてのアクセラレータを表す `accelerator` オブジェクトのベクターを返します。

```
static inline std::vector<accelerator> get_all();
```

### <a name="return-value"></a>戻り値

使用できるアクセラレータのベクター

##  <a name="get_auto_selection_view"></a> get_auto_selection_view

ランタイムによって自動的に選択される parallel_for_each カーネルを実行するためにターゲットの accelerator_view で parallel_for_each ターゲット結果として指定される場合、自動選択の accelerator_view を返します。 その他のすべての目的については、このメソッドで返される accelerator_view は、既定のアクセラレータの既定の accelerator_view と同じです。

```
static accelerator_view __cdecl get_auto_selection_view();
```

### <a name="return-value"></a>戻り値

自動選択の accelerator_view。

##  <a name="get_dedicated_memory"></a> get_dedicated_memory

`accelerator` の専用のメモリ (KB 単位) を返します。

```
size_t get_dedicated_memory() const;
```

### <a name="return-value"></a>戻り値

専用のメモリ、 `accelerator`、(キロバイト単位)。

##  <a name="get_default_cpu_access_type"></a> get_default_cpu_access_type

このアクセラレータで作成されるバッファーの既定の CPU access_type を取得します

```
access_type get_default_cpu_access_type() const;
```

### <a name="return-value"></a>戻り値

このアクセラレータで作成されるバッファーの既定の CPU access_type。

##  <a name="get_default_view"></a> get_default_view

`accelerator_view` に関連付けられている既定の `accelerator` オブジェクトを返します。

```
accelerator_view get_default_view() const;
```

### <a name="return-value"></a>戻り値

既定の`accelerator_view`オブジェクトに関連付けられている、`accelerator`します。

##  <a name="get_description"></a> get_description

`accelerator` デバイスの短い説明を返します。

```
std::wstring get_description() const;
```

### <a name="return-value"></a>戻り値

簡単な説明、`accelerator`デバイス。

##  <a name="get_device_path"></a> get_device_path

アクセラレータのパスを返します。 パスは、システム上で一意です。

```
std::wstring get_device_path() const;
```

### <a name="return-value"></a>戻り値

一意のデバイスをシステム全体のインスタンス パス。

##  <a name="get_has_display"></a> get_has_display

示すブール値を返すかどうか、`accelerator`ディスプレイに出力できます。

```
bool get_has_display() const;
```

### <a name="return-value"></a>戻り値

**true**場合、 `accelerator` ; ディスプレイに出力できる場合は、 **false**します。

##  <a name="get_is_debug"></a> get_is_debug

`accelerator` が広範なエラー レポートに有効なデバッグ レイヤーを持つかどうかを決定します。

```
bool get_is_debug() const;
```

### <a name="return-value"></a>戻り値

**true**場合、`accelerator`広範なエラー レポートに有効なデバッグ レイヤーが。 それ以外の場合、 **false**します。

##  <a name="get_is_emulated"></a> get_is_emulated

`accelerator` がエミュレートされるかどうかを決定します。

```
bool get_is_emulated() const;
```

### <a name="return-value"></a>戻り値

**true**場合、`accelerator`はエミュレートされます。 それ以外の場合、 **false**します。

##  <a name="get_supports_cpu_shared_memory"></a> get_supports_cpu_shared_memory

アクセラレータがアクセラレータと CPU の両方からアクセスできるメモリをサポートするかどうかを示すブール値を返します。

```
bool get_supports_cpu_shared_memory() const;
```

### <a name="return-value"></a>戻り値

**true**アクセラレータが CPU をサポートしています。 メモリを共有する場合はそれ以外の場合、 **false**します。

##  <a name="get_supports_double_precision"></a> get_supports_double_precision

アクセラレータが倍精度演算をサポートするかどうかを含むヒューズを示すブール値の積を返します追加 (FMA)、除算、逆数、およびの間でキャスト**int**と**double。**

```
bool get_supports_double_precision() const;
```

### <a name="return-value"></a>戻り値

**true**アクセラレータが倍精度演算; をサポートする場合、それ以外の場合**false**します。

##  <a name="get_supports_limited_double_precision"></a> get_supports_limited_double_precision

アクセラレータの倍精度演算のサポートが制限されているかどうかを示すブール値を返します。 アクセラレータがある一部のみがサポート、乗算定着し (FMA) を追加する場合除算、逆数、およびの間でキャスト**int**と**二重**はサポートされていません。

```
bool get_supports_limited_double_precision() const;
```

### <a name="return-value"></a>戻り値

**true**アクセラレータの倍精度演算; のサポートが少ない場合それ以外の場合、 **false**します。

##  <a name="get_version"></a> get_version

`accelerator` のバージョンを返します。

```
unsigned int get_version() const;
```

### <a name="return-value"></a>戻り値

バージョン、`accelerator`します。

##  <a name="has_display"></a> has_display

示すブール値を取得するかどうか、`accelerator`ディスプレイに出力できます。

```
__declspec(property(get= get_has_display)) bool has_display;
```

##  <a name="is_debug"></a> is_debug

示すブール値を取得するかどうか、`accelerator`広範なエラー レポートに有効なデバッグ レイヤーが。

```
__declspec(property(get= get_is_debug)) bool is_debug;
```

##  <a name="is_emulated"></a> is_emulated

示すブール値を取得するかどうか、`accelerator`はエミュレートされます。

```
__declspec(property(get= get_is_emulated)) bool is_emulated;
```

##  <a name="operator_neq"></a> operator!=

これを比較します`accelerator`と他のオブジェクトを返します**false**は同じである場合を返しますそれ以外の場合、 **true**します。

```
bool operator!= (const accelerator& _Other) const;
```

### <a name="parameters"></a>パラメーター

*_Other*<br/>
`accelerator`これと比較するオブジェクト。

### <a name="return-value"></a>戻り値

**false**場合、2 つ`accelerator`オブジェクトが等しい、それ以外の**true**します。

##  <a name="operator_eq"></a> 演算子 =

指定された `accelerator` オブジェクトの内容をこのオブジェクトにコピーします。

```
accelerator& operator= (const accelerator& _Other);
```

### <a name="parameters"></a>パラメーター

*_Other*<br/>
コピー元の `accelerator` オブジェクト。

### <a name="return-value"></a>戻り値

この `accelerator` オブジェクトへの参照。

##  <a name="operator_eq_eq"></a> 演算子 = =

これを比較します`accelerator`と他のオブジェクトを返します**true**は同じである場合を返しますそれ以外の場合、 **false**します。

```
bool operator== (const accelerator& _Other) const;
```

### <a name="parameters"></a>パラメーター

*_Other*<br/>
`accelerator`これと比較するオブジェクト。

### <a name="return-value"></a>戻り値

**true**場合、その他の`accelerator`オブジェクトはこれと同じ`accelerator`オブジェクト。 それ以外の場合、 **false**します。

##  <a name="set_default"></a> set_default

暗黙的に既定のアクセラレータを使用するすべての操作に使用する既定のアクセラレータを設定します。 このメソッドは、ランタイムによって選択された既定のアクセラレータが暗黙的に既定のアクセラレータを使用する操作で既に使用されていない場合にのみ正常に終了します

```
static inline bool set_default(std::wstring _Path);
```

### <a name="parameters"></a>パラメーター

*_Path*<br/>
アクセラレータへのパス。

### <a name="return-value"></a>戻り値

**true**既定のアクセラレータを設定することで、呼び出しが成功した場合。 それ以外の場合、 **false**します。

##  <a name="set_default_cpu_access_type"></a> set_default_cpu_access_type

このアクセラレータでアクセスされる array_views の一部としてこのアクセラレータで作成される配列、または暗黙的なメモリ割り当ての既定の cpu access_type を設定します。 アクセラレータの default_cpu_access_type がこのメソッドへの前の呼び出しによってまだオーバーライドされておらず、このアクセラレータのために default_cpu_access_type を選択したランタイムが、配列の割り当てまたはこのアクセラレータでアクセスされる array_view の暗黙的なメモリ割り当てバッキングにまだ使用されていない場合にのみ、このメソッドは成功します。

```
bool set_default_cpu_access_type(access_type _Default_cpu_access_type);
```

### <a name="parameters"></a>パラメーター

*_Default_cpu_access_type*<br/>
このアクセラレータの array/array_view メモリ割り当てに使用される既定の CPU access_type。

### <a name="return-value"></a>戻り値

アクセラレータの既定の CPU access_type が正常に設定されたかどうかを示すブール値。

##  <a name="supports_cpu_shared_memory"></a> supports_cpu_shared_memory

`accelerator` が共有メモリをサポートしているかどうか示すブール値を取得します。

```
__declspec(property(get= get_supports_cpu_shared_memory)) bool supports_cpu_shared_memory;
```

##  <a name="supports_double_precision"></a> supports_double_precision

アクセラレータが倍精度数値演算をサポートするかどうかを示すブール値を取得します。

```
__declspec(property(get= get_supports_double_precision)) bool supports_double_precision;
```

##  <a name="supports_limited_double_precision"></a> supports_limited_double_precision

アクセラレータの倍精度演算のサポートが制限されているかどうかを示すブール値を取得します。 アクセラレータがある一部のみがサポート、乗算定着し (FMA) を追加する場合除算、逆数、およびの間でキャスト`int`と`double`はサポートされていません。

```
__declspec(property(get= get_supports_limited_double_precision)) bool supports_limited_double_precision;
```

##  <a name="version"></a> バージョン

`accelerator` のバージョンを取得します。

```
__declspec(property(get= get_version)) unsigned int version;
```

##  <a name="dtor"></a> </a> ~accelerator_view

破棄、 [accelerator_view](accelerator-view-class.md)オブジェクト。

```
~accelerator_view();
```

### <a name="return-value"></a>戻り値

##  <a name="accelerator"></a> アクセラレータ

取得、`accelerator`オブジェクト、 [accelerator_view](accelerator-view-class.md)オブジェクト。

```
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;
```

##  <a name="ctor"></a> accelerator_view

新しいインスタンスを初期化、 [accelerator_view](accelerator-view-class.md)クラス、既存のコピーを`accelerator_view`オブジェクト。

```
accelerator_view(const accelerator_view& _Other);
```

### <a name="parameters"></a>パラメーター

*_Other*<br/>
コピーする `accelerator_view` オブジェクト。

##  <a name="create_marker"></a> create_marker

これまでにこの `accelerator_view` オブジェクトに送信されたすべてのコマンドの完了を追跡するために予定を返します。

```
concurrency::completion_future create_marker();
```

### <a name="return-value"></a>戻り値

これまでこの `accelerator_view` オブジェクトに送信されたすべてのコマンドの完了を追跡するための予定です。

##  <a name="flush"></a> フラッシュ

キューに格納されたすべての保留コマンドの送信、 [accelerator_view](accelerator-view-class.md)オブジェクト実行のためにアクセラレータにします。

```
void flush();
```

### <a name="return-value"></a>戻り値

`void` を返します。

##  <a name="get_accelerator"></a> get_accelerator

返します、`accelerator`オブジェクト、 [accelerator_view](accelerator-view-class.md)オブジェクト。

```
accelerator get_accelerator() const;
```

### <a name="return-value"></a>戻り値

`accelerator`オブジェクト、`accelerator_view`オブジェクト。

##  <a name="get_is_auto_selection"></a> get_is_auto_selection

選択かどうか、ランタイムは自動的に適切なアクセラレータ accelerator_view に渡されるかを示すブール値を返します、 [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each)します。

```
bool get_is_auto_selection() const;
```

### <a name="return-value"></a>戻り値

**true**場合は、ランタイムが適切なアクセラレータ; を選択して自動的にそれ以外の場合、 **false**します。

##  <a name="get_is_debug"></a> get_is_debug

示すブール値を返すかどうか、 [accelerator_view](accelerator-view-class.md)オブジェクトに広範なエラー レポートに有効なデバッグ レイヤー。

```
bool get_is_debug() const;
```

### <a name="return-value"></a>戻り値

示すブール値かどうか、`accelerator_view`オブジェクトに広範なエラー レポートに有効なデバッグ レイヤー。

##  <a name="get_queuing_mode"></a> get_queuing_mode

キュー モードを返します、 [accelerator_view](accelerator-view-class.md)オブジェクト。

```
queuing_mode get_queuing_mode() const;
```

### <a name="return-value"></a>戻り値

キュー モード、`accelerator_view`オブジェクト。

##  <a name="get_version"></a> get_version

バージョンを返します、 [accelerator_view](accelerator-view-class.md)します。

```
unsigned int get_version() const;
```

### <a name="return-value"></a>戻り値

バージョン、`accelerator_view`します。

##  <a name="is_auto_selection"></a> is_auto_selection

選択かどうか、ランタイムは自動的に適切なアクセラレータ accelerator_view に渡されるかを示すブール値を取得、 [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each)します。

```
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;
```

##  <a name="is_debug"></a> is_debug

示すブール値を取得するかどうか、 [accelerator_view](accelerator-view-class.md)オブジェクトに広範なエラー レポートに有効なデバッグ レイヤー。

```
__declspec(property(get= get_is_debug)) bool is_debug;
```

##  <a name="operator_neq"></a> operator!=

この比較[accelerator_view](accelerator-view-class.md)と他のオブジェクトを返します`false`は同じである場合を返しますそれ以外の場合、 `true`。

```
bool operator!= (const accelerator_view& _Other) const;
```

### <a name="parameters"></a>パラメーター

*_Other*<br/>
`accelerator_view`これと比較するオブジェクト。

### <a name="return-value"></a>戻り値

**false**場合 2 つのオブジェクトは同じです。 それ以外の場合、 **true**します。

##  <a name="operator_eq"></a> 演算子 =

指定した内容をコピー [accelerator_view](accelerator-view-class.md)をこのオブジェクト。

```
accelerator_view& operator= (const accelerator_view& _Other);
```

### <a name="parameters"></a>パラメーター

*_Other*<br/>
コピー元の `accelerator_view` オブジェクト。

### <a name="return-value"></a>戻り値

変更されたへの参照を`accelerator_view`オブジェクト。

##  <a name="operator_eq_eq"></a> 演算子 = =

これを比較します[accelerator_view](accelerator-view-class.md)と他のオブジェクトを返します**true**は同じである場合を返しますそれ以外の場合、 **false**します。

```
bool operator== (const accelerator_view& _Other) const;
```

### <a name="parameters"></a>パラメーター

*_Other*<br/>
`accelerator_view`これと比較するオブジェクト。

### <a name="return-value"></a>戻り値

**true**場合 2 つのオブジェクトは同じです。 それ以外の場合、 **false**します。

##  <a name="queuing_mode"></a> queuing_mode

キュー モードを取得、 [accelerator_view](accelerator-view-class.md)オブジェクト。

```
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;
```

##  <a name="version"></a> バージョン

バージョンを取得、 [accelerator_view](accelerator-view-class.md)します。

```
__declspec(property(get= get_version)) unsigned int version;
```

##  <a name="wait"></a> 待機

送信されたすべてのコマンドの待機、 [accelerator_view](accelerator-view-class.md)オブジェクトを終了します。

```
void wait();
```

### <a name="return-value"></a>戻り値

`void` を返します。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
