---
title: CDynamicChain クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDynamicChain
- ATLWIN/ATL::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CallChain
- ATLWIN/ATL::CDynamicChain::RemoveChainEntry
- ATLWIN/ATL::CDynamicChain::SetChainEntry
dev_langs:
- C++
helpviewer_keywords:
- message maps, chaining
- chaining message maps
- CDynamicChain class
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08f6d09546d4514950b5b45ffb9494116294d051
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364265"
---
# <a name="cdynamicchain-class"></a>CDynamicChain クラス
このクラスは、メッセージ マップの動的な組み合わせをサポートするメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
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
|[CDynamicChain::CallChain](#callchain)|Windows メッセージを別のオブジェクトのメッセージ マップを送ります。|  
|[CDynamicChain::RemoveChainEntry](#removechainentry)|コレクションからのメッセージ マップ エントリを削除します。|  
|[CDynamicChain::SetChainEntry](#setchainentry)|メッセージ マップ エントリをコレクションに追加または既存のエントリを変更します。|  
  
## <a name="remarks"></a>コメント  
 `CDynamicChain` Windows メッセージを別のオブジェクトのメッセージ マップの実行時に、送信を有効にすると、メッセージ マップのコレクションを管理します。  
  
 メッセージ マップの動的な組み合わせのサポートを追加するには、次の操作を行います。  
  
-   クラスを派生`CDynamicChain`です。 メッセージ マップで指定、[場合](message-map-macros-atl.md#chain_msg_map_dynamic)チェーンが別のオブジェクトの既定のメッセージ マップ マクロです。  
  
-   チェーンするすべてのクラスを派生させる[CMessageMap](../../atl/reference/cmessagemap-class.md)です。 `CMessageMap` 他のオブジェクトへのメッセージ マップを公開するオブジェクトを許可します。  
  
-   呼び出す`CDynamicChain::SetChainEntry`を特定してにチェーンするオブジェクトとどのようなメッセージをマップしています。  
  
 たとえば、クラスを次のように定義します。  
  
 [!code-cpp[NVC_ATL_Windowing#88](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]  
  
 クライアントは、 `CMyWindow::SetChainEntry`:  
  
 [!code-cpp[NVC_ATL_Windowing#89](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]  
  
 ここで`chainedObj`から派生したクラスのインスタンスで、チェーンされたオブジェクトは、`CMessageMap`です。 ここで場合、`myCtl`によって処理されていないメッセージを受信`OnPaint`または`OnSetFocus`、ウィンドウ プロシージャにメッセージを送信する`chainedObj`の既定のメッセージ マップです。  
  
 メッセージ マップの組み合わせの詳細については、次を参照してください[メッセージ マップ](../../atl/message-maps-atl.md)"ATL ウィンドウ クラス"記事の内容。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="callchain"></a>  CDynamicChain::CallChain  
 別のオブジェクトのメッセージ マップに Windows メッセージを送信します。  
  
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
 `dwChainID`  
 [in]チェーンされたオブジェクトとそのメッセージ マップに関連付けられている一意の識別子。  
  
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
  
### <a name="return-value"></a>戻り値  
 **TRUE**メッセージが完全に処理された、それ以外の場合**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 ウィンドウ プロシージャを呼び出す`CallChain`を指定する必要があります、[場合](message-map-macros-atl.md#chain_msg_map_dynamic)メッセージ マップ マクロです。 例については、次を参照してください。、 [CDynamicChain](../../atl/reference/cdynamicchain-class.md)の概要です。  
  
 `CallChain` 以前の呼び出しを必要と[SetChainEntry](#setchainentry)に関連付けるには、`dwChainID`オブジェクトとそのメッセージ マップを持つ値です。  
  
##  <a name="cdynamicchain"></a>  CDynamicChain::CDynamicChain  
 コンストラクターです。  
  
```
CDynamicChain();
```  
  
##  <a name="dtor"></a>  CDynamicChain:: ~ CDynamicChain  
 デストラクターです。  
  
```
~CDynamicChain();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放します。  
  
##  <a name="removechainentry"></a>  CDynamicChain::RemoveChainEntry  
 コレクションから指定されたメッセージ マップを削除します。  
  
```
BOOL RemoveChainEntry(DWORD dwChainID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwChainID`  
 [in]チェーンされたオブジェクトとそのメッセージ マップに関連付けられている一意の識別子。 最初の呼び出しを使用してこの値を定義する[SetChainEntry](#setchainentry)です。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**場合は、メッセージ マップは、コレクションから正常に削除します。 それ以外の場合、 **FALSE**です。  
  
##  <a name="setchainentry"></a>  CDynamicChain::SetChainEntry  
 コレクションに指定されたメッセージ マップを追加します。  
  
```
BOOL SetChainEntry(  
    DWORD dwChainID,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwChainID`  
 [in]チェーンされたオブジェクトとそのメッセージ マップに関連付けられている一意の識別子。  
  
 `pObject`  
 [in]メッセージ マップを宣言する連鎖オブジェクトへのポインター。 このオブジェクトから派生しなければなりません[CMessageMap](../../atl/reference/cmessagemap-class.md)です。  
  
 `dwMsgMapID`  
 [in]チェーンされたオブジェクト内のメッセージ マップの識別子。 既定値は 0 で宣言された既定のメッセージ マップ[送るに](message-map-macros-atl.md#begin_msg_map)です。 宣言された、代替のメッセージ マップを指定する[ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)、渡す`msgMapID`です。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**場合は、コレクションに、メッセージ マップを正常に追加します。 それ以外の場合、 **FALSE**です。  
  
### <a name="remarks"></a>コメント  
 場合、`dwChainID`値は、コレクションに既に存在、その関連付けられたオブジェクトとメッセージ マップに置き換えられます`pObject`と`dwMsgMapID`、それぞれします。 それ以外の場合、新しいエントリが追加されます。  
  
## <a name="see-also"></a>関連項目  
 [CWindowImpl クラス](../../atl/reference/cwindowimpl-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
