---
description: '詳細情報: CDynamicChain クラス'
title: CDynamicChain クラス
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
ms.openlocfilehash: 5ada99b519900150afa2143fb1527245797fed98
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141818"
---
# <a name="cdynamicchain-class"></a>CDynamicChain クラス

このクラスは、メッセージマップの動的チェーンをサポートするメソッドを提供します。

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
|[CDynamicChain::CDynamicChain](#cdynamicchain)|コンストラクターです。|
|[CDynamicChain:: ~ CDynamicChain](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDynamicChain:: CallChain](#callchain)|Windows メッセージを別のオブジェクトのメッセージマップに送信します。|
|[CDynamicChain:: Removの入力](#removechainentry)|コレクションからメッセージマップエントリを削除します。|
|[CDynamicChain::SetChainEntry](#setchainentry)|メッセージマップエントリをコレクションに追加するか、既存のエントリを変更します。|

## <a name="remarks"></a>解説

`CDynamicChain` メッセージマップのコレクションを管理します。これにより、Windows メッセージを実行時に別のオブジェクトのメッセージマップに転送できるようになります。

メッセージマップの動的チェーンのサポートを追加するには、次の手順を実行します。

- からクラスを派生させ `CDynamicChain` ます。 メッセージマップで、別のオブジェクトの既定のメッセージマップに連結する [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) マクロを指定します。

- チェーンを作成するすべてのクラスを [CMessageMap](../../atl/reference/cmessagemap-class.md)から派生させます。 `CMessageMap` オブジェクトが他のオブジェクトにメッセージマップを公開できるようにします。

- を呼び出し `CDynamicChain::SetChainEntry` て、チェーンするオブジェクトとメッセージマップを識別します。

たとえば、クラスが次のように定義されているとします。

[!code-cpp[NVC_ATL_Windowing#88](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]

クライアントは次を呼び出し `CMyWindow::SetChainEntry` ます。

[!code-cpp[NVC_ATL_Windowing#89](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]

ここで、 `chainedObj` はチェーンオブジェクトで、はから派生したクラスのインスタンスです `CMessageMap` 。 では、 `myCtl` またはによって処理されないメッセージをが受信すると、ウィンドウプロシージャによって `OnPaint` `OnSetFocus` メッセージが `chainedObj` 既定のメッセージマップに送られます。

メッセージマップチェーンの詳細については、「ATL ウィンドウクラス」の「 [メッセージマップ](../../atl/message-maps-atl.md) 」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** atlwin. h

## <a name="cdynamicchaincallchain"></a><a name="callchain"></a> CDynamicChain:: CallChain

Windows メッセージを別のオブジェクトのメッセージマップに送信します。

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

*dwChainID*<br/>
から連結されたオブジェクトとそのメッセージマップに関連付けられている一意の識別子。

*hWnd*<br/>
からメッセージを受信しているウィンドウへのハンドル。

*uMsg*<br/>
からウィンドウに送信されたメッセージ。

*wParam*<br/>
からメッセージ固有の追加情報。

*lParam*<br/>
からメッセージ固有の追加情報。

*lResult*<br/>
入出力メッセージ処理の結果。

### <a name="return-value"></a>戻り値

メッセージが完全に処理される場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ウィンドウプロシージャを呼び出すには、 `CallChain` メッセージマップで [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) マクロを指定する必要があります。 例については、「 [CDynamicChain](../../atl/reference/cdynamicchain-class.md) の概要」を参照してください。

`CallChain`*dwChainID* 値をオブジェクトとそのメッセージマップに関連付けるために、 [SetChainEntry](#setchainentry)を以前に呼び出す必要があります。

## <a name="cdynamicchaincdynamicchain"></a><a name="cdynamicchain"></a> CDynamicChain::CDynamicChain

コンストラクターです。

```
CDynamicChain();
```

## <a name="cdynamicchaincdynamicchain"></a><a name="dtor"></a> CDynamicChain:: ~ CDynamicChain

デストラクターです。

```
~CDynamicChain();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放します。

## <a name="cdynamicchainremovechainentry"></a><a name="removechainentry"></a> CDynamicChain:: Removの入力

指定したメッセージマップをコレクションから削除します。

```
BOOL RemoveChainEntry(DWORD dwChainID);
```

### <a name="parameters"></a>パラメーター

*dwChainID*<br/>
から連結されたオブジェクトとそのメッセージマップに関連付けられている一意の識別子。 この値は、最初に [SetChainEntry](#setchainentry)の呼び出しを使用して定義します。

### <a name="return-value"></a>戻り値

メッセージマップがコレクションから正常に削除された場合は TRUE。 それ以外の場合は FALSE。

## <a name="cdynamicchainsetchainentry"></a><a name="setchainentry"></a> CDynamicChain::SetChainEntry

指定したメッセージマップをコレクションに追加します。

```
BOOL SetChainEntry(
    DWORD dwChainID,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);
```

### <a name="parameters"></a>パラメーター

*dwChainID*<br/>
から連結されたオブジェクトとそのメッセージマップに関連付けられている一意の識別子。

*pObject*<br/>
からメッセージマップを宣言するチェーンオブジェクトへのポインター。 このオブジェクトは [CMessageMap](../../atl/reference/cmessagemap-class.md)から派生する必要があります。

*dwMsgMapID*<br/>
から連結されたオブジェクト内のメッセージマップの識別子。 既定値は0で、 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)で宣言された既定のメッセージマップを識別します。 [ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)で宣言された代替メッセージマップを指定するには、を渡し `msgMapID` ます。

### <a name="return-value"></a>戻り値

メッセージマップが正常にコレクションに追加された場合は TRUE。 それ以外の場合は FALSE。

### <a name="remarks"></a>解説

*DwChainID* 値がコレクション内に既に存在する場合、その値に関連付けられているオブジェクトとメッセージマップは、それぞれ *PObject* と *dwmsgmapid* に置き換えられます。 それ以外の場合は、新しいエントリが追加されます。

## <a name="see-also"></a>関連項目

[CWindowImpl クラス](../../atl/reference/cwindowimpl-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
