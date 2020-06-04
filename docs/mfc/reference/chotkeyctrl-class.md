---
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
ms.openlocfilehash: a79cc0ab2c01633f96430477aa536a60385461e9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750803"
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
|[コッキーCtrl::CHotKeyCtrl](#chotkeyctrl)|`CHotKeyCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[作成](#create)|ホット キー コントロールを作成し、`CHotKeyCtrl`オブジェクトにアタッチします。|
|[コトキーCtrl::作成Ex](#createex)|指定した Windows 拡張スタイルを使用してホット キー コントロールを作成`CHotKeyCtrl`し、オブジェクトにアタッチします。|
|[キーキーを取得します。](#gethotkey)|ホット キー コントロールから、ホット キーの仮想キー コードと修飾子フラグを取得します。|
|[キーキー名を取得します。](#gethotkeyname)|ホット キーに割り当てられたローカル文字セット内のキー名を取得します。|
|[キーネームを取得します。](#getkeyname)|指定した仮想キー コードに割り当てられたローカル文字セット内のキー名を取得します。|
|[セットキーキー](#sethotkey)|ホット キー コントロールのホット キーの組み合わせを設定します。|
|[次のルールを設定します。](#setrules)|ホット キー コントロールの無効な組み合わせと既定の修飾子の組み合わせを定義します。|

## <a name="remarks"></a>解説

"ホット キー コントロール" は、ユーザーがホット キーを作成できるようにするウィンドウです。 "ホットキー" は、ユーザーが操作を迅速に実行するために押すことができるキーの組み合わせです。 (たとえば、ユーザーは、特定のウィンドウをアクティブにし、Z オーダーの先頭に移動するホット キーを作成できます)。ホット キー コントロールは、ユーザーの選択内容を表示し、ユーザーが有効なキーの組み合わせを選択することを確認します。

このコントロール (および`CHotKeyCtrl`クラス) は、Windows 95/98 および Windows NT バージョン 3.51 以降で実行されているプログラムでのみ使用できます。

ユーザーがキーの組み合わせを選択すると、アプリケーションは、指定されたキーの組み合わせをコントロールから取得し、WM_SETHOTKEYメッセージを使用してシステムのホットキーを設定できます。 ユーザーがホット キーを押すと、システムの任意の部分から、WM_SETHOTKEY メッセージに指定されたウィンドウがSC_HOTKEYを指定するWM_SYSCOMMAND メッセージを受け取ります。 このメッセージは、受信するウィンドウをアクティブにします。 ホット キーは、WM_SETHOTKEYを呼び出したアプリケーションが終了するまで有効です。

このメカニズムは、WM_HOTKEY メッセージと Windows [RegisterHotKey](/windows/win32/api/winuser/nf-winuser-registerhotkey)関数と[登録解除ホットキー](/windows/win32/api/winuser/nf-winuser-unregisterhotkey)関数に依存するホット キーのサポートとは異なります。

の詳細`CHotKeyCtrl`については、「[コントロール](../../mfc/controls-mfc.md)」および[「CHotKeyCtrl](../../mfc/using-chotkeyctrl.md)の使用」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHotKeyCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

## <a name="chotkeyctrlchotkeyctrl"></a><a name="chotkeyctrl"></a>コッキーCtrl::CHotKeyCtrl

`CHotKeyCtrl` オブジェクトを構築します。

```
CHotKeyCtrl();
```

## <a name="chotkeyctrlcreate"></a><a name="create"></a>作成

ホット キー コントロールを作成し、`CHotKeyCtrl`オブジェクトにアタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
ホット キー コントロールのスタイルを指定します。 コントロール スタイルの任意の組み合わせを適用します。 詳細については、Windows SDK の[「共通のコントロール スタイル](/windows/win32/Controls/common-control-styles)」を参照してください。

*Rect*<br/>
ホット キー コントロールのサイズと位置を指定します。 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT 構造体](/windows/win32/api/windef/ns-windef-rect)のいずれかを指定できます。

*pParentWnd*<br/>
ホット キー コントロールの親ウィンドウを指定[します。](../../mfc/reference/cdialog-class.md) NULL にすることはできません。

*nID*<br/>
ホット キー コントロールの ID を指定します。

### <a name="return-value"></a>戻り値

初期化が成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

オブジェクトは`CHotKeyCtrl`2 つの手順で作成します。 まず、コンストラクタを呼び出し`Create`、次にホット キー コントロールを作成して`CHotKeyCtrl`オブジェクトにアタッチする を呼び出します。

コントロールで拡張ウィンドウ スタイルを使用する場合は、 ではなく[CreateEx](#createex)を`Create`呼び出します。

## <a name="chotkeyctrlcreateex"></a><a name="createex"></a>コトキーCtrl::作成Ex

コントロール (子ウィンドウ) を作成し、`CHotKeyCtrl`オブジェクトに関連付けます。

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
ホット キー コントロールのスタイルを指定します。 コントロール スタイルの任意の組み合わせを適用します。 詳細については、Windows SDK[の「コモン コントロール スタイル](/windows/win32/Controls/common-control-styles)」を参照してください。

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

## <a name="chotkeyctrlgethotkey"></a><a name="gethotkey"></a>キーキーを取得します。

ホット キー コントロールから、キーボード ショートカットの仮想キー コードと修飾子フラグを取得します。

```
DWORD GetHotKey() const;

void GetHotKey(
    WORD& wVirtualKeyCode,
    WORD& wModifiers) const;
```

### <a name="parameters"></a>パラメーター

*キーコード*<br/>
[アウト]キーボード ショートカットの仮想キー コード。 標準の仮想キー コードの一覧については、Winuser.h を参照してください。

*w修飾子*<br/>
[アウト]キーボード ショートカットの修飾キーを示すフラグのビットごとの組み合わせ (OR)。

修飾子フラグは次のとおりです。

|フラグ|対応するキー|
|----------|-----------------------|
|HOTKEYF_ALT|ALT キー|
|HOTKEYF_CONTROL|Ctrl キー|
|HOTKEYF_EXT|拡張キー|
|HOTKEYF_SHIFT|Shift キー|

### <a name="return-value"></a>戻り値

最初のオーバーロードされたメソッドで、仮想キー コードと修飾子フラグを含む DWORD。 下位ワードの下位バイトには仮想キー・コードが含まれ、下位ワードの上位バイトには修飾子フラグが含まれ、上位ワードはゼロです。

### <a name="remarks"></a>解説

仮想キー コードと修飾子キーを組み合わせて、キーボード ショートカットを定義します。

## <a name="chotkeyctrlgethotkeyname"></a><a name="gethotkeyname"></a>キーキー名を取得します。

ホット キーのローカライズされた名前を取得します。

```
CString GetHotKeyName() const;
```

### <a name="return-value"></a>戻り値

現在選択されているホット キーのローカライズされた名前。 ホット キーが選択されていない場合は`GetHotKeyName`、空の文字列を返します。

### <a name="remarks"></a>解説

このメンバー関数が返す名前は、キーボード ドライバーから取得されます。 ローカライズされていないキーボード ドライバーは、ローカライズ版の Windows にインストールできます。

## <a name="chotkeyctrlgetkeyname"></a><a name="getkeyname"></a>キーネームを取得します。

指定した仮想キー コードに割り当てられたキーのローカライズされた名前を取得します。

```
static CString GetKeyName(
    UINT vk,
    BOOL fExtended);
```

### <a name="parameters"></a>パラメーター

*Vk*<br/>
仮想キー コード。

*f 拡張*<br/>
仮想キー コードが拡張キーの場合は TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

*vk*パラメーターで指定されたキーのローカライズされた名前。 キーにマップされた名前がない場合は、`GetKeyName`空の文字列を返します。

### <a name="remarks"></a>解説

この関数が返すキー名はキーボード ドライバーから取得されるため、ローカライズされていないキーボード ドライバーをローカライズ版の Windows にインストールできます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#69](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]

## <a name="chotkeyctrlsethotkey"></a><a name="sethotkey"></a>セットキーキー

ホット キー コントロールのキーボード ショートカットを設定します。

```cpp
void SetHotKey(
    WORD wVirtualKeyCode,
    WORD wModifiers);
```

### <a name="parameters"></a>パラメーター

*キーコード*<br/>
[in]キーボード ショートカットの仮想キー コード。 標準の仮想キー コードの一覧については、Winuser.h を参照してください。

*w修飾子*<br/>
[in]キーボード ショートカットの修飾キーを示すフラグのビットごとの組み合わせ (OR)。

修飾子フラグは次のとおりです。

|フラグ|対応するキー|
|----------|-----------------------|
|HOTKEYF_ALT|ALT キー|
|HOTKEYF_CONTROL|Ctrl キー|
|HOTKEYF_EXT|拡張キー|
|HOTKEYF_SHIFT|Shift キー|

### <a name="remarks"></a>解説

仮想キー コードと修飾子キーを組み合わせて、キーボード ショートカットを定義します。

## <a name="chotkeyctrlsetrules"></a><a name="setrules"></a>次のルールを設定します。

ホット キー コントロールの無効な組み合わせと既定の修飾子の組み合わせを定義します。

```cpp
void SetRules(
    WORD wInvalidComb,
    WORD wModifiers);
```

### <a name="parameters"></a>パラメーター

*w無効なコーム*<br/>
無効なキーの組み合わせを指定するフラグの配列。 次の値を組み合わせて使用できます。

- alt をHKCOMB_A

- ctrl をHKCOMB_C

- ctrl キーを押しながら Alt キーを押HKCOMB_CA

- 変更されていないキーをHKCOMB_NONE

- シフトHKCOMB_S

- HKCOMB_SA SHIFT キーを押しながら ALT キーを押す

- HKCOMB_SC Shift キーを押しながら Ctrl キーを押す

- HKCOMB_SCA シフト + Ctrl + Alt キー

*w修飾子*<br/>
ユーザーが無効な組み合わせを入力したときに使用するキーの組み合わせを指定するフラグの配列。 修飾子フラグの詳細については、「 [GetHotKey](#gethotkey)」を参照してください。

### <a name="remarks"></a>解説

ユーザーが*wInvalidComb*で指定されたフラグで定義されている無効なキーの組み合わせを入力すると、システムは OR 演算子を使用して、ユーザーが入力したキーと*wModifiers*で指定されたフラグを結合します。 結果のキーの組み合わせは、文字列に変換され、ホット キー コントロールに表示されます。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
