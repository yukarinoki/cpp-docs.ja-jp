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
ms.openlocfilehash: c9e94e334318b32efcf8c9de681a78349ab12151
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751126"
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
|[をクリックします。](#cprogressctrl)|`CProgressCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[作成](#create)|プログレス バー コントロールを作成し、`CProgressCtrl`オブジェクトにアタッチします。|
|[をクリックします。](#createex)|指定した Windows 拡張スタイルを使用してプログレス コントロールを`CProgressCtrl`作成し、オブジェクトにアタッチします。|
|[をクリックします。](#getbarcolor)|現在のプログレス バー コントロールの進行状況インジケーター バーの色を取得します。|
|[をクリックします。](#getbkcolor)|現在のプログレス バーの背景色を取得します。|
|[をクリックします。](#getpos)|プログレス バーの現在の位置を取得します。|
|[をクリックします。](#getrange)|プログレス バー コントロールの範囲の下限と上限を取得します。|
|[状態を取得します。](#getstate)|現在のプログレス バー コントロールの状態を取得します。|
|[をクリックします。](#getstep)|現在のプログレス バー コントロールの進行状況バーのステップインクリメントを取得します。|
|[をクリックします。](#offsetpos)|プログレス バー コントロールの現在位置を指定した増分で進め、新しい位置を反映するようにバーを再描画します。|
|[をクリックします。](#setbarcolor)|現在のプログレス バー コントロールの進行状況インジケーター バーの色を設定します。|
|[をクリックします。](#setbkcolor)|プログレス バーの背景色を設定します。|
|[コグレスCtrl::セットマーキー](#setmarquee)|現在のプログレス バー コントロールのマーキー モードをオンまたはオフにします。|
|[をクリックします。](#setpos)|プログレス バー コントロールの現在位置を設定し、新しい位置を反映するようにバーを再描画します。|
|[をクリックします。](#setrange)|プログレス バー コントロールの最小範囲と最大範囲を設定し、新しい範囲を反映するようにバーを再描画します。|
|[状態を設定します。](#setstate)|現在の進行状況バー コントロールの状態を設定します。|
|[をクリックします。](#setstep)|プログレス バー コントロールのステップインクリメントを指定します。|
|[をクリックします。](#stepit)|進捗バー コントロールの現在位置をステップ増分[(SetStep](#setstep)を参照) だけ進み、新しい位置を反映するようにバーを再描画します。|

## <a name="remarks"></a>解説

進行状況バー コントロールは、アプリケーションが時間のかかる操作の進行状況を示すために使用できるウィンドウです。 これは、操作の進行に合ったシステムの強調表示色で、左から右に徐々に塗りつぶされる四角形で構成されます。

プログレス バー コントロールには、範囲と現在位置があります。 範囲は操作の合計期間を表し、現在の位置は、アプリケーションが操作を完了するための進行状況を表します。 ウィンドウ プロシージャでは、範囲と現在位置を使用して、強調表示色で塗りつぶすプログレス バーの割合を決定します。 範囲と現在位置の値は符号付き整数で表されるため、現在の位置値の可能な範囲は -2,147,483,648 から 2,147,483,647 までです。

の使用方法`CProgressCtrl`の詳細については、「[コントロール](../../mfc/controls-mfc.md)」および[「CProgressCtrl](../../mfc/using-cprogressctrl.md)の使用」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CProgressCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

## <a name="cprogressctrlcprogressctrl"></a><a name="cprogressctrl"></a>をクリックします。

`CProgressCtrl` オブジェクトを構築します。

```
CProgressCtrl();
```

### <a name="remarks"></a>解説

オブジェクトを構築した`CProgressCtrl`後、プロ`CProgressCtrl::Create`グレス バー コントロールを作成する呼び出し。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CProgressCtrl#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_1.cpp)]

## <a name="cprogressctrlcreate"></a><a name="create"></a>作成

プログレス バー コントロールを作成し、`CProgressCtrl`オブジェクトにアタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
プログレス バー コントロールのスタイルを指定します。 Windows SDK の[CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww)で説明されているウィンドウ スタイルの任意の組み合わせを適用し、次のプログレス バー コントロール スタイルに加えて、コントロールに適用します。

- PBS_VERTICAL 進捗状況の情報を上から下に縦に表示します。 このフラグを指定しない場合、進行状況バー コントロールは左から右に水平に表示されます。

- PBS_SMOOTH 進行状況バー コントロールで、段階的にスムーズに塗りつぶされます。 このフラグを指定しないと、コントロールはブロックで塗りつぶされます。

*Rect*<br/>
プログレス バー コントロールのサイズと位置を指定します。 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](/windows/win32/api/windef/ns-windef-rect)構造体を指定できます。 コントロールは子ウィンドウである必要があるため、指定された座標は*pParentWnd*のクライアント領域を基準にしています。

*pParentWnd*<br/>
プログレス バー コントロールの親ウィンドウを指定`CDialog`します。 NULL にすることはできません。

*nID*<br/>
プログレス バー コントロールの ID を指定します。

### <a name="return-value"></a>戻り値

オブジェクトが`CProgressCtrl`正常に作成された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

オブジェクトは`CProgressCtrl`2 つの手順で作成します。 まず、オブジェクトを作成するコンストラクターを`CProgressCtrl`呼び出し、次`Create`に を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CProgressCtrl#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_2.cpp)]

## <a name="cprogressctrlcreateex"></a><a name="createex"></a>をクリックします。

コントロール (子ウィンドウ) を作成し、オブジェクトに関連`CProgressCtrl`付けます。

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
プログレス バー コントロールのスタイルを指定します。 Windows SDK の[「ウィンドウの作成](/windows/win32/api/winuser/nf-winuser-createwindoww)」で説明されているウィンドウ スタイルの任意の組み合わせを適用します。

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

## <a name="cprogressctrlgetbarcolor"></a><a name="getbarcolor"></a>をクリックします。

現在のプログレス バー コントロールの進行状況インジケーター バーの色を取得します。

```
COLORREF GetBarColor() const;
```

### <a name="return-value"></a>戻り値

[COLORREF](/windows/win32/gdi/colorref)値として表される現在のプログレス バーの色、または進行状況インジケータ バーの色が既定の色の場合はCLR_DEFAULT。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK に記載されている[PBM_GETBARCOLOR](/windows/win32/Controls/pbm-getbarcolor)メッセージを送信します。

## <a name="cprogressctrlgetbkcolor"></a><a name="getbkcolor"></a>をクリックします。

現在のプログレス バーの背景色を取得します。

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>戻り値

COLORREF 値として表される、現在のプログレ[COLORREF](/windows/win32/gdi/colorref)ス バーの背景色。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[PBM_GETBKCOLOR](/windows/win32/Controls/pbm-getbkcolor)メッセージを送信します。

## <a name="cprogressctrlgetpos"></a><a name="getpos"></a>をクリックします。

プログレス バーの現在の位置を取得します。

```
int GetPos();
```

### <a name="return-value"></a>戻り値

プログレス バー コントロールの位置。

### <a name="remarks"></a>解説

進行状況バー コントロールの位置は、画面上の物理的な位置ではなく[、SetRange](#setrange)で示された上下の範囲の間にあります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CProgressCtrl#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_3.cpp)]

## <a name="cprogressctrlgetrange"></a><a name="getrange"></a>をクリックします。

プログレス バー コントロールの現在の下限と上限 、または範囲を取得します。

```cpp
void GetRange(
    int& nLower,
    int& nUpper);
```

### <a name="parameters"></a>パラメーター

*nローワー*<br/>
プログレス バー コントロールの下限を受け取る整数への参照。

*nアッパー*<br/>
進行状況バー コントロールの上限を受け取る整数への参照。

### <a name="remarks"></a>解説

この関数は、下限と上限の値を*nLower*および*nUpper*で参照される整数にそれぞれコピーします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CProgressCtrl#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_4.cpp)]

## <a name="cprogressctrlgetstate"></a><a name="getstate"></a>状態を取得します。

現在のプログレス バー コントロールの状態を取得します。

```
int GetState() const;
```

### <a name="return-value"></a>戻り値

現在の進行状況バー コントロールの状態は、次のいずれかの値です。

|値|State|
|-----------|-----------|
|PBST_NORMAL|進行中|
|PBST_ERROR|Error|
|PBST_PAUSED|一時停止|

### <a name="remarks"></a>解説

このメソッドは、Windows SDK に記載されている[PBM_GETSTATE](/windows/win32/Controls/pbm-getstate)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、進行状況バー コントロールにプログラムでアクセスするために使用される `m_progressCtrl` 変数を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>例

現在のプログレス バー コントロールの状態を取得するコード例を次に示します。

[!code-cpp[NVC_MFC_CProgressCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_6.cpp)]

## <a name="cprogressctrlgetstep"></a><a name="getstep"></a>をクリックします。

現在のプログレス バー コントロールの進行状況バーのステップインクリメントを取得します。

```
int GetStep() const;
```

### <a name="return-value"></a>戻り値

プログレス バーのステップインクリメント。

### <a name="remarks"></a>解説

ステップ増分は[、CProgressCtrl::Step の](#stepit)呼び出しによって、進行状況バーの現在位置が増加する量です。

このメソッドは、Windows SDK に記載されている[PBM_GETSTEP](/windows/win32/Controls/pbm-getstep)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、進行状況バー コントロールにプログラムでアクセスするために使用される `m_progressCtrl` 変数を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>例

現在のプログレス バー コントロールのステップ インクリメントを取得するコード例を次に示します。

[!code-cpp[NVC_MFC_CProgressCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_7.cpp)]

## <a name="cprogressctrloffsetpos"></a><a name="offsetpos"></a>をクリックします。

進行状況バー コントロールの現在位置を*nPos*で指定された増分値だけ進め、新しい位置を反映するようにバーを再描画します。

```
int OffsetPos(int nPos);
```

### <a name="parameters"></a>パラメーター

*Npo*<br/>
職位を進める金額です。

### <a name="return-value"></a>戻り値

プログレス バー コントロールの前の位置。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CProgressCtrl#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_8.cpp)]

## <a name="cprogressctrlsetbarcolor"></a><a name="setbarcolor"></a>をクリックします。

現在のプログレス バー コントロールの進行状況インジケーター バーの色を設定します。

```
COLORREF SetBarColor(COLORREF clrBar);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*clrBar*|[in]進行状況インジケーター バーの新しい色を指定する[COLORREF](/windows/win32/gdi/colorref)値。 プログレス バーが既定の色を使用するようにするには、CLR_DEFAULTを指定します。|

### <a name="return-value"></a>戻り値

進行状況インジケーター バーの前の色は[、COLORREF](/windows/win32/gdi/colorref)値として表され、または進行状況インジケーター バーの色が既定の色の場合はCLR_DEFAULT。

### <a name="remarks"></a>解説

この`SetBarColor`メソッドは、Windows Vista[のテーマ](/windows/win32/Controls/visual-styles-overview)が有効でない場合にのみ、プログレス バーの色を設定します。

このメソッドは、Windows SDK に記載されている[PBM_SETBARCOLOR](/windows/win32/Controls/pbm-setbarcolor)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、進行状況バー コントロールにプログラムでアクセスするために使用される `m_progressCtrl` 変数を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>例

次のコード例では、プログレス バーの色を赤、緑、青、または既定に変更します。

[!code-cpp[NVC_MFC_CProgressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_9.cpp)]

## <a name="cprogressctrlsetbkcolor"></a><a name="setbkcolor"></a>をクリックします。

プログレス バーの背景色を設定します。

```
COLORREF SetBkColor(COLORREF clrNew);
```

### <a name="parameters"></a>パラメーター

*clrNew*<br/>
新しい背景色を指定する COLORREF 値。 プログレス バーの既定の背景色を使用するCLR_DEFAULT値を指定します。

### <a name="return-value"></a>戻り値

背景色を示す[COLORREF](/windows/win32/gdi/colorref)値、または背景色が既定の色である場合はCLR_DEFAULT。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CProgressCtrl#6](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_10.cpp)]

## <a name="cprogressctrlsetmarquee"></a><a name="setmarquee"></a>コグレスCtrl::セットマーキー

現在のプログレス バー コントロールのマーキー モードをオンまたはオフにします。

```
BOOL SetMarquee(
    BOOL fMarqueeMode,
    int nInterval);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*マーキーモード*|[in]マーキーモードをオンにするにはTRUE、マーキーモードをオフにするにはFALSE。|
|*n間隔*|[in]マーキー アニメーションの更新間隔 (ミリ秒単位)。|

### <a name="return-value"></a>戻り値

このメソッドは常に TRUE を返します。

### <a name="remarks"></a>解説

マーキーモードがオンになっている場合、プログレスバーはアニメーション化され、劇場のマーキーの看板のようにスクロールします。

このメソッドは、Windows SDK に記載されている[PBM_SETMARQUEE](/windows/win32/Controls/pbm-setmarquee)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、進行状況バー コントロールにプログラムでアクセスするために使用される `m_progressCtrl` 変数を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>例

マーキー スクロール アニメーションを開始および停止するコード例を次に示します。

[!code-cpp[NVC_MFC_CProgressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_11.cpp)]

## <a name="cprogressctrlsetpos"></a><a name="setpos"></a>をクリックします。

*nPos*で指定された進行状況バー コントロールの現在位置を設定し、新しい位置を反映するようにバーを再描画します。

```
int SetPos(int nPos);
```

### <a name="parameters"></a>パラメーター

*Npo*<br/>
プログレス バー コントロールの新しい位置。

### <a name="return-value"></a>戻り値

プログレス バー コントロールの前の位置。

### <a name="remarks"></a>解説

進行状況バー コントロールの位置は、画面上の物理的な位置ではなく[、SetRange](#setrange)で示された上下の範囲の間にあります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CProgressCtrl#7](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_12.cpp)]

## <a name="cprogressctrlsetrange"></a><a name="setrange"></a>をクリックします。

プログレス バー コントロールの範囲の上限と下限を設定し、新しい範囲を反映するようにバーを再描画します。

```cpp
void SetRange(
    short nLower,
    short nUpper);

void SetRange32(
    int nLower,
    int nUpper);
```

### <a name="parameters"></a>パラメーター

*nローワー*<br/>
範囲の下限を指定します (デフォルトは 0)。

*nアッパー*<br/>
範囲の上限を指定します (デフォルトは 100)。

### <a name="remarks"></a>解説

このメンバー関数`SetRange32`は、進行状況コントロールの 32 ビット範囲を設定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CProgressCtrl#8](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_13.cpp)]

## <a name="cprogressctrlsetstate"></a><a name="setstate"></a>状態を設定します。

現在の進行状況バー コントロールの状態を設定します。

```
int SetState(int iState);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*iState*|[in]進行状況バーを設定する状態。 次のいずれかの値を使用します。<br /><br /> - PBST_NORMAL - 進行中<br />- PBST_ERROR - エラー<br />- PBST_PAUSED - 一時停止|

### <a name="return-value"></a>戻り値

現在の進行状況バー コントロールの直前の状態。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[PBM_SETSTATE](/windows/win32/Controls/pbm-setstate)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、進行状況バー コントロールにプログラムでアクセスするために使用される `m_progressCtrl` 変数を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>例

次のコード例は、現在の進行状況バー コントロールの状態を一時停止または処理中に設定します。

[!code-cpp[NVC_MFC_CProgressCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_14.cpp)]

## <a name="cprogressctrlsetstep"></a><a name="setstep"></a>をクリックします。

プログレス バー コントロールのステップインクリメントを指定します。

```
int SetStep(int nStep);
```

### <a name="parameters"></a>パラメーター

*nステップ*<br/>
新しいステップ増分。

### <a name="return-value"></a>戻り値

前のステップ増分。

### <a name="remarks"></a>解説

ステップ増分は、プログレスバーの現在位置`CProgressCtrl::StepIt`を増やす呼び出しの量です。

デフォルトのステップ増分は 10 です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CProgressCtrl#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_15.cpp)]

## <a name="cprogressctrlstepit"></a><a name="stepit"></a>をクリックします。

進捗バー コントロールの現在位置をステップ増分で進め、新しい位置を反映するようにバーを再描画します。

```
int StepIt();
```

### <a name="return-value"></a>戻り値

プログレス バー コントロールの前の位置。

### <a name="remarks"></a>解説

ステップの増分は、メンバー関数`CProgressCtrl::SetStep`によって設定されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CProgressCtrl#10](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_16.cpp)]

## <a name="see-also"></a>関連項目

[サンプル CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
