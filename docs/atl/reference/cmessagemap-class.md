---
description: '詳細情報: CMessageMap クラス'
title: CMessageMap クラス
ms.date: 11/04/2016
f1_keywords:
- CMessageMap
- ATLWIN/ATL::CMessageMap
- ATLWIN/ATL::CMessageMap::ProcessWindowMessage
helpviewer_keywords:
- CMessageMap class
- message maps, ATL
- ATL, message handlers
ms.assetid: 1f97bc16-a8a0-4cf0-b90f-1778813a5c8e
ms.openlocfilehash: 90ecdc101071b84362d328558ff2e74cb9bbeb6b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141441"
---
# <a name="cmessagemap-class"></a>CMessageMap クラス

このクラスを使用すると、オブジェクトのメッセージマップが別のオブジェクトによってアクセスできるようになります。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class ATL_NO_VTABLE CMessageMap
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMessageMap::P Roて Windowmessage](#processwindowmessage)|派生クラスのメッセージマップにアクセス `CMessageMap` します。|

## <a name="remarks"></a>解説

`CMessageMap` は、オブジェクトのメッセージマップに別のオブジェクトがアクセスできるようにする抽象基本クラスです。 オブジェクトがメッセージマップを公開するためには、そのクラスがから派生している必要があり `CMessageMap` ます。

ATL では `CMessageMap` 、を使用して、包含ウィンドウと動的メッセージマップチェーンをサポートします。 たとえば、 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) オブジェクトを含むクラスは、から派生する必要があり `CMessageMap` ます。 次のコードは、 [SUBEDIT](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit) サンプルから抜粋したものです。 [CComControl](../../atl/reference/ccomcontrol-class.md)を通じて、 `CAtlEdit` クラスはから自動的に派生 `CMessageMap` します。

[!code-cpp[NVC_ATL_Windowing#90](../../atl/codesnippet/cpp/cmessagemap-class_1.h)]

格納されているウィンドウは、を `m_EditCtrl` 含んでいるクラスのメッセージマップを使用するため、 `CAtlEdit` から派生 `CMessageMap` します。

メッセージマップの詳細については、「ATL ウィンドウクラス」の「 [メッセージマップ](../../atl/message-maps-atl.md) 」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** atlwin. h

## <a name="cmessagemapprocesswindowmessage"></a><a name="processwindowmessage"></a> CMessageMap::P Roて Windowmessage

は、派生クラスで *Dwmsgmapid* によって識別されるメッセージマップにアクセスし `CMessageMap` ます。

```
virtual BOOL ProcessWindowMessage(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult,
    DWORD dwMsgMapID) = 0;
```

### <a name="parameters"></a>パラメーター

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

*dwMsgMapID*<br/>
からメッセージを処理するメッセージマップの識別子。 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)で宣言された既定のメッセージマップは、0によって識別されます。 [ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)で宣言された代替メッセージマップは、によって識別され `msgMapID` ます。

### <a name="return-value"></a>戻り値

メッセージが完全に処理される場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

[CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)オブジェクトまたはメッセージマップに動的にチェーンするオブジェクトのウィンドウプロシージャによって呼び出されます。

## <a name="see-also"></a>関連項目

[CDynamicChain クラス](../../atl/reference/cdynamicchain-class.md)<br/>
[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
