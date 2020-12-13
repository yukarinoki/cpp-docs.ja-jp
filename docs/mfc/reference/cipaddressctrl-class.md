---
description: '詳細情報: CIPAddressCtrl クラス'
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
ms.openlocfilehash: e5791726bc31e9b7485d0de7ecfc5461408ed02a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340945"
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
|[CIPAddressCtrl::CIPAddressCtrl](#cipaddressctrl)|`CIPAddressCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CIPAddressCtrl:: ClearAddress](#clearaddress)|IP アドレスコントロールの内容を消去します。|
|[CIPAddressCtrl:: Create](#create)|IP アドレスコントロールを作成し、オブジェクトにアタッチし `CIPAddressCtrl` ます。|
|[CIPAddressCtrl:: CreateEx](#createex)|指定された Windows 拡張スタイルを使用して IP アドレスコントロールを作成し、それをオブジェクトにアタッチし `CIPAddressCtrl` ます。|
|[CIPAddressCtrl:: GetAddress](#getaddress)|IP アドレスコントロールの4つのすべてのフィールドのアドレス値を取得します。|
|[CIPAddressCtrl:: IsBlank](#isblank)|IP アドレスコントロールのすべてのフィールドが空かどうかを判断します。|
|[CIPAddressCtrl:: SetAddress](#setaddress)|IP アドレスコントロールの4つのすべてのフィールドのアドレス値を設定します。|
|[CIPAddressCtrl::SetFieldFocus](#setfieldfocus)|IP アドレスコントロールの指定されたフィールドにキーボードフォーカスを設定します。|
|[CIPAddressCtrl::SetFieldRange](#setfieldrange)|IP アドレスコントロールの指定されたフィールドの範囲を設定します。|

## <a name="remarks"></a>解説

IP アドレスコントロールは、エディットコントロールに似たコントロールであり、インターネットプロトコル (IP) 形式で数値アドレスを入力および操作できます。

このコントロール (および `CIPAddressCtrl` クラス) は、Microsoft Internet Explorer 4.0 以降で実行されているプログラムに対してのみ使用できます。 また、今後のバージョンの Windows および Windows NT でも使用できるようになります。

IP アドレス制御に関する一般的な情報については、「Windows SDK の [Ip アドレスコントロール](/windows/win32/Controls/ip-address-controls) 」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CIPAddressCtrl`

## <a name="requirements"></a>要件

**ヘッダー:** afxcmn.h

## <a name="cipaddressctrlcipaddressctrl"></a><a name="cipaddressctrl"></a> CIPAddressCtrl::CIPAddressCtrl

`CIPAddressCtrl` オブジェクトを作成します。

```
CIPAddressCtrl();
```

## <a name="cipaddressctrlclearaddress"></a><a name="clearaddress"></a> CIPAddressCtrl:: ClearAddress

IP アドレスコントロールの内容を消去します。

```cpp
void ClearAddress();
```

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [IPM_CLEARADDRESS](/windows/win32/Controls/ipm-clearaddress)の動作を実装します。

## <a name="cipaddressctrlcreate"></a><a name="create"></a> CIPAddressCtrl:: Create

IP アドレスコントロールを作成し、オブジェクトにアタッチし `CIPAddressCtrl` ます。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
IP アドレスコントロールのスタイル。 ウィンドウスタイルの組み合わせを適用します。 コントロールは子ウィンドウである必要があるため、WS_CHILD スタイルを含める必要があります。 Windows スタイルの一覧については、Windows SDK の「 [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) 」を参照してください。

*rect*<br/>
IP アドレスコントロールのサイズと位置への参照。 これは、 [CRect](../../atl-mfc-shared/reference/crect-class.md) オブジェクトまたは [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体のいずれかになります。

*pParentWnd*<br/>
IP アドレスコントロールの親ウィンドウへのポインター。 NULL にすることはできません。

*nID*<br/>
IP アドレスコントロールの ID。

### <a name="return-value"></a>戻り値

初期化が成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

オブジェクトを構築するには、 `CIPAddressCtrl` 2 つの手順を実行します。

1. オブジェクトを作成するコンストラクターを呼び出します `CIPAddressCtrl` 。

1. `Create`を呼び出して、IP アドレスコントロールを作成します。

拡張 windows スタイルをコントロールで使用する場合は、ではなく [CreateEx](#createex) を呼び出し `Create` ます。

## <a name="cipaddressctrlcreateex"></a><a name="createex"></a> CIPAddressCtrl:: CreateEx

この関数を呼び出して、コントロール (子ウィンドウ) を作成し、オブジェクトに関連付け `CIPAddressCtrl` ます。

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwExStyle*<br/>
作成するコントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧については、Windows SDK の [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)の *dwexstyle* パラメーターを参照してください。

*dwStyle*<br/>
IP アドレスコントロールのスタイル。 ウィンドウスタイルの組み合わせを適用します。 コントロールは子ウィンドウである必要があるため、WS_CHILD スタイルを含める必要があります。 Windows スタイルの一覧については、Windows SDK の「 [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) 」を参照してください。

*rect*<br/>
*PParentWnd* のクライアント座標で、作成されるウィンドウのサイズと位置を記述する [RECT](/windows/win32/api/windef/ns-windef-rect)構造体への参照。

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*nID*<br/>
コントロールの子ウィンドウ ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

`CreateEx`Windows 拡張スタイルの先頭 **WS_EX_** によって指定された拡張 windows スタイルを適用するには、[[作成](#create)] ではなくを使用します。

## <a name="cipaddressctrlgetaddress"></a><a name="getaddress"></a> CIPAddressCtrl:: GetAddress

IP アドレスコントロールの4つのすべてのフィールドのアドレス値を取得します。

```
int GetAddress(
    BYTE& nField0,
    BYTE& nField1,
    BYTE& nField2,
    BYTE& nField3);

int GetAddress(DWORD& dwAddress);
```

### <a name="parameters"></a>パラメーター

*nField0*<br/>
パックされた IP アドレスからのフィールド0の値への参照。

*nField1*<br/>
パックされた IP アドレスからのフィールド1の値への参照。

*nField2*<br/>
パックされた IP アドレスからのフィールド2の値への参照。

*nField3*<br/>
パックされた IP アドレスからのフィールド3の値への参照。

*dwAddress*<br/>
IP アドレスを受け取る DWORD 値のアドレスへの参照。 *Dwaddress* の入力方法を示す表については、「**解説**」を参照してください。

### <a name="return-value"></a>戻り値

IP アドレスコントロール内の空白以外のフィールドの数。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [IPM_GETADDRESS](/windows/win32/Controls/ipm-getaddress)の動作を実装します。 上記の最初のプロトタイプでは、コントロールのフィールド 0 ~ 3 の数値が左から右に読み取られ、4つのパラメーターが設定されています。 上記の2番目のプロトタイプでは、 *Dwaddress* は次のように設定されます。

|フィールド|フィールド値を含むビット|
|-----------|-------------------------------------|
|0|24 ~ 31|
|1|16 ~ 23|
|2|8 ~ 15|
|3|0 ~ 7|

## <a name="cipaddressctrlisblank"></a><a name="isblank"></a> CIPAddressCtrl:: IsBlank

IP アドレスコントロールのすべてのフィールドが空かどうかを判断します。

```
BOOL IsBlank() const;
```

### <a name="return-value"></a>戻り値

すべての IP アドレス制御フィールドが空の場合は0以外。それ以外の場合は0です。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [IPM_ISBLANK](/windows/win32/Controls/ipm-isblank)の動作を実装します。

## <a name="cipaddressctrlsetaddress"></a><a name="setaddress"></a> CIPAddressCtrl:: SetAddress

IP アドレスコントロールの4つのすべてのフィールドのアドレス値を設定します。

```cpp
void SetAddress(
    BYTE nField0,
    BYTE nField1,
    BYTE nField2,
    BYTE nField3);

void SetAddress(DWORD dwAddress);
```

### <a name="parameters"></a>パラメーター

*nField0*<br/>
パックされた IP アドレスのフィールド0の値。

*nField1*<br/>
パックされた IP アドレスからのフィールド1の値。

*nField2*<br/>
パックされた IP アドレスからのフィールド2の値。

*nField3*<br/>
パックされた IP アドレスのフィールド3の値。

*dwAddress*<br/>
新しい IP アドレスを含む DWORD 値です。 DWORD 値がどのように格納されるかを示す表については、「 **解説** 」を参照してください。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [IPM_SETADDRESS](/windows/win32/Controls/ipm-setaddress)の動作を実装します。 上記の最初のプロトタイプでは、コントロールのフィールド 0 ~ 3 の数値が左から右に読み取られ、4つのパラメーターが設定されています。 上記の2番目のプロトタイプでは、 *Dwaddress* は次のように設定されます。

|フィールド|フィールド値を含むビット|
|-----------|-------------------------------------|
|0|24 ~ 31|
|1|16 ~ 23|
|2|8 ~ 15|
|3|0 ~ 7|

## <a name="cipaddressctrlsetfieldfocus"></a><a name="setfieldfocus"></a> CIPAddressCtrl::SetFieldFocus

IP アドレスコントロールの指定されたフィールドにキーボードフォーカスを設定します。

```cpp
void SetFieldFocus(WORD nField);
```

### <a name="parameters"></a>パラメーター

*n フィールド*<br/>
フォーカスを設定する必要がある、0から始まるフィールドインデックス。 この値がフィールドの数より大きい場合、フォーカスは最初の空のフィールドに設定されます。 すべてのフィールドが空白でない場合、フォーカスは最初のフィールドに設定されます。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [IPM_SETFOCUS](/windows/win32/Controls/ipm-setfocus)の動作を実装します。

## <a name="cipaddressctrlsetfieldrange"></a><a name="setfieldrange"></a> CIPAddressCtrl::SetFieldRange

IP アドレスコントロールの指定されたフィールドの範囲を設定します。

```cpp
void SetFieldRange(
    int nField,
    BYTE nLower,
    BYTE nUpper);
```

### <a name="parameters"></a>パラメーター

*n フィールド*<br/>
範囲が適用される0から始まるフィールドインデックス。

*nLower*<br/>
この IP アドレスコントロール内の指定されたフィールドの下限を受け取る整数への参照。

*nUpper*<br/>
この IP アドレスコントロール内の指定されたフィールドの上限を受け取る整数への参照。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [IPM_SETRANGE](/windows/win32/Controls/ipm-setrange)の動作を実装します。 2つのパラメーター ( *Nlower* と *nlower*) を使用して、Win32 メッセージで使用される *wrange* パラメーターではなく、フィールドの下限と上限を指定します。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
