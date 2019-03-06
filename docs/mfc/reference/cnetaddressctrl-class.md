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
ms.openlocfilehash: ec4d7aa6f2a1061e632b81a27a0233cf5fdd1c63
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423561"
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
|[CNetAddressCtrl::CNetAddressCtrl](#cnetaddressctrl)|`CNetAddressCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CNetAddressCtrl::Create](#create)|指定したスタイルを使用してネットワーク アドレス コントロールを作成し、現在に結び付けます`CNetAddressCtrl`オブジェクト。|
|[CNetAddressCtrl::CreateEx](#createex)|指定された拡張スタイルを使用してネットワーク アドレス コントロールを作成し、現在に結び付けます`CNetAddressCtrl`オブジェクト。|
|[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)|ユーザーが現在のネットワーク アドレス コントロールでサポートされていないネットワーク アドレスを入力、エラーのバルーン ヒントが表示されます。|
|[CNetAddressCtrl::GetAddress](#getaddress)|現在のネットワーク アドレス コントロールに関連付けられているネットワーク アドレスの検証、解析された表現を取得します。|
|[CNetAddressCtrl::GetAllowType](#getallowtype)|現在のネットワーク アドレス コントロールをサポートするネットワーク アドレスの種類を取得します。|
|[CNetAddressCtrl::SetAllowType](#setallowtype)|現在のネットワーク アドレス コントロールをサポートするネットワーク アドレスの種類を設定します。|

## <a name="remarks"></a>Remarks

ネットワーク アドレス コントロールは、ユーザーが入力したアドレスの形式が正しいことを確認します。 コントロールは、ネットワーク アドレスを実際には接続できません。 [CNetAddressCtrl::SetAllowType](#setallowtype)メソッドは、1 つまたは複数の種類のアドレスを指定しますが、 [CNetAddressCtrl::GetAddress](#getaddress)メソッドは、解析および検証できます。 IPv4、IPv6、またはサーバー、ネットワーク、ホスト、またはブロードキャスト メッセージ送信先の名前付きのアドレスの形式で、アドレス指定できます。 使用することができます、アドレスの形式が正しくない場合、 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip)視覚的にネットワーク アドレス コントロールのテキスト ボックス をポイントし、事前に定義された表示されるヒント メッセージ ボックスを表示する方法エラー メッセージ。

`CNetAddressCtrl`から派生したクラスは、 [CEdit](../../mfc/reference/cedit-class.md)クラス。 その結果、ネットワーク アドレス コントロールは、すべての Windows 編集コントロールのメッセージへのアクセスを提供します。

次の図は、ネットワーク アドレス コントロールを含むダイアログを示しています。 テキスト ボックス (1) ネットワーク アドレス コントロールの無効なネットワーク アドレスが含まれています。 ネットワーク アドレスが有効でない場合は、ツールチップ メッセージ (2) が表示されます。

![ネットワーク アドレス コントロールおよび infotip を持つダイアログ。](../../mfc/reference/media/cnetaddctrl.png "ダイアログのネットワーク アドレス コントロールおよび infotip をします。")

## <a name="example"></a>例

次のコード例は、ネットワーク アドレスを検証する ダイアログ ボックスの一部です。 3 つのラジオ ボタンのイベント ハンドラーは、ネットワーク アドレスを指定できるで 3 つのアドレスの種類のいずれかを指定します。 ユーザーはネットワーク コントロールのテキスト ボックスにアドレスを入力し、アドレスを検証するためのボタンを押します。 アドレスが有効な場合は、成功メッセージが表示されます。それ以外の場合、定義済みのヒントのエラー メッセージが表示されます。

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]

## <a name="example"></a>例

ダイアログのヘッダー ファイルから次のコード例を定義、 [NC_ADDRESS](/windows/desktop/api/shellapi/ns-shellapi-tagnc_address)と[NET_ADDRESS_INFO](https://msdn.microsoft.com/library/windows/desktop/bb773346)に必要な変数、 [CNetAddressCtrl::GetAddress](#getaddress)メソッド。

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

`CNetAddressCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

Windows Vista 以降、このクラスはサポートされています。

このクラスの追加要件が記載されて[ビルド要件の Windows Vista コモン コントロール](../../mfc/build-requirements-for-windows-vista-common-controls.md)します。

##  <a name="cnetaddressctrl"></a>  CNetAddressCtrl::CNetAddressCtrl

`CNetAddressCtrl` オブジェクトを構築します。

```
CNetAddressCtrl();
```

### <a name="remarks"></a>Remarks

使用して、 [CNetAddressCtrl::Create](#create)または[CNetAddressCtrl::CreateEx](#createex)ネットワーク コントロールを作成し、アタッチ先メソッドを`CNetAddressCtrl`オブジェクト。

##  <a name="create"></a>  CNetAddressCtrl::Create

指定したスタイルを使用してネットワーク アドレス コントロールを作成し、現在に結び付けます`CNetAddressCtrl`オブジェクト。

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
|*dwStyle*|[in]コントロールに適用されるスタイルのビットごとの組み合わせ。 詳細については、次を参照してください。[スタイルの編集](../../mfc/reference/styles-used-by-mfc.md#edit-styles)します。|
|*rect*|[in]参照を[RECT](/previous-versions/dd162897\(v=vs.85\))コントロールのサイズと位置を含む構造体。|
|*pParentWnd*|[in]Null 以外のポインターを[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトは、コントロールの親ウィンドウです。|
|*nID*|[in]コントロールの ID。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

##  <a name="createex"></a>  CNetAddressCtrl::CreateEx

指定された拡張スタイルを使用してネットワーク アドレス コントロールを作成し、現在に結び付けます`CNetAddressCtrl`オブジェクト。

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
|*dwExStyle*|[in]コントロールに適用する拡張スタイルのビットごとの組み合わせ (OR)。 詳細については、次を参照してください。、 *dwExStyle*のパラメーター、 [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa)関数。|
|*dwStyle*|[in]コントロールに適用されるスタイルのビットごとの組み合わせ (OR)。 詳細については、次を参照してください。[スタイルの編集](../../mfc/reference/styles-used-by-mfc.md#edit-styles)します。|
|*rect*|[in]参照を[RECT](/previous-versions/dd162897\(v=vs.85\))コントロールのサイズと位置を含む構造体。|
|*pParentWnd*|[in]Null 以外のポインターを[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトは、コントロールの親ウィンドウです。|
|*nID*|[in]コントロールの ID。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

##  <a name="displayerrortip"></a>  CNetAddressCtrl::DisplayErrorTip

現在のネットワーク アドレス コントロールに関連付けられているバルーン ヒントにエラー メッセージが表示されます。

```
HRESULT DisplayErrorTip();
```

### <a name="return-value"></a>戻り値

値`S_OK`このメソッドが成功した。 それ以外の場合、エラー コード。

### <a name="remarks"></a>Remarks

使用して、 [CNetAddressCtrl::SetAllowType](#setallowtype)メソッドを現在のネットワーク アドレス コントロールをサポートするアドレスの種類を指定します。 使用して、 [CNetAddressCtrl::GetAddress](#getaddress)メソッドを検証して、ユーザーが入力したネットワーク アドレスを解析します。 使用して、 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip)場合に、エラー メッセージのヒントを表示するメソッド、 [CNetAddressCtrl::GetAddress](#getaddress)メソッドが成功しました。

このメッセージを呼び出す、 [NetAddr_DisplayErrorTip](/windows/desktop/api/shellapi/nf-shellapi-netaddr_displayerrortip)マクロで、Windows SDK に記載されています。 マクロの送信、`NCM_DISPLAYERRORTIP`メッセージ。

##  <a name="getaddress"></a>  CNetAddressCtrl::GetAddress

現在のネットワーク アドレス コントロールに関連付けられているネットワーク アドレスの検証、解析された表現を取得します。

```
HRESULT GetAddress(PNC_ADDRESS pAddress) const;
```

### <a name="parameters"></a>パラメーター

*pAddress*<br/>
[入力、出力]ポインター、 [NC_ADDRESS](/windows/desktop/api/shellapi/ns-shellapi-tagnc_address)構造体。  設定、 *pAddrInfo*のアドレスにこの構造体のメンバー、 [NET_ADDRESS_INFO](https://msdn.microsoft.com/library/windows/desktop/bb773346) GetAddress メソッドを呼び出す前に構造体します。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は S_OK 値それ以外の場合、COM エラー コード。 可能性のあるエラー コードの詳細については、の戻り値を参照してください、 [NetAddr_GetAddress](/windows/desktop/api/shellapi/nf-shellapi-netaddr_getaddress)マクロ。

### <a name="remarks"></a>Remarks

このメソッドが成功した場合、 [NET_ADDRESS_INFO](https://msdn.microsoft.com/library/windows/desktop/bb773346)構造体には、ネットワーク アドレスに関する追加情報が含まれています。

使用して、 [CNetAddressCtrl::SetAllowType](#setallowtype)メソッドを現在のネットワーク アドレス コントロールがサポートできるアドレスの種類を指定します。 使用して、 [CNetAddressCtrl::GetAddress](#getaddress)メソッドを検証して、ユーザーが入力したネットワーク アドレスを解析します。 使用して、 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip)場合に、エラー メッセージのヒントを表示するメソッド、 [CNetAddressCtrl::GetAddress](#getaddress)メソッドが成功しました。

このメソッドは、 [NetAddr_GetAddress](/windows/desktop/api/shellapi/nf-shellapi-netaddr_getaddress)マクロで、Windows SDK に記載されています。 マクロは、NCM_GETADDRESS メッセージを送信します。

##  <a name="getallowtype"></a>  CNetAddressCtrl::GetAllowType

現在のネットワーク アドレス コントロールをサポートするネットワーク アドレスの種類を取得します。

```
DWORD GetAllowType() const;
```

### <a name="return-value"></a>戻り値

アドレスの種類を指定するフラグのビットごとの組み合わせ (OR)、ネットワーク アドレス コントロールをサポートできます。 詳細については、次を参照してください。 [NET_STRING](https://msdn.microsoft.com/library/windows/desktop/bb762586)します。

### <a name="remarks"></a>Remarks

このメッセージを呼び出す、 [NetAddr_GetAllowType](/windows/desktop/api/shellapi/nf-shellapi-netaddr_getallowtype)マクロで、Windows SDK に記載されています。 マクロは、NCM_GETALLOWTYPE メッセージを送信します。

##  <a name="setallowtype"></a>  CNetAddressCtrl::SetAllowType

現在のネットワーク アドレス コントロールをサポートするネットワーク アドレスの種類を設定します。

```
HRESULT SetAllowType(DWORD dwAddrMask);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*dwAddrMask*|[in]アドレスの種類を指定するフラグのビットごとの組み合わせ (OR)、ネットワーク アドレス コントロールをサポートできます。 詳細については、次を参照してください。 [NET_STRING](https://msdn.microsoft.com/library/windows/desktop/bb762586)します。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は s_ok を返します。それ以外の場合、COM エラー コード。

### <a name="remarks"></a>Remarks

使用して、 [CNetAddressCtrl::SetAllowType](#setallowtype)メソッドを現在のネットワーク アドレス コントロールをサポートするアドレスの種類を指定します。 使用して、 [CNetAddressCtrl::GetAddress](#getaddress)メソッドを検証して、ユーザーが入力したネットワーク アドレスを解析します。 使用して、 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip)場合に、エラー メッセージのヒントを表示するメソッド、 [CNetAddressCtrl::GetAddress](#getaddress)メソッドが成功しました。

このメッセージを呼び出す、 [NetAddr_SetAllowType](/windows/desktop/api/shellapi/nf-shellapi-netaddr_setallowtype)マクロで、Windows SDK に記載されています。 マクロは、NCM_SETALLOWTYPE メッセージを送信します。

## <a name="see-also"></a>関連項目

[CNetAddressCtrl クラス](../../mfc/reference/cnetaddressctrl-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CEdit クラス](../../mfc/reference/cedit-class.md)
