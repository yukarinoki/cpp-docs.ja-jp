---
title: CSpinButtonCtrl クラス
ms.date: 11/04/2016
f1_keywords:
- CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::Create
- AFXCMN/CSpinButtonCtrl::CreateEx
- AFXCMN/CSpinButtonCtrl::GetAccel
- AFXCMN/CSpinButtonCtrl::GetBase
- AFXCMN/CSpinButtonCtrl::GetBuddy
- AFXCMN/CSpinButtonCtrl::GetPos
- AFXCMN/CSpinButtonCtrl::GetRange
- AFXCMN/CSpinButtonCtrl::SetAccel
- AFXCMN/CSpinButtonCtrl::SetBase
- AFXCMN/CSpinButtonCtrl::SetBuddy
- AFXCMN/CSpinButtonCtrl::SetPos
- AFXCMN/CSpinButtonCtrl::SetRange
helpviewer_keywords:
- CSpinButtonCtrl [MFC], CSpinButtonCtrl
- CSpinButtonCtrl [MFC], Create
- CSpinButtonCtrl [MFC], CreateEx
- CSpinButtonCtrl [MFC], GetAccel
- CSpinButtonCtrl [MFC], GetBase
- CSpinButtonCtrl [MFC], GetBuddy
- CSpinButtonCtrl [MFC], GetPos
- CSpinButtonCtrl [MFC], GetRange
- CSpinButtonCtrl [MFC], SetAccel
- CSpinButtonCtrl [MFC], SetBase
- CSpinButtonCtrl [MFC], SetBuddy
- CSpinButtonCtrl [MFC], SetPos
- CSpinButtonCtrl [MFC], SetRange
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
ms.openlocfilehash: 4230d43bad8bcc15bcb26aaf0357e70216909ba1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318123"
---
# <a name="cspinbuttonctrl-class"></a>CSpinButtonCtrl クラス

Windows コモン スピン ボタン コントロールの機能が用意されています。

## <a name="syntax"></a>構文

```
class CSpinButtonCtrl : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CスピンボタンCtrl::CスピンボタンCtrl](#cspinbuttonctrl)|`CSpinButtonCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をクリックします。](#create)|スピン ボタン コントロールを作成し、`CSpinButtonCtrl`オブジェクトにアタッチします。|
|[をクリックします。](#createex)|指定した Windows 拡張スタイルを使用してスピン ボタン コントロールを`CSpinButtonCtrl`作成し、オブジェクトにアタッチします。|
|[CスピンボタンCtrl::ゲットアッセル](#getaccel)|スピン ボタン コントロールのアクセラレータ情報を取得します。|
|[をクリックします。](#getbase)|スピン ボタン コントロールの現在のベースを取得します。|
|[をクリックします。](#getbuddy)|現在の関連ウィンドウへのポインターを取得します。|
|[をクリックします。](#getpos)|スピン ボタン コントロールの現在位置を取得します。|
|[をクリックします。](#getrange)|スピン ボタン コントロールの上限と下限 (範囲) を取得します。|
|[CスピンボタンCtrl::セットアッセル](#setaccel)|スピン ボタン コントロールの加速度を設定します。|
|[をクリックします。](#setbase)|スピン ボタン コントロールのベースを設定します。|
|[をクリックします。](#setbuddy)|スピン ボタン コントロールのバディ ウィンドウを設定します。|
|[をクリックします。](#setpos)|コントロールの現在位置を設定します。|
|[をクリックします。](#setrange)|スピン ボタン コントロールの上限と下限 (範囲) を設定します。|

## <a name="remarks"></a>解説

"スピン ボタン コントロール" (アップダウン コントロールとも呼ばれます) は、スクロール位置やコンパニオン コントロールに表示される数値など、値をインクリメントまたはデクリメントするためにクリックできる矢印ボタンのペアです。 スピン ボタン コントロールに関連付けられている値を、現在の位置と呼びます。 スピン ボタン コントロールは、コンパニオン コントロールと呼ばれる "関連ウィンドウ" と呼ばれる場合に最もよく使用されます。

このコントロール (および`CSpinButtonCtrl`クラス) は、Windows 95/98 および Windows NT バージョン 3.51 以降で実行されているプログラムでのみ使用できます。

ユーザーには、スピン ボタン コントロールとそのバディ ウィンドウは、単一のコントロールのように見えることがよくあります。 スピン ボタン コントロールが自動的に同じウィンドウの横に配置され、自動的に現在の位置に対して、そのキャプションを設定するように指定できます。 スピン ボタン コントロールとエディット コントロールを使用して、数値入力を求めるプロンプトを表示できます。

上矢印をクリックすると、現在の位置が最大値に向かって移動し、下向き矢印をクリックすると、現在の位置が最小値に向かって移動します。 デフォルトでは、最小値は 100、最大値は 0 です。 最小設定が最大値より大きい場合 (既定の設定を使用する場合など)、上矢印をクリックすると位置の値が小さくなり、下矢印をクリックすると、その設定が増えます。

相棒ウィンドウのないスピン ボタン コントロールは、一種の簡略化されたスクロール バーとして機能します。 たとえば、タブ コントロールには、ユーザーが追加のタブをスクロールして表示できるようにスピン ボタン コントロールが表示される場合があります。

の使用方法`CSpinButtonCtrl`の詳細については、「[コントロール](../../mfc/controls-mfc.md)」および[「CSpinButtonCtrl](../../mfc/using-cspinbuttonctrl.md)の使用」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSpinButtonCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

## <a name="cspinbuttonctrlcreate"></a><a name="create"></a>をクリックします。

スピン ボタン コントロールを作成し、オブジェクトに`CSpinButtonCtrl`アタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
スピン ボタン コントロールのスタイルを指定します。 スピン ボタン コントロール スタイルの任意の組み合わせをコントロールに適用します。 これらのスタイルについては、Windows SDK[のアップダウン コントロール スタイル](/windows/win32/Controls/up-down-control-styles)で説明します。

*Rect*<br/>
スピン ボタン コントロールのサイズと位置を指定します。 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](/previous-versions/dd162897\(v=vs.85\))構造体のいずれかです。

*pParentWnd*<br/>
スピン ボタン コントロールの親ウィンドウ (通常は`CDialog`. NULL にすることはできません。

*nID*<br/>
スピン ボタン コントロールの ID を指定します。

### <a name="return-value"></a>戻り値

初期化が成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

オブジェクトを`CSpinButtonCtrl`2 つの手順で作成するには、まず、コンストラクターを呼`Create`び出してから呼び出しを行います`CSpinButtonCtrl`。

拡張ウィンドウ スタイルを使用してスピン ボタン コントロールを作成するには、呼び出す[CSpinButtonCtrl::CreateEx](#createex) `Create`の代わりに.

## <a name="cspinbuttonctrlcreateex"></a><a name="createex"></a>をクリックします。

コントロール (子ウィンドウ) を作成し、オブジェクトに関連`CSpinButtonCtrl`付けます。

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
作成するコントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧については、Windows SDK の[CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)の*dwExStyle*パラメーターを参照してください。

*Dwstyle*<br/>
スピン ボタン コントロールのスタイルを指定します。 スピン ボタン コントロール スタイルの任意の組み合わせをコントロールに適用します。 これらのスタイルについては、Windows SDK[のアップダウン コントロール スタイル](/windows/win32/Controls/up-down-control-styles)で説明します。

*Rect*<br/>
作成するウィンドウのサイズと位置を記述する[RECT](/previous-versions/dd162897\(v=vs.85\))構造体への参照を *、 pParentWnd*のクライアント座標で指定します。

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*nID*<br/>
コントロールの子ウィンドウ ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

`CreateEx` [[作成]](#create)の代わりに、Windows 拡張スタイルの序文WS_EX_で指定された拡張 Windows スタイルを適用します。

## <a name="cspinbuttonctrlcspinbuttonctrl"></a><a name="cspinbuttonctrl"></a>CスピンボタンCtrl::CスピンボタンCtrl

`CSpinButtonCtrl` オブジェクトを構築します。

```
CSpinButtonCtrl();
```

## <a name="cspinbuttonctrlgetaccel"></a><a name="getaccel"></a>CスピンボタンCtrl::ゲットアッセル

スピン ボタン コントロールのアクセラレータ情報を取得します。

```
UINT GetAccel(
    int nAccel,
    UDACCEL* pAccel) const;
```

### <a name="parameters"></a>パラメーター

*ナッセル*<br/>
*pAccel*で指定された配列内の要素数。

*アッセル*<br/>
加速情報を受け取る[UDACCEL](/windows/win32/api/commctrl/ns-commctrl-udaccel)構造体の配列へのポインター。

### <a name="return-value"></a>戻り値

取得されたアクセラレータ構造の数。

## <a name="cspinbuttonctrlgetbase"></a><a name="getbase"></a>をクリックします。

スピン ボタン コントロールの現在のベースを取得します。

```
UINT GetBase() const;
```

### <a name="return-value"></a>戻り値

現在の基本値。

## <a name="cspinbuttonctrlgetbuddy"></a><a name="getbuddy"></a>をクリックします。

現在の関連ウィンドウへのポインターを取得します。

```
CWnd* GetBuddy() const;
```

### <a name="return-value"></a>戻り値

現在のウィンドウへのポインター。

## <a name="cspinbuttonctrlgetpos"></a><a name="getpos"></a>をクリックします。

スピン ボタン コントロールの現在位置を取得します。

```
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;
```

### <a name="parameters"></a>パラメーター

*エラー*<br/>
値が正常に取得された場合は 0 に設定されるブール値へのポインター、エラーが発生した場合は 0 以外の値を返します。 このパラメーターを NULL に設定すると、エラーは報告されません。

### <a name="return-value"></a>戻り値

最初のバージョンは、下位ワードの 16 ビットの現在位置を返します。 エラーが発生した場合、上位ワードは 0 以外です。

2 番目のバージョンは、32 ビットの位置を返します。

### <a name="remarks"></a>解説

返された値を処理すると、コントロールは、関連ウィンドウのキャプションに基づいて現在の位置を更新します。 関連ウィンドウがない場合、またはキャプションが無効または範囲外の値を指定している場合、コントロールはエラーを返します。

## <a name="cspinbuttonctrlgetrange"></a><a name="getrange"></a>をクリックします。

スピン ボタン コントロールの上限と下限 (範囲) を取得します。

```
DWORD GetRange() const;

void GetRange(
    int& lower,
    int& upper) const;

void GetRange32(
    int& lower,
    int &upper) const;
```

### <a name="parameters"></a>パラメーター

*低い*<br/>
コントロールの下限を受け取る整数への参照。

*上部*<br/>
コントロールの上限を受け取る整数への参照。

### <a name="return-value"></a>戻り値

最初のバージョンでは、上限と下限を含む 32 ビット値が返されます。 下位ワードはコントロールの上限であり、上位ワードは下限です。

### <a name="remarks"></a>解説

メンバー関数`GetRange32`は、スピン ボタン コントロールの範囲を 32 ビット整数として取得します。

## <a name="cspinbuttonctrlsetaccel"></a><a name="setaccel"></a>CスピンボタンCtrl::セットアッセル

スピン ボタン コントロールの加速度を設定します。

```
BOOL SetAccel(
    int nAccel,
    UDACCEL* pAccel);
```

### <a name="parameters"></a>パラメーター

*ナッセル*<br/>
*pAccel*で指定された[UDACCEL](/windows/win32/api/commctrl/ns-commctrl-udaccel)構造体の数。

*アッセル*<br/>
加速情報を含む UDACCEL 構造体の配列へのポインター。 要素は`nSec`、メンバーに基づいて昇順に並べ替える必要があります。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

## <a name="cspinbuttonctrlsetbase"></a><a name="setbase"></a>をクリックします。

スピン ボタン コントロールのベースを設定します。

```
int SetBase(int nBase);
```

### <a name="parameters"></a>パラメーター

*nベース*<br/>
コントロールの新しい基本値。 10 進数の場合は 10、16 進数の場合は 16 にすることができます。

### <a name="return-value"></a>戻り値

直前の基本値 (成功した場合) を返します。

### <a name="remarks"></a>解説

基本値は、関係ウィンドウに 10 進数または 16 進数のどちらで数値を表示するかを決定します。 16 進数は常に符号なしです。10 進数は符号付きです。

## <a name="cspinbuttonctrlsetbuddy"></a><a name="setbuddy"></a>をクリックします。

スピン ボタン コントロールのバディ ウィンドウを設定します。

```
CWnd* SetBuddy(CWnd* pWndBuddy);
```

### <a name="parameters"></a>パラメーター

*ド・ド・バ*<br/>
新しいバディ ウィンドウへのポインター。

### <a name="return-value"></a>戻り値

前のウィンドウへのポインター。

### <a name="remarks"></a>解説

スピン コントロールは、ほとんどの場合、コンテンツを表示するエディット コントロールなどの別のウィンドウに関連付けられます。 この他のウィンドウはスピン コントロールの "buddy" と呼ばれます。

## <a name="cspinbuttonctrlsetpos"></a><a name="setpos"></a>をクリックします。

スピン ボタン コントロールの現在位置を設定します。

```
int SetPos(int nPos);
int SetPos32(int nPos);
```

### <a name="parameters"></a>パラメーター

*Npo*<br/>
コントロールの新しい位置。 この値は、コントロールの上限と下限で指定された範囲内になければなりません。

### <a name="return-value"></a>戻り値

前の位置 (16 ビットの`SetPos`精度 、32 ビット`SetPos32`の精度)。

### <a name="remarks"></a>解説

`SetPos32`32 ビットの位置を設定します。

## <a name="cspinbuttonctrlsetrange"></a><a name="setrange"></a>をクリックします。

スピン ボタン コントロールの上限と下限 (範囲) を設定します。

```
void SetRange(
    short nLower,
    short nUpper);

void SetRange32(
    int nLower,
    int nUpper);
```

### <a name="parameters"></a>パラメーター

*nローワー*と*nUpper*<br/>
コントロールの上限と下限。 の`SetRange`場合、どちらの制限もUD_MAXVALより大きく、またはUD_MINVAL未満にすることはできません。また、2 つの制限の差がUD_MAXVALを超えることはできません。 `SetRange32`制限に制限はありません。任意の整数を使用します。

### <a name="remarks"></a>解説

このメンバー関数`SetRange32`は、スピン ボタン コントロールの 32 ビット範囲を設定します。

> [!NOTE]
> スピン ボタンの既定の範囲は、最大値がゼロ (0) に設定され、最小値が 100 に設定されます。 最大値が最小値より小さいため、上矢印をクリックすると位置が小さくなり、下矢印をクリックすると値が増えます。 これらの`CSpinButtonCtrl::SetRange`値を調整するために使用します。

## <a name="see-also"></a>関連項目

[サンプル CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/csliderctrl-class.md)
