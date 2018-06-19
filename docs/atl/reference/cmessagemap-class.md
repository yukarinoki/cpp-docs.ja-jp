---
title: CMessageMap クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 187d9964da0929516207a67b0e3a769649fc375b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359020"
---
# <a name="cmessagemap-class"></a>CMessageMap クラス
このクラスは、オブジェクトのメッセージが別のオブジェクトによってアクセスするマップを使用します。  
  
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
  
## <a name="remarks"></a>コメント  
 `CMessageMap` オブジェクトのメッセージを許可する抽象基本クラスのマップに別のオブジェクトによってアクセスできます。 メッセージ マップを公開するオブジェクトの順序ではそのクラスから派生しなければなりません`CMessageMap`です。  
  
 ATL を使用して`CMessageMap`サポートが含まれている windows および動的メッセージ マップのチェインにします。 たとえば、そのクラスを含む、 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)オブジェクトから派生しなければなりません`CMessageMap`です。 次のコードがから取得した、 [SUBEDIT](../../visual-cpp-samples.md)サンプルです。 を通じて[CComControl](../../atl/reference/ccomcontrol-class.md)、`CAtlEdit`から自動的に派生`CMessageMap`です。  
  
 [!code-cpp[NVC_ATL_Windowing#90](../../atl/codesnippet/cpp/cmessagemap-class_1.h)]  
  
 含まれているウィンドウ`m_EditCtrl`、外側のクラスのメッセージ マップを使用`CAtlEdit`から派生した`CMessageMap`です。  
  
 メッセージ マップの詳細については、次を参照してください[メッセージ マップ](../../atl/message-maps-atl.md)"ATL ウィンドウ クラス"記事の内容。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="processwindowmessage"></a>  CMessageMap::ProcessWindowMessage  
 によって識別されるメッセージ マップにアクセスする`dwMsgMapID`で、 `CMessageMap`-クラスを派生します。  
  
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
 `hWnd`  
 [in]メッセージの受信ウィンドウへのハンドル。  
  
 `uMsg`  
 [in]ウィンドウに送信するメッセージ。  
  
 `wParam`  
 [in]その他のメッセージに固有の情報です。  
  
 `lParam`  
 [in]その他のメッセージに固有の情報です。  
  
 `lResult`  
 [out]メッセージの処理の結果。  
  
 `dwMsgMapID`  
 [in]メッセージを処理するメッセージ マップの識別子。 宣言された既定のメッセージ マップ[送るに](message-map-macros-atl.md#begin_msg_map)0 で識別されます。 宣言された、代替のメッセージ マップ[ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)、によって識別される`msgMapID`です。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**メッセージが完全に処理される、それ以外の場合**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 ウィンドウ プロシージャによって呼び出される、 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)オブジェクトまたはオブジェクトのことを動的にチェーン メッセージ マップにします。  
  
## <a name="see-also"></a>関連項目  
 [CDynamicChain クラス](../../atl/reference/cdynamicchain-class.md)   
 [送るに](message-map-macros-atl.md#begin_msg_map)   
 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)   
 [クラスの概要](../../atl/atl-class-overview.md)
