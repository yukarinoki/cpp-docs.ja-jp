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
ms.openlocfilehash: f3be8cc3ab9a0f36027cc38c88f026570d1fdb55
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370886"
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
|[accelerator_viewコンストラクタ](#ctor)|`accelerator_view` クラスの新しいインスタンスを初期化します。|
|[~デストラクタaccelerator_view](#dtor)|`accelerator_view` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[create_marker](#create_marker)|これまでにこの `accelerator_view` オブジェクトに送信されたすべてのコマンドの完了を追跡するために予定を返します。|
|[フラッシュ](#flush)|`accelerator_view` オブジェクトのキューに格納されたすべての保留中のコマンドを実行のためにアクセラレータに送信します。|
|[get_accelerator](#get_accelerator)|`accelerator` オブジェクトの `accelerator_view` オブジェクトを返します。|
|[get_is_auto_selection](#get_is_auto_selection)|`accelerator_view`オブジェクトが[parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)に渡されるときに、ランタイムが適切なアクセラレータを自動的に選択するかどうかを示すブール値を返します。|
|[get_is_debug](#get_is_debug)|`accelerator_view` オブジェクトに広範なエラー レポートに有効なデバッグ レイヤーがあるかどうかを示すブール値を返します。|
|[get_queuing_mode](#get_queuing_mode)|`accelerator_view` オブジェクトのキュー モードを返します。|
|[get_version](#get_version)|`accelerator_view` のバージョンを返します。|
|[待つ](#wait)|終了する `accelerator_view` オブジェクトに送信されるすべてのコマンドを待機します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[演算子!=](#operator_neq)|この`accelerator_view`オブジェクトを別のオブジェクトと比較し、同じ場合は**false**を返します。それ以外の場合は**true**を返します。|
|[演算子=](#operator_eq)|指定された `accelerator_view` オブジェクトの内容をこのオブジェクトにコピーします。|
|[演算子==](#operator_eq_eq)|この`accelerator_view`オブジェクトを別のオブジェクトと比較し、同じ場合は**true**を返します。それ以外の場合は**false**を返します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[アクセラレータ](#accelerator)|`accelerator` オブジェクトの `accelerator_view` オブジェクトを取得します。|
|[is_auto_selection](#is_auto_selection)|`accelerator_view`オブジェクトが[parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)に渡されるときに、ランタイムが適切なアクセラレータを自動的に選択するかどうかを示すブール値を取得します。|
|[is_debug](#is_debug)|`accelerator_view` オブジェクトに広範なエラー レポートに有効なデバッグ レイヤーがあるかどうかを示すブール値を取得します。|
|[queuing_mode](#queuing_mode)|`accelerator_view` オブジェクトのキュー モードを取得します。|
|[version](#version)|accelerator のバージョンを取得します。|

## <a name="inheritance-hierarchy"></a>継承階層

`accelerator_view`

### <a name="remarks"></a>解説

`accelerator_view` オブジェクトは、アクセラレータの論理的で分離されたビューを表します。 単一の物理計算デバイスは、多くの論理的で分離された `accelerator_view` オブジェクトを使用できます。 各アクセラレータには既定の `accelerator_view` オブジェクトがあります。 追加の `accelerator_view` オブジェクトを作成できます。

物理デバイスは、多くのクライアント スレッド間で共有できます。 クライアント スレッドがアクセラレータの同じ `accelerator_view` オブジェクトを協調的に使用することができるか、または、各クライアントが他のクライアント スレッドから分離するために独立した `accelerator_view` オブジェクトを使用して計算デバイスと通信できます。

オブジェクト`accelerator_view`は[、2 つのqueuing_mode列挙](concurrency-namespace-enums-amp.md#queuing_mode)状態のいずれかを持つことができます。 キュー モードが `immediate` である場合、`copy` および `parallel_for_each` のようなコマンドが呼び出し元に戻るとすぐに対応するアクセラレータ デバイスに送信されます。 キュー モードが `deferred` の場合、このようなコマンドは `accelerator_view` オブジェクトに対応するコマンド キューに置かれます。 コマンドは、`flush()` が呼び出されるまでデバイスに実際に送信されません。

## <a name="requirements"></a>必要条件

**ヘッダー:** アンパート.h

**名前空間:** Concurrency

## <a name="accelerator"></a><a name="accelerator"></a>アクセラレータ

accelerator_view オブジェクトのアクセラレータ オブジェクトを取得します。

### <a name="syntax"></a>構文

```cpp
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;
```

## <a name="accelerator_view"></a><a name="ctor"></a>accelerator_view

既存`accelerator_view`のオブジェクトをコピーして、accelerator_view クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
accelerator_view( const accelerator_view & other );
```

### <a name="parameters"></a>パラメーター

*他*<br/>
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

accelerator_view オブジェクトにキューに入っているすべての保留中のコマンドを、実行のためにアクセラレータに送信します。

### <a name="syntax"></a>構文

```cpp
void flush();
```

### <a name="return-value"></a>戻り値

`void` が返されます。

## <a name="get_accelerator"></a><a name="get_accelerator"></a>get_accelerator

accelerator_view オブジェクトのアクセラレータ オブジェクトを返します。

### <a name="syntax"></a>構文

```cpp
accelerator get_accelerator() const;
```

### <a name="return-value"></a>戻り値

accelerator_view オブジェクトのアクセラレータ オブジェクト。

## <a name="get_is_auto_selection"></a><a name="get_is_auto_selection"></a>get_is_auto_selection

accelerator_viewが[parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)に渡されるときに、ランタイムが適切なアクセラレータを自動的に選択するかどうかを示すブール値を返します。

### <a name="syntax"></a>構文

```cpp
bool get_is_auto_selection() const;
```

### <a name="return-value"></a>戻り値

ランタイムが適切なアクセラレータを自動的に選択する場合は true、または、適切なアクセラレータを選択する場合は**true、** それ以外の場合**は false。**

## <a name="get_is_debug"></a><a name="get_is_debug"></a>get_is_debug

accelerator_view オブジェクトに、詳細なエラー報告用の DEBUG レイヤーが有効になっているかどうかを示すブール値を返します。

### <a name="syntax"></a>構文

```cpp
bool get_is_debug() const;
```

### <a name="return-value"></a>戻り値

オブジェクトに、詳細なエラー報告`accelerator_view`用の DEBUG 層が有効になっているかどうかを示すブール値。

## <a name="get_queuing_mode"></a><a name="get_queuing_mode"></a>get_queuing_mode

accelerator_view オブジェクトのキュー モードを返します。

### <a name="syntax"></a>構文

```cpp
queuing_mode get_queuing_mode() const;
```

### <a name="return-value"></a>戻り値

`accelerator_view`オブジェクトのキュー モード。

## <a name="get_version"></a><a name="get_version"></a>get_version

accelerator_viewのバージョンを返します。

### <a name="syntax"></a>構文

```cpp
unsigned int get_version() const;
```

### <a name="return-value"></a>戻り値

`accelerator_view` のバージョン。

## <a name="is_auto_selection"></a><a name="is_auto_selection"></a>is_auto_selection

accelerator_viewが[parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)に渡されるときに、ランタイムが適切なアクセラレータを自動的に選択するかどうかを示すブール値を取得します。

### <a name="syntax"></a>構文

```cpp
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;
```

## <a name="is_debug"></a><a name="is_debug"></a>is_debug

accelerator_view オブジェクトに、詳細なエラー報告用の DEBUG レイヤーが有効になっているかどうかを示すブール値を取得します。

### <a name="syntax"></a>構文

```cpp
__declspec(property(get= get_is_debug)) bool is_debug;
```

## <a name="operator"></a><a name="operator_neq"></a>演算子!=

このaccelerator_viewオブジェクトを別のオブジェクトと比較し、同じ場合は**false**を返します。それ以外の場合は**true**を返します。

### <a name="syntax"></a>構文

```cpp
bool operator!= ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>パラメーター

*他*<br/>
この`accelerator_view`オブジェクトと比較するオブジェクト。

### <a name="return-value"></a>戻り値

2 つのオブジェクトが同じ場合は**false。** それ以外の場合**は true**です。

## <a name="operator"></a><a name="operator_eq"></a>演算子=

指定したaccelerator_viewオブジェクトの内容をこのオブジェクトにコピーします。

### <a name="syntax"></a>構文

```cpp
accelerator_view & operator= ( const accelerator_view & other );
```

### <a name="parameters"></a>パラメーター

*他*<br/>
コピー元の `accelerator_view` オブジェクト。

### <a name="return-value"></a>戻り値

変更された`accelerator_view`オブジェクトへの参照。

## <a name="operator"></a><a name="operator_eq_eq"></a>演算子==

このaccelerator_viewオブジェクトを別のオブジェクトと比較し、同じ場合は**true**を返します。それ以外の場合は**false**を返します。

### <a name="syntax"></a>構文

```cpp
bool operator== ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>パラメーター

*他*<br/>
この`accelerator_view`オブジェクトと比較するオブジェクト。

### <a name="return-value"></a>戻り値

2 つのオブジェクトが同じ場合は**true。** それ以外の場合**は false。**

## <a name="queuing_mode"></a><a name="queuing_mode"></a>queuing_mode

accelerator_view オブジェクトのキュー モードを取得します。

### <a name="syntax"></a>構文

```cpp
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;
```

## <a name="version"></a>version

accelerator_viewのバージョンを取得します。

### <a name="syntax"></a>構文

```cpp
__declspec(property(get= get_version)) unsigned int version;
```

## <a name="wait"></a>wait

accelerator_view オブジェクトに送信されたすべてのコマンドが完了するまで待機します。

### <a name="syntax"></a>構文

```cpp
void wait();
```

### <a name="return-value"></a>戻り値

`void` が返されます。

### <a name="remarks"></a>解説

[queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode)が`immediate`の場合、このメソッドはブロックせずにすぐに戻ります。

## <a name="accelerator_view"></a><a name="dtor"></a>~accelerator_view

accelerator_viewオブジェクトを破棄します。

### <a name="syntax"></a>構文

```cpp
~accelerator_view();
```

## <a name="see-also"></a>関連項目

[同時実行名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
