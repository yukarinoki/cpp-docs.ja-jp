---
description: '詳細情報: CHotKeyCtrl クラス'
title: CHotKeyCtrl クラス
ms.date: 11/04/2016
f1_keywords:
- CHotKeyCtrl
- AFXCMN/CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::Create
- AFXCMN/CHotKeyCtrl::CreateEx
- AFXCMN/CHotKeyCtrl::GetHotKey
- AFXCMN/CHotKeyCtrl::GetHotKeyName
- AFXCMN/CHotKeyCtrl::GetKeyName
- AFXCMN/CHotKeyCtrl::SetHotKey
- AFXCMN/CHotKeyCtrl::SetRules
helpviewer_keywords:
- CHotKeyCtrl [MFC], CHotKeyCtrl
- CHotKeyCtrl [MFC], Create
- CHotKeyCtrl [MFC], CreateEx
- CHotKeyCtrl [MFC], GetHotKey
- CHotKeyCtrl [MFC], GetHotKeyName
- CHotKeyCtrl [MFC], GetKeyName
- CHotKeyCtrl [MFC], SetHotKey
- CHotKeyCtrl [MFC], SetRules
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
ms.openlocfilehash: 875b35c2c683cc8502c1bc2668aad5b4a0326757
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331770"
---
# <a name="chotkeyctrl-class"></a>CHotKeyCtrl クラス

Windows コモン ホット キー コントロールの機能が用意されています。

## <a name="syntax"></a>構文

```
class CHotKeyCtrl : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CHotKeyCtrl:: CHotKeyCtrl](#chotkeyctrl)|`CHotKeyCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CHotKeyCtrl:: Create](#create)|ホットキーコントロールを作成し、オブジェクトにアタッチし `CHotKeyCtrl` ます。|
|[CHotKeyCtrl:: CreateEx](#createex)|指定した Windows 拡張スタイルを使用してホットキーコントロールを作成し、それをオブジェクトにアタッチし `CHotKeyCtrl` ます。|
|[CHotKeyCtrl:: GetHotKey](#gethotkey)|ホットキーコントロールからホットキーの仮想キーコードと修飾子フラグを取得します。|
|[CHotKeyCtrl:: GetHotKeyName](#gethotkeyname)|ホットキーに割り当てられたローカル文字セット内のキー名を取得します。|
|[CHotKeyCtrl:: GetKeyName](#getkeyname)|指定した仮想キーコードに割り当てられた、ローカル文字セット内のキー名を取得します。|
|[CHotKeyCtrl:: SetHotKey](#sethotkey)|ホットキーコントロールのホットキーの組み合わせを設定します。|
|[CHotKeyCtrl:: SetRules](#setrules)|無効な組み合わせと、ホットキーコントロールの既定の修飾子の組み合わせを定義します。|

## <a name="remarks"></a>解説

"ホットキーコントロール" は、ユーザーがホットキーを作成できるウィンドウです。 "ホットキー" とは、ユーザーが操作を迅速に実行するために押すキーの組み合わせです。 (たとえば、ユーザーは、特定のウィンドウをアクティブにして Z オーダーの最上部に表示するホットキーを作成できます)。ホットキーコントロールはユーザーの選択肢を表示し、ユーザーが有効なキーの組み合わせを選択するようにします。

このコントロール (および `CHotKeyCtrl` クラス) は、windows 95/98 および WINDOWS NT バージョン3.51 以降で実行されているプログラムに対してのみ使用できます。

ユーザーがキーの組み合わせを選択すると、アプリケーションは指定されたキーの組み合わせをコントロールから取得し、WM_SETHOTKEY メッセージを使用してシステムのホットキーを設定できます。 ユーザーがその後、システムの任意の部分からホットキーを押すたびに、WM_SETHOTKEY メッセージに指定されたウィンドウが SC_HOTKEY を指定する WM_SYSCOMMAND メッセージを受信します。 このメッセージは、それを受信するウィンドウをアクティブにします。 ホットキーは、WM_SETHOTKEY 呼び出されたアプリケーションが終了するまで有効なままです。

このメカニズムは、WM_HOTKEY メッセージ、Windows [Registerhotkey](/windows/win32/api/winuser/nf-winuser-registerhotkey) キー、および [unregisterhotkey](/windows/win32/api/winuser/nf-winuser-unregisterhotkey) キー関数に依存するホットキーのサポートとは異なります。

の使用方法の詳細について `CHotKeyCtrl` は、「 [Controls](../../mfc/controls-mfc.md) and [using CHotKeyCtrl](../../mfc/using-chotkeyctrl.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHotKeyCtrl`

## <a name="requirements"></a>要件

**ヘッダー:** afxcmn.h

## <a name="chotkeyctrlchotkeyctrl"></a><a name="chotkeyctrl"></a> CHotKeyCtrl:: CHotKeyCtrl

`CHotKeyCtrl` オブジェクトを構築します。

```
CHotKeyCtrl();
```

## <a name="chotkeyctrlcreate"></a><a name="create"></a> CHotKeyCtrl:: Create

ホットキーコントロールを作成し、オブジェクトにアタッチし `CHotKeyCtrl` ます。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
ホットキーコントロールのスタイルを指定します。 コントロールスタイルの任意の組み合わせを適用します。 詳細については、「Windows SDK の [一般的なコントロールスタイル](/windows/win32/Controls/common-control-styles) 」を参照してください。

*rect*<br/>
ホットキーコントロールのサイズと位置を指定します。 これは、 [CRect](../../atl-mfc-shared/reference/crect-class.md) オブジェクトまたは [RECT 構造体](/windows/win32/api/windef/ns-windef-rect)のいずれかになります。

*pParentWnd*<br/>
ホットキーコントロールの親ウィンドウ (通常は、 [CDialog](../../mfc/reference/cdialog-class.md)) を指定します。 NULL にすることはできません。

*nID*<br/>
ホットキーコントロールの ID を指定します。

### <a name="return-value"></a>戻り値

初期化が成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

オブジェクトを構築するには、 `CHotKeyCtrl` 2 つの手順を実行します。 まず、コンストラクターを呼び出し、次に `Create` を呼び出します。これにより、ホットキーコントロールが作成され、オブジェクトにアタッチさ `CHotKeyCtrl` れます。

拡張 windows スタイルをコントロールで使用する場合は、ではなく [CreateEx](#createex) を呼び出し `Create` ます。

## <a name="chotkeyctrlcreateex"></a><a name="createex"></a> CHotKeyCtrl:: CreateEx

この関数を呼び出して、コントロール (子ウィンドウ) を作成し、オブジェクトに関連付け `CHotKeyCtrl` ます。

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
ホットキーコントロールのスタイルを指定します。 コントロールスタイルの任意の組み合わせを適用します。 詳細については、「Windows SDK の [コモンコントロールスタイル](/windows/win32/Controls/common-control-styles) 」を参照してください。

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

## <a name="chotkeyctrlgethotkey"></a><a name="gethotkey"></a> CHotKeyCtrl:: GetHotKey

ホットキーコントロールからキーボードショートカットの仮想キーコードと修飾子フラグを取得します。

```
DWORD GetHotKey() const;

void GetHotKey(
    WORD& wVirtualKeyCode,
    WORD& wModifiers) const;
```

### <a name="parameters"></a>パラメーター

*wVirtualKeyCode*<br/>
入出力キーボードショートカットの仮想キーコード。 標準の仮想キーコードの一覧については、「Winuser. h」を参照してください。

*wModifiers*<br/>
入出力キーボードショートカットの修飾キーを示すフラグのビットごとの組み合わせ (or)。

修飾子フラグは次のとおりです。

|フラグ|対応するキー|
|----------|-----------------------|
|HOTKEYF_ALT|ALT キー|
|HOTKEYF_CONTROL|CTRL キー|
|HOTKEYF_EXT|拡張キー|
|HOTKEYF_SHIFT|SHIFT キー|

### <a name="return-value"></a>戻り値

最初のオーバーロードされたメソッドで、仮想キーコードと修飾子フラグを含む DWORD。 下位ワードの下位バイトには、仮想キーコード、下位ワードの上位バイトに修飾子フラグ、および上位ワードがゼロであることが含まれています。

### <a name="remarks"></a>解説

仮想キーコードと修飾子キーを一緒に押すと、ショートカットキーが定義されます。

## <a name="chotkeyctrlgethotkeyname"></a><a name="gethotkeyname"></a> CHotKeyCtrl:: GetHotKeyName

このメンバー関数を呼び出して、ホットキーのローカライズされた名前を取得します。

```
CString GetHotKeyName() const;
```

### <a name="return-value"></a>戻り値

現在選択されているホットキーのローカライズされた名前。 ホットキーが選択されていない場合は、 `GetHotKeyName` 空の文字列を返します。

### <a name="remarks"></a>解説

このメンバー関数が返す名前は、キーボードドライバーから取得されます。 ローカライズされていないキーボードドライバーは、ローカライズ版の Windows にインストールできます。また、その逆も可能です。

## <a name="chotkeyctrlgetkeyname"></a><a name="getkeyname"></a> CHotKeyCtrl:: GetKeyName

指定した仮想キーコードに割り当てられているキーのローカライズされた名前を取得するには、このメンバー関数を呼び出します。

```
static CString GetKeyName(
    UINT vk,
    BOOL fExtended);
```

### <a name="parameters"></a>パラメーター

*vk*<br/>
仮想キーコード。

*fExtended*<br/>
仮想キーコードが拡張キーの場合、TRUE になります。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

*Vk* パラメーターで指定したキーのローカライズされた名前。 キーにマップされた名前がない場合、は `GetKeyName` 空の文字列を返します。

### <a name="remarks"></a>解説

この関数が返すキー名はキーボードドライバーから取得されるため、ローカライズされていないキーボードドライバーを Windows のローカライズ版にインストールできます。また、その逆も可能です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#69](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]

## <a name="chotkeyctrlsethotkey"></a><a name="sethotkey"></a> CHotKeyCtrl:: SetHotKey

ホットキーコントロールのキーボードショートカットを設定します。

```cpp
void SetHotKey(
    WORD wVirtualKeyCode,
    WORD wModifiers);
```

### <a name="parameters"></a>パラメーター

*wVirtualKeyCode*<br/>
からキーボードショートカットの仮想キーコード。 標準の仮想キーコードの一覧については、「Winuser. h」を参照してください。

*wModifiers*<br/>
からキーボードショートカットの修飾キーを示すフラグのビットごとの組み合わせ (or)。

修飾子フラグは次のとおりです。

|フラグ|対応するキー|
|----------|-----------------------|
|HOTKEYF_ALT|ALT キー|
|HOTKEYF_CONTROL|CTRL キー|
|HOTKEYF_EXT|拡張キー|
|HOTKEYF_SHIFT|SHIFT キー|

### <a name="remarks"></a>解説

仮想キーコードと修飾子キーを一緒に押すと、ショートカットキーが定義されます。

## <a name="chotkeyctrlsetrules"></a><a name="setrules"></a> CHotKeyCtrl:: SetRules

この関数を呼び出して、ホットキーコントロールの無効な組み合わせと既定の修飾子の組み合わせを定義します。

```cpp
void SetRules(
    WORD wInvalidComb,
    WORD wModifiers);
```

### <a name="parameters"></a>パラメーター

*wInvalidComb 目*<br/>
無効なキーの組み合わせを指定するフラグの配列。 次の値の組み合わせを指定できます。

- HKCOMB_A ALT

- HKCOMB_C CTRL

- HKCOMB_CA CTRL + ALT

- 未変更のキーの HKCOMB_NONE

- HKCOMB_S シフト

- HKCOMB_SA SHIFT + ALT

- HKCOMB_SC SHIFT + CTRL

- HKCOMB_SCA SHIFT + CTRL + ALT

*wModifiers*<br/>
ユーザーが無効な組み合わせを入力したときに使用するキーの組み合わせを指定するフラグの配列。 修飾子フラグの詳細については、「 [GetHotKey](#gethotkey)」を参照してください。

### <a name="remarks"></a>解説

*Winvalidcomb* 目に指定されているフラグで定義されているように、ユーザーが無効なキーの組み合わせを入力すると、システムは or 演算子を使用して、ユーザーが入力したキーと *wmodifiers* に指定されたフラグを結合します。 結果として得られるキーの組み合わせは文字列に変換され、ホットキーコントロールに表示されます。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
