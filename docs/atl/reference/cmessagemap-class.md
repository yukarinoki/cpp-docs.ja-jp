---
title: クラス
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
ms.openlocfilehash: a822f36d6b6fd49301d8240324e27f0ad9ce52e7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326719"
---
# <a name="cmessagemap-class"></a>クラス

このクラスを使用すると、オブジェクトのメッセージ マップを別のオブジェクトからアクセスできます。

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
|[メッセージマップ::Pロセスウィンドウメッセージ](#processwindowmessage)|派生クラスのメッセージ マップに`CMessageMap`アクセスします。|

## <a name="remarks"></a>解説

`CMessageMap`は、オブジェクトのメッセージ マップに別のオブジェクトからアクセスできるようにする抽象基本クラスです。 オブジェクトがメッセージ マップを公開するには、そのクラスが から`CMessageMap`派生している必要があります。

ATL`CMessageMap`は、包含ウィンドウと動的メッセージ マップ チェーンをサポートするために使用します。 たとえば[、CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)オブジェクトを含むクラスは`CMessageMap`から派生する必要があります。 次のコードは[、SUBEDIT](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit)サンプルから取得します。 を使用して[、](../../atl/reference/ccomcontrol-class.md)クラスは`CAtlEdit`自動的に から`CMessageMap`派生します。

[!code-cpp[NVC_ATL_Windowing#90](../../atl/codesnippet/cpp/cmessagemap-class_1.h)]

含まれているウィンドウは、`m_EditCtrl`含まれているクラスのメッセージ マップを使用するため、`CAtlEdit`派生`CMessageMap`します。

メッセージ マップの詳細については、「ATL ウィンドウ クラス」の[メッセージ マップ](../../atl/message-maps-atl.md)を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="cmessagemapprocesswindowmessage"></a><a name="processwindowmessage"></a>メッセージマップ::Pロセスウィンドウメッセージ

派生クラスの*dwMsgMapID*で識別されるメッセージ`CMessageMap`マップにアクセスします。

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
[in]メッセージを受信するウィンドウへのハンドル。

*をクリックします。*<br/>
[in]ウィンドウに送信されるメッセージ。

*wParam*<br/>
[in]メッセージ固有の追加情報。

*lParam*<br/>
[in]メッセージ固有の追加情報。

*lResult*<br/>
[アウト]メッセージ処理の結果。

*を使用します。*<br/>
[in]メッセージを処理するメッセージ マップの識別子。 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)で宣言された既定のメッセージ マップは 0 で識別されます。 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)で宣言された代替メッセージ・マップは、`msgMapID`によって識別されます。

### <a name="return-value"></a>戻り値

メッセージが完全に処理される場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

[CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)オブジェクトのウィンドウ プロシージャ、またはメッセージ マップに動的にチェーンされるオブジェクトによって呼び出されます。

## <a name="see-also"></a>関連項目

[Cダイナミックチェーンクラス](../../atl/reference/cdynamicchain-class.md)<br/>
[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[ALT_MSG_MAP(メッセージマップID)](message-map-macros-atl.md#alt_msg_map)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
