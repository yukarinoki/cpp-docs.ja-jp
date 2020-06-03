---
title: メッセージ マップ マクロ (ATL)
ms.date: 11/04/2016
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
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
ms.openlocfilehash: 157812fa6625869c86dd8a27156a2970a3dc8d4a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326228"
---
# <a name="message-map-macros-atl"></a>メッセージ マップ マクロ (ATL)

これらのマクロは、メッセージ・マップとエントリーを定義します。

|||
|-|-|
|[ALT_MSG_MAP](#alt_msg_map)|代替メッセージ マップの先頭を示します。|
|[BEGIN_MSG_MAP](#begin_msg_map)|既定のメッセージ マップの先頭を示します。|
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|基本クラス内の代替メッセージ マップにチェーンします。|
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|クラスのデータ メンバー内の代替メッセージ マップにチェーンします。|
|[CHAIN_MSG_MAP](#chain_msg_map)|基本クラスの既定のメッセージ マップにチェーンします。|
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|実行時に別のクラスのメッセージ マップにチェーンします。|
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|クラスのデータ メンバー内の既定のメッセージ マップにチェーンします。|
|[COMMAND_CODE_HANDLER](#command_code_handler)|通知コードに基づいて、WM_COMMANDメッセージをハンドラー関数にマップします。|
|[COMMAND_HANDLER](#command_handler)|通知コードとメニュー項目、コントロール、またはアクセラレータの識別子に基づいて、WM_COMMAND メッセージをハンドラー関数に割り当てます。|
|[COMMAND_ID_HANDLER](#command_id_handler)|メニュー項目、コントロール、またはアクセラレータの識別子に基づいて、WM_COMMAND メッセージをハンドラー関数に割り当てます。|
|[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)|通知コードと連続した範囲のコントロール識別子に基づいて、WM_COMMAND メッセージをハンドラー関数に割り当てます。|
|[COMMAND_RANGE_HANDLER](#command_range_handler)|連続した範囲のコントロール識別子に基づいて、WM_COMMAND メッセージをハンドラー関数に割り当てます。|
|[DECLARE_EMPTY_MSG_MAP](#declare_empty_msg_map)|空のメッセージ マップを実装します。|
|[DEFAULT_REFLECTION_HANDLER](#default_reflection_handler)|それ以外の場合は処理されない、リフレクション メッセージの既定のハンドラーを提供します。|
|[END_MSG_MAP](#end_msg_map)|メッセージ マップの末尾をマークします。|
|[FORWARD_NOTIFICATIONS](#forward_notifications)|通知メッセージを親ウィンドウに転送します。|
|[MESSAGE_HANDLER](#message_handler)|Windows メッセージをハンドラー関数にマップします。|
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|連続した範囲の Windows メッセージをハンドラー関数にマップします。|
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|通知コードに基づいて、WM_NOTIFYメッセージをハンドラー関数にマップします。|
|[NOTIFY_HANDLER](#notify_handler)|通知コードとコントロール識別子に基づいて、WM_NOTIFY メッセージをハンドラー関数に割り当てます。|
|[NOTIFY_ID_HANDLER](#notify_id_handler)|WM_NOTIFYメッセージをコントロール識別子に基づいてハンドラ関数に割り当てます。|
|[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)|通知コードと連続した範囲のコントロール識別子に基づいて、WM_NOTIFY メッセージをハンドラー関数に割り当てます。|
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|連続した範囲のコントロール識別子に基づいて、WM_NOTIFY メッセージをハンドラー関数に割り当てます。|
|[REFLECT_NOTIFICATIONS](#reflect_notifications)|通知メッセージを送信したウィンドウに反映します。|
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|通知コードに基づいて、メッセージの反映WM_COMMANDをハンドラー関数にマップします。|
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|通知コードとメニュー項目、コントロール、またはアクセラレータの識別子に基づいて、メッセージを反映したWM_COMMANDをハンドラー関数にマップします。|
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|メニュー項目、コントロール、またはアクセラレータの識別子に基づいて、メッセージを反映したWM_COMMANDハンドラー関数に割り当てます。|
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|通知コードと連続した範囲のコントロール識別子に基づいて、メッセージを反映したWM_COMMANDメッセージをハンドラー関数に割り当てます。|
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|コントロール識別子の連続した範囲に基づいて、リフレクションされたWM_COMMANDメッセージをハンドラー関数にマップします。|
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|通知コードに基づいて、WM_NOTIFY メッセージの反映をハンドラー関数にマップします。|
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|通知コードとコントロール識別子に基づいて、WM_NOTIFY メッセージの反映をハンドラー関数にマップします。|
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|コントロール識別子に基づいて、メッセージのリ WM_NOTIFYフレクションをハンドラー関数にマップします。|
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|通知コードと連続した範囲のコントロール識別子に基づいて、メッセージを反映したWM_NOTIFYをハンドラー関数にマップします。|
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|コントロール識別子の連続した範囲に基づいて、メッセージを反映したWM_NOTIFYをハンドラー関数に割り当てます。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="alt_msg_map"></a><a name="alt_msg_map"></a>ALT_MSG_MAP

代替メッセージ マップの先頭を示します。

```
ALT_MSG_MAP(msgMapID)
```

### <a name="parameters"></a>パラメーター

*メッセージの割り当て*<br/>
[in]メッセージ マップ識別子。

### <a name="remarks"></a>解説

ATL は、各メッセージ マップを番号で識別します。 デフォルトのメッセージ・マップ (BEGIN_MSG_MAP マクロで宣言) は 0 で識別されます。 代替メッセージ・マップは*msgMapID*によって識別されます。

メッセージ マップは、ウィンドウに送信されるメッセージを処理するために使用されます。 たとえば[、CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)を使用すると、コンテナ オブジェクト内のメッセージ マップの識別子を指定できます。 [次に、CContainedWindow::WindowProc](ccontainedwindowt-class.md#windowproc)はこのメッセージ マップを使用して、含まれているウィンドウのメッセージを適切なハンドラー関数または別のメッセージ マップに送信します。 ハンドラ関数を宣言するマクロの一覧については[、「BEGIN_MSG_MAP」](#begin_msg_map)を参照してください。

常にBEGIN_MSG_MAPでメッセージ マップを開始します。 その後、後続の代替メッセージ・マップを宣言できます。

[END_MSG_MAP](#end_msg_map)マクロは、メッセージ マップの末尾をマークします。 BEGIN_MSG_MAPとEND_MSG_MAPのインスタンスは常に 1 つだけ存在します。

ATL でのメッセージ マップの使用の詳細については、「[メッセージ マップ](../../atl/message-maps-atl.md)」を参照してください。

### <a name="example"></a>例

次の例は、デフォルトのメッセージ・マップと 1 つの代替メッセージ・マップを示しており、それぞれに 1 つのハンドラー関数が含まれています。

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

次の例は、2 つの代替メッセージ マップを示しています。 デフォルトのメッセージ マップは空です。

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="begin_msg_map"></a><a name="begin_msg_map"></a>BEGIN_MSG_MAP

既定のメッセージ マップの先頭を示します。

```
BEGIN_MSG_MAP(theClass)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
[in]メッセージ マップを含むクラスの名前。

### <a name="remarks"></a>解説

[ウィンドウに送信された](cwindowimpl-class.md#windowproc)メッセージを処理するのに既定のメッセージ マップを使用します。 メッセージ マップは、メッセージを適切なハンドラー関数または別のメッセージ マップに送信します。

次のマクロは、メッセージをハンドラー関数にマップします。 この関数は、 Class で定義*する*必要があります。

|マクロ|説明|
|-----------|-----------------|
|[MESSAGE_HANDLER](#message_handler)|Windows メッセージをハンドラー関数にマップします。|
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|連続した範囲の Windows メッセージをハンドラー関数にマップします。|
|[COMMAND_HANDLER](#command_handler)|通知コードとメニュー項目、コントロール、またはアクセラレータの識別子に基づいて、WM_COMMAND メッセージをハンドラー関数に割り当てます。|
|[COMMAND_ID_HANDLER](#command_id_handler)|メニュー項目、コントロール、またはアクセラレータの識別子に基づいて、WM_COMMAND メッセージをハンドラー関数に割り当てます。|
|[COMMAND_CODE_HANDLER](#command_handler)|通知コードに基づいて、WM_COMMANDメッセージをハンドラー関数にマップします。|
|[COMMAND_RANGE_HANDLER](#command_range_handler)|メニュー項目、コントロール、またはアクセラレータの識別子に基づいて、連続するWM_COMMAND メッセージをハンドラー関数にマップします。|
|[NOTIFY_HANDLER](#notify_handler)|通知コードとコントロール識別子に基づいて、WM_NOTIFY メッセージをハンドラー関数に割り当てます。|
|[NOTIFY_ID_HANDLER](#notify_id_handler)|WM_NOTIFYメッセージをコントロール識別子に基づいてハンドラ関数に割り当てます。|
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|通知コードに基づいて、WM_NOTIFYメッセージをハンドラー関数にマップします。|
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|コントロール識別子に基づいて、連続したWM_NOTIFY メッセージをハンドラー関数に割り当てます。|

次のマクロは、メッセージを別のメッセージ マップに送信します。 このプロセスは"連鎖"と呼ばれます。

|マクロ|説明|
|-----------|-----------------|
|[CHAIN_MSG_MAP](#chain_msg_map)|基本クラスの既定のメッセージ マップにチェーンします。|
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|クラスのデータ メンバー内の既定のメッセージ マップにチェーンします。|
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|基本クラス内の代替メッセージ マップにチェーンします。|
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|クラスのデータ メンバー内の代替メッセージ マップにチェーンします。|
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|実行時に、別のクラスのデフォルトのメッセージ・マップにチェーンします。|

次のマクロは、親ウィンドウから「リフレクション」メッセージを送信します。 たとえば、コントロールは通常、処理のために親ウィンドウに通知メッセージを送信しますが、親ウィンドウはコントロールにメッセージを反映できます。

|マクロ|説明|
|-----------|-----------------|
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|通知コードとメニュー項目、コントロール、またはアクセラレータの識別子に基づいて、メッセージを反映したWM_COMMANDをハンドラー関数にマップします。|
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|メニュー項目、コントロール、またはアクセラレータの識別子に基づいて、メッセージを反映したWM_COMMANDハンドラー関数に割り当てます。|
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|通知コードに基づいて、メッセージの反映WM_COMMANDをハンドラー関数にマップします。|
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|コントロール識別子の連続した範囲に基づいて、リフレクションされたWM_COMMANDメッセージをハンドラー関数にマップします。|
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|通知コードと連続した範囲のコントロール識別子に基づいて、メッセージを反映したWM_COMMANDメッセージをハンドラー関数に割り当てます。|
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|通知コードとコントロール識別子に基づいて、WM_NOTIFY メッセージの反映をハンドラー関数にマップします。|
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|コントロール識別子に基づいて、メッセージのリ WM_NOTIFYフレクションをハンドラー関数にマップします。|
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|通知コードに基づいて、WM_NOTIFY メッセージの反映をハンドラー関数にマップします。|
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|コントロール識別子の連続した範囲に基づいて、メッセージを反映したWM_NOTIFYをハンドラー関数に割り当てます。|
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|通知コードと連続した範囲のコントロール識別子に基づいて、メッセージを反映したWM_NOTIFYをハンドラー関数にマップします。|

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#102](../../atl/codesnippet/cpp/message-map-macros-atl_3.h)]

オブジェクトが`CMyExtWindow`WM_PAINTメッセージを受信すると、実際の処理に対して`CMyExtWindow::OnPaint`メッセージが送信されます。 メッセージ`OnPaint`がさらに処理を必要とすることを示している場合、メッセージは の既定のメッセージ マップ`CMyBaseWindow`に送信されます。

デフォルトのメッセージ マップに加えて[、ALT_MSG_MAP](#alt_msg_map)を使用して代替メッセージ マップを定義できます。 常にBEGIN_MSG_MAPでメッセージ マップを開始します。 その後、後続の代替メッセージ・マップを宣言できます。 次の例は、デフォルトのメッセージ・マップと 1 つの代替メッセージ・マップを示しており、それぞれに 1 つのハンドラー関数が含まれています。

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

次の例は、2 つの代替メッセージ マップを示しています。 デフォルトのメッセージ マップは空です。

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

[END_MSG_MAP](#end_msg_map)マクロは、メッセージ マップの末尾をマークします。 BEGIN_MSG_MAPとEND_MSG_MAPのインスタンスは常に 1 つだけ存在します。

ATL でのメッセージ マップの使用の詳細については、「[メッセージ マップ](../../atl/message-maps-atl.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="chain_msg_map_alt"></a><a name="chain_msg_map_alt"></a>CHAIN_MSG_MAP_ALT

メッセージ マップのエントリを定義します。

```
CHAIN_MSG_MAP_ALT(theChainClass, msgMapID)
```

### <a name="parameters"></a>パラメーター

*ザチェーンクラス*<br/>
[in]メッセージ マップを含む基本クラスの名前。

*メッセージの割り当て*<br/>
[in]メッセージ マップ識別子。

### <a name="remarks"></a>解説

CHAIN_MSG_MAP_ALTは、基本クラス内の代替メッセージ マップにメッセージを送信します。 この代替メッセージ マップを[ALT_MSG_MAP(msgMapID)](#alt_msg_map)で宣言している必要があります。 基本クラスの既定のメッセージ マップ ( BEGIN_MSG_MAP で宣言 ) にメッセージを送信するには[、CHAIN_MSG_MAP](#begin_msg_map)を使用します。 例については、「 [CHAIN_MSG_MAP](#chain_msg_map)」 を参照してください。

> [!NOTE]
> 常にBEGIN_MSG_MAPでメッセージ マップを開始します。 その後、ALT_MSG_MAPを使用して、後続の代替メッセージ・マップを宣言できます。 [END_MSG_MAP](#end_msg_map)マクロは、メッセージ マップの末尾をマークします。 すべてのメッセージ マップには、BEGIN_MSG_MAPとEND_MSG_MAPのインスタンスが 1 つだけ必要です。

ATL でのメッセージ マップの使用の詳細については、「[メッセージ マップ](../../atl/message-maps-atl.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="chain_msg_map_alt_member"></a><a name="chain_msg_map_alt_member"></a>CHAIN_MSG_MAP_ALT_MEMBER

メッセージ マップのエントリを定義します。

```
CHAIN_MSG_MAP_ALT_MEMBER(theChainMember, msgMapID)
```

### <a name="parameters"></a>パラメーター

*ザチェーンメンバー*<br/>
[in]メッセージ マップを含むデータ メンバーの名前。

*メッセージの割り当て*<br/>
[in]メッセージ マップ識別子。

### <a name="remarks"></a>解説

CHAIN_MSG_MAP_ALT_MEMBERは、データ メンバー内の代替メッセージ マップにメッセージを送信します。 この代替メッセージ マップを[ALT_MSG_MAP(msgMapID)](#alt_msg_map)で宣言している必要があります。 メッセージをデータ メンバーの既定のメッセージ マップ (BEGIN_MSG_MAP で宣言) に送信するには[、CHAIN_MSG_MAP_MEMBER](#begin_msg_map)を使用します。 例については、「 [CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)」を参照してください。

> [!NOTE]
> 常にBEGIN_MSG_MAPでメッセージ マップを開始します。 その後、ALT_MSG_MAPを使用して、後続の代替メッセージ・マップを宣言できます。 [END_MSG_MAP](#end_msg_map)マクロは、メッセージ マップの末尾をマークします。 すべてのメッセージ マップには、BEGIN_MSG_MAPとEND_MSG_MAPのインスタンスが 1 つだけ必要です。

ATL でのメッセージ マップの使用の詳細については、「[メッセージ マップ](../../atl/message-maps-atl.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="chain_msg_map"></a><a name="chain_msg_map"></a>CHAIN_MSG_MAP

メッセージ マップのエントリを定義します。

```
CHAIN_MSG_MAP(theChainClass)
```

### <a name="parameters"></a>パラメーター

*ザチェーンクラス*<br/>
[in]メッセージ マップを含む基本クラスの名前。

### <a name="remarks"></a>解説

CHAIN_MSG_MAPは、基本クラスの既定のメッセージ マップ ( [BEGIN_MSG_MAP](#begin_msg_map)で宣言) にメッセージを送信します。 基本クラスの代替メッセージ マップ ( [ALT_MSG_MAP](#alt_msg_map)で宣言 ) にメッセージを送信するには、 [CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)を使用します。

> [!NOTE]
> 常にBEGIN_MSG_MAPでメッセージ マップを開始します。 その後、ALT_MSG_MAPを使用して、後続の代替メッセージ・マップを宣言できます。 [END_MSG_MAP](#end_msg_map)マクロは、メッセージ マップの末尾をマークします。 すべてのメッセージ マップには、BEGIN_MSG_MAPとEND_MSG_MAPのインスタンスが 1 つだけ必要です。

ATL でのメッセージ マップの使用の詳細については、「[メッセージ マップ](../../atl/message-maps-atl.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#107](../../atl/codesnippet/cpp/message-map-macros-atl_4.h)]

この例は、次の例を示しています。

- ウィンドウ プロシージャがデフォルトの`CMyClass`メッセージ マップを使用していて`OnPaint`、メッセージを処理しない場合、メッセージは処理用`CMyBaseClass`の既定のメッセージ マップに送られます。

- ウィンドウ プロシージャが で`CMyClass`最初の代替メッセージ マップを使用している場合、すべての`CMyBaseClass`メッセージは既定のメッセージ マップに送られます。

- ウィンドウ プロシージャが 2`CMyClass`番目の代替メッセージ マップ`OnChar`を使用していて、メッセージを処理しない場合、メッセージは で指定された代替`CMyBaseClass`メッセージ マップに送られます。 `CMyBaseClass`このメッセージ マップを ALT_MSG_MAP(1) で宣言している必要があります。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="chain_msg_map_dynamic"></a><a name="chain_msg_map_dynamic"></a>CHAIN_MSG_MAP_DYNAMIC

メッセージ マップのエントリを定義します。

```
CHAIN_MSG_MAP_DYNAMIC(dynaChainID)
```

### <a name="parameters"></a>パラメーター

*ダイナチェーンID*<br/>
[in]オブジェクトのメッセージ マップの一意の識別子。

### <a name="remarks"></a>解説

CHAIN_MSG_MAP_DYNAMICは、実行時に、別のオブジェクトの既定のメッセージ マップにメッセージを送信します。 オブジェクトとそのメッセージ マップは[、CDynamicChain::SetChainEntry](cdynamicchain-class.md#setchainentry)を通じて定義する*ダイナ*チェーン ID に関連付けられます。 CHAIN_MSG_MAP_DYNAMICを使用するには、クラス`CDynamicChain`を派生させる必要があります。 例については[、CDynamicChain](../../atl/reference/cdynamicchain-class.md)の概要を参照してください。

> [!NOTE]
> 常に[BEGIN_MSG_MAP](#begin_msg_map)でメッセージ マップを開始します。 その後、ALT_MSG_MAPを使用して、後続の代替メッセージ・マップを宣言できます。 [END_MSG_MAP](#end_msg_map)マクロは、メッセージ マップの末尾をマークします。 すべてのメッセージ マップには、BEGIN_MSG_MAPとEND_MSG_MAPのインスタンスが 1 つだけ必要です。

ATL でのメッセージ マップの使用の詳細については、「[メッセージ マップ](../../atl/message-maps-atl.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="chain_msg_map_member"></a><a name="chain_msg_map_member"></a>CHAIN_MSG_MAP_MEMBER

メッセージ マップのエントリを定義します。

```
CHAIN_MSG_MAP_MEMBER(theChainMember)
```

### <a name="parameters"></a>パラメーター

*ザチェーンメンバー*<br/>
[in]メッセージ マップを含むデータ メンバーの名前。

### <a name="remarks"></a>解説

CHAIN_MSG_MAP_MEMBERは、データ メンバーの既定のメッセージ マップ ( [BEGIN_MSG_MAP](#begin_msg_map)で宣言) にメッセージを送信します。 メッセージをデータ メンバの代替メッセージ マップ ( ALT_MSG_MAP で宣言) に送信するには[、](#alt_msg_map) [CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)を使用します。

> [!NOTE]
> 常にBEGIN_MSG_MAPでメッセージ マップを開始します。 その後、ALT_MSG_MAPを使用して、後続の代替メッセージ・マップを宣言できます。 [END_MSG_MAP](#end_msg_map)マクロは、メッセージ マップの末尾をマークします。 すべてのメッセージ マップには、BEGIN_MSG_MAPとEND_MSG_MAPのインスタンスが 1 つだけ必要です。

ATL でのメッセージ マップの使用の詳細については、「[メッセージ マップ](../../atl/message-maps-atl.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#108](../../atl/codesnippet/cpp/message-map-macros-atl_5.h)]

この例は、次の例を示しています。

- ウィンドウ プロシージャがデフォルトの`CMyClass`メッセージ マップを使用していて`OnPaint`、メッセージを処理しない場合、メッセージは処理用`m_obj`の既定のメッセージ マップに送られます。

- ウィンドウ プロシージャが で`CMyClass`最初の代替メッセージ マップを使用している場合、すべての`m_obj`メッセージは既定のメッセージ マップに送られます。

- ウィンドウ プロシージャが 2`CMyClass`番目の代替メッセージ マップ`OnChar`を使用していて、メッセージを処理しない場合、メッセージは 指定された 代替`m_obj`メッセージ マップ に送られます。 クラス`CMyContainedClass`は、このメッセージ マップを ALT_MSG_MAP(1) で宣言している必要があります。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="command_code_handler"></a><a name="command_code_handler"></a>COMMAND_CODE_HANDLER

[COMMAND_HANDLER](#command_handler)と同様ですが、通知コードのみに基づいて[WM_COMMAND](/windows/win32/menurc/wm-command)メッセージをマップします。

```
COMMAND_CODE_HANDLER(code, func)
```

### <a name="parameters"></a>パラメーター

*コード*<br/>
[in]通知コード。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="command_handler"></a><a name="command_handler"></a>COMMAND_HANDLER

メッセージ マップのエントリを定義します。

```
COMMAND_HANDLER(id, code, func)
```

### <a name="parameters"></a>パラメーター

*id*<br/>
[in]メニュー項目、コントロール、またはアクセラレータの識別子。

*コード*<br/>
[in]通知コード。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="remarks"></a>解説

COMMAND_HANDLERは、通知コードとコントロール識別子に基づいて[、WM_COMMAND](/windows/win32/menurc/wm-command)メッセージを指定されたハンドラー関数にマップします。 次に例を示します。

[!code-cpp[NVC_ATL_Windowing#119](../../atl/codesnippet/cpp/message-map-macros-atl_6.h)]

COMMAND_HANDLERマクロで指定された関数は、次のように定義する必要があります。

`LRESULT CommandHandler(WORD wNotifyCode, WORD wID, HWND hWndCtl, BOOL& bHandled);`

メッセージ マップは`bHandled`、前`CommandHandler`に TRUE に設定されます。 メッセージ`CommandHandler`を完全に処理しない場合は、メッセージがさらに`bHandled`処理する必要があることを示すために FALSE に設定する必要があります。

> [!NOTE]
> 常に[BEGIN_MSG_MAP](#begin_msg_map)でメッセージ マップを開始します。 その後[、ALT_MSG_MAP](#alt_msg_map)を使用して、後続の代替メッセージ マップを宣言できます。 [END_MSG_MAP](#end_msg_map)マクロは、メッセージ マップの末尾をマークします。 すべてのメッセージ マップには、BEGIN_MSG_MAPとEND_MSG_MAPのインスタンスが 1 つだけ必要です。

COMMAND_HANDLERに加えて[、MESSAGE_HANDLER](#message_handler)を使用して、識別子やコードに関係なくWM_COMMANDメッセージをマップできます。 この場合、`MESSAGE_HANDLER(WM_COMMAND, OnHandlerFunction)`すべてのWM_COMMANDメッセージが に送信`OnHandlerFunction`されます。

ATL でのメッセージ マップの使用の詳細については、「[メッセージ マップ](../../atl/message-maps-atl.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="command_id_handler"></a><a name="command_id_handler"></a>COMMAND_ID_HANDLER

[COMMAND_HANDLER](#command_handler)と似ていますが、メニュー項目、コントロール、またはアクセラレータの識別子のみに基づいて[WM_COMMAND](/windows/win32/menurc/wm-command)メッセージをマップします。

```
COMMAND_ID_HANDLER(id, func)
```

### <a name="parameters"></a>パラメーター

*id*<br/>
[in]メッセージを送信するメニュー項目、コントロール、またはアクセラレータの識別子。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="command_range_code_handler"></a><a name="command_range_code_handler"></a>COMMAND_RANGE_CODE_HANDLER

[COMMAND_RANGE_HANDLER](#command_range_handler)と似ていますが[、WM_COMMANDコントロールの](/windows/win32/menurc/wm-command)範囲から特定の通知コードを持つメッセージを単一のハンドラー関数にマップします。

```
COMMAND_RANGE_CODE_HANDLER(idFirst, idLast, code, func)
```

### <a name="parameters"></a>パラメーター

*id最初*<br/>
[in]連続するコントロール識別子の先頭を示します。

*idLast*<br/>
[in]連続する範囲のコントロール識別子の末尾を示します。

*コード*<br/>
[in]通知コード。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="remarks"></a>解説

この範囲は、メッセージを送信するメニュー項目、コントロール、またはアクセラレータの識別子に基づいています。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="command_range_handler"></a><a name="command_range_handler"></a>COMMAND_RANGE_HANDLER

[COMMAND_HANDLER](#command_handler)と似ていますが[、WM_COMMANDのメッセージ](/windows/win32/menurc/wm-command)をコントロールの範囲から単一のハンドラー関数にマップします。

```
COMMAND_RANGE_HANDLER( idFirst, idLast, func)
```

### <a name="parameters"></a>パラメーター

*id最初*<br/>
[in]連続するコントロール識別子の先頭を示します。

*idLast*<br/>
[in]連続する範囲のコントロール識別子の末尾を示します。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="remarks"></a>解説

この範囲は、メッセージを送信するメニュー項目、コントロール、またはアクセラレータの識別子に基づいています。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="declare_empty_msg_map"></a><a name="declare_empty_msg_map"></a>DECLARE_EMPTY_MSG_MAP

空のメッセージ マップを宣言します。

```
DECLARE_EMPTY_MSG_MAP()
```

### <a name="remarks"></a>解説

DECLARE_EMPTY_MSG_MAPは、マクロ[を呼](#begin_msg_map)び[出して空](#end_msg_map)のメッセージ マップを作成END_MSG_MAPBEGIN_MSG_MAP便利なマクロです。

[!code-cpp[NVC_ATL_Windowing#122](../../atl/codesnippet/cpp/message-map-macros-atl_7.h)]

## <a name="default_reflection_handler"></a><a name="default_reflection_handler"></a>DEFAULT_REFLECTION_HANDLER

リフレクションされたメッセージを受け取る子ウィンドウ (コントロール) の既定のハンドラーを提供します。ハンドラは、ハンドルされないメッセージを適切に`DefWindowProc`に に渡します。

```
DEFAULT_REFLECTION_HANDLER()
```

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="end_msg_map"></a><a name="end_msg_map"></a>END_MSG_MAP

メッセージ マップの末尾をマークします。

```
END_MSG_MAP()
```

### <a name="remarks"></a>解説

メッセージ マップの先頭をマークするには、常に[BEGIN_MSG_MAP](#begin_msg_map)マクロを使用します。 [ALT_MSG_MAP](#alt_msg_map)を使用して、後続の代替メッセージ・マップを宣言します。

BEGIN_MSG_MAPとEND_MSG_MAPのインスタンスは常に 1 つだけ存在します。

ATL でのメッセージ マップの使用の詳細については、「[メッセージ マップ](../../atl/message-maps-atl.md)」を参照してください。

### <a name="example"></a>例

次の例は、デフォルトのメッセージ・マップと 1 つの代替メッセージ・マップを示しており、それぞれに 1 つのハンドラー関数が含まれています。

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

次の例は、2 つの代替メッセージ マップを示しています。 デフォルトのメッセージ マップは空です。

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="forward_notifications"></a><a name="forward_notifications"></a>FORWARD_NOTIFICATIONS

通知メッセージを親ウィンドウに転送します。

```
FORWARD_NOTIFICATIONS()
```

### <a name="remarks"></a>解説

このマクロをメッセージ・マップの一部として指定します。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="message_handler"></a><a name="message_handler"></a>MESSAGE_HANDLER

メッセージ マップのエントリを定義します。

```
MESSAGE_HANDLER( msg, func )
```

### <a name="parameters"></a>パラメーター

*Msg*<br/>
[in]ウィンドウズ メッセージ。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="remarks"></a>解説

MESSAGE_HANDLER、Windows メッセージを指定されたハンドラー関数にマップします。

MESSAGE_HANDLER マクロで指定された関数は、次のように定義する必要があります。

`LRESULT MessageHandler(UINT uMsg, WPARAM wParam, LPARAM lParam, BOOL& bHandled);`

メッセージ マップは`bHandled`、前`MessageHandler`に TRUE に設定されます。 メッセージ`MessageHandler`を完全に処理しない場合は、メッセージがさらに`bHandled`処理する必要があることを示すために FALSE に設定する必要があります。

> [!NOTE]
> 常に[BEGIN_MSG_MAP](#begin_msg_map)でメッセージ マップを開始します。 その後[、ALT_MSG_MAP](#alt_msg_map)を使用して、後続の代替メッセージ マップを宣言できます。 [END_MSG_MAP](#end_msg_map)マクロは、メッセージ マップの末尾をマークします。 すべてのメッセージ マップには、BEGIN_MSG_MAPとEND_MSG_MAPのインスタンスが 1 つだけ必要です。

MESSAGE_HANDLERに加えて[、COMMAND_HANDLER](#command_handler)と[NOTIFY_HANDLER](#notify_handler)を使用して[、WM_COMMAND](/windows/win32/menurc/wm-command)と[WM_NOTIFY](/windows/win32/controls/wm-notify)メッセージをそれぞれマップできます。

ATL でのメッセージ マップの使用の詳細については、「[メッセージ マップ](../../atl/message-maps-atl.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#129](../../atl/codesnippet/cpp/message-map-macros-atl_8.h)]

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="message_range_handler"></a><a name="message_range_handler"></a>MESSAGE_RANGE_HANDLER

[MESSAGE_HANDLER](#message_handler)と似ていますが、Windows メッセージの範囲を単一のハンドラー関数にマップします。

```
MESSAGE_RANGE_HANDLER( msgFirst, msgLast, func )
```

### <a name="parameters"></a>パラメーター

*最初のメッセージ*<br/>
[in]連続するメッセージ範囲の先頭を示します。

*メッセージラスト*<br/>
[in]連続するメッセージ範囲の終わりを示します。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="notify_code_handler"></a><a name="notify_code_handler"></a>NOTIFY_CODE_HANDLER

[NOTIFY_HANDLER](#notify_handler)と似ていますが、通知コードのみに基づいて[WM_NOTIFY](/windows/win32/controls/wm-notify)メッセージをマップします。

```
NOTIFY_CODE_HANDLER(cd, func)
```

### <a name="parameters"></a>パラメーター

*Cd*<br/>
[in]通知コード。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="notify_handler"></a><a name="notify_handler"></a>NOTIFY_HANDLER

メッセージ マップのエントリを定義します。

```
NOTIFY_HANDLER( id, cd, func )
```

### <a name="parameters"></a>パラメーター

*id*<br/>
[in]メッセージを送信するコントロールの識別子。

*Cd*<br/>
[in]通知コード。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="remarks"></a>解説

NOTIFY_HANDLER、通知コードとコントロール識別子に基づいて[、WM_NOTIFY](/windows/win32/controls/wm-notify)メッセージを指定されたハンドラー関数にマップします。

NOTIFY_HANDLER マクロで指定された関数は、次のように定義する必要があります。

`LRESULT NotifyHandler(int idCtrl, LPNMHDR pnmh, BOOL& bHandled);`

メッセージ マップは`bHandled`、前`NotifyHandler`に TRUE に設定されます。 メッセージ`NotifyHandler`を完全に処理しない場合は、メッセージがさらに`bHandled`処理する必要があることを示すために FALSE に設定する必要があります。

> [!NOTE]
> 常に[BEGIN_MSG_MAP](#begin_msg_map)でメッセージ マップを開始します。 その後[、ALT_MSG_MAP](#alt_msg_map)を使用して、後続の代替メッセージ マップを宣言できます。 [END_MSG_MAP](#end_msg_map)マクロは、メッセージ マップの末尾をマークします。 すべてのメッセージ マップには、BEGIN_MSG_MAPとEND_MSG_MAPのインスタンスが 1 つだけ必要です。

NOTIFY_HANDLERに加えて、MESSAGE_HANDLER[を使用](#message_handler)して、識別子やコードに関係なくWM_NOTIFY メッセージをマップできます。 この場合、`MESSAGE_HANDLER(WM_NOTIFY, OnHandlerFunction)`すべてのWM_NOTIFYメッセージを`OnHandlerFunction`に送信します。

ATL でのメッセージ マップの使用の詳細については、「[メッセージ マップ](../../atl/message-maps-atl.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#130](../../atl/codesnippet/cpp/message-map-macros-atl_9.h)]

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="notify_id_handler"></a><a name="notify_id_handler"></a>NOTIFY_ID_HANDLER

[NOTIFY_HANDLER](#notify_handler)と似ていますが、WM_NOTIFY[メッセージは](/windows/win32/controls/wm-notify)コントロール識別子のみに基づいてマップされます。

```
NOTIFY_ID_HANDLER( id, func )
```

### <a name="parameters"></a>パラメーター

*id*<br/>
[in]メッセージを送信するコントロールの識別子。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="notify_range_code_handler"></a><a name="notify_range_code_handler"></a>NOTIFY_RANGE_CODE_HANDLER

[NOTIFY_RANGE_HANDLER](#notify_range_handler)と似ていますが[、WM_NOTIFYコントロール](/windows/win32/controls/wm-notify)の範囲から特定の通知コードを持つメッセージを単一のハンドラー関数にマップします。

```
NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```

### <a name="parameters"></a>パラメーター

*id最初*<br/>
[in]連続するコントロール識別子の先頭を示します。

*idLast*<br/>
[in]連続する範囲のコントロール識別子の末尾を示します。

*Cd*<br/>
[in]通知コード。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="remarks"></a>解説

この範囲は、メッセージを送信するコントロールの識別子に基づいています。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="notify_range_handler"></a><a name="notify_range_handler"></a>NOTIFY_RANGE_HANDLER

[NOTIFY_HANDLER](#notify_handler)と似ていますが[、WM_NOTIFY](/windows/win32/controls/wm-notify)の範囲のコントロールから単一のハンドラー関数にメッセージをマップします。

```
NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>パラメーター

*id最初*<br/>
[in]連続するコントロール識別子の先頭を示します。

*idLast*<br/>
[in]連続する範囲のコントロール識別子の末尾を示します。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="remarks"></a>解説

この範囲は、メッセージを送信するコントロールの識別子に基づいています。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="reflect_notifications"></a><a name="reflect_notifications"></a>REFLECT_NOTIFICATIONS

通知メッセージを、送信した子ウィンドウ (コントロール) に反映します。

```
REFLECT_NOTIFICATIONS()
```

### <a name="remarks"></a>解説

このマクロを親ウィンドウのメッセージ マップの一部として指定します。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="reflected_command_code_handler"></a><a name="reflected_command_code_handler"></a>REFLECTED_COMMAND_CODE_HANDLER

[COMMAND_CODE_HANDLER](#command_code_handler)と似ていますが、親ウィンドウからリフレクションされたコマンドをマップします。

```
REFLECTED_COMMAND_CODE_HANDLER( code, func )
```

### <a name="parameters"></a>パラメーター

*コード*<br/>
[in]通知コード。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="reflected_command_handler"></a><a name="reflected_command_handler"></a>REFLECTED_COMMAND_HANDLER

[COMMAND_HANDLER](#command_handler)と似ていますが、親ウィンドウからリフレクションされたコマンドをマップします。

```
REFLECTED_COMMAND_HANDLER( id, code, func )
```

### <a name="parameters"></a>パラメーター

*id*<br/>
[in]メニュー項目、コントロール、またはアクセラレータの識別子。

*コード*<br/>
[in]通知コード。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="reflected_command_id_handler"></a><a name="reflected_command_id_handler"></a>REFLECTED_COMMAND_ID_HANDLER

[COMMAND_ID_HANDLER](#command_id_handler)と同様ですが、親ウィンドウから反映されたコマンドをマップします。

```
REFLECTED_COMMAND_ID_HANDLER( id, func )
```

### <a name="parameters"></a>パラメーター

*id*<br/>
[in]メニュー項目、コントロール、またはアクセラレータの識別子。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="reflected_command_range_code_handler"></a><a name="reflected_command_range_code_handler"></a>REFLECTED_COMMAND_RANGE_CODE_HANDLER

[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)と似ていますが、親ウィンドウからリフレクションされたコマンドをマップします。

```
REFLECTED_COMMAND_RANGE_CODE_HANDLER( idFirst, idLast, code, func )
```

### <a name="parameters"></a>パラメーター

*id最初*<br/>
[in]連続するコントロール識別子の先頭を示します。

*idLast*<br/>
[in]連続する範囲のコントロール識別子の末尾を示します。

*コード*<br/>
[in]通知コード。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="reflected_command_range_handler"></a><a name="reflected_command_range_handler"></a>REFLECTED_COMMAND_RANGE_HANDLER

[COMMAND_RANGE_HANDLER](#command_range_handler)と同様ですが、親ウィンドウから反映されたコマンドをマップします。

```
REFLECTED_COMMAND_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>パラメーター

*id最初*<br/>
[in]連続するコントロール識別子の先頭を示します。

*idLast*<br/>
[in]連続する範囲のコントロール識別子の末尾を示します。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="reflected_notify_code_handler"></a><a name="reflected_notify_code_handler"></a>REFLECTED_NOTIFY_CODE_HANDLER

[NOTIFY_CODE_HANDLER](#notify_code_handler)と似ていますが、親ウィンドウから反映された通知をマップします。

```
REFLECTED_NOTIFY_CODE_HANDLER_EX( cd, func )
```

### <a name="parameters"></a>パラメーター

*Cd*<br/>
[in]通知コード。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="reflected_notify_handler"></a><a name="reflected_notify_handler"></a>REFLECTED_NOTIFY_HANDLER

[NOTIFY_HANDLER](#notify_handler)と同様ですが、親ウィンドウから反映された通知をマップします。

```
REFLECTED_NOTIFY_HANDLER( id, cd, func )
```

### <a name="parameters"></a>パラメーター

*id*<br/>
[in]メニュー項目、コントロール、またはアクセラレータの識別子。

*Cd*<br/>
[in]通知コード。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="reflected_notify_id_handler"></a><a name="reflected_notify_id_handler"></a>REFLECTED_NOTIFY_ID_HANDLER

[NOTIFY_ID_HANDLER](#notify_id_handler)と同様ですが、親ウィンドウから反映された通知をマップします。

```
REFLECTED_NOTIFY_ID_HANDLER( id, func )
```

### <a name="parameters"></a>パラメーター

*id*<br/>
[in]メニュー項目、コントロール、またはアクセラレータの識別子。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="reflected_notify_range_code_handler"></a><a name="reflected_notify_range_code_handler"></a>REFLECTED_NOTIFY_RANGE_CODE_HANDLER

[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)と同様ですが、親ウィンドウから反映された通知をマップします。

```
REFLECTED_NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```

### <a name="parameters"></a>パラメーター

*id最初*<br/>
[in]連続するコントロール識別子の先頭を示します。

*idLast*<br/>
[in]連続する範囲のコントロール識別子の末尾を示します。

*Cd*<br/>
[in]通知コード。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="reflected_notify_range_handler"></a><a name="reflected_notify_range_handler"></a>REFLECTED_NOTIFY_RANGE_HANDLER

[NOTIFY_RANGE_HANDLER](#notify_range_handler)と似ていますが、親ウィンドウから反映された通知をマップします。

```
REFLECTED_NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>パラメーター

*id最初*<br/>
[in]連続するコントロール識別子の先頭を示します。

*idLast*<br/>
[in]連続する範囲のコントロール識別子の末尾を示します。

*Func*<br/>
[in]メッセージ ハンドラー関数の名前。

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)
