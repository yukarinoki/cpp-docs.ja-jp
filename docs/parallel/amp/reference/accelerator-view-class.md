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
ms.openlocfilehash: 4075051ec07fc1331d815534a715c0411160fe14
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2019
ms.locfileid: "58566027"
---
# <a name="acceleratorview-class"></a>accelerator_view クラス

C ++. AMP のデータ並列アクセラレータでの仮想デバイスの抽象化を表します。

### <a name="syntax"></a>構文

```
class accelerator_view;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[accelerator_view コンス トラクター](#ctor)|`accelerator_view` クラスの新しいインスタンスを初期化します。|
|[~ accelerator_view デストラクター](#dtor)|`accelerator_view` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[create_marker](#create_marker)|これまでにこの `accelerator_view` オブジェクトに送信されたすべてのコマンドの完了を追跡するために予定を返します。|
|[flush](#flush)|`accelerator_view` オブジェクトのキューに格納されたすべての保留中のコマンドを実行のためにアクセラレータに送信します。|
|[get_accelerator](#get_accelerator)|`accelerator` オブジェクトの `accelerator_view` オブジェクトを返します。|
|[get_is_auto_selection](#get_is_auto_selection)|ランタイムの適切なアクセラレータが自動的に選択するかどうかを示すブール値を返すときに、`accelerator_view`にオブジェクトが渡される、 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)。|
|[get_is_debug](#get_is_debug)|`accelerator_view` オブジェクトに広範なエラー レポートに有効なデバッグ レイヤーがあるかどうかを示すブール値を返します。|
|[get_queuing_mode](#get_queuing_mode)|`accelerator_view` オブジェクトのキュー モードを返します。|
|[get_version](#get_version)|`accelerator_view` のバージョンを返します。|
|[wait](#wait)|終了する `accelerator_view` オブジェクトに送信されるすべてのコマンドを待機します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[operator!=](#operator_neq)|これを比較します`accelerator_view`と他のオブジェクトを返します**false**は同じである場合を返しますそれ以外の場合、 **true**します。|
|[operator=](#operator_eq)|指定された `accelerator_view` オブジェクトの内容をこのオブジェクトにコピーします。|
|[operator==](#operator_eq_eq)|これを比較します`accelerator_view`と他のオブジェクトを返します**true**は同じである場合を返しますそれ以外の場合、 **false**します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[accelerator](#accelerator)|`accelerator` オブジェクトの `accelerator_view` オブジェクトを取得します。|
|[is_auto_selection](#is_auto_selection)|ランタイムの適切なアクセラレータが自動的に選択するかどうかを示すブール値を取得ときに、`accelerator_view`にオブジェクトが渡される、 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)します。|
|[is_debug](#is_debug)|`accelerator_view` オブジェクトに広範なエラー レポートに有効なデバッグ レイヤーがあるかどうかを示すブール値を取得します。|
|[queuing_mode](#queuing_mode)|`accelerator_view` オブジェクトのキュー モードを取得します。|
|[version](#version)|accelerator のバージョンを取得します。|

## <a name="inheritance-hierarchy"></a>継承階層

`accelerator_view`

### <a name="remarks"></a>Remarks

`accelerator_view` オブジェクトは、アクセラレータの論理的で分離されたビューを表します。 単一の物理計算デバイスは、多くの論理的で分離された `accelerator_view` オブジェクトを使用できます。 各アクセラレータには既定の `accelerator_view` オブジェクトがあります。 追加の `accelerator_view` オブジェクトを作成できます。

物理デバイスは、多くのクライアント スレッド間で共有できます。 クライアント スレッドがアクセラレータの同じ `accelerator_view` オブジェクトを協調的に使用することができるか、または、各クライアントが他のクライアント スレッドから分離するために独立した `accelerator_view` オブジェクトを使用して計算デバイスと通信できます。

`accelerator_view`オブジェクトには、2 つのいずれかを指定できる[queuing_mode 列挙型](concurrency-namespace-enums-amp.md#queuing_mode)状態。 キュー モードが `immediate` である場合、`copy` および `parallel_for_each` のようなコマンドが呼び出し元に戻るとすぐに対応するアクセラレータ デバイスに送信されます。 キュー モードが `deferred` の場合、このようなコマンドは `accelerator_view` オブジェクトに対応するコマンド キューに置かれます。 コマンドは、`flush()` が呼び出されるまでデバイスに実際に送信されません。

## <a name="requirements"></a>必要条件

**ヘッダー:** amprt.h

**名前空間:** コンカレンシー

## <a name="accelerator"></a> アクセラレータ

Accelerator_view オブジェクトのアクセラレータのオブジェクトを取得します。

### <a name="syntax"></a>構文

```
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;
```

## <a name="ctor"></a> accelerator_view

既存のコピーすることで、accelerator_view クラスの新しいインスタンスを初期化します`accelerator_view`オブジェクト。

### <a name="syntax"></a>構文

```
accelerator_view( const accelerator_view & other );
```

### <a name="parameters"></a>パラメーター

*other*<br/>
コピーする `accelerator_view` オブジェクト。

## <a name="createmarker"></a>create_marker

これまでにこの `accelerator_view` オブジェクトに送信されたすべてのコマンドの完了を追跡するために予定を返します。

### <a name="syntax"></a>構文

```
concurrency::completion_future create_marker();
```

### <a name="return-value"></a>戻り値

これまでこの `accelerator_view` オブジェクトに送信されたすべてのコマンドの完了を追跡するための予定です。

## <a name="flush"></a>flush

実行のためにアクセラレータ accelerator_view オブジェクトをキューに保留中のすべてのコマンドを送信します。

### <a name="syntax"></a>構文

```
void flush();
```

### <a name="return-value"></a>戻り値

`void` を返します。

## <a name="getaccelerator"></a>get_accelerator

Accelerator_view オブジェクトのアクセラレータのオブジェクトを返します。
### <a name="syntax"></a>構文

```
accelerator get_accelerator() const;
```

### <a name="return-value"></a>戻り値

Accelerator_view オブジェクトのアクセラレータのオブジェクト。

## <a name="getisautoselection"></a>get_is_auto_selection

選択かどうか、ランタイムは自動的に適切なアクセラレータ accelerator_view に渡されるかを示すブール値を返します、 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)します。

### <a name="syntax"></a>構文

```
bool get_is_auto_selection() const;
```

### <a name="return-value"></a>戻り値

**true**場合は、ランタイムが適切なアクセラレータ; を選択して自動的にそれ以外の場合、 **false**します。

## <a name="getisdebug"></a>get_is_debug

Accelerator_view オブジェクトに広範なエラー レポートに有効なデバッグ レイヤーがあるかどうかを示すブール値を返します。

### <a name="syntax"></a>構文

```
bool get_is_debug() const;
```

### <a name="return-value"></a>戻り値

示すブール値かどうか、`accelerator_view`オブジェクトに広範なエラー レポートに有効なデバッグ レイヤー。

## <a name="getqueuingmode"></a>get_queuing_mode

Accelerator_view オブジェクトのキュー モードを返します。

### <a name="syntax"></a>構文

```
queuing_mode get_queuing_mode() const;
```

### <a name="return-value"></a>戻り値

キュー モード、`accelerator_view`オブジェクト。

## <a name="getversion"></a>get_version

Accelerator_view のバージョンを返します。

### <a name="syntax"></a>構文

```
unsigned int get_version() const;
```

### <a name="return-value"></a>戻り値

バージョン、`accelerator_view`します。

## <a name="isautoselection"></a>is_auto_selection

選択かどうか、ランタイムは自動的に適切なアクセラレータ accelerator_view に渡されるかを示すブール値を取得、 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)します。

### <a name="syntax"></a>構文

```
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;
```

## <a name="isdebug"></a>is_debug

Accelerator_view オブジェクトに広範なエラー レポートに有効なデバッグ レイヤーがあるかどうかを示すブール値を取得します。

### <a name="syntax"></a>構文

```
__declspec(property(get= get_is_debug)) bool is_debug;
```

## <a name="operator_neq"></a> operator!=

この accelerator_view オブジェクトと別に比較し、返します**false**は同じである場合を返しますそれ以外の場合、 **true**します。

### <a name="syntax"></a>構文

```
bool operator!= ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>パラメーター

*other*<br/>
`accelerator_view`これと比較するオブジェクト。

### <a name="return-value"></a>戻り値

**false**場合 2 つのオブジェクトは同じです。 それ以外の場合、 **true**します。

## <a name="operator_eq"></a> 演算子 =

これには、指定された accelerator_view オブジェクトの内容をコピーします。

### <a name="syntax"></a>構文

```
accelerator_view & operator= ( const accelerator_view & other );
```

### <a name="parameters"></a>パラメーター

*other*<br/>
コピー元の `accelerator_view` オブジェクト。

### <a name="return-value"></a>戻り値

変更されたへの参照を`accelerator_view`オブジェクト。

## <a name="operator_eq_eq"></a> 演算子 = =

この accelerator_view オブジェクトと別に比較し、返します**true**は同じである場合を返しますそれ以外の場合、 **false**します。

### <a name="syntax"></a>構文

```
bool operator== ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>パラメーター

*other*<br/>
`accelerator_view`これと比較するオブジェクト。

### <a name="return-value"></a>戻り値

**true**場合 2 つのオブジェクトは同じです。 それ以外の場合、 **false**します。

## <a name="queuingmode"></a>queuing_mode

Accelerator_view オブジェクトのキュー モードを取得します。

### <a name="syntax"></a>構文

```
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;
```

## <a name="version"></a>version

Accelerator_view のバージョンを取得します。

### <a name="syntax"></a>構文

```
__declspec(property(get= get_version)) unsigned int version;
```

## <a name="wait"></a>待機

Accelerator_view オブジェクトに送信されたすべてのコマンドを完了するまで待機します。

### <a name="syntax"></a>構文

```
void wait();
```

### <a name="return-value"></a>戻り値

`void` を返します。

### <a name="remarks"></a>Remarks

場合、 [queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode)は`immediate`、このメソッドをブロックすることがなくすぐに返します。

##  <a name="dtor"></a> ~accelerator_view

Accelerator_view オブジェクトを破棄します。

### <a name="syntax"></a>構文

```
~accelerator_view();
```

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
