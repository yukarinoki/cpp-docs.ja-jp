---
title: CIPAddressCtrl クラス
ms.date: 11/04/2016
f1_keywords:
- CIPAddressCtrl
- AFXCMN/CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::ClearAddress
- AFXCMN/CIPAddressCtrl::Create
- AFXCMN/CIPAddressCtrl::CreateEx
- AFXCMN/CIPAddressCtrl::GetAddress
- AFXCMN/CIPAddressCtrl::IsBlank
- AFXCMN/CIPAddressCtrl::SetAddress
- AFXCMN/CIPAddressCtrl::SetFieldFocus
- AFXCMN/CIPAddressCtrl::SetFieldRange
helpviewer_keywords:
- CIPAddressCtrl [MFC], CIPAddressCtrl
- CIPAddressCtrl [MFC], ClearAddress
- CIPAddressCtrl [MFC], Create
- CIPAddressCtrl [MFC], CreateEx
- CIPAddressCtrl [MFC], GetAddress
- CIPAddressCtrl [MFC], IsBlank
- CIPAddressCtrl [MFC], SetAddress
- CIPAddressCtrl [MFC], SetFieldFocus
- CIPAddressCtrl [MFC], SetFieldRange
ms.assetid: 9764d2f4-cb14-4ba8-b799-7f57a55a47c6
ms.openlocfilehash: 0613dea766b022acf140a82bb4b01784793c2589
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754965"
---
# <a name="cipaddressctrl-class"></a>CIPAddressCtrl クラス

Windows コモン IP アドレス コントロールの機能が用意されています。

## <a name="syntax"></a>構文

```
class CIPAddressCtrl : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[クリックキー::CIPアドレスCtrl](#cipaddressctrl)|`CIPAddressCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[住所をクリアします。](#clearaddress)|IP アドレスコントロールの内容をクリアします。|
|[クリックキー::作成](#create)|IP アドレス コントロールを作成し、オブジェクトに`CIPAddressCtrl`アタッチします。|
|[クリックキー::作成します。](#createex)|指定した Windows 拡張スタイルを使用して IP アドレス コントロールを`CIPAddressCtrl`作成し、オブジェクトにアタッチします。|
|[住所を取得します。](#getaddress)|IP アドレス コントロール内の 4 つのフィールドすべてのアドレス値を取得します。|
|[クリックキー::イブランク](#isblank)|IP アドレスコントロールのすべてのフィールドが空かどうかを判断します。|
|[を設定します。](#setaddress)|IP アドレスコントロールの 4 つのフィールドすべてにアドレス値を設定します。|
|[をクリックします。](#setfieldfocus)|IP アドレス コントロールの指定されたフィールドにキーボード フォーカスを設定します。|
|[をクリックします。](#setfieldrange)|IP アドレスコントロールの指定されたフィールドの範囲を設定します。|

## <a name="remarks"></a>解説

IP アドレス コントロールは、編集コントロールに似たコントロールで、IP (インターネット プロトコル) 形式の数値アドレスを入力および操作できます。

このコントロール (および`CIPAddressCtrl`クラス) は、Internet Explorer 4.0 以降で実行されているプログラムでのみ使用できます。 また、将来のバージョンの Windows および Windows NT でも使用できるようになります。

IP アドレスコントロールの一般的な情報については、Windows SDK の[「IP アドレスコントロール](/windows/win32/Controls/ip-address-controls)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CIPAddressCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

## <a name="cipaddressctrlcipaddressctrl"></a><a name="cipaddressctrl"></a>クリックキー::CIPアドレスCtrl

`CIPAddressCtrl` オブジェクトを作成します。

```
CIPAddressCtrl();
```

## <a name="cipaddressctrlclearaddress"></a><a name="clearaddress"></a>住所をクリアします。

IP アドレスコントロールの内容をクリアします。

```cpp
void ClearAddress();
```

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[IPM_CLEARADDRESS](/windows/win32/Controls/ipm-clearaddress)の動作を実装します。

## <a name="cipaddressctrlcreate"></a><a name="create"></a>クリックキー::作成

IP アドレス コントロールを作成し、オブジェクトに`CIPAddressCtrl`アタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
IP アドレス コントロールのスタイル。 ウィンドウ スタイルの組み合わせを適用します。 コントロールは子ウィンドウである必要があるため、WS_CHILDスタイルを含める必要があります。 ウィンドウ スタイルの一覧については、Windows SDK の[「ウィンドウの作成](/windows/win32/api/winuser/nf-winuser-createwindoww)」を参照してください。

*Rect*<br/>
IP アドレス コントロールのサイズと位置への参照。 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](/windows/win32/api/windef/ns-windef-rect)構造体を指定できます。

*pParentWnd*<br/>
IP アドレス コントロールの親ウィンドウへのポインター。 NULL にすることはできません。

*nID*<br/>
IP アドレス コントロールの ID。

### <a name="return-value"></a>戻り値

初期化が成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

オブジェクトは`CIPAddressCtrl`2 つの手順で作成します。

1. オブジェクトを作成するコンストラクターを`CIPAddressCtrl`呼び出します。

1. 呼`Create`び出しは、IP アドレスコントロールを作成します。

コントロールで拡張ウィンドウ スタイルを使用する場合は、 ではなく[CreateEx](#createex)を`Create`呼び出します。

## <a name="cipaddressctrlcreateex"></a><a name="createex"></a>クリックキー::作成します。

コントロール (子ウィンドウ) を作成し、`CIPAddressCtrl`オブジェクトに関連付けます。

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*ドウェエクススタイル*<br/>
作成するコントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧については、Windows SDK の*DwExStyle*パラメーター[を](/windows/win32/api/winuser/nf-winuser-createwindowexw)参照してください。

*Dwstyle*<br/>
IP アドレス コントロールのスタイル。 ウィンドウ スタイルの組み合わせを適用します。 コントロールは子ウィンドウである必要があるため、WS_CHILDスタイルを含める必要があります。 ウィンドウ スタイルの一覧については、Windows SDK の[「ウィンドウの作成](/windows/win32/api/winuser/nf-winuser-createwindoww)」を参照してください。

*Rect*<br/>
作成するウィンドウのサイズと位置を記述する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体への参照を *、 pParentWnd*のクライアント座標で指定します。

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*nID*<br/>
コントロールの子ウィンドウ ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

[`CreateEx`[作成]](#create)の代わりに、Windows 拡張スタイルの序文で指定された拡張 Windows スタイル**を適用WS_EX_。**

## <a name="cipaddressctrlgetaddress"></a><a name="getaddress"></a>住所を取得します。

IP アドレス コントロール内の 4 つのフィールドすべてのアドレス値を取得します。

```
int GetAddress(
    BYTE& nField0,
    BYTE& nField1,
    BYTE& nField2,
    BYTE& nField3);

int GetAddress(DWORD& dwAddress);
```

### <a name="parameters"></a>パラメーター

*nフィールド0*<br/>
パックされた IP アドレスからのフィールド 0 値への参照。

*nフィールド1*<br/>
パックされた IP アドレスからのフィールド 1 の値への参照。

*nフィールド2*<br/>
パックされた IP アドレスからのフィールド 2 値への参照。

*nフィールド3*<br/>
パックされた IP アドレスからのフィールド 3 値への参照。

*dw アドレス*<br/>
IP アドレスを受け取る DWORD 値のアドレスへの参照。 *dwAddress*の塗りつぶし方法を示す表については、「**解説」** を参照してください。

### <a name="return-value"></a>戻り値

IP アドレスコントロールの空白以外のフィールドの数。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[IPM_GETADDRESS](/windows/win32/Controls/ipm-getaddress)の動作を実装します。 上記の最初のプロトタイプでは、コントロールのフィールド 0 ~ 3 の数値をそれぞれ左から右に読み取り、4 つのパラメーターを設定します。 上の 2 番目のプロトタイプでは *、dwAddress*は次のように設定されます。

|フィールド|フィールド値を含むビット|
|-----------|-------------------------------------|
|0|24 から 31|
|1|16から23まで|
|2|8から15まで|
|3|0 から 7|

## <a name="cipaddressctrlisblank"></a><a name="isblank"></a>クリックキー::イブランク

IP アドレスコントロールのすべてのフィールドが空かどうかを判断します。

```
BOOL IsBlank() const;
```

### <a name="return-value"></a>戻り値

IP アドレス制御フィールドがすべて空の場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[IPM_ISBLANK](/windows/win32/Controls/ipm-isblank)の動作を実装します。

## <a name="cipaddressctrlsetaddress"></a><a name="setaddress"></a>を設定します。

IP アドレスコントロールの 4 つのフィールドすべてにアドレス値を設定します。

```cpp
void SetAddress(
    BYTE nField0,
    BYTE nField1,
    BYTE nField2,
    BYTE nField3);

void SetAddress(DWORD dwAddress);
```

### <a name="parameters"></a>パラメーター

*nフィールド0*<br/>
パックされた IP アドレスからのフィールド 0 の値。

*nフィールド1*<br/>
パックされた IP アドレスからのフィールド 1 の値。

*nフィールド2*<br/>
パックされた IP アドレスからのフィールド 2 の値。

*nフィールド3*<br/>
パックされた IP アドレスからのフィールド 3 の値。

*dw アドレス*<br/>
新しい IP アドレスを含む DWORD 値。 DWORD 値の入力方法を示す表については、「**解説」** を参照してください。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[IPM_SETADDRESS](/windows/win32/Controls/ipm-setaddress)の動作を実装します。 上記の最初のプロトタイプでは、コントロールのフィールド 0 ~ 3 の数値をそれぞれ左から右に読み取り、4 つのパラメーターを設定します。 上の 2 番目のプロトタイプでは *、dwAddress*は次のように設定されます。

|フィールド|フィールド値を含むビット|
|-----------|-------------------------------------|
|0|24 から 31|
|1|16から23まで|
|2|8から15まで|
|3|0 から 7|

## <a name="cipaddressctrlsetfieldfocus"></a><a name="setfieldfocus"></a>をクリックします。

IP アドレス コントロールの指定されたフィールドにキーボード フォーカスを設定します。

```cpp
void SetFieldFocus(WORD nField);
```

### <a name="parameters"></a>パラメーター

*nフィールド*<br/>
フォーカスを設定する必要がある、0 から始まるフィールド インデックス。 この値がフィールド数より大きい場合、フォーカスは最初の空白フィールドに設定されます。 すべてのフィールドが空白以外の場合、フォーカスは最初のフィールドに設定されます。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[IPM_SETFOCUS](/windows/win32/Controls/ipm-setfocus)の動作を実装します。

## <a name="cipaddressctrlsetfieldrange"></a><a name="setfieldrange"></a>をクリックします。

IP アドレスコントロールの指定されたフィールドの範囲を設定します。

```cpp
void SetFieldRange(
    int nField,
    BYTE nLower,
    BYTE nUpper);
```

### <a name="parameters"></a>パラメーター

*nフィールド*<br/>
範囲が適用される、0 から始まるフィールド インデックス。

*nローワー*<br/>
この IP アドレス制御で指定されたフィールドの下限を受け取る整数への参照。

*nアッパー*<br/>
この IP アドレス制御で指定されたフィールドの上限を受け取る整数への参照。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[IPM_SETRANGE](/windows/win32/Controls/ipm-setrange)の動作を実装します。 Win32 メッセージで使用される*wRange*パラメーターの代わりに、フィールドの下限と上限を示すには *、nLower*と*nUpper*の 2 つのパラメーターを使用します。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
