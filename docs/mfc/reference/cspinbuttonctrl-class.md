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
ms.openlocfilehash: 6f864a37c46158ab98776cd96d9f50d7cfaeb13d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58776350"
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
|[CSpinButtonCtrl::CSpinButtonCtrl](#cspinbuttonctrl)|`CSpinButtonCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSpinButtonCtrl::Create](#create)|スピン ボタン コントロールを作成しにアタッチします、`CSpinButtonCtrl`オブジェクト。|
|[CSpinButtonCtrl::CreateEx](#createex)|指定された Windows の拡張スタイルのスピン ボタン コントロールを作成しにアタッチします、`CSpinButtonCtrl`オブジェクト。|
|[CSpinButtonCtrl::GetAccel](#getaccel)|スピン ボタン コントロールの高速化の情報を取得します。|
|[CSpinButtonCtrl::GetBase](#getbase)|スピン ボタン コントロールの現在の基数を取得します。|
|[CSpinButtonCtrl::GetBuddy](#getbuddy)|現在の連動ウィンドウへのポインターを取得します。|
|[CSpinButtonCtrl::GetPos](#getpos)|スピン ボタン コントロールの現在の位置を取得します。|
|[CSpinButtonCtrl::GetRange](#getrange)|スピン ボタン コントロールの上限と下限制限 (範囲) を取得します。|
|[CSpinButtonCtrl::SetAccel](#setaccel)|スピン ボタン コントロールの高速化を設定します。|
|[CSpinButtonCtrl::SetBase](#setbase)|スピン ボタン コントロールの基本クラスを設定します。|
|[CSpinButtonCtrl::SetBuddy](#setbuddy)|スピン ボタン コントロールの連動ウィンドウを設定します。|
|[CSpinButtonCtrl::SetPos](#setpos)|コントロールの現在の位置を設定します。|
|[CSpinButtonCtrl::SetRange](#setrange)|スピン ボタン コントロールの上限と下限 (範囲) を設定します。|

## <a name="remarks"></a>Remarks

「スピン ボタン コントロール」(、アップダウン コントロールとも呼ばれます) は、インクリメントまたはデクリメントのスクロール位置または横にあるコントロールに表示される番号などの値をユーザーがクリックできる矢印ボタンのペアです。 スピン ボタン コントロールに関連付けられている値には、現在の位置が呼び出されます。 スピン ボタン コントロールが、「友人ウィンドウ」と呼ばれるコントロールと共に使用されるほとんどの場合

このコントロール (つまり、`CSpinButtonCtrl`クラス) は以降、Windows 95/98 および Windows NT version 3.51 で実行するプログラムにのみ使用できます。

スピン ボタン コントロールとその関連ウィンドウは、ユーザーに、多くの場合、1 つのコントロールのようになります。 スピン ボタン コントロールを自動的に配置自体の連動ウィンドウの横にあると、現在の位置の連動ウィンドウのキャプションを自動的に設定を指定できます。 エディット コントロールでスピン ボタン コントロールを使用すると、数値入力の入力を求めます。

最大で、現在の位置を移動上矢印をクリックし、最小値には、現在の位置を移動します下向き矢印をクリックします。 既定では、最小値は 100 と最大値は 0。 最小値の設定が (たとえば、既定の設定が使用されます) ときに設定し、上向きの矢印がクリックすると、最大値より大きい位置の値と下矢印をクリックすると増大にします。

関連ウィンドウなしのスピン ボタン コントロールは、簡略化されたスクロール バーの一種として機能します。 たとえば、タブ コントロールでは、スピン ボタン コントロールの追加のタブをスクロールして表示するユーザーを有効にする場合がありますが表示されます。

使用しての詳細については`CSpinButtonCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CSpinButtonCtrl](../../mfc/using-cspinbuttonctrl.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSpinButtonCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

##  <a name="create"></a>  CSpinButtonCtrl::Create

スピン ボタン コントロールを作成しにアタッチします、`CSpinButtonCtrl`オブジェクト.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
スピン ボタン コントロールのスタイルを指定します。 スピン ボタン コントロールのスタイルの任意の組み合わせをコントロールに適用されます。 これらのスタイルが記載されています[アップダウン コントロールのスタイル](/windows/desktop/Controls/up-down-control-styles)Windows SDK に含まれています。

*rect*<br/>
スピン ボタン コントロールのサイズと位置を指定します。 いずれかのことができます、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](/previous-versions/dd162897\(v=vs.85\))構造体

*pParentWnd*<br/>
スピン ボタン コントロールの親ウィンドウ、通常へのポインター、`CDialog`します。 NULL は指定できません。

*nID*<br/>
スピン ボタン コントロールの ID を指定します

### <a name="return-value"></a>戻り値

初期化が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

構築する、`CSpinButtonCtrl`まずオブジェクトの 2 つの手順で、コンス トラクターを呼び出してを呼び出して`Create`、スピン ボタン コントロールを作成しにアタッチする`CSpinButtonCtrl`オブジェクト。

拡張ウィンドウ スタイルのスピン ボタン コントロールを作成するには、呼び出す[CSpinButtonCtrl::CreateEx](#createex)の代わりに`Create`します。

##  <a name="createex"></a>  CSpinButtonCtrl::CreateEx

コントロール (子ウィンドウ) を作成しに関連付けます、`CSpinButtonCtrl`オブジェクト。

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
作成されるコントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、 *dwExStyle*パラメーター [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK に含まれています。

*dwStyle*<br/>
スピン ボタン コントロールのスタイルを指定します。 スピン ボタン コントロールのスタイルの任意の組み合わせをコントロールに適用されます。 これらのスタイルが記載されています[アップダウン コントロールのスタイル](/windows/desktop/Controls/up-down-control-styles)Windows SDK に含まれています。

*rect*<br/>
参照を[RECT](/previous-versions/dd162897\(v=vs.85\))のクライアント座標で、作成するには、ウィンドウの位置とサイズを記述する構造体*pParentWnd*します。

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*nID*<br/>
コントロールの子ウィンドウ ID

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

使用`CreateEx`の代わりに[作成](#create)Windows の拡張スタイル先頭 WS_EX で指定された、Windows の拡張スタイルを適用します。

##  <a name="cspinbuttonctrl"></a>  CSpinButtonCtrl::CSpinButtonCtrl

`CSpinButtonCtrl` オブジェクトを構築します。

```
CSpinButtonCtrl();
```

##  <a name="getaccel"></a>  CSpinButtonCtrl::GetAccel

スピン ボタン コントロールの高速化の情報を取得します。

```
UINT GetAccel(
    int nAccel,
    UDACCEL* pAccel) const;
```

### <a name="parameters"></a>パラメーター

*nAccel*<br/>
指定された配列の要素数*pAccel*します。

*pAccel*<br/>
配列を指すポインター [UDACCEL](/windows/desktop/api/commctrl/ns-commctrl-_udaccel)の高速化の情報を受け取る構造体。

### <a name="return-value"></a>戻り値

アクセラレータの構造体の数を取得します。

##  <a name="getbase"></a>  CSpinButtonCtrl::GetBase

スピン ボタン コントロールの現在の基数を取得します。

```
UINT GetBase() const;
```

### <a name="return-value"></a>戻り値

現在の基本値。

##  <a name="getbuddy"></a>  CSpinButtonCtrl::GetBuddy

現在の連動ウィンドウへのポインターを取得します。

```
CWnd* GetBuddy() const;
```

### <a name="return-value"></a>戻り値

現在の連動ウィンドウへのポインター。

##  <a name="getpos"></a>  CSpinButtonCtrl::GetPos

スピン ボタン コントロールの現在の位置を取得します。

```
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;
```

### <a name="parameters"></a>パラメーター

*lpbError*<br/>
値の場合は 0 に設定されているブール値へのポインターは、正常に取得した、または 0 以外の場合、エラーが発生します。 このパラメーターが NULL に設定されている場合、エラーは報告されません。

### <a name="return-value"></a>戻り値

最初のバージョンでは、下位ワードで 16 ビットの現在位置を返します。 上位ワードは、エラーが発生した場合、0 以外の場合は。

2 番目のバージョンでは、32 ビットの位置を返します。

### <a name="remarks"></a>Remarks

返される値を処理するとき、コントロールが連動ウィンドウのキャプションに基づく現在の位置を更新します。 コントロールは、関連ウィンドウがない場合、またはキャプションを無効または範囲外の値を指定する場合、エラーを返します。

##  <a name="getrange"></a>  CSpinButtonCtrl::GetRange

スピン ボタン コントロールの上限と下限制限 (範囲) を取得します。

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
コントロールの下限値を受け取る整数への参照。

*上限*<br/>
コントロールの上限値を受け取る整数への参照。

### <a name="return-value"></a>戻り値

最初のバージョンでは、上限と下限を格納している 32 ビット値を返します。 下位ワードは、コントロールの上限と、上位の単語が下限値。

### <a name="remarks"></a>Remarks

メンバー関数は、`GetRange32`スピン ボタン コントロールの範囲を 32 ビット整数として取得します。

##  <a name="setaccel"></a>  CSpinButtonCtrl::SetAccel

スピン ボタン コントロールの高速化を設定します。

```
BOOL SetAccel(
    int nAccel,
    UDACCEL* pAccel);
```

### <a name="parameters"></a>パラメーター

*nAccel*<br/>
数[UDACCEL](/windows/desktop/api/commctrl/ns-commctrl-_udaccel)構造体で指定された*pAccel*します。

*pAccel*<br/>
高速化の情報を含む UDACCEL 構造体の配列へのポインター。 要素は、に基づいて昇順で並べ替える必要があります、`nSec`メンバー。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

##  <a name="setbase"></a>  CSpinButtonCtrl::SetBase

スピン ボタン コントロールの基本クラスを設定します。

```
int SetBase(int nBase);
```

### <a name="parameters"></a>パラメーター

*nBase*<br/>
コントロールの新しい基本値。 10 は 10 進数または 16 の 16 進数を指定できます。

### <a name="return-value"></a>戻り値

成功した場合は、前の基本値または 0 の場合は、無効な基数を指定します。

### <a name="remarks"></a>Remarks

基本の値は、連動ウィンドウが 10 進数または 16 進数の桁の番号を表示するかどうかを判断します。 16 進数は、常に署名します。10 進数が署名されます。

##  <a name="setbuddy"></a>  CSpinButtonCtrl::SetBuddy

スピン ボタン コントロールの連動ウィンドウを設定します。

```
CWnd* SetBuddy(CWnd* pWndBuddy);
```

### <a name="parameters"></a>パラメーター

*pWndBuddy*<br/>
新しい関連ウィンドウへのポインター。

### <a name="return-value"></a>戻り値

前の連動ウィンドウへのポインター。

### <a name="remarks"></a>Remarks

スピン コントロールは、一部のコンテンツを表示するエディット コントロールなどの別のウィンドウに関連付けられてをほぼ常にします。 この他のウィンドウは、スピン コントロールの「メンバー」と呼ばれます。

##  <a name="setpos"></a>  CSpinButtonCtrl::SetPos

スピン ボタン コントロールの現在位置を設定します。

```
int SetPos(int nPos);
int SetPos32(int nPos);
```

### <a name="parameters"></a>パラメーター

*nPos*<br/>
コントロールの新しい位置。 この値は、コントロールの上限と下限に指定した範囲でなければなりません。

### <a name="return-value"></a>戻り値

前の位置 (16 ビット精度`SetPos`、32 ビットの精度`SetPos32`)。

### <a name="remarks"></a>Remarks

`SetPos32` 32 ビットの位置を設定します。

##  <a name="setrange"></a>  CSpinButtonCtrl::SetRange

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

*上限値*と*下限*<br/>
コントロールの上限と下限。 `SetRange`UD_MINVAL; より小さいさらに、2 つの制限の違いできません ud_maxval やも制限は UD_MAXVAL より大きくすることができます。 `SetRange32` 制限; での制限を配置しません。任意の整数を使用します。

### <a name="remarks"></a>Remarks

メンバー関数は、`SetRange32`スピン ボタン コントロールの 32 ビットの範囲を設定します。

> [!NOTE]
>  スピン ボタンの既定の範囲は、ゼロ (0) に設定した最大値、最小値が 100 に設定します。 最大値は最小値より小さいため、上向きの矢印をクリックすると低下し、は、位置下矢印をクリックすると向上します。 使用`CSpinButtonCtrl::SetRange`をこれらの値を調整します。

## <a name="see-also"></a>関連項目

[MFC サンプル CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CSliderCtrl クラス](../../mfc/reference/csliderctrl-class.md)
