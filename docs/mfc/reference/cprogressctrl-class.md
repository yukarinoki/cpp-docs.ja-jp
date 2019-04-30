---
title: CProgressCtrl クラス
ms.date: 11/04/2016
f1_keywords:
- CProgressCtrl
- AFXCMN/CProgressCtrl
- AFXCMN/CProgressCtrl::CProgressCtrl
- AFXCMN/CProgressCtrl::Create
- AFXCMN/CProgressCtrl::CreateEx
- AFXCMN/CProgressCtrl::GetBarColor
- AFXCMN/CProgressCtrl::GetBkColor
- AFXCMN/CProgressCtrl::GetPos
- AFXCMN/CProgressCtrl::GetRange
- AFXCMN/CProgressCtrl::GetState
- AFXCMN/CProgressCtrl::GetStep
- AFXCMN/CProgressCtrl::OffsetPos
- AFXCMN/CProgressCtrl::SetBarColor
- AFXCMN/CProgressCtrl::SetBkColor
- AFXCMN/CProgressCtrl::SetMarquee
- AFXCMN/CProgressCtrl::SetPos
- AFXCMN/CProgressCtrl::SetRange
- AFXCMN/CProgressCtrl::SetState
- AFXCMN/CProgressCtrl::SetStep
- AFXCMN/CProgressCtrl::StepIt
helpviewer_keywords:
- CProgressCtrl [MFC], CProgressCtrl
- CProgressCtrl [MFC], Create
- CProgressCtrl [MFC], CreateEx
- CProgressCtrl [MFC], GetBarColor
- CProgressCtrl [MFC], GetBkColor
- CProgressCtrl [MFC], GetPos
- CProgressCtrl [MFC], GetRange
- CProgressCtrl [MFC], GetState
- CProgressCtrl [MFC], GetStep
- CProgressCtrl [MFC], OffsetPos
- CProgressCtrl [MFC], SetBarColor
- CProgressCtrl [MFC], SetBkColor
- CProgressCtrl [MFC], SetMarquee
- CProgressCtrl [MFC], SetPos
- CProgressCtrl [MFC], SetRange
- CProgressCtrl [MFC], SetState
- CProgressCtrl [MFC], SetStep
- CProgressCtrl [MFC], StepIt
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
ms.openlocfilehash: 15241485278f09d16c86fc7274f2fc1d85a7a2f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372414"
---
# <a name="cprogressctrl-class"></a>CProgressCtrl クラス

Windows コモン プログレス バー コントロールの機能が用意されています。

## <a name="syntax"></a>構文

```
class CProgressCtrl : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CProgressCtrl::CProgressCtrl](#cprogressctrl)|`CProgressCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CProgressCtrl::Create](#create)|進行状況バー コントロールを作成しにアタッチします、`CProgressCtrl`オブジェクト。|
|[CProgressCtrl::CreateEx](#createex)|指定した Windows の拡張スタイルを使用して進行状況コントロールを作成しにアタッチします、`CProgressCtrl`オブジェクト。|
|[CProgressCtrl::GetBarColor](#getbarcolor)|現在の進行状況バー コントロールの進行状況インジケーターのバーの色を取得します。|
|[CProgressCtrl::GetBkColor](#getbkcolor)|現在の進行状況バーの背景色を取得します。|
|[CProgressCtrl::GetPos](#getpos)|進行状況バーの現在の位置を取得します。|
|[CProgressCtrl::GetRange](#getrange)|進行状況バー コントロールの範囲の下限と上限の制限を取得します。|
|[CProgressCtrl::GetState](#getstate)|現在の進行状況バー コントロールの状態を取得します。|
|[CProgressCtrl::GetStep](#getstep)|進行状況バーが、現在の進行状況バー コントロールのステップの増分値を取得します。|
|[CProgressCtrl::OffsetPos](#offsetpos)|指定された増分で進行状況バー コントロールの現在位置を進めます、新しい位置を反映するようにバーを再描画します。|
|[CProgressCtrl::SetBarColor](#setbarcolor)|現在の進行状況バー コントロールでは、進行状況インジケーターのバーの色を設定します。|
|[CProgressCtrl::SetBkColor](#setbkcolor)|進行状況バーの背景色を設定します。|
|[CProgressCtrl::SetMarquee](#setmarquee)|現在の進行状況バー コントロールのマーキー モードをオンまたはオフになります。|
|[CProgressCtrl::SetPos](#setpos)|進行状況バー コントロールの現在の位置を設定し、新しい位置を反映するようにバーを再描画します。|
|[CProgressCtrl::SetRange](#setrange)|進行状況バー コントロールの最小値と最大範囲を設定し、新しい範囲を反映するようにバーを再描画します。|
|[CProgressCtrl::SetState](#setstate)|現在の進行状況バー コントロールの状態を設定します。|
|[CProgressCtrl::SetStep](#setstep)|進行状況バー コントロールのステップの増分値を指定します。|
|[CProgressCtrl::StepIt](#stepit)|増分の進行状況バー コントロールの現在位置を進めます (を参照してください[SetStep](#setstep)) し、新しい位置を反映するように、バーを再描画します。|

## <a name="remarks"></a>Remarks

進行状況バー コントロールは、アプリケーションが時間のかかる操作の進行状況を示すために使用できるウィンドウです。 左から右、システムで強調表示色として処理の進行状況に徐々 に塗りつぶされる四角形で構成されます。

進行状況バー コントロールは、範囲と現在の位置をが。 範囲は、操作の合計継続時間を表し、現在の位置は、アプリケーションが行った操作の完了に向けた進行状況を表します。 ウィンドウ プロシージャは、範囲と現在の位置を使用して、進行状況バーが強調表示色で塗りつぶすの割合を決定します。 範囲と現在位置の値が符号付き整数として表されるので、現在位置の値の可能な範囲は 2,147, 483,647 包括-2,147, 483,648 です。

使用しての詳細については`CProgressCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CProgressCtrl](../../mfc/using-cprogressctrl.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CProgressCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

##  <a name="cprogressctrl"></a>  CProgressCtrl::CProgressCtrl

`CProgressCtrl` オブジェクトを構築します。

```
CProgressCtrl();
```

### <a name="remarks"></a>Remarks

構築した後、`CProgressCtrl`オブジェクト、呼び出す`CProgressCtrl::Create`進行状況バー コントロールを作成します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CProgressCtrl#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_1.cpp)]

##  <a name="create"></a>  CProgressCtrl::Create

進行状況バー コントロールを作成しにアタッチします、`CProgressCtrl`オブジェクト。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
進行状況バー コントロールのスタイルを指定します。 ウィンドウ stylesdescribed 内の任意の組み合わせを適用[CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa)次の進行状況バー コントロールのスタイルをコントロールに加え、Windows sdk:

- PBS_VERTICAL 表示では、進行状況を垂直方向に、上下から。 このフラグを設定せず、進行状況バー コントロールは、右に水平方向、左を表示します。

- PBS_SMOOTH 表示段階、smooth、進行状況バー コントロールに入力します。 このフラグを設定しないブロックのコントロールを生成します。

*rect*<br/>
進行状況バー コントロールのサイズと位置を指定します。 いずれかのことができます、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](/previous-versions/dd162897\(v=vs.85\))構造体。 指定した座標がのクライアント領域を基準とは、コントロールは、子ウィンドウにある必要があります、ため、 *pParentWnd*します。

*pParentWnd*<br/>
通常、進行状況バー コントロールの親ウィンドウを指定します、`CDialog`します。 NULL は指定できません。

*nID*<br/>
進行状況バー コントロールの ID を指定します

### <a name="return-value"></a>戻り値

TRUE の場合、`CProgressCtrl`オブジェクトが正常に作成されました。 それ以外の場合は FALSE。

### <a name="remarks"></a>Remarks

構築する、 `CProgressCtrl` 2 つのステップ内のオブジェクト。 最初に、作成するコンス トラクターを呼び出し、`CProgressCtrl`オブジェクトを呼び出して`Create`、進行状況バー コントロールを作成します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CProgressCtrl#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_2.cpp)]

##  <a name="createex"></a>  CProgressCtrl::CreateEx

コントロール (子ウィンドウ) を作成しに関連付けます、`CProgressCtrl`オブジェクト。

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
作成されるコントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧は、次を参照してください。、 *dwExStyle*パラメーターを[CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK に含まれています。

*dwStyle*<br/>
進行状況バー コントロールのスタイルを指定します。 説明されているウィンドウのスタイルの任意の組み合わせを適用[CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) Windows SDK に含まれています。

*rect*<br/>
参照を[RECT](/previous-versions/dd162897\(v=vs.85\))のクライアント座標で、作成するには、ウィンドウの位置とサイズを記述する構造体*pParentWnd*します。

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*nID*<br/>
コントロールの子ウィンドウ ID

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

使用`CreateEx`の代わりに[作成](#create)、Windows の拡張スタイルの先頭で指定された、Windows の拡張スタイルを適用する**WS_EX**します。

##  <a name="getbarcolor"></a>  CProgressCtrl::GetBarColor

現在の進行状況バー コントロールの進行状況インジケーターのバーの色を取得します。

```
COLORREF GetBarColor() const;
```

### <a name="return-value"></a>戻り値

として現在の進行状況バーの色が表される、 [COLORREF](/windows/desktop/gdi/colorref)値、またはとき、進行状況インジケーターのバーの色が既定の色である場合。

### <a name="remarks"></a>Remarks

このメソッドは、送信、 [PBM_GETBARCOLOR](/windows/desktop/Controls/pbm-getbarcolor)メッセージは、Windows SDK で説明します。

##  <a name="getbkcolor"></a>  CProgressCtrl::GetBkColor

現在の進行状況バーの背景色を取得します。

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>戻り値

として現在の進行状況バーの背景色が表される、 [COLORREF](/windows/desktop/gdi/colorref)値。

### <a name="remarks"></a>Remarks

このメソッドは、送信、 [PBM_GETBKCOLOR](/windows/desktop/Controls/pbm-getbkcolor)メッセージは、Windows SDK で説明します。

##  <a name="getpos"></a>  CProgressCtrl::GetPos

進行状況バーの現在の位置を取得します。

```
int GetPos();
```

### <a name="return-value"></a>戻り値

進行状況バー コントロールの位置。

### <a name="remarks"></a>Remarks

進行状況バー コントロールの位置が画面で、物理的な場所ではありませんではなく上部と下部の範囲で示された[SetRange](#setrange)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CProgressCtrl#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_3.cpp)]

##  <a name="getrange"></a>  CProgressCtrl::GetRange

現在の下限と上限の制限、または進行状況バー コントロールの範囲を取得します。

```
void GetRange(
    int& nLower,
    int& nUpper);
```

### <a name="parameters"></a>パラメーター

*nLower*<br/>
進行状況バー コントロールの下限値を受け取る整数への参照。

*nUpper*<br/>
進行状況バー コントロールの上限値を受け取る整数への参照。

### <a name="remarks"></a>Remarks

この関数によって参照される整数への下限と上限の制限の値をコピーする*上限値*と*下限*、それぞれします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CProgressCtrl#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_4.cpp)]

##  <a name="getstate"></a>  CProgressCtrl::GetState

現在の進行状況バー コントロールの状態を取得します。

```
int GetState() const;
```

### <a name="return-value"></a>戻り値

次の値の 1 つは、現在の進行状況バー コントロールの状態。

|[値]|状態|
|-----------|-----------|
|PBST_NORMAL|処理中|
|PBST_ERROR|Error|
|PBST_PAUSED|一時停止|

### <a name="remarks"></a>Remarks

このメソッドは、送信、 [PBM_GETSTATE](/windows/desktop/Controls/pbm-getstate)メッセージは、Windows SDK で説明します。

### <a name="example"></a>例

次のコード例では、進行状況バー コントロールにプログラムでアクセスするために使用される `m_progressCtrl` 変数を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>例

次のコード例では、現在の進行状況バー コントロールの状態を取得します。

[!code-cpp[NVC_MFC_CProgressCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_6.cpp)]

##  <a name="getstep"></a>  CProgressCtrl::GetStep

進行状況バーが、現在の進行状況バー コントロールのステップの増分値を取得します。

```
int GetStep() const;
```

### <a name="return-value"></a>戻り値

進行状況バーの増分値。

### <a name="remarks"></a>Remarks

ステップの増分値は、量への呼び出し[CProgressCtrl::StepIt](#stepit)進行状況バーの現在の位置が増加します。

このメソッドは、送信、 [PBM_GETSTEP](/windows/desktop/Controls/pbm-getstep)メッセージは、Windows SDK で説明します。

### <a name="example"></a>例

次のコード例では、進行状況バー コントロールにプログラムでアクセスするために使用される `m_progressCtrl` 変数を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>例

次のコード例では、現在の進行状況バー コントロールの増分値を取得します。

[!code-cpp[NVC_MFC_CProgressCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_7.cpp)]

##  <a name="offsetpos"></a>  CProgressCtrl::OffsetPos

指定された増分値で、進行状況バー コントロールの現在位置を進めます*nPos*し、新しい位置を反映するように、バーを再描画します。

```
int OffsetPos(int nPos);
```

### <a name="parameters"></a>パラメーター

*nPos*<br/>
位置を進める量。

### <a name="return-value"></a>戻り値

前に、進行状況バー コントロールの位置。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CProgressCtrl#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_8.cpp)]

##  <a name="setbarcolor"></a>  CProgressCtrl::SetBarColor

現在の進行状況バー コントロールでは、進行状況インジケーターのバーの色を設定します。

```
COLORREF SetBarColor(COLORREF clrBar);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*clrBar*|[in]A [COLORREF](/windows/desktop/gdi/colorref)新しい進行状況インジケーターのバーの色を指定する値。 既定の色を使用する進行状況バーが発生するときを指定します。|

### <a name="return-value"></a>戻り値

として表される、進行状況インジケーターのバーの前の色、 [COLORREF](/windows/desktop/gdi/colorref)値、またはときの進行状況インジケーターのバーの色が既定の色である場合。

### <a name="remarks"></a>Remarks

`SetBarColor`メソッドは、進行状況バーの色場合にのみ、Windows Vista 設定[テーマ](/windows/desktop/Controls/visual-styles-overview)は無効です。

このメソッドは、送信、 [PBM_SETBARCOLOR](/windows/desktop/Controls/pbm-setbarcolor)メッセージは、Windows SDK で説明します。

### <a name="example"></a>例

次のコード例では、進行状況バー コントロールにプログラムでアクセスするために使用される `m_progressCtrl` 変数を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>例

次のコード例では、赤、緑、青、または既定値に進行状況バーの色を変更します。

[!code-cpp[NVC_MFC_CProgressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_9.cpp)]

##  <a name="setbkcolor"></a>  CProgressCtrl::SetBkColor

進行状況バーの背景色を設定します。

```
COLORREF SetBkColor(COLORREF clrNew);
```

### <a name="parameters"></a>パラメーター

*clrNew*<br/>
新しい背景色を示す COLORREF 値。 進行状況バーの既定の背景色を使用するときの値を指定します。

### <a name="return-value"></a>戻り値

[COLORREF](/windows/desktop/gdi/colorref)場合は、既定の色の背景色は、前の背景色またはときを示す値。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CProgressCtrl#6](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_10.cpp)]

##  <a name="setmarquee"></a>  CProgressCtrl::SetMarquee

現在の進行状況バー コントロールのマーキー モードをオンまたはオフになります。

```
BOOL SetMarquee(
    BOOL fMarqueeMode,
    int nInterval);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*fMarqueeMode*|[in]True、on、または選択範囲のモードをオフにする場合は FALSE マーキー モードを有効にします。|
|*nInterval*|[in]時間マーキー アニメーションの更新間隔 (ミリ秒)。|

### <a name="return-value"></a>戻り値

このメソッドは、常に TRUE を返します。

### <a name="remarks"></a>Remarks

マーキーのモードがオンになっている場合は、進行状況バーがアニメーション化されるようにスクロール シアター マーキー サインオンします。

このメソッドは、送信、 [PBM_SETMARQUEE](/windows/desktop/Controls/pbm-setmarquee)メッセージは、Windows SDK で説明します。

### <a name="example"></a>例

次のコード例では、進行状況バー コントロールにプログラムでアクセスするために使用される `m_progressCtrl` 変数を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>例

次のコード例を起動し、マーキー スクロール アニメーションを停止します。

[!code-cpp[NVC_MFC_CProgressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_11.cpp)]

##  <a name="setpos"></a>  CProgressCtrl::SetPos

バーのコントロールの現在の位置で指定された進行状況を設定*nPos*し、新しい位置を反映するように、バーを再描画します。

```
int SetPos(int nPos);
```

### <a name="parameters"></a>パラメーター

*nPos*<br/>
進行状況バー コントロールの新しい位置。

### <a name="return-value"></a>戻り値

前に、進行状況バー コントロールの位置。

### <a name="remarks"></a>Remarks

進行状況バー コントロールの位置が画面で、物理的な場所ではありませんではなく上部と下部の範囲で示された[SetRange](#setrange)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CProgressCtrl#7](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_12.cpp)]

##  <a name="setrange"></a>  CProgressCtrl::SetRange

進行状況バー コントロールの範囲の上限と下限を設定し、新しい範囲を反映するようにバーを再描画します。

```
void SetRange(
    short nLower,
    short nUpper);

void SetRange32(
    int nLower,
    int nUpper);
```

### <a name="parameters"></a>パラメーター

*nLower*<br/>
範囲の下限値を指定します (既定値は 0)。

*nUpper*<br/>
範囲の上限を指定します (既定値は 100)。

### <a name="remarks"></a>Remarks

メンバー関数は、`SetRange32`プログレス コントロールの 32 ビットの範囲を設定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CProgressCtrl#8](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_13.cpp)]

##  <a name="setstate"></a>  CProgressCtrl::SetState

現在の進行状況バー コントロールの状態を設定します。

```
int SetState(int iState);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*iState*|[in]進行状況バーを設定する状態。 次のいずれかの値を使用します。<br /><br /> -PBST_NORMAL - 進行中です。<br />-PBST_ERROR - エラー<br />-PBST_PAUSED - 一時停止|

### <a name="return-value"></a>戻り値

現在の進行状況バー コントロールの直前の状態。

### <a name="remarks"></a>Remarks

このメソッドは、送信、 [PBM_SETSTATE](/windows/desktop/Controls/pbm-setstate)メッセージは、Windows SDK で説明します。

### <a name="example"></a>例

次のコード例では、進行状況バー コントロールにプログラムでアクセスするために使用される `m_progressCtrl` 変数を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>例

次のコード例は、現在の進行状況バー コントロールの状態を一時停止または処理中に設定します。

[!code-cpp[NVC_MFC_CProgressCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_14.cpp)]

##  <a name="setstep"></a>  CProgressCtrl::SetStep

進行状況バー コントロールのステップの増分値を指定します。

```
int SetStep(int nStep);
```

### <a name="parameters"></a>パラメーター

*nStep*<br/>
新しい増分値。

### <a name="return-value"></a>戻り値

前のステップの増分します。

### <a name="remarks"></a>Remarks

ステップの増分量への呼び出し`CProgressCtrl::StepIt`増加の進行状況バーの現在の位置。

既定の増分には 10 です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CProgressCtrl#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_15.cpp)]

##  <a name="stepit"></a>  CProgressCtrl::StepIt

増分の進行状況バー コントロールの現在位置を進め、新しい位置を反映するようにバーを再描画します。

```
int StepIt();
```

### <a name="return-value"></a>戻り値

前に、進行状況バー コントロールの位置。

### <a name="remarks"></a>Remarks

ステップの増分値が設定されて、`CProgressCtrl::SetStep`メンバー関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CProgressCtrl#10](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_16.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
