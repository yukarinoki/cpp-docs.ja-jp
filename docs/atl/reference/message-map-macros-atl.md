---
title: メッセージ マップ マクロ (ATL) |Microsoft ドキュメント
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
ms.openlocfilehash: f026e7b8190b311b16e86673b6f2271637442df0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366131"
---
# <a name="message-map-macros-atl"></a>メッセージ マップ マクロ (ATL)
これらのマクロは、メッセージ マップとエントリを定義します。  
  
|||  
|-|-|  
|[ALT_MSG_MAP](#alt_msg_map)|代替のメッセージ マップの先頭をマークします。|  
|[送るに](#begin_msg_map)|既定のメッセージ マップの先頭をマークします。|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|基本クラスのマップに代替のメッセージをチェインします。|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|クラスのデータ メンバーのマップに代替のメッセージをチェインします。|  
|[CHAIN_MSG_MAP](#chain_msg_map)|既定のメッセージのチェーンは、基底クラスにマップします。|  
|[場合](#chain_msg_map_dynamic)|メッセージにチェーンは、実行時に、別のクラスにマップします。|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|クラスのデータ メンバーの既定のメッセージ マップにチェーンされます。|  
|[COMMAND_CODE_HANDLER](#command_code_handler)|マップ、 **WM_COMMAND**メッセージ ハンドラー関数の場合、通知のコードに基づいています。|  
|[COMMAND_HANDLER](#command_handler)|マップ、 **WM_COMMAND**メッセージ通知コードと、メニュー項目、コントロール、またはアクセラレータの識別子に基づいて、ハンドラー関数をします。|  
|[COMMAND_ID_HANDLER](#command_id_handler)|マップ、 **WM_COMMAND**メッセージ ハンドラー関数の場合、メニュー項目、コントロール、またはアクセラレータの識別子に基づくをします。|  
|[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)|マップ、 **WM_COMMAND**メッセージ ハンドラー関数の場合、通知コードとコントロールの識別子の連続した範囲に基づくをします。|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|マップ、 **WM_COMMAND**メッセージ ハンドラー関数の場合、連続した範囲のコントロール id に基づくをします。|  
|[DECLARE_EMPTY_MSG_MAP](#declare_empty_msg_map)|空のメッセージ マップを実装します。|  
|[DEFAULT_REFLECTION_HANDLER](#default_reflection_handler)|それ以外の場合は処理されない返送されたメッセージの既定のハンドラーを提供します。|  
|[も](#end_msg_map)|メッセージ マップの最後をマークします。|  
|[FORWARD_NOTIFICATIONS](#forward_notifications)|親ウィンドウへ通知メッセージを転送します。|  
|[MESSAGE_HANDLER](#message_handler)|Windows メッセージをハンドラー関数にマップされます。|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|連続した範囲の Windows メッセージをハンドラー関数にマップします。|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|マップ、 **WM_NOTIFY**メッセージ ハンドラー関数の場合、通知のコードに基づいています。|  
|[NOTIFY_HANDLER](#notify_handler)|マップ、 **WM_NOTIFY**メッセージ ハンドラー関数の場合、通知コードとコントロール id に基づくをします。|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|マップ、 **WM_NOTIFY**メッセージ ハンドラー関数にコントロール id に基づいています。|  
|[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)|マップ、 **WM_NOTIFY**メッセージ ハンドラー関数の場合、通知コードとコントロールの識別子の連続した範囲に基づくをします。|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|マップ、 **WM_NOTIFY**メッセージ ハンドラー関数の場合、連続した範囲のコントロール id に基づくをします。|  
|[REFLECT_NOTIFICATIONS](#reflect_notifications)|通知メッセージを送信元ウィンドウに反映されます。|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|マップはリフレクション**WM_COMMAND**メッセージ ハンドラー関数の場合、通知コードに基づくをします。|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|マップはリフレクション**WM_COMMAND**メッセージ通知コードと、メニュー項目、コントロール、またはアクセラレータの識別子に基づいて、ハンドラー関数をします。|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|マップはリフレクション**WM_COMMAND**メッセージ ハンドラー関数の場合、メニュー項目、コントロール、またはアクセラレータの識別子に基づくをします。|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|マップはリフレクション**WM_COMMAND**メッセージ ハンドラー関数の場合、通知コードとコントロールの識別子の連続した範囲に基づくをします。|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|マップはリフレクション**WM_COMMAND**メッセージ ハンドラー関数の場合、連続した範囲のコントロール id に基づくをします。|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|マップはリフレクション**WM_NOTIFY**メッセージ ハンドラー関数の場合、通知コードに基づくをします。|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|マップはリフレクション**WM_NOTIFY**メッセージ ハンドラー関数の場合、通知コードとコントロール id に基づくをします。|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|マップはリフレクション**WM_NOTIFY**メッセージ ハンドラー関数の場合、コントロールの識別子に基づくをします。|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|マップはリフレクション**WM_NOTIFY**メッセージ ハンドラー関数の場合、通知コードとコントロールの識別子の連続した範囲に基づくをします。|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|マップはリフレクション**WM_NOTIFY**メッセージ ハンドラー関数の場合、連続した範囲のコントロール id に基づくをします。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  

##  <a name="alt_msg_map"></a>  ALT_MSG_MAP  
 代替のメッセージ マップの先頭をマークします。  
  
```
ALT_MSG_MAP(msgMapID)
```  
  
### <a name="parameters"></a>パラメーター  
 `msgMapID`  
 [in]メッセージ マップの識別子。  
  
### <a name="remarks"></a>コメント  
 ATL は、各メッセージ マップを数値を識別します。 既定のメッセージ マップ (で宣言された、`BEGIN_MSG_MAP`マクロ) は 0 で識別します。 代替のメッセージ マップがによって識別される`msgMapID`です。  
  
 メッセージ マップは、ウィンドウに送信されるメッセージの処理に使用されます。 たとえば、 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)コンテナー オブジェクトでメッセージ マップの識別子を指定することができます。 [CContainedWindow::WindowProc](ccontainedwindowt-class.md#windowproc)このメッセージ マップを使用して、適切なハンドラー関数に、または別のメッセージ マップに含まれているウィンドウのメッセージを送信します。 ハンドラー関数を宣言するマクロの一覧は、次を参照してください。[送るに](#begin_msg_map)です。  
  
 メッセージ マップは常に開始`BEGIN_MSG_MAP`です。 代替の後続のメッセージ マップを宣言することができます。  
  
 [も](#end_msg_map)マクロは、メッセージ マップの末尾をマークします。 1 つのインスタンスは常に注意してください`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 ATL でメッセージ マップを使用する方法の詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)です。  
  
### <a name="example"></a>例  
 次の例では、既定のメッセージ マップと、それぞれ 1 つのハンドラー関数を含む 1 つの代替のメッセージ マップを示します。  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 次の例では、2 つの代替のメッセージ マップを示します。 既定のメッセージ マップが空です。  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   

##  <a name="begin_msg_map"></a>  送るに  
 既定のメッセージ マップの先頭をマークします。  
  
```
BEGIN_MSG_MAP(theClass)
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 [in]メッセージ マップを含むクラスの名前。  
  
### <a name="remarks"></a>コメント  
 [CWindowImpl::WindowProc](cwindowimpl-class.md#windowproc)ウィンドウに送信されたメッセージを処理する既定のメッセージ マップを使用します。 メッセージ マップでは、適切なハンドラー関数または別のメッセージ マップのいずれかのメッセージを出力します。  

  
 次のマクロは、メッセージをハンドラー関数にマップします。 この関数を定義する必要があります`theClass`です。  
  
|マクロ|説明|  
|-----------|-----------------|  
|[MESSAGE_HANDLER](#message_handler)|Windows メッセージをハンドラー関数にマップされます。|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|連続した範囲の Windows メッセージをハンドラー関数にマップします。|  
|[COMMAND_HANDLER](#command_handler)|マップ、 **WM_COMMAND**メッセージ通知コードと、メニュー項目、コントロール、またはアクセラレータの識別子に基づいて、ハンドラー関数をします。|  
|[COMMAND_ID_HANDLER](#command_id_handler)|マップ、 **WM_COMMAND**メッセージ ハンドラー関数の場合、メニュー項目、コントロール、またはアクセラレータの識別子に基づくをします。|  
|[COMMAND_CODE_HANDLER](#command_handler)|マップ、 **WM_COMMAND**メッセージ ハンドラー関数の場合、通知のコードに基づいています。|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|連続した範囲**WM_COMMAND**ハンドラー関数にメッセージがメニュー項目、コントロール、またはアクセラレータの識別子に基づきます。|  
|[NOTIFY_HANDLER](#notify_handler)|マップ、 **WM_NOTIFY**メッセージ ハンドラー関数の場合、通知コードとコントロール id に基づくをします。|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|マップ、 **WM_NOTIFY**メッセージ ハンドラー関数にコントロール id に基づいています。|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|マップ、 **WM_NOTIFY**メッセージ ハンドラー関数の場合、通知のコードに基づいています。|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|連続した範囲の**WM_NOTIFY**コントロール id に基づいて、メッセージ ハンドラー関数をします。|  
  
 次のマクロは、別のメッセージ マップへのメッセージを送ります。 このプロセスは「チェーン」と呼ばれる  
  
|マクロ|説明|  
|-----------|-----------------|  
|[CHAIN_MSG_MAP](#chain_msg_map)|既定のメッセージのチェーンは、基底クラスにマップします。|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|クラスのデータ メンバーの既定のメッセージ マップにチェーンされます。|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|基本クラスのマップに代替のメッセージをチェインします。|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|クラスのデータ メンバーのマップに代替のメッセージをチェインします。|  
|[場合](#chain_msg_map_dynamic)|既定のメッセージのチェーンは、実行時に別のクラスにマップします。|  
  
 次のマクロは、親ウィンドウから「反映」メッセージを送ります。 たとえば、コントロール通常送信します通知メッセージを親ウィンドウに処理しますが、親ウィンドウは、コントロールにメッセージを反映できます。  
  
|マクロ|説明|  
|-----------|-----------------|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|マップはリフレクション**WM_COMMAND**メッセージ通知コードと、メニュー項目、コントロール、またはアクセラレータの識別子に基づいて、ハンドラー関数をします。|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|マップはリフレクション**WM_COMMAND**メッセージ ハンドラー関数の場合、メニュー項目、コントロール、またはアクセラレータの識別子に基づくをします。|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|マップはリフレクション**WM_COMMAND**メッセージ ハンドラー関数の場合、通知コードに基づくをします。|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|マップはリフレクション**WM_COMMAND**メッセージ ハンドラー関数の場合、連続した範囲のコントロール id に基づくをします。|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|マップはリフレクション**WM_COMMAND**メッセージ ハンドラー関数の場合、通知コードとコントロールの識別子の連続した範囲に基づくをします。|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|マップはリフレクション**WM_NOTIFY**メッセージ ハンドラー関数の場合、通知コードとコントロール id に基づくをします。|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|マップはリフレクション**WM_NOTIFY**メッセージ ハンドラー関数の場合、コントロールの識別子に基づくをします。|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|マップはリフレクション**WM_NOTIFY**メッセージ ハンドラー関数の場合、通知コードに基づくをします。|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|マップはリフレクション**WM_NOTIFY**メッセージ ハンドラー関数の場合、連続した範囲のコントロール id に基づくをします。|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|マップはリフレクション**WM_NOTIFY**メッセージ ハンドラー関数の場合、通知コードとコントロールの識別子の連続した範囲に基づくをします。|  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#102](../../atl/codesnippet/cpp/message-map-macros-atl_3.h)]  
  
 ときに、`CMyExtWindow`オブジェクトを受け取る、`WM_PAINT`メッセージ、メッセージ送信先`CMyExtWindow::OnPaint`実際の処理です。 場合`OnPaint`メッセージは、さらに処理、メッセージがする必要があります。 し、既定のメッセージ マップに送られます`CMyBaseWindow`です。  
  
 代替のメッセージ マップを定義するだけでなく、既定のメッセージ マップ[ALT_MSG_MAP](#alt_msg_map)です。 メッセージ マップは常に開始`BEGIN_MSG_MAP`です。 代替の後続のメッセージ マップを宣言することができます。 次の例では、既定のメッセージ マップと、それぞれ 1 つのハンドラー関数を含む 1 つの代替のメッセージ マップを示します。  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 次の例では、2 つの代替のメッセージ マップを示します。 既定のメッセージ マップが空です。  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
 [も](#end_msg_map)マクロは、メッセージ マップの末尾をマークします。 1 つのインスタンスは常に注意してください`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 ATL でメッセージ マップを使用する方法の詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="chain_msg_map_alt"></a>  CHAIN_MSG_MAP_ALT  
 メッセージ マップのエントリを定義します。  
  
```
CHAIN_MSG_MAP_ALT(theChainClass, msgMapID)
```  
  
### <a name="parameters"></a>パラメーター  
 `theChainClass`  
 [in]メッセージ マップを含む基本クラスの名前。  
  
 `msgMapID`  
 [in]メッセージ マップの識別子。  
  
### <a name="remarks"></a>コメント  
 `CHAIN_MSG_MAP_ALT` 基底クラスで、代替のメッセージ マップへのメッセージを出力します。 この代替のメッセージ マップが宣言されている必要があります[ALT_MSG_MAP(msgMapID)](#alt_msg_map)です。 基本クラスの既定のメッセージ マップへのメッセージを送信するため (を使用して宣言[送るに](#begin_msg_map))、使用して`CHAIN_MSG_MAP`です。 例については、次を参照してください。 [CHAIN_MSG_MAP](#chain_msg_map)です。  
  
> [!NOTE]
>  メッセージ マップは常に開始`BEGIN_MSG_MAP`です。 代替の後続のメッセージ マップを宣言することができます`ALT_MSG_MAP`です。 [も](#end_msg_map)マクロは、メッセージ マップの末尾をマークします。 すべてのメッセージ マップが正確に 1 つのインスタンスをいる必要があります`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 ATL でメッセージ マップを使用する方法の詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="chain_msg_map_alt_member"></a>  CHAIN_MSG_MAP_ALT_MEMBER  
 メッセージ マップのエントリを定義します。  
  
```
CHAIN_MSG_MAP_ALT_MEMBER(theChainMember, msgMapID)
```  
  
### <a name="parameters"></a>パラメーター  
 `theChainMember`  
 [in]メッセージ マップを含むデータ メンバーの名前。  
  
 `msgMapID`  
 [in]メッセージ マップの識別子。  
  
### <a name="remarks"></a>コメント  
 `CHAIN_MSG_MAP_ALT_MEMBER` データ メンバーには、代替のメッセージ マップにメッセージを出力します。 この代替のメッセージ マップが宣言されている必要があります[ALT_MSG_MAP(msgMapID)](#alt_msg_map)です。 データ メンバーの既定のメッセージ マップへのメッセージを送信するため (で宣言された[送るに](#begin_msg_map)) を使用して`CHAIN_MSG_MAP_MEMBER`です。 例については、次を参照してください。 [CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)です。  
  
> [!NOTE]
>  メッセージ マップは常に開始`BEGIN_MSG_MAP`です。 代替の後続のメッセージ マップを宣言することができます`ALT_MSG_MAP`です。 [も](#end_msg_map)マクロは、メッセージ マップの末尾をマークします。 すべてのメッセージ マップが正確に 1 つのインスタンスをいる必要があります`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 ATL でメッセージ マップを使用する方法の詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="chain_msg_map"></a>  CHAIN_MSG_MAP  
 メッセージ マップのエントリを定義します。  
  
```
CHAIN_MSG_MAP(theChainClass)
```  
  
### <a name="parameters"></a>パラメーター  
 `theChainClass`  
 [in]メッセージ マップを含む基本クラスの名前。  
  
### <a name="remarks"></a>コメント  
 `CHAIN_MSG_MAP` 基本クラスの既定のメッセージ マップへのメッセージを送ります (を使用して宣言[送るに](#begin_msg_map))。 基本クラスの代替のメッセージ マップにメッセージを送信するため (を使用して宣言[ALT_MSG_MAP](#alt_msg_map))、使用して[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)です。  
  
> [!NOTE]
>  メッセージ マップは常に開始`BEGIN_MSG_MAP`です。 代替の後続のメッセージ マップを宣言することができます`ALT_MSG_MAP`です。 [も](#end_msg_map)マクロは、メッセージ マップの末尾をマークします。 すべてのメッセージ マップが正確に 1 つのインスタンスをいる必要があります`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 ATL でメッセージ マップを使用する方法の詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#107](../../atl/codesnippet/cpp/message-map-macros-atl_4.h)]  
  
 この例は、次のいずれかを示します。  
  
-   ウィンドウ プロシージャが使用されている場合`CMyClass`の既定のメッセージ マップおよび`OnPaint`メッセージ、メッセージ送信先ハンドル以外は`CMyBaseClass`の処理のための既定のメッセージ マップです。  
  
-   ウィンドウ プロシージャが最初の代替のメッセージ マップを使用している`CMyClass`、すべてのメッセージが宛て`CMyBaseClass`の既定のメッセージ マップです。  
  
-   ウィンドウ プロシージャが使用されている場合`CMyClass`の代替の 2 番目のメッセージ マップおよび`OnChar`メッセージ、メッセージは、指定した代替のメッセージ マップに送られますハンドル以外は`CMyBaseClass`します。 `CMyBaseClass` このメッセージ マップが宣言されている必要があります`ALT_MSG_MAP(1)`です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="chain_msg_map_dynamic"></a>  場合  
 メッセージ マップのエントリを定義します。  
  
```
CHAIN_MSG_MAP_DYNAMIC(dynaChainID)
```  
  
### <a name="parameters"></a>パラメーター  
 *dynaChainID*  
 [in]オブジェクトのメッセージ マップの一意の識別子。  
  
### <a name="remarks"></a>コメント  
 `CHAIN_MSG_MAP_DYNAMIC` 別のオブジェクトの既定のメッセージ マップに、実行時に、メッセージを出力します。 オブジェクトとそのメッセージ マップに関連付けられた*dynaChainID*を定義する[CDynamicChain::SetChainEntry](cdynamicchain-class.md#setchainentry)です。 クラスを派生させる必要があります`CDynamicChain`を使用するために`CHAIN_MSG_MAP_DYNAMIC`です。 例については、次を参照してください。、 [CDynamicChain](../../atl/reference/cdynamicchain-class.md)の概要です。  

  
> [!NOTE]
>  メッセージ マップは常に開始[送るに](#begin_msg_map)です。 代替の後続のメッセージ マップを宣言することができます`ALT_MSG_MAP`です。 [も](#end_msg_map)マクロは、メッセージ マップの末尾をマークします。 すべてのメッセージ マップが正確に 1 つのインスタンスをいる必要があります`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 ATL でメッセージ マップを使用する方法の詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="chain_msg_map_member"></a>  CHAIN_MSG_MAP_MEMBER  
 メッセージ マップのエントリを定義します。  
  
```
CHAIN_MSG_MAP_MEMBER(theChainMember)
```  
  
### <a name="parameters"></a>パラメーター  
 `theChainMember`  
 [in]メッセージ マップを含むデータ メンバーの名前。  
  
### <a name="remarks"></a>コメント  
 `CHAIN_MSG_MAP_MEMBER` データ メンバーの既定のメッセージ マップへのメッセージを送ります (を使用して宣言[送るに](#begin_msg_map))。 データ メンバーの代替のメッセージ マップにメッセージを送信するため (で宣言された[ALT_MSG_MAP](#alt_msg_map)) を使用して[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)。  
  
> [!NOTE]
>  メッセージ マップは常に開始`BEGIN_MSG_MAP`です。 代替の後続のメッセージ マップを宣言することができます`ALT_MSG_MAP`です。 [も](#end_msg_map)マクロは、メッセージ マップの末尾をマークします。 すべてのメッセージ マップが正確に 1 つのインスタンスをいる必要があります`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 ATL でメッセージ マップを使用する方法の詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#108](../../atl/codesnippet/cpp/message-map-macros-atl_5.h)]  
  
 この例は、次のいずれかを示します。  
  
-   ウィンドウ プロシージャが使用されている場合`CMyClass`の既定のメッセージ マップおよび`OnPaint`メッセージ、メッセージ送信先ハンドル以外は`m_obj`の処理のための既定のメッセージ マップです。  
  
-   ウィンドウ プロシージャが最初の代替のメッセージ マップを使用している`CMyClass`、すべてのメッセージが宛て`m_obj`の既定のメッセージ マップです。  
  
-   ウィンドウ プロシージャが使用されている場合`CMyClass`の代替の 2 番目のメッセージ マップおよび`OnChar`の指定した代替のメッセージ マップに、メッセージが送られますハンドル以外は`m_obj`します。 クラス`CMyContainedClass`でこのメッセージ マップが宣言されている必要があります`ALT_MSG_MAP(1)`です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="command_code_handler"></a>  COMMAND_CODE_HANDLER  
 ような[COMMAND_HANDLER](#command_handler)、マップしますが、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)メッセージが通知コードにのみ基づいています。  
  
```
COMMAND_CODE_HANDLER(code, func)
```  
  
### <a name="parameters"></a>パラメーター  
 `code`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="command_handler"></a>  COMMAND_HANDLER  
 メッセージ マップのエントリを定義します。  
  
```
COMMAND_HANDLER(id, code, func)
```    
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]メニュー項目、コントロール、またはアクセラレータの識別子。  
  
 `code`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 `COMMAND_HANDLER` マップ、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)メッセージ通知コードとコントロール id に基づいて、指定されたハンドラー関数をします。 例えば:  
  
 [!code-cpp[NVC_ATL_Windowing#119](../../atl/codesnippet/cpp/message-map-macros-atl_6.h)]  
  
 指定された関数、`COMMAND_HANDLER`マクロは次のように定義する必要があります。  
  
 `LRESULT CommandHandler(WORD wNotifyCode, WORD wID, HWND hWndCtl, BOOL& bHandled);`  
  
 メッセージ マップ セット`bHandled`に**TRUE**する前に`CommandHandler`と呼びます。 場合`CommandHandler`、メッセージを完全に処理しませんに設定する必要があります`bHandled`に**FALSE**を示すメッセージがさらに処理を必要があります。  
  
> [!NOTE]
>  メッセージ マップは常に開始[送るに](#begin_msg_map)です。 代替の後続のメッセージ マップを宣言することができます[ALT_MSG_MAP](#alt_msg_map)です。 [も](#end_msg_map)マクロは、メッセージ マップの末尾をマークします。 すべてのメッセージ マップが正確に 1 つのインスタンスをいる必要があります`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 加え`COMMAND_HANDLER`、使用することができます[MESSAGE_HANDLER](#message_handler)にマップする、 **WM_COMMAND**識別子またはコードに関係なくメッセージ。 この場合、`MESSAGE_HANDLER(WM_COMMAND, OnHandlerFunction)`がリダイレクトされますすべて**WM_COMMAND**へのメッセージ`OnHandlerFunction`です。  
  
 ATL でメッセージ マップを使用する方法の詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="command_id_handler"></a>  COMMAND_ID_HANDLER  
 ような[COMMAND_HANDLER](#command_handler)、マップしますが、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)メッセージがメニュー項目、コントロール、またはアクセラレータの識別子にのみ基づいています。  
  
```
COMMAND_ID_HANDLER(id, func)
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]メニュー項目、コントロール、またはメッセージを送信するアクセラレータの識別子。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="command_range_code_handler"></a>  COMMAND_RANGE_CODE_HANDLER  
 ような[COMMAND_RANGE_HANDLER](#command_range_handler)、マップしますが、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)コントロールの範囲から 1 つのハンドラー関数の特定の通知コードとメッセージです。  
  
```
COMMAND_RANGE_CODE_HANDLER(idFirst, idLast, code, func)
```    
  
### <a name="parameters"></a>パラメーター  
 `idFirst`  
 [in]コントロール id の連続した範囲の先頭をマークします。  
  
 `idLast`  
 [in]コントロール id の連続した範囲の末尾をマークします。  
  
 `code`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 この範囲は、メニュー項目、コントロール、またはメッセージを送信するアクセラレータの識別子に基づいています。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="command_range_handler"></a>  COMMAND_RANGE_HANDLER  
 ような[COMMAND_HANDLER](#command_handler)、マップしますが、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)コントロールの範囲からメッセージを 1 つのハンドラー関数をします。  
  
```
COMMAND_RANGE_HANDLER( idFirst, idLast, func)
```    
  
### <a name="parameters"></a>パラメーター  
 `idFirst`  
 [in]コントロール id の連続した範囲の先頭をマークします。  
  
 `idLast`  
 [in]コントロール id の連続した範囲の末尾をマークします。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 この範囲は、メニュー項目、コントロール、またはメッセージを送信するアクセラレータの識別子に基づいています。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="declare_empty_msg_map"></a>  DECLARE_EMPTY_MSG_MAP  
 空のメッセージ マップを宣言します。  
  
```
DECLARE_EMPTY_MSG_MAP()
```  
  
### <a name="remarks"></a>コメント  
 `DECLARE_EMPTY_MSG_MAP` マクロを呼び出す便利なマクロは、[送るに](#begin_msg_map)と[も](#end_msg_map)空のメッセージ マップを作成します。  
  
 [!code-cpp[NVC_ATL_Windowing#122](../../atl/codesnippet/cpp/message-map-macros-atl_7.h)]  
  
##  <a name="default_reflection_handler"></a>  DEFAULT_REFLECTION_HANDLER  
 戻されたメッセージを受信する子ウィンドウ (コントロール) の既定のハンドラーを提供します。ハンドラーで適切に処理不能なメッセージを渡す`DefWindowProc`です。  
  
```
DEFAULT_REFLECTION_HANDLER()
```  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="end_msg_map"></a>  も  
 メッセージ マップの最後をマークします。  
  
```
END_MSG_MAP()
```  
  
### <a name="remarks"></a>コメント  
 常に使用する、[送るに](#begin_msg_map)マクロをメッセージ マップの開始をマークします。 使用して[ALT_MSG_MAP](#alt_msg_map)を代替の後続のメッセージ マップを宣言します。  
  
 1 つのインスタンスは常に注意してください`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 ATL でメッセージ マップを使用する方法の詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)です。  
  
### <a name="example"></a>例  
 次の例では、既定のメッセージ マップと、それぞれ 1 つのハンドラー関数を含む 1 つの代替のメッセージ マップを示します。  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 次の例では、2 つの代替のメッセージ マップを示します。 既定のメッセージ マップが空です。  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="forward_notifications"></a>  FORWARD_NOTIFICATIONS  
 親ウィンドウへ通知メッセージを転送します。  
  
```
FORWARD_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>コメント  
 メッセージ マップの一部としてこのマクロを指定します。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="message_handler"></a>  MESSAGE_HANDLER  
 メッセージ マップのエントリを定義します。  
  
```
MESSAGE_HANDLER( msg, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `msg`  
 [in]Windows メッセージ。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 `MESSAGE_HANDLER` Windows メッセージを指定されたハンドラー関数にマップされます。  
  
 指定された関数、`MESSAGE_HANDLER`マクロは次のように定義する必要があります。  
  
 `LRESULT MessageHandler(UINT uMsg, WPARAM wParam, LPARAM lParam, BOOL& bHandled);`  
  
 メッセージ マップ セット`bHandled`に**TRUE**する前に`MessageHandler`と呼びます。 場合`MessageHandler`、メッセージを完全に処理しませんに設定する必要があります`bHandled`に**FALSE**を示すメッセージがさらに処理を必要があります。  
  
> [!NOTE]
>  メッセージ マップは常に開始[送るに](#begin_msg_map)です。 代替の後続のメッセージ マップを宣言することができます[ALT_MSG_MAP](#alt_msg_map)です。 [も](#end_msg_map)マクロは、メッセージ マップの末尾をマークします。 すべてのメッセージ マップが正確に 1 つのインスタンスをいる必要があります`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 加え`MESSAGE_HANDLER`、使用することができます[COMMAND_HANDLER](#command_handler)と[NOTIFY_HANDLER](#notify_handler)にマップする[WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)と[WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)メッセージ、それぞれします。  
  
 ATL でメッセージ マップを使用する方法の詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#129](../../atl/codesnippet/cpp/message-map-macros-atl_8.h)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="message_range_handler"></a>  MESSAGE_RANGE_HANDLER  
 ような[MESSAGE_HANDLER](#message_handler)が、範囲の Windows メッセージを 1 つのハンドラー関数にマップします。  
  
```
MESSAGE_RANGE_HANDLER( msgFirst, msgLast, func )
```  
  
### <a name="parameters"></a>パラメーター  
 *msgFirst*  
 [in]メッセージの連続した範囲の先頭をマークします。  
  
 *msgLast*  
 [in]メッセージの連続した範囲の末尾をマークします。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="notify_code_handler"></a>  NOTIFY_CODE_HANDLER  
 ような[NOTIFY_HANDLER](#notify_handler)、マップしますが、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)メッセージが通知コードにのみ基づいています。  
  
```
NOTIFY_CODE_HANDLER(cd, func)
```  
  
### <a name="parameters"></a>パラメーター  
 `cd`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="notify_handler"></a>  NOTIFY_HANDLER  
 メッセージ マップのエントリを定義します。  
  
```
NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]メッセージを送信するコントロールの識別子。  
  
 `cd`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 `NOTIFY_HANDLER` マップ、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)メッセージ通知コードとコントロール id に基づいて、指定されたハンドラー関数をします。  
  
 指定された関数、`NOTIFY_HANDLER`マクロは次のように定義する必要があります。  
  
 `LRESULT NotifyHandler(int idCtrl, LPNMHDR pnmh, BOOL& bHandled);`  
  
 メッセージ マップ セット`bHandled`に**TRUE**する前に`NotifyHandler`と呼びます。 場合`NotifyHandler`、メッセージを完全に処理しませんに設定する必要があります`bHandled`に**FALSE**を示すメッセージがさらに処理を必要があります。  
  
> [!NOTE]
>  メッセージ マップは常に開始[送るに](#begin_msg_map)です。 代替の後続のメッセージ マップを宣言することができます[ALT_MSG_MAP](#alt_msg_map)です。 [も](#end_msg_map)マクロは、メッセージ マップの末尾をマークします。 すべてのメッセージ マップが正確に 1 つのインスタンスをいる必要があります`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 加え`NOTIFY_HANDLER`、使用することができます[MESSAGE_HANDLER](#message_handler)にマップする、 **WM_NOTIFY**識別子またはコードに関係なくメッセージ。 この場合、`MESSAGE_HANDLER(WM_NOTIFY, OnHandlerFunction)`がリダイレクトされますすべて**WM_NOTIFY**へのメッセージ`OnHandlerFunction`です。  
  
 ATL でメッセージ マップを使用する方法の詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#130](../../atl/codesnippet/cpp/message-map-macros-atl_9.h)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="notify_id_handler"></a>  NOTIFY_ID_HANDLER  
 ような[NOTIFY_HANDLER](#notify_handler)、マップしますが、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)メッセージがコントロール id にのみ基づいています。  
  
```
NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]メッセージを送信するコントロールの識別子。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="notify_range_code_handler"></a>  NOTIFY_RANGE_CODE_HANDLER  
 ような[NOTIFY_RANGE_HANDLER](#notify_range_handler)、マップしますが、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)コントロールの範囲から 1 つのハンドラー関数の特定の通知コードとメッセージです。  
  
```
NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `idFirst`  
 [in]コントロール id の連続した範囲の先頭をマークします。  
  
 `idLast`  
 [in]コントロール id の連続した範囲の末尾をマークします。  
  
 `cd`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 この範囲は、メッセージを送信するコントロールの識別子に基づいています。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="notify_range_handler"></a>  NOTIFY_RANGE_HANDLER  
 ような[NOTIFY_HANDLER](#notify_handler)、マップしますが、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)コントロールの範囲からメッセージを 1 つのハンドラー関数をします。  
  
```
NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `idFirst`  
 [in]コントロール id の連続した範囲の先頭をマークします。  
  
 `idLast`  
 [in]コントロール id の連続した範囲の末尾をマークします。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 この範囲は、メッセージを送信するコントロールの識別子に基づいています。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="reflect_notifications"></a>  REFLECT_NOTIFICATIONS  
 子ウィンドウ (コントロール) を送信元に通知メッセージが反映されます。  
  
```
REFLECT_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>コメント  
 親ウィンドウのメッセージ マップの一部としてこのマクロを指定します。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="reflected_command_code_handler"></a>  REFLECTED_COMMAND_CODE_HANDLER  
 ような[COMMAND_CODE_HANDLER](#command_code_handler)が、親ウィンドウから反映されたコマンドにマップします。  
  
```
REFLECTED_COMMAND_CODE_HANDLER( code, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `code`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
   
##  <a name="reflected_command_handler"></a>  REFLECTED_COMMAND_HANDLER  
 ような[COMMAND_HANDLER](#command_handler)が、親ウィンドウから反映されたコマンドにマップします。  
  
```
REFLECTED_COMMAND_HANDLER( id, code, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]メニュー項目、コントロール、またはアクセラレータの識別子。  
  
 `code`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  

##  <a name="reflected_command_id_handler"></a>  REFLECTED_COMMAND_ID_HANDLER  
 ような[COMMAND_ID_HANDLER](#command_id_handler)が、親ウィンドウから反映されたコマンドにマップします。  
  
```
REFLECTED_COMMAND_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]メニュー項目、コントロール、またはアクセラレータの識別子。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  

##  <a name="reflected_command_range_code_handler"></a>  REFLECTED_COMMAND_RANGE_CODE_HANDLER  
 ような[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)が、親ウィンドウから反映されたコマンドにマップします。  
  
```
REFLECTED_COMMAND_RANGE_CODE_HANDLER( idFirst, idLast, code, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `idFirst`  
 [in]コントロール id の連続した範囲の先頭をマークします。  
  
 `idLast`  
 [in]コントロール id の連続した範囲の末尾をマークします。  
  
 `code`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  

##  <a name="reflected_command_range_handler"></a>  REFLECTED_COMMAND_RANGE_HANDLER  
 ような[COMMAND_RANGE_HANDLER](#command_range_handler)が、親ウィンドウから反映されたコマンドにマップします。  
  
```
REFLECTED_COMMAND_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `idFirst`  
 [in]コントロール id の連続した範囲の先頭をマークします。  
  
 `idLast`  
 [in]コントロール id の連続した範囲の末尾をマークします。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  

##  <a name="reflected_notify_code_handler"></a>  REFLECTED_NOTIFY_CODE_HANDLER  
 ような[NOTIFY_CODE_HANDLER](#notify_code_handler)が、親ウィンドウから反映された通知をマップします。  
  
```
REFLECTED_NOTIFY_CODE_HANDLER_EX( cd, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `cd`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  

##  <a name="reflected_notify_handler"></a>  REFLECTED_NOTIFY_HANDLER  
 ような[NOTIFY_HANDLER](#notify_handler)が、親ウィンドウから反映された通知をマップします。  
  
```
REFLECTED_NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]メニュー項目、コントロール、またはアクセラレータの識別子。  
  
 `cd`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  

##  <a name="reflected_notify_id_handler"></a>  REFLECTED_NOTIFY_ID_HANDLER  
 ような[NOTIFY_ID_HANDLER](#notify_id_handler)が、親ウィンドウから反映された通知をマップします。  
  
```
REFLECTED_NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]メニュー項目、コントロール、またはアクセラレータの識別子。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  

##  <a name="reflected_notify_range_code_handler"></a>  REFLECTED_NOTIFY_RANGE_CODE_HANDLER  
 ような[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)が、親ウィンドウから反映された通知をマップします。  
  
```
REFLECTED_NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```    
  
### <a name="parameters"></a>パラメーター  
 `idFirst`  
 [in]コントロール id の連続した範囲の先頭をマークします。  
  
 `idLast`  
 [in]コントロール id の連続した範囲の末尾をマークします。  
  
 `cd`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="reflected_notify_range_handler"></a>  REFLECTED_NOTIFY_RANGE_HANDLER  
 ような[NOTIFY_RANGE_HANDLER](#notify_range_handler)が、親ウィンドウから反映された通知をマップします。  
  
```
REFLECTED_NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `idFirst`  
 [in]コントロール id の連続した範囲の先頭をマークします。  
  
 `idLast`  
 [in]コントロール id の連続した範囲の末尾をマークします。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
## <a name="see-also"></a>関連項目  
 [[マクロ]](../../atl/reference/atl-macros.md)
