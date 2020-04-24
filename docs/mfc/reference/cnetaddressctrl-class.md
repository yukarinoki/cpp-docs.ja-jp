---
title: CNetAddressCtrl クラス
ms.date: 11/19/2018
f1_keywords:
- CNetAddressCtrl
- AFXCMN/CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::Create
- AFXCMN/CNetAddressCtrl::CreateEx
- AFXCMN/CNetAddressCtrl::DisplayErrorTip
- AFXCMN/CNetAddressCtrl::GetAddress
- AFXCMN/CNetAddressCtrl::GetAllowType
- AFXCMN/CNetAddressCtrl::SetAllowType
helpviewer_keywords:
- CNetAddressCtrl [MFC], CNetAddressCtrl
- CNetAddressCtrl [MFC], Create
- CNetAddressCtrl [MFC], CreateEx
- CNetAddressCtrl [MFC], DisplayErrorTip
- CNetAddressCtrl [MFC], GetAddress
- CNetAddressCtrl [MFC], GetAllowType
- CNetAddressCtrl [MFC], SetAllowType
ms.assetid: cb4c6aca-3f49-4b52-b76c-65f57096155b
ms.openlocfilehash: c6f391966ef6657363e8f23e5666a57a935b08e1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752775"
---
# <a name="cnetaddressctrl-class"></a>CNetAddressCtrl クラス

`CNetAddressCtrl` クラスは、ネットワーク アドレス コントロールを表します。このコントロールを使用すると、IPv4 アドレス、IPv6 アドレス、および名前付き DNS アドレスの形式を入力して検証できます。

## <a name="syntax"></a>構文

```
class CNetAddressCtrl : public CEdit
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CNet アドレスCtrl::CネットアドレスCtrl](#cnetaddressctrl)|`CNetAddressCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[作成](#create)|指定したスタイルを使用してネットワーク アドレス コントロールを作成し、`CNetAddressCtrl`現在のオブジェクトにアタッチします。|
|[CNet アドレスCtrl::作成します。](#createex)|指定した拡張スタイルを使用してネットワーク アドレス コントロールを作成し、`CNetAddressCtrl`現在のオブジェクトにアタッチします。|
|[エラーヒントを:D](#displayerrortip)|現在のネットワーク アドレス コントロールでサポートされていないネットワーク アドレスをユーザーが入力すると、エラー バルーン ヒントが表示されます。|
|[をクリックします。](#getaddress)|現在のネットワーク アドレス コントロールに関連付けられているネットワーク アドレスの検証済みおよび解析済みの表現を取得します。|
|[次の値を取得します。](#getallowtype)|現在のネットワーク アドレス コントロールがサポートできるネットワーク アドレスの種類を取得します。|
|[次の値を指定します。](#setallowtype)|現在のネットワーク アドレス コントロールがサポートできるネットワーク アドレスの種類を設定します。|

## <a name="remarks"></a>解説

ネットワーク アドレス コントロールは、ユーザーが入力したアドレスの形式が正しいことを確認します。 コントロールは実際にはネットワーク アドレスに接続しません。 メソッドは、メソッドが解析および検証できる 1 つ以上の種類のアドレスを指定[CNetAddressCtrl::GetAddress](#getaddress)[します](#setallowtype)。 アドレスは、サーバー、ネットワーク、ホスト、またはブロードキャスト メッセージの宛先の IPv4、IPv6、または名前付きアドレスの形式で指定できます。 アドレスの形式が正しくない場合は[、CNetAddressCtrl::DisplayErrorTip](#displayerrortip)メソッドを使用して、ネットワーク アドレス コントロールのテキスト ボックスをグラフィカルにポイントし、定義済みのエラー メッセージを表示する情報ヒント メッセージ ボックスを表示できます。

クラス`CNetAddressCtrl`は[CEdit](../../mfc/reference/cedit-class.md)クラスから派生します。 したがって、ネットワーク アドレス コントロールは、すべての Windows 編集コントロール メッセージにアクセスできます。

次の図は、ネットワーク アドレス コントロールを含むダイアログを示しています。 ネットワーク アドレス コントロールのテキスト ボックス (1) に無効なネットワーク アドレスが含まれています。 ネットワーク アドレスが無効な場合は、情報ヒント メッセージ (2) が表示されます。

![ネットワーク アドレス コントロールおよび infotip を含むダイアログ。](../../mfc/reference/media/cnetaddctrl.png "ネットワーク アドレス コントロールおよび infotip を含むダイアログ。")

## <a name="example"></a>例

次のコード例は、ネットワーク アドレスを検証するダイアログの一部です。 3 つのラジオ ボタンのイベント ハンドラーは、ネットワーク アドレスが 3 つのアドレスの種類のいずれかであることを指定します。 ユーザーは、ネットワーク コントロールのテキスト ボックスにアドレスを入力し、ボタンを押してアドレスを検証します。 アドレスが有効な場合は、成功メッセージが表示されます。それ以外の場合は、定義済みの情報ヒントのエラー メッセージが表示されます。

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]

## <a name="example"></a>例

ダイアログ ヘッダー ファイルの次のコード例では[、CNetAddressCtrl::GetAddress](#getaddress)メソッドで必要な[NC_ADDRESS](/windows/win32/api/shellapi/ns-shellapi-nc_address)と[NET_ADDRESS_INFO](/windows/win32/shell/hkey-type)変数を定義します。

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

`CNetAddressCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

このクラスは、Windows Vista 以降でサポートされています。

このクラスの追加要件については、「 [Windows Vista コモン コントロールのビルド要件](../../mfc/build-requirements-for-windows-vista-common-controls.md)」を参照してください。

## <a name="cnetaddressctrlcnetaddressctrl"></a><a name="cnetaddressctrl"></a>CNet アドレスCtrl::CネットアドレスCtrl

`CNetAddressCtrl` オブジェクトを構築します。

```
CNetAddressCtrl();
```

### <a name="remarks"></a>解説

ネットワーク コントロールを作成し、オブジェクトにアタッチするには[、CNetAddressCtrl::作成](#create)または[CNetAddressCtrl::CreateEx](#createex)メソッドを使用します`CNetAddressCtrl`。

## <a name="cnetaddressctrlcreate"></a><a name="create"></a>作成

指定したスタイルを使用してネットワーク アドレス コントロールを作成し、`CNetAddressCtrl`現在のオブジェクトにアタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Dwstyle*|[in]コントロールに適用するスタイルのビットごとの組み合わせ。 詳細については、「[スタイルの編集](../../mfc/reference/styles-used-by-mfc.md#edit-styles)」を参照してください。|
|*Rect*|[in]コントロールの位置とサイズを格納する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体への参照。|
|*pParentWnd*|[in]コントロールの親ウィンドウである[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトへの非 null ポインター。|
|*nID*|[in]コントロールの ID。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

## <a name="cnetaddressctrlcreateex"></a><a name="createex"></a>CNet アドレスCtrl::作成します。

指定した拡張スタイルを使用してネットワーク アドレス コントロールを作成し、`CNetAddressCtrl`現在のオブジェクトにアタッチします。

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*ドウェエクススタイル*|[in]コントロールに適用する拡張スタイルのビットごとの組み合わせ (OR)。 詳細については、関数の*dwExStyle*パラメーターを参照[してください](/windows/win32/api/winuser/nf-winuser-createwindowexw)。|
|*Dwstyle*|[in]コントロールに適用するスタイルのビットごとの組み合わせ (OR)。 詳細については、「[スタイルの編集](../../mfc/reference/styles-used-by-mfc.md#edit-styles)」を参照してください。|
|*Rect*|[in]コントロールの位置とサイズを格納する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体への参照。|
|*pParentWnd*|[in]コントロールの親ウィンドウである[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトへの非 null ポインター。|
|*nID*|[in]コントロールの ID。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

## <a name="cnetaddressctrldisplayerrortip"></a><a name="displayerrortip"></a>エラーヒントを:D

現在のネットワーク アドレス コントロールに関連付けられているバルーン ヒントにエラー メッセージを表示します。

```
HRESULT DisplayErrorTip();
```

### <a name="return-value"></a>戻り値

このメソッド`S_OK`が成功した場合は値を返します。それ以外の場合はエラー コード。

### <a name="remarks"></a>解説

現在のネットワーク アドレス コントロールでサポートできるアドレスの種類を指定するには[、CNetAddressCtrl::SetAllowType](#setallowtype)メソッドを使用します。 ユーザーが入力したネットワーク アドレスを検証および解析するには[、CNetAddressCtrl::GetAddress](#getaddress)メソッドを使用します。 メソッドが失敗した場合にエラー メッセージ情報ヒントを表示するには[、CNetAddressCtrl::DisplayErrorTip](#getaddress)メソッドを使用します。 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip)

このメッセージは、Windows SDK で説明されている[NetAddr_DisplayErrorTip](/windows/win32/api/shellapi/nf-shellapi-netaddr_displayerrortip)マクロを呼び出します。 そのマクロはメッセージ`NCM_DISPLAYERRORTIP`を送信します。

## <a name="cnetaddressctrlgetaddress"></a><a name="getaddress"></a>をクリックします。

現在のネットワーク アドレス コントロールに関連付けられているネットワーク アドレスの検証済みおよび解析済みの表現を取得します。

```
HRESULT GetAddress(PNC_ADDRESS pAddress) const;
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[イン、アウト][NC_ADDRESS](/windows/win32/api/shellapi/ns-shellapi-nc_address)構造体へのポインター。  GetAddress メソッドを呼び出す前に、この構造体の*pAddrInfo*メンバーを[NET_ADDRESS_INFO](/windows/win32/shell/hkey-type)構造体のアドレスに設定します。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は、値がS_OK。それ以外の場合は、COM エラー コード。 考えられるエラー コードの詳細については[、NetAddr_GetAddress](/windows/win32/api/shellapi/nf-shellapi-netaddr_getaddress)マクロの戻り値セクションを参照してください。

### <a name="remarks"></a>解説

このメソッドが成功した場合[、NET_ADDRESS_INFO](/windows/win32/shell/hkey-type)構造体には、ネットワーク アドレスに関する追加情報が含まれます。

現在のネットワーク アドレス コントロールがサポートできるアドレスの種類を指定するには[、CNetAddressCtrl::SetAllowType](#setallowtype)メソッドを使用します。 ユーザーが入力したネットワーク アドレスを検証および解析するには[、CNetAddressCtrl::GetAddress](#getaddress)メソッドを使用します。 メソッドが失敗した場合にエラー メッセージ情報ヒントを表示するには[、CNetAddressCtrl::DisplayErrorTip](#getaddress)メソッドを使用します。 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip)

このメソッドは、Windows SDK で説明されている[NetAddr_GetAddress](/windows/win32/api/shellapi/nf-shellapi-netaddr_getaddress)マクロを呼び出します。 そのマクロはNCM_GETADDRESSメッセージを送信します。

## <a name="cnetaddressctrlgetallowtype"></a><a name="getallowtype"></a>次の値を取得します。

現在のネットワーク アドレス コントロールがサポートできるネットワーク アドレスの種類を取得します。

```
DWORD GetAllowType() const;
```

### <a name="return-value"></a>戻り値

ネットワーク アドレス コントロールがサポートできるアドレスの種類を指定するフラグのビットごとの組み合わせ (OR)。 詳細については、「 [NET_STRING](/windows/win32/shell/net-string)」を参照してください。

### <a name="remarks"></a>解説

このメッセージは、Windows SDK で説明されている[NetAddr_GetAllowType](/windows/win32/api/shellapi/nf-shellapi-netaddr_getallowtype)マクロを呼び出します。 そのマクロはNCM_GETALLOWTYPEメッセージを送信します。

## <a name="cnetaddressctrlsetallowtype"></a><a name="setallowtype"></a>次の値を指定します。

現在のネットワーク アドレス コントロールがサポートできるネットワーク アドレスの種類を設定します。

```
HRESULT SetAllowType(DWORD dwAddrMask);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*ドワッドマスク*|[in]ネットワーク アドレス コントロールがサポートできるアドレスの種類を指定するフラグのビットごとの組み合わせ (OR)。 詳細については、「 [NET_STRING](/windows/win32/shell/net-string)」を参照してください。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合はS_OK。それ以外の場合は、COM エラー コード。

### <a name="remarks"></a>解説

現在のネットワーク アドレス コントロールでサポートできるアドレスの種類を指定するには[、CNetAddressCtrl::SetAllowType](#setallowtype)メソッドを使用します。 ユーザーが入力したネットワーク アドレスを検証および解析するには[、CNetAddressCtrl::GetAddress](#getaddress)メソッドを使用します。 メソッドが失敗した場合にエラー メッセージ情報ヒントを表示するには[、CNetAddressCtrl::DisplayErrorTip](#getaddress)メソッドを使用します。 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip)

このメッセージは、Windows SDK で説明されている[NetAddr_SetAllowType](/windows/win32/api/shellapi/nf-shellapi-netaddr_setallowtype)マクロを呼び出します。 そのマクロはNCM_SETALLOWTYPEメッセージを送信します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/cnetaddressctrl-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)
