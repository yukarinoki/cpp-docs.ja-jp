---
title: CSplitterWnd クラス
ms.date: 11/04/2016
f1_keywords:
- CSplitterWnd
- AFXEXT/CSplitterWnd
- AFXEXT/CSplitterWnd::CSplitterWnd
- AFXEXT/CSplitterWnd::ActivateNext
- AFXEXT/CSplitterWnd::CanActivateNext
- AFXEXT/CSplitterWnd::Create
- AFXEXT/CSplitterWnd::CreateScrollBarCtrl
- AFXEXT/CSplitterWnd::CreateStatic
- AFXEXT/CSplitterWnd::CreateView
- AFXEXT/CSplitterWnd::DeleteColumn
- AFXEXT/CSplitterWnd::DeleteRow
- AFXEXT/CSplitterWnd::DeleteView
- AFXEXT/CSplitterWnd::DoKeyboardSplit
- AFXEXT/CSplitterWnd::DoScroll
- AFXEXT/CSplitterWnd::DoScrollBy
- AFXEXT/CSplitterWnd::GetActivePane
- AFXEXT/CSplitterWnd::GetColumnCount
- AFXEXT/CSplitterWnd::GetColumnInfo
- AFXEXT/CSplitterWnd::GetPane
- AFXEXT/CSplitterWnd::GetRowCount
- AFXEXT/CSplitterWnd::GetRowInfo
- AFXEXT/CSplitterWnd::GetScrollStyle
- AFXEXT/CSplitterWnd::IdFromRowCol
- AFXEXT/CSplitterWnd::IsChildPane
- AFXEXT/CSplitterWnd::IsTracking
- AFXEXT/CSplitterWnd::RecalcLayout
- AFXEXT/CSplitterWnd::SetActivePane
- AFXEXT/CSplitterWnd::SetColumnInfo
- AFXEXT/CSplitterWnd::SetRowInfo
- AFXEXT/CSplitterWnd::SetScrollStyle
- AFXEXT/CSplitterWnd::SplitColumn
- AFXEXT/CSplitterWnd::SplitRow
- AFXEXT/CSplitterWnd::OnDraw
- AFXEXT/CSplitterWnd::OnDrawSplitter
- AFXEXT/CSplitterWnd::OnInvertTracker
helpviewer_keywords:
- CSplitterWnd [MFC], CSplitterWnd
- CSplitterWnd [MFC], ActivateNext
- CSplitterWnd [MFC], CanActivateNext
- CSplitterWnd [MFC], Create
- CSplitterWnd [MFC], CreateScrollBarCtrl
- CSplitterWnd [MFC], CreateStatic
- CSplitterWnd [MFC], CreateView
- CSplitterWnd [MFC], DeleteColumn
- CSplitterWnd [MFC], DeleteRow
- CSplitterWnd [MFC], DeleteView
- CSplitterWnd [MFC], DoKeyboardSplit
- CSplitterWnd [MFC], DoScroll
- CSplitterWnd [MFC], DoScrollBy
- CSplitterWnd [MFC], GetActivePane
- CSplitterWnd [MFC], GetColumnCount
- CSplitterWnd [MFC], GetColumnInfo
- CSplitterWnd [MFC], GetPane
- CSplitterWnd [MFC], GetRowCount
- CSplitterWnd [MFC], GetRowInfo
- CSplitterWnd [MFC], GetScrollStyle
- CSplitterWnd [MFC], IdFromRowCol
- CSplitterWnd [MFC], IsChildPane
- CSplitterWnd [MFC], IsTracking
- CSplitterWnd [MFC], RecalcLayout
- CSplitterWnd [MFC], SetActivePane
- CSplitterWnd [MFC], SetColumnInfo
- CSplitterWnd [MFC], SetRowInfo
- CSplitterWnd [MFC], SetScrollStyle
- CSplitterWnd [MFC], SplitColumn
- CSplitterWnd [MFC], SplitRow
- CSplitterWnd [MFC], OnDraw
- CSplitterWnd [MFC], OnDrawSplitter
- CSplitterWnd [MFC], OnInvertTracker
ms.assetid: fd0de258-6dbe-4552-9e47-a39de0471d51
ms.openlocfilehash: 065735c13a3e763208142eb6bc989d3a496221f0
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78890955"
---
# <a name="csplitterwnd-class"></a>CSplitterWnd クラス

分割ウィンドウの機能が用意されています。分割ウィンドウとは複数のペインを持つウィンドウです。

## <a name="syntax"></a>構文

```
class CSplitterWnd : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|説明|
|----------|-----------------|
|[CSplitterWnd:: CSplitterWnd](#csplitterwnd)|を呼び出して `CSplitterWnd` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[CSplitterWnd:: ActivateNext](#activatenext)|次のペインまたは前のペインコマンドを実行します。|
|[CSplitterWnd:: CanActivateNext](#canactivatenext)|次のペインまたは前のペインコマンドが現在可能かどうかを確認します。|
|[CSplitterWnd:: Create](#create)|を呼び出して、動的分割ウィンドウを作成し、`CSplitterWnd` オブジェクトにアタッチします。|
|[CSplitterWnd:: CreateScrollBarCtrl](#createscrollbarctrl)|共有スクロールバーコントロールを作成します。|
|[CSplitterWnd:: CreateStatic](#createstatic)|を呼び出して、静的なスプリッターウィンドウを作成し、`CSplitterWnd` オブジェクトにアタッチします。|
|[CSplitterWnd:: CreateView](#createview)|を呼び出して、スプリッターウィンドウにウィンドウを作成します。|
|[CSplitterWnd::D eleteColumn](#deletecolumn)|スプリッターウィンドウから列を削除します。|
|[CSplitterWnd::D eleteRow](#deleterow)|スプリッターウィンドウから行を削除します。|
|[CSplitterWnd::D eleteView](#deleteview)|スプリッターウィンドウからビューを削除します。|
|[CSplitterWnd::D Oキーボード分割](#dokeyboardsplit)|キーボード分割コマンド (通常は "ウィンドウ分割") を実行します。|
|[CSplitterWnd::D oScroll](#doscroll)|分割ウィンドウの同期スクロールを実行します。|
|[CSplitterWnd::D oScrollBy](#doscrollby)|分割ウィンドウを指定されたピクセル数でスクロールします。|
|[CSplitterWnd:: GetActivePane](#getactivepane)|フレーム内のフォーカスビューまたはアクティブビューからアクティブペインを決定します。|
|[CSplitterWnd:: GetColumnCount](#getcolumncount)|現在のペインの列数を返します。|
|[CSplitterWnd:: GetColumnInfo](#getcolumninfo)|指定された列に関する情報を返します。|
|[CSplitterWnd:: GetPane](#getpane)|指定された行と列にあるペインを返します。|
|[CSplitterWnd:: GetRowCount](#getrowcount)|現在のペインの行数を返します。|
|[CSplitterWnd:: GetRowInfo](#getrowinfo)|指定された行に関する情報を返します。|
|[CSplitterWnd:: GetScrollStyle](#getscrollstyle)|共有スクロールバーのスタイルを返します。|
|[CSplitterWnd:: IdFromRowCol](#idfromrowcol)|指定された行と列にあるペインの子ウィンドウ ID を返します。|
|[CSplitterWnd:: IsChildPane](#ischildpane)|を呼び出して、ウィンドウが現在このスプリッターウィンドウの子ペインであるかどうかを確認します。|
|[CSplitterWnd:: IsTracking](#istracking)|分割バーを現在移動しているかどうかを判断します。|
|[CSplitterWnd:: RecalcLayout](#recalclayout)|を呼び出して、行または列のサイズを調整した後にスプリッターウィンドウを再表示します。|
|[CSplitterWnd:: SetActivePane](#setactivepane)|ウィンドウをフレーム内のアクティブなペインに設定します。|
|[CSplitterWnd:: SetColumnInfo](#setcolumninfo)|を呼び出して、指定された列情報を設定します。|
|[CSplitterWnd:: SetRowInfo](#setrowinfo)|を呼び出して、指定された行情報を設定します。|
|[CSplitterWnd:: SetScrollStyle](#setscrollstyle)|スプリッターウィンドウの共有スクロールバーサポートの新しいスクロールバースタイルを指定します。|
|[CSplitterWnd:: SplitColumn](#splitcolumn)|フレームウィンドウが垂直方向に分割する場所を示します。|
|[CSplitterWnd:: SplitRow](#splitrow)|フレームウィンドウを水平方向に分割する場所を示します。|

### <a name="protected-methods"></a>プロテクト メソッド

|Name|説明|
|----------|-----------------|
|[CSplitterWnd:: OnDraw](#ondraw)|スプリッターウィンドウを描画するためにフレームワークによって呼び出されます。|
|[CSplitterWnd:: OnDrawSplitter](#ondrawsplitter)|分割ウィンドウのイメージをレンダリングします。|
|[CSplitterWnd:: OnInvertTracker](#oninverttracker)|分割ウィンドウのイメージを、フレームウィンドウと同じサイズおよび形状になるように表示します。|

## <a name="remarks"></a>コメント

通常、ペインは、 [CView](../../mfc/reference/cview-class.md)から派生したアプリケーション固有のオブジェクトですが、適切な子ウィンドウ ID を持つ任意の[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトにすることができます。

`CSplitterWnd` オブジェクトは通常、親の[CFrameWnd](../../mfc/reference/cframewnd-class.md)または[CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)オブジェクトに埋め込まれます。 次の手順に従って、`CSplitterWnd` オブジェクトを作成します。

1. `CSplitterWnd` メンバー変数を親フレームに埋め込みます。

2. 親フレームの[CFrameWnd:: OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)メンバー関数をオーバーライドします。

3. オーバーライドされた `OnCreateClient`内から、`CSplitterWnd`の[Create](#create)または[createstatic](#createstatic)メンバー関数を呼び出します。

`Create` メンバー関数を呼び出して、動的なスプリッターウィンドウを作成します。 通常、動的分割ウィンドウは、同じドキュメントの複数のペイン (ビュー) を作成およびスクロールするために使用されます。 フレームワークによって、スプリッターの初期ペインが自動的に作成されます。次に、ユーザーがスプリッターウィンドウのコントロールを操作するときに、フレームワークによって追加のペインの作成、サイズ変更、および破棄が行われます。

`Create`を呼び出すときに、ペインが小さすぎて表示できない場合を決定する、行の最小の高さと列の幅を指定します。 `Create`を呼び出した後は、 [SetColumnInfo](#setcolumninfo)および[SetRowInfo](#setrowinfo)メンバー関数を呼び出すことで、これらの最小を調整できます。

また、`SetColumnInfo` および `SetRowInfo` のメンバー関数を使用して、列に "最適" の幅を設定し、行に "理想的な" 高さを設定します。 フレームワークが分割ウィンドウを表示すると、最初に親フレーム、次に分割ウィンドウが表示されます。 次に、フレームワークは、最適なディメンションに従って列と行のペインをレイアウトし、スプリッターウィンドウのクライアント領域の左上から右下隅に向かって作業します。

動的分割ウィンドウのすべてのペインは、同じクラスである必要があります。 動的分割ウィンドウをサポートする使い慣れたアプリケーションには、Microsoft Word と Microsoft Excel があります。

`CreateStatic` メンバー関数を使用して、静的なスプリッターウィンドウを作成します。 ユーザーは、数値や順序ではなく、静的な分割ウィンドウのペインのサイズのみを変更できます。

静的スプリッターを作成するときは、すべての静的スプリッターのペインを明示的に作成する必要があります。 親フレームの `OnCreateClient` メンバー関数がを返す前に、すべてのペインを必ず作成してください。指定しないと、フレームワークによってウィンドウが正しく表示されません。

`CreateStatic` メンバー関数は、行の最小の高さと列の幅を0に設定して、静的スプリッターを自動的に初期化します。 `Create`を呼び出した後、 [SetColumnInfo](#setcolumninfo)および[SetRowInfo](#setrowinfo)メンバー関数を呼び出してこれらの最小を調整します。 また、必要な最適なペインディメンションを示すには、`CreateStatic` を呼び出した後に `SetColumnInfo` と `SetRowInfo` を使用します。

静的スプリッターの個々のペインは、多くの場合、異なるクラスに属しています。 静的スプリッターウィンドウの例については、「グラフィックスエディター」と「Windows ファイルマネージャー」を参照してください。

スプリッターウィンドウでは、特別なスクロールバーがサポートされています (ペインのスクロールバーとは別)。 これらのスクロールバーは `CSplitterWnd` オブジェクトの子であり、ペインと共有されます。

これらの特殊なスクロールバーは、分割ウィンドウを作成するときに作成します。 たとえば、1つの行、2つの列、および WS_VSCROLL スタイルを持つ `CSplitterWnd` には、2つのペインで共有されている垂直スクロールバーが表示されます。 ユーザーがスクロールバーを移動すると、WM_VSCROLL メッセージが両方のウィンドウに送信されます。 ペインがスクロールバーの位置を設定すると、共有スクロールバーが設定されます。

分割ウィンドウの詳細については、「[テクニカルノート 29](../../mfc/tn029-splitter-windows.md)」を参照してください。

動的分割ウィンドウを作成する方法の詳細については、次を参照してください。

- MFC サンプル[Scribble](../../overview/visual-cpp-samples.md)

- MFC サンプル[VIEWEX](../../overview/visual-cpp-samples.md)。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[から派生しているのではない](../../mfc/reference/cwnd-class.md)

`CSplitterWnd`

## <a name="requirements"></a>要件

**ヘッダー:** afxext.h

##  <a name="activatenext"></a>CSplitterWnd:: ActivateNext

次のペインまたは前のペインコマンドを実行するために、フレームワークによって呼び出されます。

```
virtual void ActivateNext(BOOL bPrev = FALSE);
```

### <a name="parameters"></a>パラメーター

*bPrev*<br/>
アクティブにするウィンドウを示します。 前の場合は**TRUE** 。次の場合は**FALSE** 。

### <a name="remarks"></a>コメント

このメンバー関数は、`CSplitterWnd` の実装に委任するために[CView](../../mfc/reference/cview-class.md)クラスによって使用される高レベルのコマンドです。

##  <a name="canactivatenext"></a>CSplitterWnd:: CanActivateNext

次のペインまたは前のペインコマンドが現在可能かどうかを確認するために、フレームワークによって呼び出されます。

```
virtual BOOL CanActivateNext(BOOL bPrev = FALSE);
```

### <a name="parameters"></a>パラメーター

*bPrev*<br/>
アクティブにするウィンドウを示します。 前の場合は**TRUE** 。次の場合は**FALSE** 。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>コメント

このメンバー関数は、`CSplitterWnd` の実装に委任するために[CView](../../mfc/reference/cview-class.md)クラスによって使用される高レベルのコマンドです。

##  <a name="create"></a>CSplitterWnd:: Create

動的分割ウィンドウを作成するには、`Create` メンバー関数を呼び出します。

```
virtual BOOL Create(
    CWnd* pParentWnd,
    int nMaxRows,
    int nMaxCols,
    SIZE sizeMin,
    CCreateContext* pContext,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_HSCROLL | WS_VSCROLL | SPLS_DYNAMIC_SPLIT,
    UINT nID = AFX_IDW_PANE_FIRST);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
分割ウィンドウの親フレームウィンドウ。

*nMaxRows*<br/>
分割ウィンドウ内の行の最大数。 この値は2を超えることはできません。

*nMaxCols*<br/>
分割ウィンドウ内の列の最大数。 この値は2を超えることはできません。

*sizeMin*<br/>
ペインを表示できる最小サイズを指定します。

*pContext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md)構造体へのポインター。 ほとんどの場合、これは親フレームウィンドウに渡される*pContext*にすることができます。

*dwStyle*<br/>
ウィンドウスタイルを指定します。

*nID*<br/>
ウィンドウの子ウィンドウ ID。 分割ウィンドウが別のスプリッターウィンドウ内に入れ子になっている場合を除き、ID を AFX_IDW_PANE_FIRST できます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>コメント

次の手順に従って、`CSplitterWnd` を親の[CFrameWnd](../../mfc/reference/cframewnd-class.md)または[CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)オブジェクトに埋め込むことができます。

1. `CSplitterWnd` メンバー変数を親フレームに埋め込みます。

1. 親フレームの[CFrameWnd:: OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)メンバー関数をオーバーライドします。

1. オーバーライドされた `OnCreateClient`内から `Create` メンバー関数を呼び出します。

親フレーム内からスプリッターウィンドウを作成する場合は、親フレームの*pContext*パラメーターを分割ウィンドウに渡します。 それ以外の場合、このパラメーターには NULL を指定できます。

動的分割ウィンドウの初期の行の最小の高さと列の幅は、 *sizeMin*パラメーターによって設定されます。 これらの最小数は、ペインが小さすぎて完全に表示できないかどうかを判断するために、 [SetRowInfo](#setrowinfo)および[SetColumnInfo](#setcolumninfo)メンバー関数を使用して変更できます。

動的分割ウィンドウの詳細については、「複数のドキュメントの[種類、ビュー、フレームウィンドウ](../../mfc/multiple-document-types-views-and-frame-windows.md)、[テクニカルノート 29](../../mfc/tn029-splitter-windows.md)、`CSplitterWnd` クラスの概要」の「分割ウィンドウ」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#125](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_1.cpp)]

##  <a name="createscrollbarctrl"></a>CSplitterWnd:: CreateScrollBarCtrl

共有スクロールバーコントロールを作成するために、フレームワークによって呼び出されます。

```
virtual BOOL CreateScrollBarCtrl(
    DWORD dwStyle,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
ウィンドウスタイルを指定します。

*nID*<br/>
ウィンドウの子ウィンドウ ID。 分割ウィンドウが別のスプリッターウィンドウ内に入れ子になっている場合を除き、ID を AFX_IDW_PANE_FIRST できます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>コメント

スクロールバーの横に追加のコントロールを含めるには、`CreateScrollBarCtrl` をオーバーライドします。 既定の動作では、通常の Windows スクロールバーコントロールが作成されます。

##  <a name="createstatic"></a>CSplitterWnd:: CreateStatic

静的なスプリッターウィンドウを作成するには、`CreateStatic` メンバー関数を呼び出します。

```
virtual BOOL CreateStatic(
    CWnd* pParentWnd,
    int nRows,
    int nCols,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,
    UINT nID = AFX_IDW_PANE_FIRST);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
分割ウィンドウの親フレームウィンドウ。

*nRows*<br/>
行数です。 この値は16を超えないようにする必要があります。

*nCols*<br/>
列数です。 この値は16を超えないようにする必要があります。

*dwStyle*<br/>
ウィンドウスタイルを指定します。

*nID*<br/>
ウィンドウの子ウィンドウ ID。 分割ウィンドウが別のスプリッターウィンドウ内に入れ子になっている場合を除き、ID を AFX_IDW_PANE_FIRST できます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>コメント

`CSplitterWnd` は通常、次の手順を実行することで親 `CFrameWnd` または[CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)オブジェクトに埋め込まれます。

1. `CSplitterWnd` メンバー変数を親フレームに埋め込みます。

1. 親フレームの `OnCreateClient` メンバー関数をオーバーライドします。

1. オーバーライドされた[CFrameWnd:: OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)内から `CreateStatic` メンバー関数を呼び出します。

静的スプリッターウィンドウには、固定された数のペインが含まれており、多くの場合、さまざまなクラスに含まれています。

静的な分割ウィンドウを作成する場合は、すべてのペインを同時に作成する必要があります。 [CreateView](#createview)メンバー関数は、通常、この目的で使用されますが、他の非ビュークラスを作成することもできます。

静的な分割ウィンドウの初期の行の最小の高さと列の幅は、0です。 これらの最小数は、ペインが小さすぎて完全に表示できない場合に、 [SetRowInfo](#setrowinfo)および[SetColumnInfo](#setcolumninfo)メンバー関数を使用して変更できます。

静的スプリッターウィンドウにスクロールバーを追加するには、WS_HSCROLL と WS_VSCROLL スタイルを*dwStyle*に追加します。

静的スプリッターウィンドウの詳細については、「[複数のドキュメントの種類、ビュー、フレームウィンドウ](../../mfc/multiple-document-types-views-and-frame-windows.md)」、「[テクニカルノート 29](../../mfc/tn029-splitter-windows.md)」、および「`CSplitterWnd` クラスの概要」の「分割ウィンドウ」を参照してください。

##  <a name="createview"></a>CSplitterWnd:: CreateView

静的スプリッターウィンドウのペインを作成します。

```
virtual BOOL CreateView(
    int row,
    int col,
    CRuntimeClass* pViewClass,
    SIZE sizeInit,
    CCreateContext* pContext);
```

### <a name="parameters"></a>パラメーター

*row*<br/>
新しいビューを配置する分割ウィンドウの行を指定します。

*col*<br/>
新しいビューを配置する分割ウィンドウ列を指定します。

*pViewClass*<br/>
新しいビューの[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)を指定します。

*sizeInit*<br/>
新しいビューの初期サイズを指定します。

*pContext*<br/>
ビューを作成するために使用される作成コンテキストへのポインター (通常は、分割ウィンドウを作成する親フレームのオーバーライドされた[CFrameWnd:: OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)メンバー関数に渡される*pContext* )。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>コメント

フレームワークがスプリッターを表示する前に、静的なスプリッターウィンドウのすべてのペインを作成する必要があります。

また、このメンバー関数は、動的分割ウィンドウのユーザーがペイン、行、または列を分割したときに新しいペインを作成するためにも呼び出されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#4](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_2.cpp)]

##  <a name="csplitterwnd"></a>CSplitterWnd:: CSplitterWnd

を呼び出して `CSplitterWnd` オブジェクトを構築します。

```
CSplitterWnd();
```

### <a name="remarks"></a>コメント

2つの手順で `CSplitterWnd` オブジェクトを構築します。 まず、コンストラクターを呼び出して `CSplitterWnd` オブジェクトを作成した後、 [Create](#create) member 関数を呼び出します。これにより、分割ウィンドウが作成され、`CSplitterWnd` オブジェクトにアタッチされます。

##  <a name="deletecolumn"></a>CSplitterWnd::D eleteColumn

スプリッターウィンドウから列を削除します。

```
virtual void DeleteColumn(int colDelete);
```

### <a name="parameters"></a>パラメーター

*colDelete*<br/>
削除する列を指定します。

### <a name="remarks"></a>コメント

このメンバー関数は、動的分割ウィンドウのロジックを実装するためにフレームワークによって呼び出されます (つまり、スプリッターウィンドウに SPLS_DYNAMIC_SPLIT スタイルがある場合)。 仮想関数[CreateView](#createview)と共にカスタマイズして、より高度な動的スプリッターを実装することができます。

##  <a name="deleterow"></a>CSplitterWnd::D eleteRow

スプリッターウィンドウから行を削除します。

```
virtual void DeleteRow(int rowDelete);
```

### <a name="parameters"></a>パラメーター

*行の削除*<br/>
削除する行を指定します。

### <a name="remarks"></a>コメント

このメンバー関数は、動的分割ウィンドウのロジックを実装するためにフレームワークによって呼び出されます (つまり、スプリッターウィンドウに SPLS_DYNAMIC_SPLIT スタイルがある場合)。 仮想関数[CreateView](#createview)と共にカスタマイズして、より高度な動的スプリッターを実装することができます。

##  <a name="deleteview"></a>CSplitterWnd::D eleteView

スプリッターウィンドウからビューを削除します。

```
virtual void DeleteView(
    int row,
    int col);
```

### <a name="parameters"></a>パラメーター

*row*<br/>
ビューを削除する分割ウィンドウの行を指定します。

*col*<br/>
ビューを削除する分割ウィンドウ列を指定します。

### <a name="remarks"></a>コメント

アクティブなビューが削除されている場合は、次のビューがアクティブになります。 既定の実装では、 [PostNcDestroy](../../mfc/reference/cwnd-class.md#postncdestroy)でビューが自動的に削除されます。

このメンバー関数は、動的分割ウィンドウのロジックを実装するためにフレームワークによって呼び出されます (つまり、スプリッターウィンドウに SPLS_DYNAMIC_SPLIT スタイルがある場合)。 仮想関数[CreateView](#createview)と共にカスタマイズして、より高度な動的スプリッターを実装することができます。

##  <a name="dokeyboardsplit"></a>CSplitterWnd::D Oキーボード分割

キーボード分割コマンド (通常は "ウィンドウ分割") を実行します。

```
virtual BOOL DoKeyboardSplit();
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>コメント

このメンバー関数は、`CSplitterWnd` の実装に委任するために[CView](../../mfc/reference/cview-class.md)クラスによって使用される高レベルのコマンドです。

##  <a name="doscroll"></a>CSplitterWnd::D oScroll

分割ウィンドウの同期スクロールを実行します。

```
virtual BOOL DoScroll(
    CView* pViewFrom,
    UINT nScrollCode,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>パラメーター

*pViewFrom*<br/>
スクロールメッセージの生成元であるビューへのポインター。

*nScrollCode*<br/>
ユーザーのスクロール要求を示すスクロールバーコード。 このパラメーターは2つの部分で構成されています。下位バイトは、水平方向に発生するスクロールの種類を決定し、上位バイトは垂直方向に発生するスクロールの種類を決定します。

    - SB_BOTTOM が一番下までスクロールします。

    - SB_LINEDOWN 1 行下にスクロールします。

    - SB_LINEUP 1 行上へスクロールします。

    - SB_PAGEDOWN 1 ページ下にスクロールします。

    - SB_PAGEUP 1 ページ上にスクロールします。

    - SB_TOP が一番上にスクロールします。

*bDoScroll*<br/>
指定されたスクロール操作が行われるかどうかを判断します。 *BDoScroll*が TRUE の場合 (つまり、子ウィンドウが存在し、分割ウィンドウにスクロール範囲がある場合)、指定されたスクロール操作を実行できます。*bDoScroll*が FALSE の場合 (つまり、子ウィンドウが存在しない場合、または分割ビューにスクロール範囲がない場合)、スクロールは行われません。

### <a name="return-value"></a>戻り値

同期されたスクロールが発生した場合は0以外。それ以外の場合は0です。

### <a name="remarks"></a>コメント

このメンバー関数は、ビューがスクロールメッセージを受信したときに分割ウィンドウの同期スクロールを実行するために、フレームワークによって呼び出されます。 同期スクロールが許可される前に、ユーザーによる操作が必要になるようにオーバーライドします。

##  <a name="doscrollby"></a>CSplitterWnd::D oScrollBy

分割ウィンドウを指定されたピクセル数でスクロールします。

```
virtual BOOL DoScrollBy(
    CView* pViewFrom,
    CSize sizeScroll,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>パラメーター

*pViewFrom*<br/>
スクロールメッセージの生成元であるビューへのポインター。

*sizeScroll*<br/>
水平方向および垂直方向にスクロールするピクセル数。

*bDoScroll*<br/>
指定されたスクロール操作が行われるかどうかを判断します。 *BDoScroll*が TRUE の場合 (つまり、子ウィンドウが存在し、分割ウィンドウにスクロール範囲がある場合)、指定されたスクロール操作を実行できます。*bDoScroll*が FALSE の場合 (つまり、子ウィンドウが存在しない場合、または分割ビューにスクロール範囲がない場合)、スクロールは行われません。

### <a name="return-value"></a>戻り値

同期されたスクロールが発生した場合は0以外。それ以外の場合は0です。

### <a name="remarks"></a>コメント

このメンバー関数は、スクロールメッセージに応答してフレームワークによって呼び出され、分割ウィンドウの同期されたスクロールをピクセル単位で*sizeScroll*によって実行します。 正の値は、スクロールダウンと右側の値を示します。負の値は、左右にスクロールすることを示します。

スクロールを許可する前に、ユーザーによる操作が必要になるようにオーバーライドします。

##  <a name="getactivepane"></a>CSplitterWnd:: GetActivePane

フレーム内のフォーカスビューまたはアクティブビューからアクティブペインを決定します。

```
virtual CWnd* GetActivePane(
    int* pRow = NULL,
    int* pCol = NULL);
```

### <a name="parameters"></a>パラメーター

*pRow*<br/>
アクティブなペインの行番号を取得するための**int**を指すポインターです。

*pCol*<br/>
アクティブなペインの列番号を取得するための**int**を指すポインターです。

### <a name="return-value"></a>戻り値

アクティブなペインへのポインター。 アクティブなペインが存在しない場合は NULL です。

### <a name="remarks"></a>コメント

このメンバー関数は、分割ウィンドウのアクティブペインを決定するためにフレームワークによって呼び出されます。 作業中のペインを取得する前に、ユーザーによる操作が必要になるようにオーバーライドします。

##  <a name="getcolumncount"></a>CSplitterWnd:: GetColumnCount

現在のペインの列数を返します。

```
int GetColumnCount() const;
```

### <a name="return-value"></a>戻り値

スプリッター内の現在の列数を返します。 静的スプリッターの場合は、列の最大数でもあります。

##  <a name="getcolumninfo"></a>CSplitterWnd:: GetColumnInfo

指定された列に関する情報を返します。

```
void GetColumnInfo(
    int col,
    int& cxCur,
    int& cxMin) const;
```

### <a name="parameters"></a>パラメーター

*col*<br/>
列を指定します。

*cxCur 異なる*<br/>
列の現在の幅に設定される**int**への参照。

*cxMin*<br/>
列の現在の最小幅に設定される**int**への参照。

##  <a name="getpane"></a>CSplitterWnd:: GetPane

指定された行と列にあるペインを返します。

```
CWnd* GetPane(
    int row,
    int col) const;
```

### <a name="parameters"></a>パラメーター

*row*<br/>
行を指定します。

*col*<br/>
列を指定します。

### <a name="return-value"></a>戻り値

指定された行と列にあるペインを返します。 返されるペインは、通常、 [CView](../../mfc/reference/cview-class.md)の派生クラスです。

##  <a name="getrowcount"></a>CSplitterWnd:: GetRowCount

現在のペインの行数を返します。

```
int GetRowCount() const;
```

### <a name="return-value"></a>戻り値

分割ウィンドウの現在の行数を返します。 静的スプリッターウィンドウの場合は、最大行数にもなります。

##  <a name="getrowinfo"></a>CSplitterWnd:: GetRowInfo

指定された行に関する情報を返します。

```
void GetRowInfo(
    int row,
    int& cyCur,
    int& cyMin) const;
```

### <a name="parameters"></a>パラメーター

*row*<br/>
行を指定します。

*cyCur*<br/>
行の現在の高さ (ピクセル単位) に設定される**int**への参照。

*cyMin*<br/>
行の現在の最小の高さ (ピクセル単位) に設定される**int**への参照。

### <a name="remarks"></a>コメント

指定した行に関する情報を取得するには、このメンバー関数を呼び出します。 *Cycur*パラメーターには、指定された行の現在の高さが格納され、 *cymin に*は行の最小の高さが格納されます。

##  <a name="getscrollstyle"></a>CSplitterWnd:: GetScrollStyle

スプリッターウィンドウの共有スクロールバースタイルを返します。

```
DWORD GetScrollStyle() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、次の windows スタイルフラグの1つ以上。

    - スプリッターが現在共有されている水平スクロールバーを管理している場合に WS_HSCROLL します。

    - スプリッターが現在共有されている垂直スクロールバーを管理している場合に WS_VSCROLL します。

0の場合、スプリッターウィンドウは、現在、共有されているスクロールバーを管理しません。

##  <a name="idfromrowcol"></a>CSplitterWnd:: IdFromRowCol

指定した行と列にあるペインの子ウィンドウ ID を取得します。

```
int IdFromRowCol(
    int row,
    int col) const;
```

### <a name="parameters"></a>パラメーター

*row*<br/>
分割ウィンドウの行を指定します。

*col*<br/>
分割ウィンドウ列を指定します。

### <a name="return-value"></a>戻り値

ペインの子ウィンドウ ID。

### <a name="remarks"></a>コメント

このメンバー関数は、非ビューをペインとして作成するために使用され、ペインが存在する前に呼び出すことができます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#5](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_3.cpp)]

##  <a name="ischildpane"></a>CSplitterWnd:: IsChildPane

*PWnd*がこのスプリッターウィンドウの子ペインであるかどうかを判断します。

```
BOOL IsChildPane(
    CWnd* pWnd,
    int* pRow,
    int* pCol);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
テストする[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトへのポインター。

*pRow*<br/>
行番号を格納する**int**を指すポインターです。

*pCol*<br/>
列番号を格納する**int**へのポインター。

### <a name="return-value"></a>戻り値

0以外の場合、 *pWnd*はこのスプリッターウィンドウの子ペインであり、 *Prow*と*pcol*は分割ウィンドウのペインの位置を使用して入力されます。 [ *PWnd* ] がこのスプリッターウィンドウの子ペインでない場合は、0が返されます。

### <a name="remarks"></a>コメント

6\.0 よりC++前の Visual バージョンでは、この関数はとして定義されていました。

`BOOL IsChildPane(CWnd* pWnd, int& row, int& col);`

このバージョンは互換性のために残されています。使用しないでください。

##  <a name="istracking"></a>CSplitterWnd:: IsTracking

このメンバー関数を呼び出して、ウィンドウの分割バーが現在移動されているかどうかを確認します。

```
BOOL IsTracking();
```

### <a name="return-value"></a>戻り値

スプリッター操作が進行中の場合は0以外。それ以外の場合は0です。

##  <a name="ondrawsplitter"></a>CSplitterWnd:: OnDrawSplitter

分割ウィンドウのイメージをレンダリングします。

```
virtual void OnDrawSplitter(
    CDC* pDC,
    ESplitType nType,
    const CRect& rect);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
描画するデバイスコンテキストへのポインター。 *PDC*が NULL の場合、 [CWnd:: redrawwindow](../../mfc/reference/cwnd-class.md#redrawwindow)はフレームワークによって呼び出され、分割ウィンドウは描画されません。

*nType*<br/>
`enum ESplitType`の値。次のいずれかを指定できます。

    - スプリッターのドラッグボックスを `splitBox` します。

    - 2つの分割ウィンドウの間に表示されるバーを `splitBar` します。

    - 分割ウィンドウの交差部分を `splitIntersection` します。 この要素は、Windows 95/98 で実行されている場合は呼び出されません。

    - 分割ウィンドウの境界線を `splitBorder` します。

*rect*<br/>
分割ウィンドウのサイズと形状を指定する、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトへの参照。

### <a name="remarks"></a>コメント

このメンバー関数は、スプリッターウィンドウの正確な特性を描画して指定するために、フレームワークによって呼び出されます。 分割ウィンドウのさまざまなグラフィカルコンポーネントの画像の高度なカスタマイズのために `OnDrawSplitter` をオーバーライドします。 既定の画像は、Microsoft Works for Windows または Microsoft Windows 95/98 のスプリッターに似ています。これは、分割バーの交差部分が一緒にブレンドされる点です。

動的分割ウィンドウの詳細については、「複数のドキュメントの[種類、ビュー、フレームウィンドウ](../../mfc/multiple-document-types-views-and-frame-windows.md)、[テクニカルノート 29](../../mfc/tn029-splitter-windows.md)、`CSplitterWnd` クラスの概要」の「分割ウィンドウ」を参照してください。

##  <a name="oninverttracker"></a>CSplitterWnd:: OnInvertTracker

分割ウィンドウのイメージを、フレームウィンドウと同じサイズおよび形状になるように表示します。

```
virtual void OnInvertTracker(const CRect& rect);
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
追跡四角形を指定する `CRect` オブジェクトへの参照。

### <a name="remarks"></a>コメント

このメンバー関数は、スプリッターのサイズ変更時にフレームワークによって呼び出されます。 分割ウィンドウの画像の高度なカスタマイズのために `OnInvertTracker` をオーバーライドします。 既定の画像は、Microsoft Works for Windows または Microsoft Windows 95/98 のスプリッターに似ています。これは、分割バーの交差部分が一緒にブレンドされる点です。

動的分割ウィンドウの詳細については、「複数のドキュメントの[種類、ビュー、フレームウィンドウ](../../mfc/multiple-document-types-views-and-frame-windows.md)、[テクニカルノート 29](../../mfc/tn029-splitter-windows.md)、`CSplitterWnd` クラスの概要」の「分割ウィンドウ」を参照してください。

##  <a name="recalclayout"></a>CSplitterWnd:: RecalcLayout

を呼び出して、行または列のサイズを調整した後にスプリッターウィンドウを再表示します。

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>コメント

[SetRowInfo](#setrowinfo)および[SetColumnInfo](#setcolumninfo)メンバー関数を使用して行と列のサイズを調整した後に、このメンバー関数を呼び出して、スプリッターウィンドウを正しく再表示します。 分割ウィンドウを表示する前に、作成プロセスの一部として行と列のサイズを変更した場合、このメンバー関数を呼び出す必要はありません。

このメンバー関数は、ユーザーがスプリッターウィンドウのサイズを変更するか、分割を移動するたびに、フレームワークによって呼び出されます。

### <a name="example"></a>例

  [CSplitterWnd:: SetColumnInfo](#setcolumninfo)の例を参照してください。

##  <a name="setactivepane"></a>CSplitterWnd:: SetActivePane

ウィンドウをフレーム内のアクティブなペインに設定します。

```
virtual void SetActivePane(
    int row,
    int col,
    CWnd* pWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*row*<br/>
*PWnd*が NULL の場合は、アクティブになるペイン内の行を指定します。

*col*<br/>
*PWnd*が NULL の場合は、アクティブになるペイン内の列を指定します。

*pWnd*<br/>
`CWnd` オブジェクトを指すポインターです。 NULL の場合、*行*と*列*によって指定されたペインはアクティブに設定されます。 NULL でない場合は、アクティブに設定されているペインを指定します。

### <a name="remarks"></a>コメント

このメンバー関数は、ユーザーがフレームウィンドウ内のペインにフォーカスを変更したときにペインをアクティブとして設定するために、フレームワークによって呼び出されます。 明示的に `SetActivePane` を呼び出して、指定されたビューにフォーカスを移すことができます。

行と列のいずれかを指定する**か、または** *pWnd*を提供して、ペインを指定します。

##  <a name="setcolumninfo"></a>CSplitterWnd:: SetColumnInfo

を呼び出して、指定された列情報を設定します。

```
void SetColumnInfo(
    int col,
    int cxIdeal,
    int cxMin);
```

### <a name="parameters"></a>パラメーター

*col*<br/>
分割ウィンドウ列を指定します。

*cxIdeal*<br/>
スプリッターウィンドウの列に対して最適な幅をピクセル単位で指定します。

*cxMin*<br/>
分割ウィンドウの列の最小幅をピクセル単位で指定します。

### <a name="remarks"></a>コメント

このメンバー関数を呼び出して、列の新しい最小幅と最適な幅を設定します。 列の最小値によって、列が小さすぎて完全に表示されるかどうかが決まります。

フレームワークは、分割ウィンドウを表示すると、最適なディメンションに従って列と行のペインをレイアウトし、スプリッターウィンドウのクライアント領域の左上から右下に向かって作業します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#6](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_4.cpp)]

##  <a name="setrowinfo"></a>CSplitterWnd:: SetRowInfo

を呼び出して、指定された行情報を設定します。

```
void SetRowInfo(
    int row,
    int cyIdeal,
    int cyMin);
```

### <a name="parameters"></a>パラメーター

*row*<br/>
分割ウィンドウの行を指定します。

*cyIdeal*<br/>
分割ウィンドウの行に最適な高さをピクセル単位で指定します。

*cyMin*<br/>
分割ウィンドウの行の最小の高さをピクセル単位で指定します。

### <a name="remarks"></a>コメント

このメンバー関数を呼び出して、行に新しい最小の高さと理想的な高さを設定します。 行の最小値は、行が小さすぎて完全に表示されるかどうかを決定します。

フレームワークは、分割ウィンドウを表示すると、最適なディメンションに従って列と行のペインをレイアウトし、スプリッターウィンドウのクライアント領域の左上から右下に向かって作業します。

##  <a name="setscrollstyle"></a>CSplitterWnd:: SetScrollStyle

スプリッターウィンドウの共有スクロールバーサポートの新しいスクロールスタイルを指定します。

```
void SetScrollStyle(DWORD dwStyle);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
スプリッターウィンドウの共有スクロールバーサポートの新しいスクロールスタイル。次のいずれかの値を指定できます。

- WS_HSCROLL、水平方向の共有スクロールバーを作成または表示します。

- WS_VSCROLL、垂直方向の共有スクロールバーを作成または表示します。

### <a name="remarks"></a>コメント

スクロールバーが作成されると、そのスタイルを指定せずに `SetScrollStyle` が呼び出されても、破棄されません。スクロールバーは表示されません。 これにより、スクロールバーが非表示になっている場合でも状態を維持できます。 `SetScrollStyle` を呼び出した後、すべての変更を有効にするには、 [RecalcLayout](#recalclayout)を呼び出す必要があります。

##  <a name="splitcolumn"></a>CSplitterWnd:: SplitColumn

フレームウィンドウが垂直方向に分割する場所を示します。

```
virtual BOOL SplitColumn(int cxBefore);
```

### <a name="parameters"></a>パラメーター

*cxBefore*<br/>
分割が行われる前の位置 (ピクセル単位)。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>コメント

このメンバー関数は、垂直分割ウィンドウが作成されるときに呼び出されます。 `SplitColumn` は、分割が発生する既定の場所を示します。

`SplitColumn` は、動的分割ウィンドウのロジックを実装するためにフレームワークによって呼び出されます (つまり、スプリッターウィンドウに SPLS_DYNAMIC_SPLIT スタイルがある場合)。 仮想関数[CreateView](#createview)と共にカスタマイズして、より高度な動的スプリッターを実装することができます。

##  <a name="splitrow"></a>CSplitterWnd:: SplitRow

フレームウィンドウを水平方向に分割する場所を示します。

```
virtual BOOL SplitRow(int cyBefore);
```

### <a name="parameters"></a>パラメーター

*cyBefore*<br/>
分割が行われる前の位置 (ピクセル単位)。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>コメント

このメンバー関数は、水平分割ウィンドウが作成されるときに呼び出されます。 `SplitRow` は、分割が発生する既定の場所を示します。

`SplitRow` は、動的分割ウィンドウのロジックを実装するためにフレームワークによって呼び出されます (つまり、スプリッターウィンドウに SPLS_DYNAMIC_SPLIT スタイルがある場合)。 仮想関数[CreateView](#createview)と共にカスタマイズして、より高度な動的スプリッターを実装することができます。

##  <a name="ondraw"></a>CSplitterWnd:: OnDraw

スプリッターウィンドウを描画するためにフレームワークによって呼び出されます。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
デバイスコンテキストへのポインター。

### <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[MFC のサンプル VIEWEX](../../overview/visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CView クラス](../../mfc/reference/cview-class.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)
