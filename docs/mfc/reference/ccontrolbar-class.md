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
ms.openlocfilehash: c2f8ea48bf9a1f015928650085b07198b152771a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754792"
---
# <a name="ccontrolbar-class"></a>CControlBar Class

コントロール バー クラスの基本クラス[CStatusBar](../../mfc/reference/cstatusbar-class.md) [、C](../../mfc/reference/ctoolbar-class.md)ツールバー [、CDialogBar](../../mfc/reference/cdialogbar-class.md) [、CReBar](../../mfc/reference/crebar-class.md)、および[COleResizeBar](../../mfc/reference/coleresizebar-class.md)。

## <a name="syntax"></a>構文

```
class CControlBar : public CWnd
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[コントロールバー::コントロールバー](#ccontrolbar)|`CControlBar` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コントロールバー::カルクダイナミックレイアウト](#calcdynamiclayout)|[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトとして、動的コントロール バーのサイズを返します。|
|[コントロールバー::計算式レイアウト](#calcfixedlayout)|コントロール バーのサイズを[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトとして返します。|
|[コントロールバー::カルクインサイドレック](#calcinsiderect)|境界線を含むコントロール バー領域の現在のディメンションを返します。|
|[コントロールバー::Doペイント](#dopaint)|コントロール バーの境界線およびグリップをレンダリングします。|
|[コントロールバー::Dローボーダーズ](#drawborders)|コントロール バーの境界線をレンダリングします。|
|[コントロールバー::Dローグリッパー](#drawgripper)|コントロール バーのグリップをレンダリングします。|
|[コントロールバー::ドッキングを有効にする](#enabledocking)|コントロール バーをドッキングまたはフローティングできるようにします。|
|[コントロールバー::ゲットバースタイル](#getbarstyle)|コントロール バーのスタイル設定を取得します。|
|[コントロールバー::ゲットボーダー](#getborders)|コントロール バーの境界線の値を取得します。|
|[コントロールバー::取得カウント](#getcount)|コントロール バー内の HWND 要素以外の要素の数を返します。|
|[コントロールバー::取得ドッキングフレーム](#getdockingframe)|コントロール バーがドッキングされるフレームへのポインターを返します。|
|[コントロールバー::イズフローティング](#isfloating)|対象のコントロール バーがフローティング コントロール バーである場合に、ゼロ以外の値を返します。|
|[コントロールバー::オンアップデートCmdUI](#onupdatecmdui)|コマンド UI ハンドラーを呼び出します。|
|[コントロールバー::セットバースタイル](#setbarstyle)|コントロール バーのスタイル設定を変更します。|
|[コントロールバー::セットボーダー](#setborders)|コントロール バーの境界線の値を設定します。|
|[コントロールバー::セットインプレイスオーナー](#setinplaceowner)|コントロール バーのインプレース所有者を変更します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[コントロールバー::m_bAutoDelete](#m_bautodelete)|ゼロ以外の場合は、Windows のコントロール バーが破棄されると、`CControlBar` オブジェクトが削除されます。|
|[コントロールバー::m_pInPlaceOwner](#m_pinplaceowner)|コントロール バーのインプレース所有者です。|

## <a name="remarks"></a>解説

通常、コントロール バーは、フレーム ウィンドウの左側または右側にアラインされるウィンドウです。 WINDOWS メッセージを生成して応答する WINDOWS コントロール、または HWND ベース以外の項目を生成し、アプリケーション コードまたはフレームワーク コードによって管理される子項目を含めることができます。 リスト ボックスとエディット コントロールは HWND ベースのコントロールの例です。ステータス バー ペインとビットマップ ボタンは、HWND ベース以外のコントロールの例です。

通常、コントロール バーのウィンドウは親フレーム ウィンドウの子ウィンドウであり、通常はクライアント ビューまたはフレーム ウィンドウの MDI クライアントの兄弟です。 `CControlBar` オブジェクトは、親ウィンドウのクライアント領域の四角形に関する情報を使用して、それ自体を配置します。 次に、親ウィンドウのクライアント領域においてどの程度の未割り当て領域が残っているかについて、親ウィンドウに通知します。

`CControlBar` の詳細については、次を参照してください。

- [コントロール バー](../../mfc/control-bars.md)

- [テクニカルノート 31: コントロールバー](../../mfc/tn031-control-bars.md).

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CControlBar`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxext.h

## <a name="ccontrolbarcalcdynamiclayout"></a><a name="calcdynamiclayout"></a>コントロールバー::カルクダイナミックレイアウト

フレームワークは、動的なツール バーのディメンションを計算するために、このメンバー関数を呼び出します。

```
virtual CSize CalcDynamicLayout(
    int nLength,
    DWORD nMode);
```

### <a name="parameters"></a>パラメーター

*nレングス*<br/>
コントロール バーの要求されたディメンションは *、dwMode*によって水平方向または垂直方向です。

*nモード*<br/>
次の定義済みのフラグを使用して、動的コントロール バーの高さと幅を決定します。 フラグを結合するには、ビットごとの OR (&#124;) 演算子を使用します。

|レイアウト モード フラグ|意味|
|-----------------------|-------------------|
|LM_STRETCH|コントロール バーをフレームのサイズに合わせます。 バーがドッキング バーでない場合に設定します (ドッキングには使用できません)。 バーがドッキングまたはフローティング状態の場合は設定されません(ドッキング可能)。 設定すると、LM_STRETCHは*nLength を*無視し、LM_HORZ状態に基づいてディメンションを返します。 LM_STRETCHは、[計算固定レイアウト](#calcfixedlayout)で使用される*bStretch*パラメーターと同様に動作します。ストレッチと方向の関係の詳細については、そのメンバー関数を参照してください。|
|LM_HORZ|バーが水平方向または垂直方向であることを示します。 バーが水平方向に設定されている場合、垂直に向いている場合は設定されません。 LM_HORZは[、計算式レイアウト](#calcfixedlayout)で使用される*bHorz*パラメーターと同様に動作します。ストレッチと方向の関係の詳細については、そのメンバー関数を参照してください。|
|LM_MRUWIDTH|最近使用した動的幅。 *nLength*パラメーターを無視し、記憶に残された最後に使用された幅を使用します。|
|LM_HORZDOCK|水平ドッキング寸法。 *nLength*パラメータを無視し、最大幅のダイナミック サイズを返します。|
|LM_VERTDOCK|垂直ドッキング寸法。 *nLength*パラメータを無視し、高さが最も大きいダイナミック サイズを返します。|
|LM_LENGTHY|*nLength*が幅ではなく高さ (Y 方向) を示す場合に設定します。|
|LM_COMMIT|LM_MRUWIDTHを現在のコントロール バーの幅に戻します。|

### <a name="return-value"></a>戻り値

[コントロール](../../atl-mfc-shared/reference/csize-class.md)バーのサイズ (ピクセル単位) です。

### <a name="remarks"></a>解説

から`CControlBar`派生したクラスで独自の動的レイアウトを提供するには、このメンバー関数をオーバーライドします。 CToolbar などの`CControlBar`派生 MFC[CToolbar](../../mfc/reference/ctoolbar-class.md)クラスは、このメンバー関数をオーバーライドし、独自の実装を提供します。

## <a name="ccontrolbarcalcfixedlayout"></a><a name="calcfixedlayout"></a>コントロールバー::計算式レイアウト

コントロール バーの水平方向のサイズを計算します。

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>パラメーター

*bストレッチ*<br/>
バーをフレームのサイズまで拡大するかどうかを示します。 バーがドッキング バー (ドッキングには使用できません) でない場合は *、bStretch*パラメーターは 0 以外であり、ドッキングまたはフローティング (ドッキングに使用可能) の場合は 0 です。

*bHorz*<br/>
バーが水平方向または垂直方向であることを示します。 バーが水平方向の場合は*bHorz*パラメータは 0 以外で、縦方向の場合は 0 です。

### <a name="return-value"></a>戻り値

オブジェクトのコントロール バーのサイズ (`CSize`ピクセル単位)。

### <a name="remarks"></a>解説

ツールバーなどのコントロール バーは、コントロール バーに含まれるボタンに合わせて、水平方向または垂直方向に伸縮できます。

*bStretch*が TRUE の場合は *、bHorz*で指定された方向に沿って寸法を伸ばします。 つまり *、bHorz*が FALSE の場合、コントロールバーは垂直方向に伸ばされます。 *bStretch*が FALSE の場合、ストレッチは行われません。 次の表は *、bStretch*および*bHorz*の、可能な順列とその結果として得られるコントロールバースタイルを示しています。

|bストレッチ|bHorz|ストレッチ|方向|ドッキング/ドッキングしない|
|--------------|-----------|----------------|-----------------|--------------------------|
|TRUE|TRUE|水平ストレッチ|水平方向|ドッキングしない|
|TRUE|FALSE|垂直ストレッチ|垂直方向|ドッキングしない|
|FALSE|TRUE|ストレッチなし|水平方向|ドッキング|
|FALSE|FALSE|ストレッチなし|垂直方向|ドッキング|

## <a name="ccontrolbarcalcinsiderect"></a><a name="calcinsiderect"></a>コントロールバー::カルクインサイドレック

フレームワークは、コントロール バーのクライアント領域を計算するために、この関数を呼び出します。

```
virtual void CalcInsideRect(
    CRect& rect,
    BOOL bHorz) const;
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
コントロール バーの現在のサイズを格納します。国境を含む。

*bHorz*<br/>
バーが水平方向または垂直方向であることを示します。 バーが水平方向の場合は*bHorz*パラメータは 0 以外で、縦方向の場合は 0 です。

### <a name="remarks"></a>解説

この関数は、コントロール バーを描画する前に呼び出されます。

コントロール バーの境界線とグリップ バーのレンダリングをカスタマイズするには、この関数をオーバーライドします。

## <a name="ccontrolbarccontrolbar"></a><a name="ccontrolbar"></a>コントロールバー::コントロールバー

`CControlBar` オブジェクトを構築します。

```
CControlBar();
```

## <a name="ccontrolbardopaint"></a><a name="dopaint"></a>コントロールバー::Doペイント

コントロール バーの境界線とグリップ バーをレンダリングするために、フレームワークによって呼び出されます。

```
virtual void DoPaint(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
コントロール バーの境界線とグリッパーのレンダリングに使用するデバイス コンテキストへのポイント。

### <a name="remarks"></a>解説

コントロール バーの描画動作をカスタマイズするには、この関数をオーバーライドします。

もう 1 つのカスタマイズ方法`DrawBorders`は`DrawGripper`、 および 関数をオーバーライドし、境界線とグリッパーのカスタム描画コードを追加することです。 これらのメソッドは既定`DoPaint`のメソッドによって呼び出されるため、オーバーライド`DoPaint`は必要ありません。

## <a name="ccontrolbardrawborders"></a><a name="drawborders"></a>コントロールバー::Dローボーダーズ

コントロール バーの境界線をレンダリングするために、フレームワークによって呼び出されます。

```
virtual void DrawBorders(
    CDC* pDC,
    CRect& rect);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
コントロール バーの境界線のレンダリングに使用するデバイス コンテキストへのポイント。

*Rect*<br/>
コントロール`CRect`バーのサイズを格納しているオブジェクト。

### <a name="remarks"></a>解説

コントロール バーの境界線の外観をカスタマイズするには、この関数をオーバーライドします。

## <a name="ccontrolbardrawgripper"></a><a name="drawgripper"></a>コントロールバー::Dローグリッパー

コントロール バーのグリッパーをレンダリングするために、フレームワークによって呼び出されます。

```
virtual void DrawGripper(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
コントロール バー のグリッパーの描画に使用するデバイス コンテキストへのポイント。

*Rect*<br/>
コントロール`CRect`バー のグリップの寸法を格納するオブジェクト。

### <a name="remarks"></a>解説

コントロール バー のグリップの外観をカスタマイズするには、この関数をオーバーライドします。

## <a name="ccontrolbarenabledocking"></a><a name="enabledocking"></a>コントロールバー::ドッキングを有効にする

コントロール バーをドッキングできるようにします。

```cpp
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>パラメーター

*ドウドックスタイル*<br/>
コントロール バーがドッキングをサポートするかどうか、およびコントロール バーをドッキングできる親ウィンドウの辺 (サポートされている場合) をサポートするかどうかを指定します。 次の 1 つ以上の値を指定できます。

- CBRS_ALIGN_TOP クライアント領域の上部にドッキングできます。

- CBRS_ALIGN_BOTTOM クライアント領域の下部にドッキングできます。

- CBRS_ALIGN_LEFT クライアント領域の左側にドッキングできます。

- CBRS_ALIGN_RIGHT クライアント領域の右側にドッキングできます。

- CBRS_ALIGN_ANY クライアント領域の任意の側にドッキングできます。

- CBRS_FLOAT_MULTI 複数のコントロール バーを 1 つのミニフレーム ウィンドウに浮動させることができます。

0 (つまりフラグがないことを示す) の場合、コントロール バーはドッキングしません。

### <a name="remarks"></a>解説

指定した辺は、ドッキング先フレーム ウィンドウでドッキングが有効になっている辺のいずれかと一致する必要があります。

## <a name="ccontrolbargetbarstyle"></a><a name="getbarstyle"></a>コントロールバー::ゲットバースタイル

コントロール バーに現在設定されている**CBRS_** (コントロール バーのスタイル) 設定を調べます。

```
DWORD GetBarStyle();
```

### <a name="return-value"></a>戻り値

コントロール バーの現在**のCBRS_** (コントロール バーのスタイル) 設定。 利用可能なスタイルの完全なリストについては[、CControlBar::SetBarStyle](#setbarstyle)を参照してください。

### <a name="remarks"></a>解説

**WS_** (ウィンドウ スタイル) スタイルを処理しません。

## <a name="ccontrolbargetborders"></a><a name="getborders"></a>コントロールバー::ゲットボーダー

コントロール バーの現在の境界線の値を返します。

```
CRect GetBorders() const;
```

### <a name="return-value"></a>戻り値

コントロール`CRect`バー オブジェクトの各辺の現在の幅 (ピクセル単位) を格納するオブジェクト。 たとえば[、CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトの*左*メンバーの値は、左辺の境界線の幅です。

## <a name="ccontrolbargetcount"></a><a name="getcount"></a>コントロールバー::取得カウント

オブジェクト上の HWND 以外の項目の`CControlBar`数を返します。

```
int GetCount() const;
```

### <a name="return-value"></a>戻り値

オブジェクト上の HWND 以外の項目`CControlBar`の数。 この関数は[、CDialogBar](../../mfc/reference/cdialogbar-class.md)オブジェクトの 0 を返します。

### <a name="remarks"></a>解説

項目の種類は、派生オブジェクトによって異なります: [CStatusBar](../../mfc/reference/cstatusbar-class.md)オブジェクトのペイン、[および CToolBar](../../mfc/reference/ctoolbar-class.md)オブジェクトのボタンと区切り記号。

## <a name="ccontrolbargetdockingframe"></a><a name="getdockingframe"></a>コントロールバー::取得ドッキングフレーム

コントロール バーがドッキングされている現在のフレーム ウィンドウへのポインターを取得します。

```
CFrameWnd* GetDockingFrame() const;
```

### <a name="return-value"></a>戻り値

成功した場合はフレーム ウィンドウへのポインター。それ以外の場合は NULL。

コントロール バーがフレーム ウィンドウにドッキングされていない場合 (つまり、コントロール バーがフローティング状態の場合)、この関数は親[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)へのポインタを返します。

### <a name="remarks"></a>解説

ドッキング可能なコントロール バーの詳細については[、「CControlBar:::ドッキング](#enabledocking)と[CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar)を有効にする」を参照してください。

## <a name="ccontrolbarisfloating"></a><a name="isfloating"></a>コントロールバー::イズフローティング

コントロール バーがフローティング状態かドッキングされているかどうかを調べます。

```
BOOL IsFloating() const;
```

### <a name="return-value"></a>戻り値

コントロール バーが浮動状態の場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

コントロール バーの状態をドッキングからフローティングに変更するには[、CFrameWnd::FloatControlBar](../../mfc/reference/cframewnd-class.md#floatcontrolbar)を呼び出します。

## <a name="ccontrolbarm_bautodelete"></a><a name="m_bautodelete"></a>コントロールバー::m_bAutoDelete

ゼロ以外の場合は、Windows のコントロール バーが破棄されると、`CControlBar` オブジェクトが削除されます。

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>解説

*m_bAutoDelete*は BOOL 型のパブリック変数です。

通常、コントロール バー オブジェクトは、フレーム ウィンドウ オブジェクトに埋め込まれます。 この場合、フレーム ウィンドウが破棄されると埋め込まれたコントロール バー オブジェクトが破棄されるため *、m_bAutoDelete*は 0 になります。

ヒープに`CControlBar`オブジェクトを割り当て **、delete**を呼び出す予定がない場合は、この変数を 0 以外の値に設定します。

## <a name="ccontrolbarm_pinplaceowner"></a><a name="m_pinplaceowner"></a>コントロールバー::m_pInPlaceOwner

コントロール バーのインプレース所有者です。

```
CWnd* m_pInPlaceOwner;
```

## <a name="ccontrolbaronupdatecmdui"></a><a name="onupdatecmdui"></a>コントロールバー::オンアップデートCmdUI

このメンバー関数は、ツール バーまたはステータス バーの状態を更新するために、フレームワークによって呼び出されます。

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler) = 0;
```

### <a name="parameters"></a>パラメーター

*pターゲット*<br/>
アプリケーションのメイン フレーム ウィンドウへのポイント。 このポインターは、更新メッセージのルーティングに使用されます。

*ノフドラー*<br/>
更新ハンドラーを持たないコントロールを自動的に無効に表示するかどうかを示すフラグ。

### <a name="remarks"></a>解説

個々のボタンまたはペインを更新するには、メッセージ マップの ON_UPDATE_COMMAND_UI マクロを使用して、更新ハンドラーを適切に設定します。 このマクロの使用の詳細については[、「ON_UPDATE_COMMAND_UI」](message-map-macros-mfc.md#on_update_command_ui)を参照してください。

`OnUpdateCmdUI`は、アプリケーションがアイドル状態のときにフレームワークによって呼び出されます。 更新するフレーム ウィンドウは、少なくとも間接的に表示されるフレーム ウィンドウの子ウィンドウである必要があります。 `OnUpdateCmdUI`は、高度なオーバーライド可能です。

## <a name="ccontrolbarsetbarstyle"></a><a name="setbarstyle"></a>コントロールバー::セットバースタイル

コントロール バーに必要な**CBRS_** スタイルを設定します。

```cpp
void SetBarStyle(DWORD dwStyle);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
コントロール バーのスタイル。 次の 1 つ以上の値を指定できます。

- CBRS_ALIGN_TOP フレーム ウィンドウのクライアント領域の上部にコントロール バーをドッキングできます。

- CBRS_ALIGN_BOTTOM フレーム ウィンドウのクライアント領域の下部にコントロール バーをドッキングできます。

- CBRS_ALIGN_LEFT コントロール バーをフレーム ウィンドウのクライアント領域の左側にドッキングできます。

- CBRS_ALIGN_RIGHT フレーム ウィンドウのクライアント領域の右側にコントロール バーをドッキングできます。

- CBRS_ALIGN_ANY フレーム ウィンドウのクライアント領域の任意の側にコントロール バーをドッキングできます。

- CBRS_BORDER_TOP コントロール バーの上端に境界線が表示される場合に描画されます。

- CBRS_BORDER_BOTTOM コントロール バーの下端に境界線が表示される場合に描画されます。

- CBRS_BORDER_LEFT コントロール バーの左端に境界線が表示される場合に描画されます。

- CBRS_BORDER_RIGHT コントロール バーが表示される場合に、コントロール バーの右端に境界線を描画します。

- CBRS_FLOAT_MULTI 複数のコントロール バーを 1 つのミニフレーム ウィンドウに浮動させることができます。

- CBRS_TOOLTIPS コントロール バーにツール ヒントを表示します。

- CBRS_FLYBY メッセージ テキストがツール ヒントと同時に更新されます。

- CBRS_GRIPPER`CReBar`オブジェクトのバンドで使用されるグリッパーを、派生クラスに描画します`CControlBar`。

### <a name="remarks"></a>解説

**WS_(** 窓スタイル)の設定には影響しません。

## <a name="ccontrolbarsetborders"></a><a name="setborders"></a>コントロールバー::セットボーダー

コントロール バーの境界線のサイズを設定します。

```cpp
void SetBorders(
    int cxLeft = 0,
    int cyTop = 0,
    int cxRight = 0,
    int cyBottom = 0);

void SetBorders(LPCRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*左上*<br/>
コントロール バーの左の境界線の幅 (ピクセル単位)。

*サイトップ*<br/>
コントロール バーの上の境界線の高さ (ピクセル単位)。

*cx右*<br/>
コントロール バーの右境界線の幅 (ピクセル単位)。

*サイボトム*<br/>
コントロール バーの下の境界線の高さ (ピクセル単位)。

*Lprect*<br/>
コントロール バー オブジェクトの各境界線の現在の幅 (ピクセル単位) を含む[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトへのポインター。

### <a name="example"></a>例

次のコード例では、コントロール バーの上端と下の境界線を 5 ピクセルに、左右の境界線を 2 ピクセルに設定します。

[!code-cpp[NVC_MFCControlLadenDialog#61](../../mfc/codesnippet/cpp/ccontrolbar-class_1.cpp)]

## <a name="ccontrolbarsetinplaceowner"></a><a name="setinplaceowner"></a>コントロールバー::セットインプレイスオーナー

コントロール バーのインプレース所有者を変更します。

```cpp
void SetInPlaceOwner(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
`CWnd` オブジェクトを指すポインターです。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[MFC サンプル CTRL バー](../../overview/visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CToolBar クラス](../../mfc/reference/ctoolbar-class.md)<br/>
[CDialogBar クラス](../../mfc/reference/cdialogbar-class.md)<br/>
[クラス](../../mfc/reference/cstatusbar-class.md)<br/>
[CReBar クラス](../../mfc/reference/crebar-class.md)
