---
title: accelerator_view クラス
ms.date: 03/27/2019
f1_keywords:
- accelerator_view
- AMPRT/accelerator_view
- AMPRT/Concurrency::accelerator_view::accelerator_view
- AMPRT/Concurrency::accelerator_view::create_marker
- AMPRT/Concurrency::accelerator_view::flush
- AMPRT/Concurrency::accelerator_view::get_accelerator
- AMPRT/Concurrency::accelerator_view::get_is_auto_selection
- AMPRT/Concurrency::accelerator_view::get_is_debug
- AMPRT/Concurrency::accelerator_view::get_queuing_mode
- AMPRT/Concurrency::accelerator_view::get_version
- AMPRT/Concurrency::accelerator_view::wait
- AMPRT/Concurrency::accelerator_view::accelerator
- AMPRT/Concurrency::accelerator_view::is_auto_selection
- AMPRT/Concurrency::accelerator_view::is_debug
- AMPRT/Concurrency::accelerator_view::queuing_mode
- AMPRT/Concurrency::accelerator_view::version
helpviewer_keywords:
- accelerator_view class
ms.assetid: 9f298c21-bf62-46e0-88b8-01c5c78ef144
ms.openlocfilehash: 0020acfda7b506bf9f0547b9daedff34d80204f7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87182760"
---
# <a name="accelerator_view-class"></a>accelerator_view クラス

C ++. AMP のデータ並列アクセラレータでの仮想デバイスの抽象化を表します。

## <a name="syntax"></a>構文

```cpp
class accelerator_view;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[accelerator_view コンストラクター](#ctor)|`accelerator_view` クラスの新しいインスタンスを初期化します。|
|[~ accelerator_view デストラクター](#dtor)|`accelerator_view` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[create_marker](#create_marker)|これまでにこの `accelerator_view` オブジェクトに送信されたすべてのコマンドの完了を追跡するために予定を返します。|
|[揃える](#flush)|`accelerator_view` オブジェクトのキューに格納されたすべての保留中のコマンドを実行のためにアクセラレータに送信します。|
|[get_accelerator](#get_accelerator)|`accelerator` オブジェクトの `accelerator_view` オブジェクトを返します。|
|[get_is_auto_selection](#get_is_auto_selection)|`accelerator_view`オブジェクトが[parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)に渡されたときに、ランタイムが適切なアクセラレータを自動的に選択するかどうかを示すブール値を返します。|
|[get_is_debug](#get_is_debug)|`accelerator_view` オブジェクトに広範なエラー レポートに有効なデバッグ レイヤーがあるかどうかを示すブール値を返します。|
|[get_queuing_mode](#get_queuing_mode)|`accelerator_view` オブジェクトのキュー モードを返します。|
|[get_version](#get_version)|`accelerator_view` のバージョンを返します。|
|[待機](#wait)|終了する `accelerator_view` オブジェクトに送信されるすべてのコマンドを待機します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[operator! =](#operator_neq)|このオブジェクトと別のオブジェクトを比較 `accelerator_view` し、同じである場合はを返します **`false`** 。それ以外の場合はを返し **`true`** ます。|
|[operator =](#operator_eq)|指定された `accelerator_view` オブジェクトの内容をこのオブジェクトにコピーします。|
|[operator = =](#operator_eq_eq)|このオブジェクトと別のオブジェクトを比較 `accelerator_view` し、同じである場合はを返します **`true`** 。それ以外の場合はを返し **`false`** ます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[アクセラレーター](#accelerator)|`accelerator` オブジェクトの `accelerator_view` オブジェクトを取得します。|
|[is_auto_selection](#is_auto_selection)|`accelerator_view`オブジェクトが[parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)に渡されたときに、ランタイムが適切なアクセラレータを自動的に選択するかどうかを示すブール値を取得します。|
|[is_debug](#is_debug)|`accelerator_view` オブジェクトに広範なエラー レポートに有効なデバッグ レイヤーがあるかどうかを示すブール値を取得します。|
|[queuing_mode](#queuing_mode)|`accelerator_view` オブジェクトのキュー モードを取得します。|
|[version](#version)|accelerator のバージョンを取得します。|

## <a name="inheritance-hierarchy"></a>継承階層

`accelerator_view`

### <a name="remarks"></a>解説

`accelerator_view` オブジェクトは、アクセラレータの論理的で分離されたビューを表します。 単一の物理計算デバイスは、多くの論理的で分離された `accelerator_view` オブジェクトを使用できます。 各アクセラレータには既定の `accelerator_view` オブジェクトがあります。 追加の `accelerator_view` オブジェクトを作成できます。

物理デバイスは、多くのクライアント スレッド間で共有できます。 クライアント スレッドがアクセラレータの同じ `accelerator_view` オブジェクトを協調的に使用することができるか、または、各クライアントが他のクライアント スレッドから分離するために独立した `accelerator_view` オブジェクトを使用して計算デバイスと通信できます。

オブジェクトは、 `accelerator_view` 2 つの[queuing_mode 列挙](concurrency-namespace-enums-amp.md#queuing_mode)状態のいずれかを持つことができます。 キュー モードが `immediate` である場合、`copy` および `parallel_for_each` のようなコマンドが呼び出し元に戻るとすぐに対応するアクセラレータ デバイスに送信されます。 キュー モードが `deferred` の場合、このようなコマンドは `accelerator_view` オブジェクトに対応するコマンド キューに置かれます。 コマンドは、`flush()` が呼び出されるまでデバイスに実際に送信されません。

## <a name="requirements"></a>必要条件

**ヘッダー:** amprt. h

**名前空間:** Concurrency

## <a name="accelerator"></a><a name="accelerator"></a>アクセラレーター

Accelerator_view オブジェクトのアクセラレータオブジェクトを取得します。

### <a name="syntax"></a>構文

```cpp
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;
```

## <a name="accelerator_view"></a><a name="ctor"></a>accelerator_view

既存のオブジェクトをコピーして、accelerator_view クラスの新しいインスタンスを初期化 `accelerator_view` します。

### <a name="syntax"></a>構文

```cpp
accelerator_view( const accelerator_view & other );
```

### <a name="parameters"></a>パラメーター

*他の*<br/>
コピーする `accelerator_view` オブジェクトです。

## <a name="create_marker"></a><a name="create_marker"></a>create_marker

これまでにこの `accelerator_view` オブジェクトに送信されたすべてのコマンドの完了を追跡するために予定を返します。

### <a name="syntax"></a>構文

```cpp
concurrency::completion_future create_marker();
```

### <a name="return-value"></a>戻り値

これまでこの `accelerator_view` オブジェクトに送信されたすべてのコマンドの完了を追跡するための予定です。

## <a name="flush"></a>flush

Accelerator_view オブジェクトにキューに置かれている保留中のすべてのコマンドを、実行のためにアクセラレータに送信します。

### <a name="syntax"></a>構文

```cpp
void flush();
```

### <a name="return-value"></a>戻り値

を返し **`void`** ます。

## <a name="get_accelerator"></a><a name="get_accelerator"></a>get_accelerator

Accelerator_view オブジェクトのアクセラレータオブジェクトを返します。

### <a name="syntax"></a>構文

```cpp
accelerator get_accelerator() const;
```

### <a name="return-value"></a>戻り値

Accelerator_view オブジェクトの accelerator オブジェクト。

## <a name="get_is_auto_selection"></a><a name="get_is_auto_selection"></a>get_is_auto_selection

Accelerator_view が[parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)に渡されたときに、ランタイムが適切なアクセラレータを自動的に選択するかどうかを示すブール値を返します。

### <a name="syntax"></a>構文

```cpp
bool get_is_auto_selection() const;
```

### <a name="return-value"></a>戻り値

**`true`** ランタイムが適切なアクセラレータを自動的に選択する場合は、それ以外の場合は **`false`** 。

## <a name="get_is_debug"></a><a name="get_is_debug"></a>get_is_debug

Accelerator_view オブジェクトの詳細なエラー報告が有効になっているデバッグ層があるかどうかを示すブール値を返します。

### <a name="syntax"></a>構文

```cpp
bool get_is_debug() const;
```

### <a name="return-value"></a>戻り値

`accelerator_view`オブジェクトで広範なエラー報告が有効になっているデバッグレイヤーがあるかどうかを示すブール値。

## <a name="get_queuing_mode"></a><a name="get_queuing_mode"></a>get_queuing_mode

Accelerator_view オブジェクトのキューモードを返します。

### <a name="syntax"></a>構文

```cpp
queuing_mode get_queuing_mode() const;
```

### <a name="return-value"></a>戻り値

オブジェクトのキューモード `accelerator_view` 。

## <a name="get_version"></a><a name="get_version"></a>get_version

Accelerator_view のバージョンを返します。

### <a name="syntax"></a>構文

```cpp
unsigned int get_version() const;
```

### <a name="return-value"></a>戻り値

`accelerator_view` のバージョン。

## <a name="is_auto_selection"></a><a name="is_auto_selection"></a>is_auto_selection

Accelerator_view が[parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)に渡されたときに、ランタイムが適切なアクセラレータを自動的に選択するかどうかを示すブール値を取得します。

### <a name="syntax"></a>構文

```cpp
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;
```

## <a name="is_debug"></a><a name="is_debug"></a>is_debug

Accelerator_view オブジェクトの詳細なエラー報告が有効になっているデバッグ層があるかどうかを示すブール値を取得します。

### <a name="syntax"></a>構文

```cpp
__declspec(property(get= get_is_debug)) bool is_debug;
```

## <a name="operator"></a><a name="operator_neq"></a>operator! =

この accelerator_view オブジェクトと別のオブジェクトを比較し、同じである場合はを返します **`false`** 。それ以外の場合はを返し **`true`** ます。

### <a name="syntax"></a>構文

```cpp
bool operator!= ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>パラメーター

*他の*<br/>
`accelerator_view`このと比較するオブジェクト。

### <a name="return-value"></a>戻り値

**`false`** 2つのオブジェクトが同じ場合は。それ以外の場合は **`true`** 。

## <a name="operator"></a><a name="operator_eq"></a>operator =

指定された accelerator_view オブジェクトの内容をこのオブジェクトにコピーします。

### <a name="syntax"></a>構文

```cpp
accelerator_view & operator= ( const accelerator_view & other );
```

### <a name="parameters"></a>パラメーター

*他の*<br/>
コピー元の `accelerator_view` オブジェクト。

### <a name="return-value"></a>戻り値

変更されたオブジェクトへの参照 `accelerator_view` 。

## <a name="operator"></a><a name="operator_eq_eq"></a>operator = =

この accelerator_view オブジェクトと別のオブジェクトを比較し、同じである場合はを返します **`true`** 。それ以外の場合はを返し **`false`** ます。

### <a name="syntax"></a>構文

```cpp
bool operator== ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>パラメーター

*他の*<br/>
`accelerator_view`このと比較するオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 2つのオブジェクトが同じ場合は。それ以外の場合は **`false`** 。

## <a name="queuing_mode"></a><a name="queuing_mode"></a>queuing_mode

Accelerator_view オブジェクトのキューモードを取得します。

### <a name="syntax"></a>構文

```cpp
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;
```

## <a name="version"></a>version

Accelerator_view のバージョンを取得します。

### <a name="syntax"></a>構文

```cpp
__declspec(property(get= get_version)) unsigned int version;
```

## <a name="wait"></a>wait

Accelerator_view オブジェクトに送信されたすべてのコマンドが終了するまで待機します。

### <a name="syntax"></a>構文

```cpp
void wait();
```

### <a name="return-value"></a>戻り値

を返し **`void`** ます。

### <a name="remarks"></a>解説

[Queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode)がの場合 `immediate` 、このメソッドは、ブロックなしですぐに制御を戻します。

## <a name="accelerator_view"></a><a name="dtor"></a>~ accelerator_view

Accelerator_view オブジェクトを破棄します。

### <a name="syntax"></a>構文

```cpp
~accelerator_view();
```

## <a name="see-also"></a>関連項目

[Concurrency 名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
