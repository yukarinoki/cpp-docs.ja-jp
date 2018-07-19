---
title: CMessageMap クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CMessageMap
- ATLWIN/ATL::CMessageMap
- ATLWIN/ATL::CMessageMap::ProcessWindowMessage
dev_langs:
- C++
helpviewer_keywords:
- CMessageMap class
- message maps, ATL
- ATL, message handlers
ms.assetid: 1f97bc16-a8a0-4cf0-b90f-1778813a5c8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 663ee462bf03e76ab15cbac05790c89dcaf07dca
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884855"
---
# <a name="cmessagemap-class"></a>CMessageMap クラス
このクラスは、別のオブジェクトによってアクセスされるオブジェクトのメッセージにマップを使用できます。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class ATL_NO_VTABLE CMessageMap
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMessageMap::ProcessWindowMessage](#processwindowmessage)|メッセージ マップにアクセスする、 `CMessageMap`-クラスを派生します。|  
  
## <a name="remarks"></a>Remarks  
 `CMessageMap` 抽象基本クラスでオブジェクトのメッセージ マップに別のオブジェクトによってアクセスできます。 オブジェクトのメッセージ マップを公開するためはそのクラスから派生する必要があります`CMessageMap`します。  
  
 ATL を使用して`CMessageMap`サポートが含まれている windows および動的メッセージ マップのチェーンにします。 たとえば、すべてを含むクラスを[CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)オブジェクトがから派生する必要があります`CMessageMap`します。 次のコードから取得されますが、 [SUBEDIT](../../visual-cpp-samples.md)サンプル。 を通じて[CComControl](../../atl/reference/ccomcontrol-class.md)、`CAtlEdit`から自動的に派生`CMessageMap`します。  
  
 [!code-cpp[NVC_ATL_Windowing#90](../../atl/codesnippet/cpp/cmessagemap-class_1.h)]  
  
 ため、コンテナー内のウィンドウでは、 `m_EditCtrl`、外側のクラスのメッセージ マップを使用`CAtlEdit`から派生`CMessageMap`します。  
  
 メッセージ マップの詳細については、次を参照してください[メッセージ マップ](../../atl/message-maps-atl.md)"ATL ウィンドウ クラス"の記事。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h  
  
##  <a name="processwindowmessage"></a>  CMessageMap::ProcessWindowMessage  
 識別されるメッセージ マップにアクセスする*dwMsgMapID*で、 `CMessageMap`-クラスを派生します。  
  
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
 *hWnd*  
 [in]メッセージを受信するウィンドウ ハンドル。  
  
 *uMsg*  
 [in]ウィンドウに送信されるメッセージ。  
  
 *wParam*  
 [in]追加のメッセージに固有の情報。  
  
 *lParam*  
 [in]追加のメッセージに固有の情報。  
  
 *lResult*  
 [out]メッセージの処理の結果。  
  
 *dwMsgMapID*  
 [in]メッセージを処理するメッセージ マップの識別子。 宣言された既定のメッセージ マップ[送るに](message-map-macros-atl.md#begin_msg_map)、0 によって識別されます。 宣言された、代替メッセージ マップ[ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)、によって識別される`msgMapID`します。  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合は、メッセージが完全に処理されます。それ以外の場合、FALSE です。  
  
### <a name="remarks"></a>Remarks  
 ウィンドウ プロシージャによって呼び出される、 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)オブジェクトまたはオブジェクトのですが動的に連鎖をメッセージ マップです。  
  
## <a name="see-also"></a>関連項目  
 [CDynamicChain クラス](../../atl/reference/cdynamicchain-class.md)   
 [送るに](message-map-macros-atl.md#begin_msg_map)   
 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)   
 [クラスの概要](../../atl/atl-class-overview.md)
