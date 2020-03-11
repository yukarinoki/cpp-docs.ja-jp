---
title: CControlBar Class
ms.date: 11/04/2016
f1_keywords:
- CControlBar
- AFXEXT/CControlBar
- AFXEXT/CControlBar::CControlBar
- AFXEXT/CControlBar::CalcDynamicLayout
- AFXEXT/CControlBar::CalcFixedLayout
- AFXEXT/CControlBar::CalcInsideRect
- AFXEXT/CControlBar::DoPaint
- AFXEXT/CControlBar::DrawBorders
- AFXEXT/CControlBar::DrawGripper
- AFXEXT/CControlBar::EnableDocking
- AFXEXT/CControlBar::GetBarStyle
- AFXEXT/CControlBar::GetBorders
- AFXEXT/CControlBar::GetCount
- AFXEXT/CControlBar::GetDockingFrame
- AFXEXT/CControlBar::IsFloating
- AFXEXT/CControlBar::OnUpdateCmdUI
- AFXEXT/CControlBar::SetBarStyle
- AFXEXT/CControlBar::SetBorders
- AFXEXT/CControlBar::SetInPlaceOwner
- AFXEXT/CControlBar::m_bAutoDelete
- AFXEXT/CControlBar::m_pInPlaceOwner
helpviewer_keywords:
- CControlBar [MFC], CControlBar
- CControlBar [MFC], CalcDynamicLayout
- CControlBar [MFC], CalcFixedLayout
- CControlBar [MFC], CalcInsideRect
- CControlBar [MFC], DoPaint
- CControlBar [MFC], DrawBorders
- CControlBar [MFC], DrawGripper
- CControlBar [MFC], EnableDocking
- CControlBar [MFC], GetBarStyle
- CControlBar [MFC], GetBorders
- CControlBar [MFC], GetCount
- CControlBar [MFC], GetDockingFrame
- CControlBar [MFC], IsFloating
- CControlBar [MFC], OnUpdateCmdUI
- CControlBar [MFC], SetBarStyle
- CControlBar [MFC], SetBorders
- CControlBar [MFC], SetInPlaceOwner
- CControlBar [MFC], m_bAutoDelete
- CControlBar [MFC], m_pInPlaceOwner
ms.assetid: 4d668c55-9b42-4838-97ac-cf2b3000b82c
ms.openlocfilehash: 41e40b3da7b4a294fe396a9d93f7c6a93593ff95
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78866438"
---
# <a name="ccontrolbar-class"></a>CControlBar Class

コントロールバークラス[CStatusBar](../../mfc/reference/cstatusbar-class.md)、 [CToolBar](../../mfc/reference/ctoolbar-class.md)、 [CDialogBar](../../mfc/reference/cdialogbar-class.md)、 [CReBar](../../mfc/reference/crebar-class.md)、および[coleresizebar](../../mfc/reference/coleresizebar-class.md)の基本クラス。

## <a name="syntax"></a>構文

```
class CControlBar : public CWnd
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|Name|説明|
|----------|-----------------|
|[CControlBar:: CControlBar](#ccontrolbar)|`CControlBar` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[CControlBar:: CalcDynamicLayout](#calcdynamiclayout)|動的コントロールバーのサイズを[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトとして返します。|
|[CControlBar:: CalcFixedLayout](#calcfixedlayout)|コントロールバーのサイズを[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトとして返します。|
|[CControlBar:: CalcInsideRect](#calcinsiderect)|境界線を含むコントロール バー領域の現在のディメンションを返します。|
|[CControlBar::D oPaint](#dopaint)|コントロール バーの境界線およびグリップをレンダリングします。|
|[CControlBar::D rawBorders](#drawborders)|コントロール バーの境界線をレンダリングします。|
|[CControlBar::D rawGripper](#drawgripper)|コントロール バーのグリップをレンダリングします。|
|[CControlBar:: EnableDocking](#enabledocking)|コントロール バーをドッキングまたはフローティングできるようにします。|
|[CControlBar:: GetBarStyle](#getbarstyle)|コントロール バーのスタイル設定を取得します。|
|[CControlBar:: GetBorders](#getborders)|コントロール バーの境界線の値を取得します。|
|[CControlBar:: GetCount](#getcount)|コントロールバーの非 HWND 要素の数を返します。|
|[CControlBar:: Getdocの枠](#getdockingframe)|コントロール バーがドッキングされるフレームへのポインターを返します。|
|[CControlBar:: IsFloating](#isfloating)|対象のコントロール バーがフローティング コントロール バーである場合に、ゼロ以外の値を返します。|
|[CControlBar:: OnUpdateCmdUI](#onupdatecmdui)|コマンド UI ハンドラーを呼び出します。|
|[CControlBar:: SetBarStyle](#setbarstyle)|コントロール バーのスタイル設定を変更します。|
|[CControlBar:: SetBorders](#setborders)|コントロール バーの境界線の値を設定します。|
|[CControlBar:: Setinplace 所有者](#setinplaceowner)|コントロール バーのインプレース所有者を変更します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|Name|説明|
|----------|-----------------|
|[CControlBar:: m_bAutoDelete](#m_bautodelete)|ゼロ以外の場合は、Windows のコントロール バーが破棄されると、`CControlBar` オブジェクトが削除されます。|
|[CControlBar:: m_pInPlaceOwner](#m_pinplaceowner)|コントロール バーのインプレース所有者です。|

## <a name="remarks"></a>コメント

通常、コントロール バーは、フレーム ウィンドウの左側または右側にアラインされるウィンドウです。 これには、HWND ベースのコントロールである子項目が含まれる場合があります。これは、windows メッセージを生成して応答するウィンドウであるか、または windows ではなく、アプリケーションコードまたはフレームワークコードによって管理されている非 HWND ベースの項目です。 リストボックスとエディットコントロールは、HWND ベースのコントロールの例です。ステータスバーペインおよびビットマップボタンは、HWND ベースでないコントロールの例です。

通常、コントロール バーのウィンドウは親フレーム ウィンドウの子ウィンドウであり、通常はクライアント ビューまたはフレーム ウィンドウの MDI クライアントの兄弟です。 `CControlBar` オブジェクトは、親ウィンドウのクライアント領域の四角形に関する情報を使用して、それ自体を配置します。 次に、親ウィンドウのクライアント領域においてどの程度の未割り当て領域が残っているかについて、親ウィンドウに通知します。

`CControlBar` の詳細については、次を参照してください。

- [コントロール バー](../../mfc/control-bars.md)

- [テクニカルノート 31: コントロールバー](../../mfc/tn031-control-bars.md)。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[から派生しているのではない](../../mfc/reference/cwnd-class.md)

`CControlBar`

## <a name="requirements"></a>要件

**ヘッダー:** afxext.h

##  <a name="calcdynamiclayout"></a>CControlBar:: CalcDynamicLayout

フレームワークは、このメンバー関数を呼び出して、動的ツールバーのサイズを計算します。

```
virtual CSize CalcDynamicLayout(
    int nLength,
    DWORD nMode);
```

### <a name="parameters"></a>パラメーター

*nLength*<br/>
*Dwmode*に応じて、水平方向または垂直方向のコントロールバーの要求されたディメンション。

*Evaluationmode*<br/>
次の定義済みフラグは、ダイナミックコントロールバーの高さと幅を決定するために使用されます。 フラグを組み合わせるには、&#124;ビットごとの or () 演算子を使用します。

|レイアウトモードフラグ|意味|
|-----------------------|-------------------|
|LM_STRETCH|コントロールバーをフレームのサイズに拡大する必要があるかどうかを示します。 バーがドッキングバーではない (ドッキングでは使用できない) 場合に設定します。 バーがドッキングされている場合、またはフローティング状態の場合 (ドッキングで使用可能) には設定されません。 設定した場合、LM_STRETCH は*Nlength*を無視し、LM_HORZ の状態に基づいてディメンションを返します。 LM_STRETCH は、 [CalcFixedLayout](#calcfixedlayout)で使用される*bstretch*パラメーターと同様に機能します。拡大と向きの関係の詳細については、メンバー関数を参照してください。|
|LM_HORZ|バーが水平方向または垂直方向であることを示します。 バーを水平方向に配置するかどうかを設定します。垂直方向の場合は設定されません。 LM_HORZ は、 [CalcFixedLayout](#calcfixedlayout)で使用される*bHorz*パラメーターと同様に機能します。拡大と向きの関係の詳細については、メンバー関数を参照してください。|
|LM_MRUWIDTH|最近使用した動的な幅。 は*Nlength*パラメーターを無視し、最近使用した文字幅を記憶しています。|
|LM_HORZDOCK|水平方向にドッキングされた寸法。 *Nlength*パラメーターを無視し、最大幅の動的サイズを返します。|
|LM_VERTDOCK|垂直方向にドッキングされた寸法。 は、 *Nlength*パラメーターを無視し、最大の高さを持つ動的なサイズを返します。|
|LM_LENGTHY|*Nlength*が幅ではなく高さ (Y 方向) を示す場合に設定します。|
|LM_COMMIT|LM_MRUWIDTH をフローティングコントロールバーの現在の幅にリセットします。|

### <a name="return-value"></a>戻り値

[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトのコントロールバーのサイズ (ピクセル単位)。

### <a name="remarks"></a>コメント

このメンバー関数をオーバーライドすると、`CControlBar`から派生したクラスに独自の動的レイアウトが提供されます。 `CControlBar`から派生した MFC クラス ( [CToolbar](../../mfc/reference/ctoolbar-class.md)など) は、このメンバー関数をオーバーライドし、独自の実装を提供します。

##  <a name="calcfixedlayout"></a>CControlBar:: CalcFixedLayout

コントロールバーの水平方向のサイズを計算するには、このメンバー関数を呼び出します。

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>パラメーター

*bStretch*<br/>
バーをフレームのサイズに拡大する必要があるかどうかを示します。 バーがドッキングバーではなく、ドッキングされている (ドッキングで使用可能な) 場合、 *Bstretch*パラメーターは0以外になります。

*bHorz*<br/>
バーが水平方向または垂直方向であることを示します。 *BHorz*パラメーターは、横棒が水平方向の場合は0以外で、垂直方向の場合は0になります。

### <a name="return-value"></a>戻り値

`CSize` オブジェクトのコントロールバーのサイズ (ピクセル単位)。

### <a name="remarks"></a>コメント

ツールバーなどのコントロールバーは、水平方向または垂直方向に伸縮して、コントロールバーに含まれるボタンを収めることができます。

*Bstretch*が TRUE の場合は、 *bHorz*によって提供される方向に沿ってディメンションを伸縮します。 つまり、 *bHorz*が FALSE の場合、コントロールバーは垂直方向に拡大されます。 *Bstretch*が FALSE の場合、ストレッチは行われません。 次の表は、 *Bstretch*と*bHorz*の考えられる順列と、結果として得られるコントロールバーのスタイルを示しています。

|bStretch|bHorz|拡大|[方向]|ドッキング/非ドッキング|
|--------------|-----------|----------------|-----------------|--------------------------|
|TRUE|TRUE|横方向の伸縮|水平方向|ドッキングしない|
|TRUE|FALSE|垂直方向の伸縮|垂直方向|ドッキングしない|
|FALSE|TRUE|拡張を使用できません|水平方向|ドッキング|
|FALSE|FALSE|拡張を使用できません|垂直方向|ドッキング|

##  <a name="calcinsiderect"></a>CControlBar:: CalcInsideRect

フレームワークは、この関数を呼び出して、コントロールバーのクライアント領域を計算します。

```
virtual void CalcInsideRect(
    CRect& rect,
    BOOL bHorz) const;
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
コントロールバーの現在の大きさを格納します。境界線を含めます。

*bHorz*<br/>
バーが水平方向または垂直方向であることを示します。 *BHorz*パラメーターは、横棒が水平方向の場合は0以外で、垂直方向の場合は0になります。

### <a name="remarks"></a>コメント

この関数は、コントロールバーが描画される前に呼び出されます。

コントロールバーの境界線とグリップバーのレンダリングをカスタマイズするには、この関数をオーバーライドします。

##  <a name="ccontrolbar"></a>CControlBar:: CControlBar

`CControlBar` オブジェクトを構築します。

```
CControlBar();
```

##  <a name="dopaint"></a>CControlBar::D oPaint

コントロールバーの境界線とグリップバーを描画するためにフレームワークによって呼び出されます。

```
virtual void DoPaint(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
コントロールバーの境界線とグリップのレンダリングに使用されるデバイスコンテキストを指します。

### <a name="remarks"></a>コメント

コントロールバーの描画動作をカスタマイズするには、この関数をオーバーライドします。

別のカスタマイズ方法として、`DrawBorders` および `DrawGripper` 関数をオーバーライドし、境界線とグリップのカスタム描画コードを追加します。 これらのメソッドは既定の `DoPaint` メソッドによって呼び出されるため、`DoPaint` のオーバーライドは必要ありません。

##  <a name="drawborders"></a>CControlBar::D rawBorders

コントロールバーの境界線を描画するためにフレームワークによって呼び出されます。

```
virtual void DrawBorders(
    CDC* pDC,
    CRect& rect);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
コントロールバーの境界線を描画するために使用されるデバイスコンテキストを指します。

*rect*<br/>
コントロールバーの大きさを格納している `CRect` オブジェクト。

### <a name="remarks"></a>コメント

コントロールバーの境界線の外観をカスタマイズするには、この関数をオーバーライドします。

##  <a name="drawgripper"></a>CControlBar::D rawGripper

コントロールバーのグリップをレンダリングするためにフレームワークによって呼び出されます。

```
virtual void DrawGripper(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
コントロールバーのグリップを表示するために使用されるデバイスコンテキストを指します。

*rect*<br/>
コントロールバーのグリップの大きさを格納している `CRect` オブジェクト。

### <a name="remarks"></a>コメント

コントロールバーのグリップの外観をカスタマイズするには、この関数をオーバーライドします。

##  <a name="enabledocking"></a>CControlBar:: EnableDocking

コントロールバーをドッキングできるようにするには、この関数を呼び出します。

```
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>パラメーター

*dwDockStyle*<br/>
コントロールバーがドッキングをサポートしている場合は、コントロールバーがドッキングできる親ウィンドウの辺をサポートするかどうかを指定します。 次の1つまたは複数を指定できます。

- CBRS_ALIGN_TOP を使用すると、クライアント領域の上部にドッキングできます。

- CBRS_ALIGN_BOTTOM を使用すると、クライアント領域の下部にドッキングできます。

- CBRS_ALIGN_LEFT を使用すると、クライアント領域の左側にドッキングできます。

- CBRS_ALIGN_RIGHT を使用すると、クライアント領域の右側にドッキングできます。

- CBRS_ALIGN_ANY を使用すると、クライアント領域の任意の側でドッキングできます。

- CBRS_FLOAT_MULTI を使用すると、1つのミニフレームウィンドウで複数のコントロールバーをフローティングできます。

0の場合 (つまり、フラグが指定されていない場合)、コントロールバーはドッキングされません。

### <a name="remarks"></a>コメント

指定された辺は、対象のフレームウィンドウでドッキングが有効になっている側のいずれかと一致する必要があります。または、コントロールバーをそのフレームウィンドウにドッキングできません。

##  <a name="getbarstyle"></a>CControlBar:: GetBarStyle

コントロールバーに現在設定されている**CBRS_** (コントロールバースタイル) 設定を確認するには、この関数を呼び出します。

```
DWORD GetBarStyle();
```

### <a name="return-value"></a>戻り値

コントロールバーの現在の**CBRS_** (コントロールバーのスタイル) 設定。 使用できるスタイルの完全な一覧については、「 [CControlBar:: SetBarStyle](#setbarstyle) 」を参照してください。

### <a name="remarks"></a>コメント

**WS_** (ウィンドウスタイル) スタイルを処理しません。

##  <a name="getborders"></a>CControlBar:: GetBorders

コントロールバーの現在の境界の値を返します。

```
CRect GetBorders() const;
```

### <a name="return-value"></a>戻り値

コントロールバーオブジェクトの各辺の現在の幅 (ピクセル単位) を格納している `CRect` オブジェクト。 たとえば、*左側*のメンバーの値 ( [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクト) は、左側の境界線の幅です。

##  <a name="getcount"></a>CControlBar:: GetCount

`CControlBar` オブジェクト上の HWND 以外の項目の数を返します。

```
int GetCount() const;
```

### <a name="return-value"></a>戻り値

`CControlBar` オブジェクト上の HWND 以外の項目の数。 この関数は、 [CDialogBar](../../mfc/reference/cdialogbar-class.md)オブジェクトに対して0を返します。

### <a name="remarks"></a>コメント

項目の型は、派生オブジェクト、 [CStatusBar](../../mfc/reference/cstatusbar-class.md)オブジェクトのペイン、および[CToolBar](../../mfc/reference/ctoolbar-class.md)オブジェクトのボタンと区切り記号によって異なります。

##  <a name="getdockingframe"></a>CControlBar:: Getdocの枠

コントロールバーがドッキングされている現在のフレームウィンドウへのポインターを取得するには、このメンバー関数を呼び出します。

```
CFrameWnd* GetDockingFrame() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、フレームウィンドウへのポインター。それ以外の場合は NULL。

コントロールバーがフレームウィンドウにドッキングされていない場合 (つまり、コントロールバーが浮動小数点型の場合)、この関数は親[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)へのポインターを返します。

### <a name="remarks"></a>コメント

ドッキング可能なコントロールバーの詳細については、「 [CControlBar:: EnableDocking](#enabledocking) and [CFrameWnd::D ockcontrolbar](../../mfc/reference/cframewnd-class.md#dockcontrolbar)」を参照してください。

##  <a name="isfloating"></a>CControlBar:: IsFloating

コントロールバーがフローティングまたはドッキングされているかどうかを判断するには、このメンバー関数を呼び出します。

```
BOOL IsFloating() const;
```

### <a name="return-value"></a>戻り値

コントロールバーがフローティングの場合は0以外の場合は。それ以外の場合は0です。

### <a name="remarks"></a>コメント

コントロールバーの状態をドッキングからフローティングに変更するには、 [CFrameWnd:: FloatControlBar](../../mfc/reference/cframewnd-class.md#floatcontrolbar)を呼び出します。

##  <a name="m_bautodelete"></a>CControlBar:: m_bAutoDelete

ゼロ以外の場合は、Windows のコントロール バーが破棄されると、`CControlBar` オブジェクトが削除されます。

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>コメント

*m_bAutoDelete*は、BOOL 型のパブリック変数です。

通常、コントロールバーオブジェクトはフレームウィンドウオブジェクトに埋め込まれます。 この場合、埋め込まれたコントロールバーオブジェクトは、フレームウィンドウが破棄されると破棄されるため、 *m_bAutoDelete*は0になります。

ヒープに `CControlBar` オブジェクトを割り当て、 **delete**を呼び出す予定がない場合は、この変数を0以外の値に設定します。

##  <a name="m_pinplaceowner"></a>CControlBar:: m_pInPlaceOwner

コントロール バーのインプレース所有者です。

```
CWnd* m_pInPlaceOwner;
```

##  <a name="onupdatecmdui"></a>CControlBar:: OnUpdateCmdUI

このメンバー関数は、ツールバーまたはステータスバーの状態を更新するためにフレームワークによって呼び出されます。

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler) = 0;
```

### <a name="parameters"></a>パラメーター

*pTarget*<br/>
アプリケーションのメインフレームウィンドウをポイントします。 このポインターは、更新メッセージをルーティングするために使用されます。

*bDisableIfNoHndler*<br/>
更新ハンドラーを持たないコントロールを自動的に無効として表示するかどうかを示すフラグです。

### <a name="remarks"></a>コメント

個々のボタンまたはウィンドウを更新するには、メッセージマップで ON_UPDATE_COMMAND_UI マクロを使用して、更新ハンドラーを適切に設定します。 このマクロの使用方法の詳細については、「 [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) 」を参照してください。

`OnUpdateCmdUI` は、アプリケーションがアイドル状態のときにフレームワークによって呼び出されます。 更新するフレームウィンドウは、少なくとも、表示されているフレームウィンドウの子ウィンドウである必要があります。 `OnUpdateCmdUI` は高度なオーバーライド可能です。

##  <a name="setbarstyle"></a>CControlBar:: SetBarStyle

コントロールバーの目的の**CBRS_** スタイルを設定するには、この関数を呼び出します。

```
void SetBarStyle(DWORD dwStyle);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
コントロールバーに必要なスタイル。 次の1つまたは複数を指定できます。

- CBRS_ALIGN_TOP を使用すると、コントロールバーをフレームウィンドウのクライアント領域の上部にドッキングできます。

- CBRS_ALIGN_BOTTOM を使用すると、コントロールバーをフレームウィンドウのクライアント領域の下部にドッキングできます。

- CBRS_ALIGN_LEFT を使用すると、コントロールバーをフレームウィンドウのクライアント領域の左側にドッキングできます。

- CBRS_ALIGN_RIGHT を使用すると、コントロールバーをフレームウィンドウのクライアント領域の右側にドッキングできます。

- CBRS_ALIGN_ANY を使用すると、コントロールバーをフレームウィンドウのクライアント領域の任意の辺にドッキングできます。

- CBRS_BORDER_TOP を使用すると、コントロールバーの上端に境界線が表示されます。

- CBRS_BORDER_BOTTOM を使用すると、コントロールバーの下端に境界線が表示されます。

- CBRS_BORDER_LEFT により、コントロールバーの左端に境界線が表示されます。

- CBRS_BORDER_RIGHT によって、表示されるときにコントロールバーの右端に境界線が描画されます。

- CBRS_FLOAT_MULTI を使用すると、1つのミニフレームウィンドウで複数のコントロールバーをフローティングできます。

- CBRS_TOOLTIPS によって、コントロールバーにツールヒントが表示されます。

- CBRS_FLYBY すると、メッセージテキストがツールヒントと同時に更新されます。

- CBRS_GRIPPER により、`CReBar` オブジェクトのバンドで使用されるようなグリップが、`CControlBar`派生クラスに描画されます。

### <a name="remarks"></a>コメント

**WS_** (ウィンドウスタイル) 設定には影響しません。

##  <a name="setborders"></a>CControlBar:: SetBorders

コントロールバーの境界線のサイズを設定するには、この関数を呼び出します。

```
void SetBorders(
    int cxLeft = 0,
    int cyTop = 0,
    int cxRight = 0,
    int cyBottom = 0);

void SetBorders(LPCRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*cxLeft*<br/>
コントロールバーの左の境界線の幅 (ピクセル単位)。

*cyTop*<br/>
コントロールバーの上罫線の高さ (ピクセル単位)。

*cxRight*<br/>
コントロールバーの右の境界線の幅 (ピクセル単位)。

*cyBottom*<br/>
コントロールバーの下境界線の高さ (ピクセル単位)。

*lpRect*<br/>
コントロールバーオブジェクトの各境界線の現在の幅 (ピクセル単位) を格納している、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトへのポインター。

### <a name="example"></a>例

次のコード例では、コントロールバーの上と下の境界線を5ピクセルに設定し、左と右の境界線を2ピクセルに設定します。

[!code-cpp[NVC_MFCControlLadenDialog#61](../../mfc/codesnippet/cpp/ccontrolbar-class_1.cpp)]

##  <a name="setinplaceowner"></a>CControlBar:: Setinplace 所有者

コントロール バーのインプレース所有者を変更します。

```
void SetInPlaceOwner(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
`CWnd` オブジェクトを指すポインターです。

### <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[MFC のサンプル CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CToolBar クラス](../../mfc/reference/ctoolbar-class.md)<br/>
[CDialogBar クラス](../../mfc/reference/cdialogbar-class.md)<br/>
[CStatusBar クラス](../../mfc/reference/cstatusbar-class.md)<br/>
[CReBar クラス](../../mfc/reference/crebar-class.md)
