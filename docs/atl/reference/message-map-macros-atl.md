---
title: メッセージ マップ マクロ (ATL) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlwin/ATL::ALT_MSG_MAP
- atlwin/ATL::BEGIN_MSG_MAP
- atlwin/ATL::CHAIN_MSG_MAP_ALT
- atlwin/ATL::CHAIN_MSG_MAP_ALT_MEMBER
- atlwin/ATL::CHAIN_MSG_MAP
- atlwin/ATL::CHAIN_MSG_MAP_DYNAMIC
- atlwin/ATL::CHAIN_MSG_MAP_MEMBER
- atlwin/ATL::COMMAND_CODE_HANDLER
- atlwin/ATL::COMMAND_HANDLER
- atlwin/ATL::COMMAND_ID_HANDLER
- atlwin/ATL::COMMAND_RANGE_CODE_HANDLER
- atlwin/ATL::COMMAND_RANGE_HANDLER
- atlwin/ATL::DECLARE_EMPTY_MSG_MAP
- atlwin/ATL::DEFAULT_REFLECTION_HANDLER
- atlwin/ATL::END_MSG_MAP
- atlwin/ATL::FORWARD_NOTIFICATIONS
- atlwin/ATL::MESSAGE_HANDLER
- atlwin/ATL::MESSAGE_RANGE_HANDLER
- atlwin/ATL::NOTIFY_CODE_HANDLER
- atlwin/ATL::NOTIFY_HANDLER
- atlwin/ATL::NOTIFY_ID_HANDLER
- atlwin/ATL::NOTIFY_RANGE_CODE_HANDLER
- atlwin/ATL::NOTIFY_RANGE_HANDLER
- atlwin/ATL::REFLECT_NOTIFICATIONS
- atlwin/ATL::REFLECTED_COMMAND_CODE_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_ID_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_RANGE_CODE_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_RANGE_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_CODE_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_ID_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_RANGE_CODE_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_RANGE_HANDLER
dev_langs:
- C++
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 295fb6944c3c18c2e7794ca13ad5ab93b788a776
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883480"
---
# <a name="message-map-macros-atl"></a>メッセージ マップ マクロ (ATL)
これらのマクロは、メッセージ マップとエントリを定義します。  
  
|||  
|-|-|  
|[ALT_MSG_MAP](#alt_msg_map)|代替メッセージ マップの先頭をマークします。|  
|[送るに](#begin_msg_map)|既定のメッセージ マップの先頭をマークします。|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|基底クラスのマップに代替メッセージをチェインします。|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|クラスのデータ メンバーのマップに代替メッセージをチェインします。|  
|[CHAIN_MSG_MAP](#chain_msg_map)|基本クラスの既定のメッセージ マップにチェーンします。|  
|[場合](#chain_msg_map_dynamic)|実行時に別のクラスのメッセージ マップにチェーンします。|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|クラスのデータ メンバーの既定のメッセージ マップにチェーンします。|  
|[COMMAND_CODE_HANDLER](#command_code_handler)|WM_COMMAND メッセージは、通知コードに基づいて、ハンドラー関数にマップします。|  
|[COMMAND_HANDLER](#command_handler)|WM_COMMAND メッセージは、通知コードとメニュー項目、コントロール、またはアクセラレータの識別子に基づいて、ハンドラー関数にマップします。|  
|[COMMAND_ID_HANDLER](#command_id_handler)|WM_COMMAND メッセージは、メニュー項目、コントロール、またはアクセラレータの識別子に基づいて、ハンドラー関数にマップします。|  
|[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)|WM_COMMAND メッセージは、通知コードと連続した範囲のコントロール id に基づいて、ハンドラー関数にマップします。|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|WM_COMMAND メッセージを連続した範囲のコントロール id に基づく、ハンドラー関数にマップします。|  
|[DECLARE_EMPTY_MSG_MAP](#declare_empty_msg_map)|空のメッセージ マップを実装します。|  
|[DEFAULT_REFLECTION_HANDLER](#default_reflection_handler)|それ以外の場合は処理されないリフレクション メッセージ用の既定のハンドラーを提供します。|  
|[も](#end_msg_map)|メッセージ マップの最後をマークします。|  
|[FORWARD_NOTIFICATIONS](#forward_notifications)|親ウィンドウへの通知メッセージを転送します。|  
|[MESSAGE_HANDLER](#message_handler)|Windows メッセージをハンドラー関数にマップします。|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|連続した範囲の Windows メッセージをハンドラー関数にマップします。|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|WM_NOTIFY メッセージは、通知コードに基づいて、ハンドラー関数にマップします。|  
|[NOTIFY_HANDLER](#notify_handler)|WM_NOTIFY メッセージは、通知コードとコントロールの識別子に基づいて、ハンドラー関数にマップします。|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|WM_NOTIFY メッセージは、コントロールの識別子に基づいて、ハンドラー関数にマップします。|  
|[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)|WM_NOTIFY メッセージは、通知コードと連続した範囲のコントロール id に基づいて、ハンドラー関数にマップします。|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|WM_NOTIFY メッセージを連続した範囲のコントロール id に基づく、ハンドラー関数にマップします。|  
|[REFLECT_NOTIFICATIONS](#reflect_notifications)|通知メッセージを送信元ウィンドウに反映されます。|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|リフレクション WM_COMMAND メッセージは、通知コードに基づいて、ハンドラー関数にマップします。|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|リフレクション WM_COMMAND メッセージは、通知コードとメニュー項目、コントロール、またはアクセラレータの識別子に基づいて、ハンドラー関数にマップします。|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|リフレクション WM_COMMAND メッセージは、メニュー項目、コントロール、またはアクセラレータの識別子に基づいて、ハンドラー関数にマップします。|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|リフレクション WM_COMMAND メッセージは、通知コードと連続した範囲のコントロール id に基づいて、ハンドラー関数にマップします。|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|リフレクション WM_COMMAND メッセージを連続した範囲のコントロール id に基づく、ハンドラー関数にマップします。|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|リフレクション WM_NOTIFY メッセージは、通知コードに基づいて、ハンドラー関数にマップします。|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|リフレクション WM_NOTIFY メッセージは、通知コードとコントロールの識別子に基づいて、ハンドラー関数にマップします。|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|コントロールの識別子に基づいて、ハンドラー関数には、リフレクション WM_NOTIFY メッセージをマップします。|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|リフレクション WM_NOTIFY メッセージは、通知コードと連続した範囲のコントロール id に基づいて、ハンドラー関数にマップします。|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|リフレクション WM_NOTIFY メッセージを連続した範囲のコントロール id に基づく、ハンドラー関数にマップします。|  

## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h  

##  <a name="alt_msg_map"></a>  ALT_MSG_MAP  
 代替メッセージ マップの先頭をマークします。  
  
```
ALT_MSG_MAP(msgMapID)
```  
  
### <a name="parameters"></a>パラメーター  
 *msgMapID*  
 [in]メッセージ マップの識別子。  
  
### <a name="remarks"></a>Remarks  
 ATL では、各メッセージ マップの数を識別します。 (送るにマクロで宣言された) 既定のメッセージ マップは、0 によって識別されます。 代替メッセージ マップがで識別される*msgMapID*します。  
  
 メッセージ マップは、ウィンドウに送信されるメッセージの処理に使用されます。 たとえば、 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)コンテナー オブジェクトでメッセージ マップの識別子を指定することができます。 [CContainedWindow::WindowProc](ccontainedwindowt-class.md#windowproc)このメッセージ マップを使用して、適切なハンドラー関数に、または別のメッセージ マップに含まれているウィンドウのメッセージを送信します。 ハンドラー関数を宣言するマクロの一覧は、次を参照してください。[送るに](#begin_msg_map)します。  
  
 常に、メッセージ マップを開始します。 代替の後続のメッセージ マップを宣言することができます。  
  
 [も](#end_msg_map)マクロは、メッセージ マップの終わりをマークします。 1 つのインスタンスは常に注意してください。  
  
 ATL でメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="example"></a>例  
 次の例では、既定のメッセージ マップと、それぞれ 1 つのハンドラー関数を含む 1 つの代替メッセージ マップを示します。  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 次の例では、2 つの代替メッセージ マップが表示されます。 既定のメッセージ マップが空です。  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   

##  <a name="begin_msg_map"></a>  送るに  
 既定のメッセージ マップの先頭をマークします。  
  
```
BEGIN_MSG_MAP(theClass)
```  
  
### <a name="parameters"></a>パラメーター  
 *クラス*  
 [in]メッセージ マップを含むクラスの名前。  
  
### <a name="remarks"></a>Remarks  
 [CWindowImpl::WindowProc](cwindowimpl-class.md#windowproc)既定のメッセージ マップを使用して、ウィンドウに送信されるメッセージを処理します。 メッセージ マップでは、適切なハンドラー関数または別のメッセージ マップのいずれかのメッセージを送信します。  

  
 次のマクロは、メッセージをハンドラー関数にマップします。 この関数を定義する必要があります*クラス*します。  
  
|マクロ|説明|  
|-----------|-----------------|  
|[MESSAGE_HANDLER](#message_handler)|Windows メッセージをハンドラー関数にマップします。|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|連続した範囲の Windows メッセージをハンドラー関数にマップします。|  
|[COMMAND_HANDLER](#command_handler)|WM_COMMAND メッセージは、通知コードとメニュー項目、コントロール、またはアクセラレータの識別子に基づいて、ハンドラー関数にマップします。|  
|[COMMAND_ID_HANDLER](#command_id_handler)|WM_COMMAND メッセージは、メニュー項目、コントロール、またはアクセラレータの識別子に基づいて、ハンドラー関数にマップします。|  
|[COMMAND_CODE_HANDLER](#command_handler)|WM_COMMAND メッセージは、通知コードに基づいて、ハンドラー関数にマップします。|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|連続した範囲の WM_COMMAND メッセージ ハンドラー関数の場合、メニュー項目、コントロール、またはアクセラレータの識別子に基づくにマップします。|  
|[NOTIFY_HANDLER](#notify_handler)|WM_NOTIFY メッセージは、通知コードとコントロールの識別子に基づいて、ハンドラー関数にマップします。|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|WM_NOTIFY メッセージは、コントロールの識別子に基づいて、ハンドラー関数にマップします。|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|WM_NOTIFY メッセージは、通知コードに基づいて、ハンドラー関数にマップします。|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|コントロールの識別子に基づいて、ハンドラー関数に連続する範囲の WM_NOTIFY メッセージにマップします。|  
  
 次のマクロは、別のメッセージ マップにメッセージを送ります。 このプロセスは「チェーン」と呼ばれる  
  
|マクロ|説明|  
|-----------|-----------------|  
|[CHAIN_MSG_MAP](#chain_msg_map)|基本クラスの既定のメッセージ マップにチェーンします。|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|クラスのデータ メンバーの既定のメッセージ マップにチェーンします。|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|基底クラスのマップに代替メッセージをチェインします。|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|クラスのデータ メンバーのマップに代替メッセージをチェインします。|  
|[場合](#chain_msg_map_dynamic)|実行時に別のクラスの既定のメッセージ マップにチェーンします。|  
  
 次のマクロでは、親ウィンドウから「反映」のメッセージを送信します。 たとえば、コントロールを通常通知メッセージを送信用の親ウィンドウに、処理しますが、親ウィンドウは、コントロールにメッセージを反映できます。  
  
|マクロ|説明|  
|-----------|-----------------|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|リフレクション WM_COMMAND メッセージは、通知コードとメニュー項目、コントロール、またはアクセラレータの識別子に基づいて、ハンドラー関数にマップします。|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|リフレクション WM_COMMAND メッセージは、メニュー項目、コントロール、またはアクセラレータの識別子に基づいて、ハンドラー関数にマップします。|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|リフレクション WM_COMMAND メッセージは、通知コードに基づいて、ハンドラー関数にマップします。|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|リフレクション WM_COMMAND メッセージを連続した範囲のコントロール id に基づく、ハンドラー関数にマップします。|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|リフレクション WM_COMMAND メッセージは、通知コードと連続した範囲のコントロール id に基づいて、ハンドラー関数にマップします。|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|リフレクション WM_NOTIFY メッセージは、通知コードとコントロールの識別子に基づいて、ハンドラー関数にマップします。|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|コントロールの識別子に基づいて、ハンドラー関数には、リフレクション WM_NOTIFY メッセージをマップします。|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|リフレクション WM_NOTIFY メッセージは、通知コードに基づいて、ハンドラー関数にマップします。|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|リフレクション WM_NOTIFY メッセージを連続した範囲のコントロール id に基づく、ハンドラー関数にマップします。|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|リフレクション WM_NOTIFY メッセージは、通知コードと連続した範囲のコントロール id に基づいて、ハンドラー関数にマップします。|  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#102](../../atl/codesnippet/cpp/message-map-macros-atl_3.h)]  
  
 ときに、`CMyExtWindow`オブジェクトが WM_PAINT メッセージを受信、メッセージの送信先に`CMyExtWindow::OnPaint`実際の処理。 場合`OnPaint`さらに処理、メッセージは、メッセージが必要とすることを示しますで既定のメッセージ マップに送られる`CMyBaseWindow`します。  
  
 代替メッセージ マップを定義するだけでなく、既定のメッセージ マップ[ALT_MSG_MAP](#alt_msg_map)します。 常に、メッセージ マップを開始します。 代替の後続のメッセージ マップを宣言することができます。 次の例では、既定のメッセージ マップと、それぞれ 1 つのハンドラー関数を含む 1 つの代替メッセージ マップを示します。  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 次の例では、2 つの代替メッセージ マップが表示されます。 既定のメッセージ マップが空です。  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
 [も](#end_msg_map)マクロは、メッセージ マップの終わりをマークします。 1 つのインスタンスは常に注意してください。  
  
 ATL でメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="chain_msg_map_alt"></a>  CHAIN_MSG_MAP_ALT  
 メッセージ マップ エントリを定義します。  
  
```
CHAIN_MSG_MAP_ALT(theChainClass, msgMapID)
```  
  
### <a name="parameters"></a>パラメーター  
 *theChainClass*  
 [in]メッセージ マップを含む基本クラスの名前。  
  
 *msgMapID*  
 [in]メッセージ マップの識別子。  
  
### <a name="remarks"></a>Remarks  
 CHAIN_MSG_MAP_ALT では、基底クラスの代替メッセージ マップへのメッセージを送信します。 この代替メッセージ マップが宣言されている必要があります[ALT_MSG_MAP(msgMapID)](#alt_msg_map)します。 基本クラスの既定のメッセージ マップにメッセージを送信する (で宣言された[送るに](#begin_msg_map))、CHAIN_MSG_MAP を使用します。 例については、次を参照してください。 [CHAIN_MSG_MAP](#chain_msg_map)します。  
  
> [!NOTE]
>  常に、メッセージ マップを開始します。 ALT_MSG_MAP を使って代替メッセージ マップを宣言することができます。 [も](#end_msg_map)マクロは、メッセージ マップの終わりをマークします。 すべてのメッセージ マップには、1 つのインスタンスも必要があります。  
  
 ATL でメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="chain_msg_map_alt_member"></a>  CHAIN_MSG_MAP_ALT_MEMBER  
 メッセージ マップ エントリを定義します。  
  
```
CHAIN_MSG_MAP_ALT_MEMBER(theChainMember, msgMapID)
```  
  
### <a name="parameters"></a>パラメーター  
 *theChainMember*  
 [in]メッセージ マップを含むデータ メンバーの名前。  
  
 *msgMapID*  
 [in]メッセージ マップの識別子。  
  
### <a name="remarks"></a>Remarks  
 CHAIN_MSG_MAP_ALT_MEMBER は、データ メンバー、別のメッセージ マップにメッセージを送信します。 この代替メッセージ マップが宣言されている必要があります[ALT_MSG_MAP(msgMapID)](#alt_msg_map)します。 データ メンバーの既定のメッセージ マップにメッセージを送信する (で宣言された[送るに](#begin_msg_map))、CHAIN_MSG_MAP_MEMBER を使用します。 例については、次を参照してください。 [CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)します。  
  
> [!NOTE]
>  常に、メッセージ マップを開始します。 ALT_MSG_MAP を使って代替メッセージ マップを宣言することができます。 [も](#end_msg_map)マクロは、メッセージ マップの終わりをマークします。 すべてのメッセージ マップには、1 つのインスタンスも必要があります。  
  
 ATL でメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="chain_msg_map"></a>  CHAIN_MSG_MAP  
 メッセージ マップ エントリを定義します。  
  
```
CHAIN_MSG_MAP(theChainClass)
```  
  
### <a name="parameters"></a>パラメーター  
 *theChainClass*  
 [in]メッセージ マップを含む基本クラスの名前。  
  
### <a name="remarks"></a>Remarks  
 CHAIN_MSG_MAP が基本クラスの既定のメッセージ マップにメッセージを送信 (を使用して宣言[送るに](#begin_msg_map))。 基本クラスの別のメッセージ マップにメッセージを送信する (で宣言された[ALT_MSG_MAP](#alt_msg_map)) を使用して、 [CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)します。  
  
> [!NOTE]
>  常に、メッセージ マップを開始します。 ALT_MSG_MAP を使って代替メッセージ マップを宣言することができます。 [も](#end_msg_map)マクロは、メッセージ マップの終わりをマークします。 すべてのメッセージ マップには、1 つのインスタンスも必要があります。  
  
 ATL でメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#107](../../atl/codesnippet/cpp/message-map-macros-atl_4.h)]  
  
 この例を次に示します。  
  
-   ウィンドウ プロシージャを使用している場合`CMyClass`の既定のメッセージ マップおよび`OnPaint`メッセージ、メッセージ送信先ハンドル以外は`CMyBaseClass`の処理のための既定のメッセージ マップです。  
  
-   ウィンドウ プロシージャの最初の代替メッセージ マップが使用されている`CMyClass`、宛てのすべてのメッセージ`CMyBaseClass`の既定のメッセージ マップです。  
  
-   ウィンドウ プロシージャを使用している場合`CMyClass`の 2 つ目の代替メッセージ マップおよび`OnChar`メッセージ、メッセージは指定した代替のメッセージ マップに送られますハンドルしないの`CMyBaseClass`します。 `CMyBaseClass` 必要があります、ALT_MSG_MAP(1) では、このメッセージ マップが宣言されています。  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="chain_msg_map_dynamic"></a>  場合  
 メッセージ マップ エントリを定義します。  
  
```
CHAIN_MSG_MAP_DYNAMIC(dynaChainID)
```  
  
### <a name="parameters"></a>パラメーター  
 *dynaChainID*  
 [in]オブジェクトのメッセージ マップの一意の識別子。  
  
### <a name="remarks"></a>Remarks  
 場合は、別のオブジェクトの既定のメッセージ マップに、実行時に、メッセージを送信します。 オブジェクトとそのメッセージ マップに関連付けられている*dynaChainID*を使用して定義する[CDynamicChain::SetChainEntry](cdynamicchain-class.md#setchainentry)します。 クラスを派生する必要があります`CDynamicChain`場合を使用するためにします。 例については、次を参照してください。、 [CDynamicChain](../../atl/reference/cdynamicchain-class.md)の概要。  

  
> [!NOTE]
>  メッセージ マップは常に開始[送るに](#begin_msg_map)します。 ALT_MSG_MAP を使って代替メッセージ マップを宣言することができます。 [も](#end_msg_map)マクロは、メッセージ マップの終わりをマークします。 すべてのメッセージ マップには、1 つのインスタンスも必要があります。  
  
 ATL でメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="chain_msg_map_member"></a>  CHAIN_MSG_MAP_MEMBER  
 メッセージ マップ エントリを定義します。  
  
```
CHAIN_MSG_MAP_MEMBER(theChainMember)
```  
  
### <a name="parameters"></a>パラメーター  
 *theChainMember*  
 [in]メッセージ マップを含むデータ メンバーの名前。  
  
### <a name="remarks"></a>Remarks  
 CHAIN_MSG_MAP_MEMBER データ メンバーの既定のメッセージ マップにメッセージを送信する (で宣言された[送るに](#begin_msg_map))。 データ メンバーの別のメッセージ マップにメッセージを送信する (で宣言された[ALT_MSG_MAP](#alt_msg_map)) を使用して、 [CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)します。  
  
> [!NOTE]
>  常に、メッセージ マップを開始します。 ALT_MSG_MAP を使って代替メッセージ マップを宣言することができます。 [も](#end_msg_map)マクロは、メッセージ マップの終わりをマークします。 すべてのメッセージ マップには、1 つのインスタンスも必要があります。  
  
 ATL でメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#108](../../atl/codesnippet/cpp/message-map-macros-atl_5.h)]  
  
 この例を次に示します。  
  
-   ウィンドウ プロシージャを使用している場合`CMyClass`の既定のメッセージ マップおよび`OnPaint`メッセージ、メッセージ送信先ハンドル以外は`m_obj`の処理のための既定のメッセージ マップです。  
  
-   ウィンドウ プロシージャの最初の代替メッセージ マップが使用されている`CMyClass`、宛てのすべてのメッセージ`m_obj`の既定のメッセージ マップです。  
  
-   ウィンドウ プロシージャを使用している場合`CMyClass`の 2 つ目の代替メッセージ マップおよび`OnChar`の指定した代替のメッセージ マップに、メッセージが送られますハンドル以外は`m_obj`します。 クラス`CMyContainedClass`ALT_MSG_MAP(1) では、このメッセージ マップが宣言されている必要があります。  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="command_code_handler"></a>  COMMAND_CODE_HANDLER  
 ような[COMMAND_HANDLER](#command_handler)、マップしますが、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)メッセージ ベースの通知のコードに対してのみです。  
  
```
COMMAND_CODE_HANDLER(code, func)
```  
  
### <a name="parameters"></a>パラメーター  
 *コード*  
 [in]通知コード。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="command_handler"></a>  COMMAND_HANDLER  
 メッセージ マップ エントリを定義します。  
  
```
COMMAND_HANDLER(id, code, func)
```    
  
### <a name="parameters"></a>パラメーター  
 *ID*  
 [in]メニュー項目、コントロール、またはアクセラレータの識別子。  
  
 *コード*  
 [in]通知コード。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>Remarks  
 COMMAND_HANDLER マップ、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)通知コードとコントロールの識別子に基づいて、指定されたハンドラー関数にメッセージ。 例えば:  
  
 [!code-cpp[NVC_ATL_Windowing#119](../../atl/codesnippet/cpp/message-map-macros-atl_6.h)]  
  
 COMMAND_HANDLER マクロで指定された任意の関数は、次のように定義する必要があります。  
  
 `LRESULT CommandHandler(WORD wNotifyCode, WORD wID, HWND hWndCtl, BOOL& bHandled);`  
  
 メッセージ マップ セット`bHandled`する前に TRUE を`CommandHandler`が呼び出されます。 場合`CommandHandler`、メッセージを完全に処理しない設定があります`bHandled`パラメーターに、メッセージは、さらに処理を必要があります。  
  
> [!NOTE]
>  メッセージ マップは常に開始[送るに](#begin_msg_map)します。 代替の後続のメッセージ マップを宣言することができます[ALT_MSG_MAP](#alt_msg_map)します。 [も](#end_msg_map)マクロは、メッセージ マップの終わりをマークします。 すべてのメッセージ マップには、1 つのインスタンスも必要があります。  
  
 使用することができます、COMMAND_HANDLER に加えて[MESSAGE_HANDLER](#message_handler)識別子またはコードに関係なく WM_COMMAND メッセージにマップします。 この場合、`MESSAGE_HANDLER(WM_COMMAND, OnHandlerFunction)`すべて WM_COMMAND メッセージには直接`OnHandlerFunction`します。  
  
 ATL でメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="command_id_handler"></a>  COMMAND_ID_HANDLER  
 ような[COMMAND_HANDLER](#command_handler)、マップしますが、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)メッセージがメニュー項目、コントロール、またはアクセラレータの識別子にのみ基づいています。  
  
```
COMMAND_ID_HANDLER(id, func)
```  
  
### <a name="parameters"></a>パラメーター  
 *ID*  
 [in]メニュー項目、コントロール、またはメッセージを送信するアクセラレータの識別子。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="command_range_code_handler"></a>  COMMAND_RANGE_CODE_HANDLER  
 ような[COMMAND_RANGE_HANDLER](#command_range_handler)、マップしますが、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)コントロールの範囲から 1 つのハンドラー関数の特定の通知コードを持つメッセージ。  
  
```
COMMAND_RANGE_CODE_HANDLER(idFirst, idLast, code, func)
```    
  
### <a name="parameters"></a>パラメーター  
 *idFirst*  
 [in]コントロールの識別子の連続する範囲の先頭をマークします。  
  
 *idLast*  
 [in]コントロールの識別子の連続する範囲の末尾をマークします。  
  
 *コード*  
 [in]通知コード。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>Remarks  
 この範囲は、メニュー項目、コントロール、またはメッセージを送信するアクセラレータの識別子に基づきます。  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="command_range_handler"></a>  COMMAND_RANGE_HANDLER  
 ような[COMMAND_HANDLER](#command_handler)、マップしますが、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)コントロールの範囲から 1 つのハンドラー関数へのメッセージ。  
  
```
COMMAND_RANGE_HANDLER( idFirst, idLast, func)
```    
  
### <a name="parameters"></a>パラメーター  
 *idFirst*  
 [in]コントロールの識別子の連続する範囲の先頭をマークします。  
  
 *idLast*  
 [in]コントロールの識別子の連続する範囲の末尾をマークします。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>Remarks  
 この範囲は、メニュー項目、コントロール、またはメッセージを送信するアクセラレータの識別子に基づきます。  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="declare_empty_msg_map"></a>  DECLARE_EMPTY_MSG_MAP  
 空のメッセージ マップを宣言します。  
  
```
DECLARE_EMPTY_MSG_MAP()
```  
  
### <a name="remarks"></a>Remarks  
 DECLARE_EMPTY_MSG_MAP はマクロを呼び出す便利なマクロ[送るに](#begin_msg_map)と[も](#end_msg_map)空のメッセージ マップを作成します。  
  
 [!code-cpp[NVC_ATL_Windowing#122](../../atl/codesnippet/cpp/message-map-macros-atl_7.h)]  
  
##  <a name="default_reflection_handler"></a>  DEFAULT_REFLECTION_HANDLER  
 戻されたメッセージを受信する子ウィンドウ (コントロール) の既定のハンドラーを提供します。ハンドラーで適切に未処理のメッセージを渡す`DefWindowProc`します。  
  
```
DEFAULT_REFLECTION_HANDLER()
```  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="end_msg_map"></a>  も  
 メッセージ マップの最後をマークします。  
  
```
END_MSG_MAP()
```  
  
### <a name="remarks"></a>Remarks  
 常に使用して、[送るに](#begin_msg_map)マクロをメッセージ マップの先頭をマークします。 使用[ALT_MSG_MAP](#alt_msg_map)代替メッセージ マップを宣言します。  
  
 1 つのインスタンスは常に注意してください。  
  
 ATL でメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="example"></a>例  
 次の例では、既定のメッセージ マップと、それぞれ 1 つのハンドラー関数を含む 1 つの代替メッセージ マップを示します。  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 次の例では、2 つの代替メッセージ マップが表示されます。 既定のメッセージ マップが空です。  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="forward_notifications"></a>  FORWARD_NOTIFICATIONS  
 親ウィンドウへの通知メッセージを転送します。  
  
```
FORWARD_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>Remarks  
 このマクロをメッセージ マップの一部として指定します。  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="message_handler"></a>  MESSAGE_HANDLER  
 メッセージ マップ エントリを定義します。  
  
```
MESSAGE_HANDLER( msg, func )
```  
  
### <a name="parameters"></a>パラメーター  
 *メッセージ*  
 [in]Windows メッセージ。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>Remarks  
 MESSAGE_HANDLER は、Windows メッセージを指定されたハンドラー関数にマップします。  
  
 MESSAGE_HANDLER マクロで指定された任意の関数は、次のように定義する必要があります。  
  
 `LRESULT MessageHandler(UINT uMsg, WPARAM wParam, LPARAM lParam, BOOL& bHandled);`  
  
 メッセージ マップ セット`bHandled`する前に TRUE を`MessageHandler`が呼び出されます。 場合`MessageHandler`、メッセージを完全に処理しない設定があります`bHandled`パラメーターに、メッセージは、さらに処理を必要があります。  
  
> [!NOTE]
>  メッセージ マップは常に開始[送るに](#begin_msg_map)します。 代替の後続のメッセージ マップを宣言することができます[ALT_MSG_MAP](#alt_msg_map)します。 [も](#end_msg_map)マクロは、メッセージ マップの終わりをマークします。 すべてのメッセージ マップには、1 つのインスタンスも必要があります。  
  
 MESSAGE_HANDLER、に加えて使用できます[COMMAND_HANDLER](#command_handler)と[NOTIFY_HANDLER](#notify_handler)にマップする[WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)と[WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)メッセージ、それぞれします。  
  
 ATL でメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#129](../../atl/codesnippet/cpp/message-map-macros-atl_8.h)]  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="message_range_handler"></a>  MESSAGE_RANGE_HANDLER  
 ような[MESSAGE_HANDLER](#message_handler)が、範囲の Windows メッセージを 1 つのハンドラー関数にマップします。  
  
```
MESSAGE_RANGE_HANDLER( msgFirst, msgLast, func )
```  
  
### <a name="parameters"></a>パラメーター  
 *msgFirst*  
 [in]メッセージの連続する範囲の先頭をマークします。  
  
 *msgLast*  
 [in]メッセージの連続する範囲の末尾をマークします。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="notify_code_handler"></a>  NOTIFY_CODE_HANDLER  
 ような[NOTIFY_HANDLER](#notify_handler)、マップしますが、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)メッセージ ベースの通知のコードに対してのみです。  
  
```
NOTIFY_CODE_HANDLER(cd, func)
```  
  
### <a name="parameters"></a>パラメーター  
 *cd*  
 [in]通知コード。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="notify_handler"></a>  NOTIFY_HANDLER  
 メッセージ マップ エントリを定義します。  
  
```
NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>パラメーター  
 *ID*  
 [in]メッセージを送信するコントロールの識別子です。  
  
 *cd*  
 [in]通知コード。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>Remarks  
 NOTIFY_HANDLER マップ、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)通知コードとコントロールの識別子に基づいて、指定されたハンドラー関数にメッセージ。  
  
 NOTIFY_HANDLER マクロで指定された任意の関数は、次のように定義する必要があります。  
  
 `LRESULT NotifyHandler(int idCtrl, LPNMHDR pnmh, BOOL& bHandled);`  
  
 メッセージ マップ セット`bHandled`する前に TRUE を`NotifyHandler`が呼び出されます。 場合`NotifyHandler`、メッセージを完全に処理しない設定があります`bHandled`パラメーターに、メッセージは、さらに処理を必要があります。  
  
> [!NOTE]
>  メッセージ マップは常に開始[送るに](#begin_msg_map)します。 代替の後続のメッセージ マップを宣言することができます[ALT_MSG_MAP](#alt_msg_map)します。 [も](#end_msg_map)マクロは、メッセージ マップの終わりをマークします。 すべてのメッセージ マップには、1 つのインスタンスも必要があります。  
  
 使用することができます、NOTIFY_HANDLER に加えて[MESSAGE_HANDLER](#message_handler)識別子またはコードに関係なく WM_NOTIFY メッセージにマップします。 この場合、`MESSAGE_HANDLER(WM_NOTIFY, OnHandlerFunction)`すべて WM_NOTIFY メッセージには直接`OnHandlerFunction`します。  
  
 ATL でメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#130](../../atl/codesnippet/cpp/message-map-macros-atl_9.h)]  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="notify_id_handler"></a>  NOTIFY_ID_HANDLER  
 ような[NOTIFY_HANDLER](#notify_handler)、マップしますが、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)メッセージ ベースのコントロール識別子でのみです。  
  
```
NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>パラメーター  
 *ID*  
 [in]メッセージを送信するコントロールの識別子です。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="notify_range_code_handler"></a>  NOTIFY_RANGE_CODE_HANDLER  
 ような[NOTIFY_RANGE_HANDLER](#notify_range_handler)、マップしますが、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)コントロールの範囲から 1 つのハンドラー関数の特定の通知コードを持つメッセージ。  
  
```
NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```  
  
### <a name="parameters"></a>パラメーター  
 *idFirst*  
 [in]コントロールの識別子の連続する範囲の先頭をマークします。  
  
 *idLast*  
 [in]コントロールの識別子の連続する範囲の末尾をマークします。  
  
 *cd*  
 [in]通知コード。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>Remarks  
 この範囲は、メッセージを送信するコントロールの識別子に基づきます。  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="notify_range_handler"></a>  NOTIFY_RANGE_HANDLER  
 ような[NOTIFY_HANDLER](#notify_handler)、マップしますが、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)コントロールの範囲から 1 つのハンドラー関数へのメッセージ。  
  
```
NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>パラメーター  
 *idFirst*  
 [in]コントロールの識別子の連続する範囲の先頭をマークします。  
  
 *idLast*  
 [in]コントロールの識別子の連続する範囲の末尾をマークします。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>Remarks  
 この範囲は、メッセージを送信するコントロールの識別子に基づきます。  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="reflect_notifications"></a>  REFLECT_NOTIFICATIONS  
 通知メッセージを送信する子ウィンドウ (コントロール) に反映されます。  
  
```
REFLECT_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>Remarks  
 このマクロは、親ウィンドウのメッセージ マップの一部として指定します。  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="reflected_command_code_handler"></a>  REFLECTED_COMMAND_CODE_HANDLER  
 ような[COMMAND_CODE_HANDLER](#command_code_handler)を親ウィンドウから反映されたコマンドにマッピングします。  
  
```
REFLECTED_COMMAND_CODE_HANDLER( code, func )
```  
  
### <a name="parameters"></a>パラメーター  
 *コード*  
 [in]通知コード。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h  
   
##  <a name="reflected_command_handler"></a>  REFLECTED_COMMAND_HANDLER  
 ような[COMMAND_HANDLER](#command_handler)を親ウィンドウから反映されたコマンドにマッピングします。  
  
```
REFLECTED_COMMAND_HANDLER( id, code, func )
```  
  
### <a name="parameters"></a>パラメーター  
 *ID*  
 [in]メニュー項目、コントロール、またはアクセラレータの識別子。  
  
 *コード*  
 [in]通知コード。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h  

##  <a name="reflected_command_id_handler"></a>  REFLECTED_COMMAND_ID_HANDLER  
 ような[COMMAND_ID_HANDLER](#command_id_handler)を親ウィンドウから反映されたコマンドにマッピングします。  
  
```
REFLECTED_COMMAND_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>パラメーター  
 *ID*  
 [in]メニュー項目、コントロール、またはアクセラレータの識別子。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h  

##  <a name="reflected_command_range_code_handler"></a>  REFLECTED_COMMAND_RANGE_CODE_HANDLER  
 ような[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)を親ウィンドウから反映されたコマンドにマッピングします。  
  
```
REFLECTED_COMMAND_RANGE_CODE_HANDLER( idFirst, idLast, code, func )
```  
  
### <a name="parameters"></a>パラメーター  
 *idFirst*  
 [in]コントロールの識別子の連続する範囲の先頭をマークします。  
  
 *idLast*  
 [in]コントロールの識別子の連続する範囲の末尾をマークします。  
  
 *コード*  
 [in]通知コード。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h  

##  <a name="reflected_command_range_handler"></a>  REFLECTED_COMMAND_RANGE_HANDLER  
 ような[COMMAND_RANGE_HANDLER](#command_range_handler)を親ウィンドウから反映されたコマンドにマッピングします。  
  
```
REFLECTED_COMMAND_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>パラメーター  
 *idFirst*  
 [in]コントロールの識別子の連続する範囲の先頭をマークします。  
  
 *idLast*  
 [in]コントロールの識別子の連続する範囲の末尾をマークします。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h  

##  <a name="reflected_notify_code_handler"></a>  REFLECTED_NOTIFY_CODE_HANDLER  
 ような[NOTIFY_CODE_HANDLER](#notify_code_handler)が、親ウィンドウから反映された通知をマップします。  
  
```
REFLECTED_NOTIFY_CODE_HANDLER_EX( cd, func )
```  
  
### <a name="parameters"></a>パラメーター  
 *cd*  
 [in]通知コード。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h  

##  <a name="reflected_notify_handler"></a>  REFLECTED_NOTIFY_HANDLER  
 ような[NOTIFY_HANDLER](#notify_handler)が、親ウィンドウから反映された通知をマップします。  
  
```
REFLECTED_NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>パラメーター  
 *ID*  
 [in]メニュー項目、コントロール、またはアクセラレータの識別子。  
  
 *cd*  
 [in]通知コード。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h  

##  <a name="reflected_notify_id_handler"></a>  REFLECTED_NOTIFY_ID_HANDLER  
 ような[NOTIFY_ID_HANDLER](#notify_id_handler)が、親ウィンドウから反映された通知をマップします。  
  
```
REFLECTED_NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>パラメーター  
 *ID*  
 [in]メニュー項目、コントロール、またはアクセラレータの識別子。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h  

##  <a name="reflected_notify_range_code_handler"></a>  REFLECTED_NOTIFY_RANGE_CODE_HANDLER  
 ような[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)が、親ウィンドウから反映された通知をマップします。  
  
```
REFLECTED_NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```    
  
### <a name="parameters"></a>パラメーター  
 *idFirst*  
 [in]コントロールの識別子の連続する範囲の先頭をマークします。  
  
 *idLast*  
 [in]コントロールの識別子の連続する範囲の末尾をマークします。  
  
 *cd*  
 [in]通知コード。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h   
  
##  <a name="reflected_notify_range_handler"></a>  REFLECTED_NOTIFY_RANGE_HANDLER  
 ような[NOTIFY_RANGE_HANDLER](#notify_range_handler)が、親ウィンドウから反映された通知をマップします。  
  
```
REFLECTED_NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>パラメーター  
 *idFirst*  
 [in]コントロールの識別子の連続する範囲の先頭をマークします。  
  
 *idLast*  
 [in]コントロールの識別子の連続する範囲の末尾をマークします。  
  
 *func*  
 [in]メッセージ ハンドラー関数の名前。  
  
## <a name="see-also"></a>関連項目  
 [[マクロ]](../../atl/reference/atl-macros.md)
