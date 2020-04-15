---
title: Cダイナミックチェーンクラス
ms.date: 11/04/2016
f1_keywords:
- CDynamicChain
- ATLWIN/ATL::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CallChain
- ATLWIN/ATL::CDynamicChain::RemoveChainEntry
- ATLWIN/ATL::CDynamicChain::SetChainEntry
helpviewer_keywords:
- message maps, chaining
- chaining message maps
- CDynamicChain class
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
ms.openlocfilehash: 4a72b3b4308ed83dfdc4a2895a04d1fe9a177ce5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327034"
---
# <a name="cdynamicchain-class"></a>Cダイナミックチェーンクラス

このクラスには、メッセージ マップの動的チェーンをサポートするメソッドが用意されています。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CDynamicChain
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cダイナミックチェーン::Cダイナミックチェーン](#cdynamicchain)|コンストラクターです。|
|[Cダイナミックチェーン::~Cダイナミックチェーン](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cダイナミックチェーン::コールチェーン](#callchain)|Windows メッセージを別のオブジェクトのメッセージ マップに送信します。|
|[Cダイナミックチェーン::除去チェーンエントリ](#removechainentry)|メッセージ マップ エントリをコレクションから削除します。|
|[Cダイナミックチェーン::セットチェーンエントリー](#setchainentry)|メッセージ マップ エントリをコレクションに追加するか、既存のエントリを変更します。|

## <a name="remarks"></a>解説

`CDynamicChain`メッセージ マップのコレクションを管理し、Windows メッセージを実行時に別のオブジェクトのメッセージ マップに送信できるようにします。

メッセージ マップの動的チェーンのサポートを追加するには、次の操作を行います。

- から`CDynamicChain`クラスを派生させる。 メッセージ マップで、別のオブジェクトの既定のメッセージ マップにチェーンする[CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic)マクロを指定します。

- [CMessageMap](../../atl/reference/cmessagemap-class.md)からチェインするクラスをすべて派生させます。 `CMessageMap`では、オブジェクトがメッセージ マップを他のオブジェクトに公開できます。

- チェーン`CDynamicChain::SetChainEntry`先のオブジェクトとメッセージ マップを識別する呼び出し。

たとえば、クラスが次のように定義されているとします。

[!code-cpp[NVC_ATL_Windowing#88](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]

クライアントは次の`CMyWindow::SetChainEntry`呼び出しを行います。

[!code-cpp[NVC_ATL_Windowing#89](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]

は`chainedObj`チェインされたオブジェクトで、 から`CMessageMap`派生したクラスのインスタンスです。 ここで、`myCtl`または`OnPaint``OnSetFocus`で処理されないメッセージを受信した場合、ウィンドウ プロシージャはメッセージを既定の`chainedObj`メッセージ マップに送信します。

メッセージ マップのチェーンの詳細については、「ATL ウィンドウ クラス」の[「メッセージ マップ](../../atl/message-maps-atl.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="cdynamicchaincallchain"></a><a name="callchain"></a>Cダイナミックチェーン::コールチェーン

Windows メッセージを別のオブジェクトのメッセージ マップに送信します。

```
BOOL CallChain(
    DWORD dwChainID,
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult);
```

### <a name="parameters"></a>パラメーター

*ドウチェーンID*<br/>
[in]チェーン オブジェクトとそのメッセージ マップに関連付けられた一意の識別子。

*hWnd*<br/>
[in]メッセージを受信するウィンドウへのハンドル。

*をクリックします。*<br/>
[in]ウィンドウに送信されるメッセージ。

*wParam*<br/>
[in]メッセージ固有の追加情報。

*lParam*<br/>
[in]メッセージ固有の追加情報。

*lResult*<br/>
[アウト]メッセージ処理の結果。

### <a name="return-value"></a>戻り値

メッセージが完全に処理される場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ウィンドウ プロシージャを呼び`CallChain`出すには、メッセージ マップで[CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic)マクロを指定する必要があります。 例については[、CDynamicChain](../../atl/reference/cdynamicchain-class.md)の概要を参照してください。

`CallChain`*は、dwChainID*値をオブジェクトとそのメッセージ マップに関連付けるために、前の呼び出しを[SetChainEntry](#setchainentry)に対して必要とします。

## <a name="cdynamicchaincdynamicchain"></a><a name="cdynamicchain"></a>Cダイナミックチェーン::Cダイナミックチェーン

コンストラクターです。

```
CDynamicChain();
```

## <a name="cdynamicchaincdynamicchain"></a><a name="dtor"></a>Cダイナミックチェーン::~Cダイナミックチェーン

デストラクターです。

```
~CDynamicChain();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放します。

## <a name="cdynamicchainremovechainentry"></a><a name="removechainentry"></a>Cダイナミックチェーン::除去チェーンエントリ

指定したメッセージ マップをコレクションから削除します。

```
BOOL RemoveChainEntry(DWORD dwChainID);
```

### <a name="parameters"></a>パラメーター

*ドウチェーンID*<br/>
[in]チェーン オブジェクトとそのメッセージ マップに関連付けられた一意の識別子。 この値は、もともと[SetChainEntry](#setchainentry)の呼び出しを通じて定義されていました。

### <a name="return-value"></a>戻り値

メッセージ マップがコレクションから正常に削除された場合は TRUE。 それ以外の場合は FALSE。

## <a name="cdynamicchainsetchainentry"></a><a name="setchainentry"></a>Cダイナミックチェーン::セットチェーンエントリー

指定したメッセージ マップをコレクションに追加します。

```
BOOL SetChainEntry(
    DWORD dwChainID,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);
```

### <a name="parameters"></a>パラメーター

*ドウチェーンID*<br/>
[in]チェーン オブジェクトとそのメッセージ マップに関連付けられた一意の識別子。

*pObject*<br/>
[in]メッセージ マップを宣言するチェーン オブジェクトへのポインター。 このオブジェクトは[、CMessageMap](../../atl/reference/cmessagemap-class.md)から派生する必要があります。

*を使用します。*<br/>
[in]チェーン オブジェクト内のメッセージ マップの識別子。 デフォルト値は 0 で[、BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)で宣言されたデフォルトのメッセージ・マップを識別します。 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)で宣言された代替メッセージ マップを指定`msgMapID`するには、 を渡します。

### <a name="return-value"></a>戻り値

メッセージ マップがコレクションに正常に追加された場合は TRUE。 それ以外の場合は FALSE。

### <a name="remarks"></a>解説

*dwChainID*値がコレクション内に既に存在する場合、関連付けられているオブジェクトとメッセージ マップは、それぞれ*pObject*と*dwMsgMapID*に置き換えられます。 それ以外の場合は、新しいエントリが追加されます。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/cwindowimpl-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
