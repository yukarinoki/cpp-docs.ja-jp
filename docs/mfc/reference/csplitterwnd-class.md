---
title: クラスを分割する
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
ms.openlocfilehash: 8c8ce90f5e36d6cdc2592233588bc3bd7bf2c9d6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371692"
---
# <a name="csplitterwnd-class"></a>クラスを分割する

分割ウィンドウの機能が用意されています。分割ウィンドウとは複数のペインを持つウィンドウです。

## <a name="syntax"></a>構文

```
class CSplitterWnd : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cスプリットターウンド::Cスプリットターウンド](#csplitterwnd)|オブジェクトを構築するための`CSplitterWnd`呼び出し。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[次の手順をアクティブにします。](#activatenext)|[次のペイン] または [前のウィンドウ] コマンドを実行します。|
|[次にスプリッターウンド::カンアクティベート](#canactivatenext)|[次のウィンドウ] コマンドまたは [前のウィンドウ] コマンドが現在使用可能かどうかを確認します。|
|[スプリッタウンド::作成](#create)|動的分割ウィンドウを作成し、`CSplitterWnd`オブジェクトにアタッチする呼び出し。|
|[分割された分割::作成スクロールバーネク](#createscrollbarctrl)|共有スクロール バー コントロールを作成します。|
|[スプリッタンド::作成静的](#createstatic)|静的分割ウィンドウを作成し、`CSplitterWnd`オブジェクトにアタッチする呼び出し。|
|[スプリッタウンド::ビューの作成](#createview)|分割ウィンドウにペインを作成する呼び出し。|
|[スプリッターウンド::Dエレテカラム](#deletecolumn)|分割ウィンドウから列を削除します。|
|[CSplitterWnd::Dエレテロウ](#deleterow)|分割ウィンドウから行を削除します。|
|[スプリッターウンド::Dエレテビュー](#deleteview)|分割ウィンドウからビューを削除します。|
|[スプリッターウンド::Doキーボードスプリット](#dokeyboardsplit)|キーボード分割コマンド (通常はウィンドウ分割) を実行します。|
|[:Dスクロール](#doscroll)|分割ウィンドウの同期スクロールを実行します。|
|[スプリッターウンド::Doスクロールバイ](#doscrollby)|指定したピクセル数だけ分割ウィンドウをスクロールします。|
|[スプリッタウンド::Getアクティブペイン](#getactivepane)|フレーム内のフォーカスまたはアクティブなビューからアクティブなペインを決定します。|
|[スプリッタウンド::ゲットカラムカウント](#getcolumncount)|現在のペインの列数を返します。|
|[スプリッタンド::ゲットカラムインフォ](#getcolumninfo)|指定した列の情報を返します。|
|[スプリッタウンド::ゲットペイン](#getpane)|指定した行と列のペインを返します。|
|[スプリッターウンド::ゲットローカウント](#getrowcount)|現在のペインの行数を返します。|
|[スプリッターウンド::ゲットロウインフォ](#getrowinfo)|指定した行の情報を返します。|
|[スプリッターウンド:::ゲットスクロールスタイル](#getscrollstyle)|共有スクロール バーのスタイルを返します。|
|[スプリッターウンド::IdFromRowCol](#idfromrowcol)|指定した行と列のペインの子ウィンドウ ID を返します。|
|[スプリッタンド::イスプリットペイン](#ischildpane)|ウィンドウが現在この分割ウィンドウの子ウィンドウかどうかを確認する呼び出し。|
|[スプリッターウンド::イズトラッキング](#istracking)|分割バーが現在移動中かどうかを判断します。|
|[CSplitterWnd::再計算レイアウト](#recalclayout)|行または列のサイズを調整した後に、分割ウィンドウを再表示する呼び出し。|
|[スプリッタウンド::セットアクティブペイン](#setactivepane)|枠内のアクティブなペインに設定します。|
|[分割された項目::列の設定](#setcolumninfo)|指定した列情報を設定する呼び出し。|
|[スプリッターウンド::セットローインフォ](#setrowinfo)|指定された行情報を設定する呼び出し。|
|[スプリッタウンド::セットスクロールスタイル](#setscrollstyle)|分割ウィンドウの共有スクロール バーのサポートに対する新しいスクロール バー スタイルを指定します。|
|[分割列::分割列](#splitcolumn)|フレーム ウィンドウが垂直方向に分割される位置を示します。|
|[スプリッタローンド::スプリットロー](#splitrow)|フレーム ウィンドウが水平方向に分割される位置を示します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[スプリッタウンド::オンドロー](#ondraw)|分割ウィンドウを描画するためにフレームワークによって呼び出されます。|
|[スプリッタ分割::オンドロースプリッター](#ondrawsplitter)|分割ウィンドウのイメージをレンダリングします。|
|[Cスプリッターウンド::オンインバートトラッカー](#oninverttracker)|分割ウィンドウのイメージをフレーム ウィンドウと同じサイズおよびシェイプにレンダリングします。|

## <a name="remarks"></a>解説

ペインは通常[CView](../../mfc/reference/cview-class.md)から派生したアプリケーション固有のオブジェクトですが、適切な子ウィンドウ ID を持つ[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトを指定できます。

`CSplitterWnd`オブジェクトは通常、親[CFrameWnd](../../mfc/reference/cframewnd-class.md)または[CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)オブジェクトに埋め込まれます。 次の`CSplitterWnd`手順でオブジェクトを作成します。

1. 親フレーム`CSplitterWnd`にメンバー変数を埋め込みます。

2. 親フレームの[CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)メンバー関数をオーバーライドします。

3. `OnCreateClient`オーバーライドされた 内から、 の[作成](#create)または[静的な作成](#createstatic)のメンバー`CSplitterWnd`関数を呼び出します。

`Create`動的分割ウィンドウを作成するには、メンバー関数を呼び出します。 動的分割ウィンドウは、通常、同じドキュメントの複数の個別のペイン (ビュー) を作成およびスクロールするために使用されます。 フレームワークは、スプリッターの初期ペインを自動的に作成します。次に、ユーザーが分割ウィンドウのコントロールを操作すると、フレームワークは追加のペインを作成、サイズ変更、および破棄します。

呼び出`Create`しを行う場合は、行の高さと列の幅の最小値を指定します。 呼び出`Create`し後は、[メンバー](#setcolumninfo)関数を呼び出すことによってこれらの[最小値を調整](#setrowinfo)できます。

また、`SetColumnInfo`および`SetRowInfo`メンバー関数を使用して、列の 「理想的な」 幅と行の 「理想的な」高さを設定します。 フレームワークが分割ウィンドウを表示すると、最初に親フレームが表示され、次に分割ウィンドウが表示されます。 フレームワークは、最適なサイズに応じて、ペインを列と行に配置し、スプリッタ ウィンドウのクライアント領域の左上から右下隅まで作業します。

動的分割ウィンドウ内のすべてのペインは、同じクラスである必要があります。 動的分割ウィンドウをサポートする使い慣れたアプリケーションには、Word と Excel があります。

メンバー関数`CreateStatic`を使用して、静的分割ウィンドウを作成します。 ユーザーは、静的分割ウィンドウ内のペインのサイズのみを変更でき、その数や順序は変更できません。

静的分割線を作成するときは、静的分割線のすべてのペインを具体的に作成する必要があります。 親フレームの`OnCreateClient`メンバー関数が返される前に、すべてのペインを作成するか、フレームワークがウィンドウを正しく表示しないようにしてください。

この`CreateStatic`メンバー関数は、行の高さと列幅が 0 の最小値を使用して静的分割線を自動的に初期化します。 を呼び`Create`出した後、これらの最小値を調整するには、[メンバー](#setcolumninfo)関数[SetRowInfo](#setrowinfo)を呼び出します。 また、`SetColumnInfo`希望`SetRowInfo`する理想的な`CreateStatic`ペインの寸法を示すために、呼び出した後も使用します。

静的分割線の個々のペインは、多くの場合、異なるクラスに属します。 静的分割ウィンドウの例については、グラフィックス エディターと Windows ファイル マネージャーを参照してください。

分割ウィンドウでは、(ペインに表示されるスクロール バーを除く) 特別なスクロール バーがサポートされます。 これらのスクロール バーはオブジェクトの`CSplitterWnd`子であり、ペインと共有されます。

分割ウィンドウを作成するときに、これらの特別なスクロール バーを作成します。 たとえば、 1`CSplitterWnd`行、2 列、および WS_VSCROLL スタイルを持つ a には、2 つのペインで共有される垂直スクロール バーが表示されます。 ユーザーがスクロール バーを移動すると、WM_VSCROLLメッセージが両方のペインに送信されます。 ペインがスクロール バーの位置を設定すると、共有スクロール バーが設定されます。

スプリッタ ウィンドウの詳細については、[テクニカル ノート 29](../../mfc/tn029-splitter-windows.md)を参照してください。

動的分割ウィンドウの作成方法の詳細については、以下を参照してください。

- MFC サンプル[落書き](../../overview/visual-cpp-samples.md)

- MFC サンプル[のビューエックス](../../overview/visual-cpp-samples.md)

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSplitterWnd`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxext.h

## <a name="csplitterwndactivatenext"></a><a name="activatenext"></a>次の手順をアクティブにします。

[次のウィンドウ] または [前のウィンドウ] コマンドを実行するために、フレームワークによって呼び出されます。

```
virtual void ActivateNext(BOOL bPrev = FALSE);
```

### <a name="parameters"></a>パラメーター

*bプレフ*<br/>
アクティブにするウィンドウを示します。 **前の場合は TRUE。** 次の**場合は FALSE。**

### <a name="remarks"></a>解説

このメンバー関数は[、CView](../../mfc/reference/cview-class.md)クラスが実装にデリゲートするために使用する高レベルのコマンド`CSplitterWnd`です。

## <a name="csplitterwndcanactivatenext"></a><a name="canactivatenext"></a>次にスプリッターウンド::カンアクティベート

[次のウィンドウ] コマンドまたは [前のウィンドウ] コマンドが現在可能かどうかを確認するために、フレームワークによって呼び出されます。

```
virtual BOOL CanActivateNext(BOOL bPrev = FALSE);
```

### <a name="parameters"></a>パラメーター

*bプレフ*<br/>
アクティブにするウィンドウを示します。 **前の場合は TRUE。** 次の**場合は FALSE。**

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は[、CView](../../mfc/reference/cview-class.md)クラスが実装にデリゲートするために使用する高レベルのコマンド`CSplitterWnd`です。

## <a name="csplitterwndcreate"></a><a name="create"></a>スプリッタウンド::作成

動的分割ウィンドウを作成するには、メンバー関数を`Create`呼び出します。

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
分割ウィンドウの親フレーム ウィンドウ。

*数列数*<br/>
分割ウィンドウの最大行数。 この値は 2 を超えることはできません。

*nマックスコルズ*<br/>
分割ウィンドウの列の最大数。 この値は 2 を超えることはできません。

*サイズミン*<br/>
ペインを表示できる最小サイズを指定します。

*pContext*<br/>
[構造体](../../mfc/reference/ccreatecontext-structure.md)へのポインター。 ほとんどの場合、親フレーム ウィンドウに渡される*pContext*を指定できます。

*Dwstyle*<br/>
ウィンドウ スタイルを指定します。

*nID*<br/>
ウィンドウの子ウィンドウ ID。 分割ウィンドウが別の分割ウィンドウ内にネストされていない限り、ID をAFX_IDW_PANE_FIRSTできます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

親`CSplitterWnd`[CFrameWnd](../../mfc/reference/cframewnd-class.md)オブジェクトまたは[CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)オブジェクトに埋め込むには、次の手順を実行します。

1. 親フレーム`CSplitterWnd`にメンバー変数を埋め込みます。

1. 親フレームの[CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)メンバー関数をオーバーライドします。

1. オーバーライドされた`Create``OnCreateClient`内からメンバー関数を呼び出します。

親フレーム内から分割ウィンドウを作成する場合は、親フレームの*pContext*パラメーターを分割ウィンドウに渡します。 それ以外の場合、このパラメーターは NULL にすることができます。

動的分割ウィンドウの行の高さと列の幅の初期の最小幅は *、sizeMin*パラメーターによって設定されます。 ペインが小さすぎて全体を表示できないかどうかを決定するこれらの最小値は[、SetRowInfo](#setrowinfo)および[SetColumnInfo](#setcolumninfo)メンバー関数を使用して変更できます。

動的分割ウィンドウの詳細については、[記事「複数のドキュメントの種類、ビュー、およびフレーム ウィンドウ](../../mfc/multiple-document-types-views-and-frame-windows.md)」の「スプリッタ ウィンドウ」、テクニカル ノート`CSplitterWnd` [29、](../../mfc/tn029-splitter-windows.md)およびクラスの概要を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#125](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_1.cpp)]

## <a name="csplitterwndcreatescrollbarctrl"></a><a name="createscrollbarctrl"></a>分割された分割::作成スクロールバーネク

共有スクロール バー コントロールを作成するために、フレームワークによって呼び出されます。

```
virtual BOOL CreateScrollBarCtrl(
    DWORD dwStyle,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
ウィンドウ スタイルを指定します。

*nID*<br/>
ウィンドウの子ウィンドウ ID。 分割ウィンドウが別の分割ウィンドウ内にネストされていない限り、ID をAFX_IDW_PANE_FIRSTできます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

スクロール`CreateScrollBarCtrl`バーの横にコントロールを追加する場合は、オーバーライドします。 既定の動作では、通常の Windows スクロール バー コントロールが作成されます。

## <a name="csplitterwndcreatestatic"></a><a name="createstatic"></a>スプリッタンド::作成静的

静的分割ウィンドウを作成するには、メンバー関数を`CreateStatic`呼び出します。

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
分割ウィンドウの親フレーム ウィンドウ。

*nRows*<br/>
行数です。 この値は 16 を超えてはなりません。

*nコル*<br/>
列数です。 この値は 16 を超えてはなりません。

*Dwstyle*<br/>
ウィンドウ スタイルを指定します。

*nID*<br/>
ウィンドウの子ウィンドウ ID。 分割ウィンドウが別の分割ウィンドウ内にネストされていない限り、ID をAFX_IDW_PANE_FIRSTできます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

A`CSplitterWnd`は通常、次の`CFrameWnd`手順を実行して、親オブジェクトまたは[CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)オブジェクトに埋め込まれます。

1. 親フレーム`CSplitterWnd`にメンバー変数を埋め込みます。

1. 親フレームのメンバー関数を`OnCreateClient`オーバーライドします。

1. オーバーライドされた`CreateStatic` [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)内からメンバー関数を呼び出します。

静的分割ウィンドウには、多くの場合、異なるクラスの一定の数のペインが含まれています。

静的分割ウィンドウを作成する場合は、同時にすべてのウィンドウを作成する必要があります。 [通常、CreateView](#createview)メンバー関数は、この目的のために使用されますが、他の非ビュー クラスも作成できます。

静的分割ウィンドウの行の高さと列の最初の最小幅は 0 です。 ペインが小さすぎて全体を表示できない場合に、これらの最小値を[指定するには、SetRowInfo](#setrowinfo)と[SetColumnInfo](#setcolumninfo)メンバー関数を使用します。

静的な分割ウィンドウにスクロール バーを追加するには、WS_HSCROLLとWS_VSCROLLスタイルを*dwStyle*に追加します。

静的分割ウィンドウの詳細については、「複数の[ドキュメントの種類、ビュー、およびフレーム ウィンドウ](../../mfc/multiple-document-types-views-and-frame-windows.md)」の「スプリッタ`CSplitterWnd`ウィンドウ」、テクニカル ノート[29、](../../mfc/tn029-splitter-windows.md)およびクラスの概要を参照してください。

## <a name="csplitterwndcreateview"></a><a name="createview"></a>スプリッタウンド::ビューの作成

静的分割ウィンドウのペインを作成します。

```
virtual BOOL CreateView(
    int row,
    int col,
    CRuntimeClass* pViewClass,
    SIZE sizeInit,
    CCreateContext* pContext);
```

### <a name="parameters"></a>パラメーター

*行*<br/>
新しいビューを配置する分割ウィンドウの行を指定します。

*col*<br/>
新しいビューを配置する分割ウィンドウの列を指定します。

*クラスを表示します。*<br/>
新しいビューの[C ランタイム クラス](../../mfc/reference/cruntimeclass-structure.md)を指定します。

*サイズイニト*<br/>
新しいビューの初期サイズを指定します。

*pContext*<br/>
ビューの作成に使用される作成コンテキストへのポインター (通常、スプリッター ウィンドウが作成される親フレームのオーバーライドされた[CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)メンバー関数に渡される*pContext)。*

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

静的分割ウィンドウのすべてのウィンドウは、フレームワークが分割ウィンドウを表示する前に作成する必要があります。

また、動的分割ウィンドウのユーザーがペイン、行、または列を分割したときに、フレームワークは、このメンバー関数を呼び出して新しいペインを作成します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#4](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_2.cpp)]

## <a name="csplitterwndcsplitterwnd"></a><a name="csplitterwnd"></a>Cスプリットターウンド::Cスプリットターウンド

オブジェクトを構築するための`CSplitterWnd`呼び出し。

```
CSplitterWnd();
```

### <a name="remarks"></a>解説

2`CSplitterWnd`つの手順でオブジェクトを作成します。 まず、オブジェクトを作成するコンストラクターを`CSplitterWnd`呼び出し、次に[Create](#create)メンバー関数を`CSplitterWnd`呼び出します。

## <a name="csplitterwnddeletecolumn"></a><a name="deletecolumn"></a>スプリッターウンド::Dエレテカラム

分割ウィンドウから列を削除します。

```
virtual void DeleteColumn(int colDelete);
```

### <a name="parameters"></a>パラメーター

*コル削除*<br/>
削除する列を指定します。

### <a name="remarks"></a>解説

このメンバー関数は、フレームワークによって動的分割ウィンドウのロジックを実装するために呼び出されます (つまり、分割ウィンドウにSPLS_DYNAMIC_SPLITスタイルがある場合)。 仮想関数[CreateView](#createview)と共にカスタマイズして、より高度な動的スプリッタを実装できます。

## <a name="csplitterwnddeleterow"></a><a name="deleterow"></a>CSplitterWnd::Dエレテロウ

分割ウィンドウから行を削除します。

```
virtual void DeleteRow(int rowDelete);
```

### <a name="parameters"></a>パラメーター

*行削除*<br/>
削除する行を指定します。

### <a name="remarks"></a>解説

このメンバー関数は、フレームワークによって動的分割ウィンドウのロジックを実装するために呼び出されます (つまり、分割ウィンドウにSPLS_DYNAMIC_SPLITスタイルがある場合)。 仮想関数[CreateView](#createview)と共にカスタマイズして、より高度な動的スプリッタを実装できます。

## <a name="csplitterwnddeleteview"></a><a name="deleteview"></a>スプリッターウンド::Dエレテビュー

分割ウィンドウからビューを削除します。

```
virtual void DeleteView(
    int row,
    int col);
```

### <a name="parameters"></a>パラメーター

*行*<br/>
ビューを削除する分割ウィンドウ行を指定します。

*col*<br/>
ビューを削除する分割ウィンドウの列を指定します。

### <a name="remarks"></a>解説

アクティブなビューが削除されている場合、次のビューがアクティブになります。 既定の実装では、ビューが[PostNcDestroy](../../mfc/reference/cwnd-class.md#postncdestroy)で自動的に削除されることを前提としています。

このメンバー関数は、フレームワークによって動的分割ウィンドウのロジックを実装するために呼び出されます (つまり、分割ウィンドウにSPLS_DYNAMIC_SPLITスタイルがある場合)。 仮想関数[CreateView](#createview)と共にカスタマイズして、より高度な動的スプリッタを実装できます。

## <a name="csplitterwnddokeyboardsplit"></a><a name="dokeyboardsplit"></a>スプリッターウンド::Doキーボードスプリット

キーボード分割コマンド (通常はウィンドウ分割) を実行します。

```
virtual BOOL DoKeyboardSplit();
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は[、CView](../../mfc/reference/cview-class.md)クラスが実装にデリゲートするために使用する高レベルのコマンド`CSplitterWnd`です。

## <a name="csplitterwnddoscroll"></a><a name="doscroll"></a>:Dスクロール

分割ウィンドウの同期スクロールを実行します。

```
virtual BOOL DoScroll(
    CView* pViewFrom,
    UINT nScrollCode,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>パラメーター

*から見る*<br/>
スクロール メッセージの発生元のビューへのポインター。

*スクロールコード*<br/>
ユーザーのスクロール要求を示すスクロール バー コード。 このパラメーターは、水平に行われるスクロールのタイプを決定する下位バイトと、垂直に発生するスクロールのタイプを決定する高次バイトの 2 つの部分で構成されます。

- SB_BOTTOM 下にスクロールします。

- SB_LINEDOWN 1 行下にスクロールします。

- SB_LINEUP 1 行上にスクロールします。

- SB_PAGEDOWN 1 ページ下にスクロールします。

- SB_PAGEUP 1 ページ上にスクロールします。

- SB_TOP上にスクロールします。

*スクロール*<br/>
指定されたスクロール操作が発生するかどうかを判断します。 *bDoScroll*が TRUE の場合 (つまり、子ウィンドウが存在し、分割ウィンドウにスクロール範囲がある場合)、指定されたスクロールアクションが実行されます。*bDoScroll*が FALSE の場合 (つまり、子ウィンドウが存在しない場合、または分割ビューにスクロール範囲がない場合)、スクロールは行われません。

### <a name="return-value"></a>戻り値

同期スクロールが発生した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメンバー関数は、ビューがスクロール メッセージを受信したときに分割ウィンドウの同期スクロールを実行するために、フレームワークによって呼び出されます。 同期スクロールが許可される前にユーザーによる操作を要求する場合は、オーバーライドします。

## <a name="csplitterwnddoscrollby"></a><a name="doscrollby"></a>スプリッターウンド::Doスクロールバイ

指定したピクセル数だけ分割ウィンドウをスクロールします。

```
virtual BOOL DoScrollBy(
    CView* pViewFrom,
    CSize sizeScroll,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>パラメーター

*から見る*<br/>
スクロール メッセージの発生元のビューへのポインター。

*サイズスクロール*<br/>
水平方向および垂直方向にスクロールするピクセル数です。

*スクロール*<br/>
指定されたスクロール操作が発生するかどうかを判断します。 *bDoScroll*が TRUE の場合 (つまり、子ウィンドウが存在し、分割ウィンドウにスクロール範囲がある場合)、指定されたスクロールアクションが実行されます。*bDoScroll*が FALSE の場合 (つまり、子ウィンドウが存在しない場合、または分割ビューにスクロール範囲がない場合)、スクロールは行われません。

### <a name="return-value"></a>戻り値

同期スクロールが発生した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメンバー関数は、スクロール メッセージに応答してフレームワークによって呼び出され、*サイズによって*示されるピクセル単位の分割ウィンドウの同期スクロールを実行します。 正の値は、スクロールダウンと右を示します。負の値は、左にスクロールすることを示します。

スクロールを許可する前にユーザーによる操作を要求する場合は、オーバーライドします。

## <a name="csplitterwndgetactivepane"></a><a name="getactivepane"></a>スプリッタウンド::Getアクティブペイン

フレーム内のフォーカスまたはアクティブなビューからアクティブなペインを決定します。

```
virtual CWnd* GetActivePane(
    int* pRow = NULL,
    int* pCol = NULL);
```

### <a name="parameters"></a>パラメーター

*pRow*<br/>
アクティブなペインの行番号を取得する**int**へのポインター。

*pCol*<br/>
アクティブなペインの列番号を取得する**int**へのポインター。

### <a name="return-value"></a>戻り値

アクティブなペインへのポインター。 アクティブなペインが存在しない場合は NULL。

### <a name="remarks"></a>解説

このメンバー関数は、分割ウィンドウのアクティブなペインを決定するために、フレームワークによって呼び出されます。 アクティブなペインを取得する前にユーザーが操作を要求する場合は、オーバーライドします。

## <a name="csplitterwndgetcolumncount"></a><a name="getcolumncount"></a>スプリッタウンド::ゲットカラムカウント

現在のペインの列数を返します。

```
int GetColumnCount() const;
```

### <a name="return-value"></a>戻り値

分割線の現在の列数を返します。 静的分割線の場合、これは列の最大数でもあります。

## <a name="csplitterwndgetcolumninfo"></a><a name="getcolumninfo"></a>スプリッタンド::ゲットカラムインフォ

指定した列の情報を返します。

```
void GetColumnInfo(
    int col,
    int& cxCur,
    int& cxMin) const;
```

### <a name="parameters"></a>パラメーター

*col*<br/>
列を指定します。

*cxCur*<br/>
列の現在の幅に設定する**int**への参照。

*cxMin*<br/>
列の現在の最小幅に設定する**int**への参照。

## <a name="csplitterwndgetpane"></a><a name="getpane"></a>スプリッタウンド::ゲットペイン

指定した行と列のペインを返します。

```
CWnd* GetPane(
    int row,
    int col) const;
```

### <a name="parameters"></a>パラメーター

*行*<br/>
行を指定します。

*col*<br/>
列を指定します。

### <a name="return-value"></a>戻り値

指定した行と列のペインを返します。 返されるペインは、通常[、CView](../../mfc/reference/cview-class.md)派生クラスです。

## <a name="csplitterwndgetrowcount"></a><a name="getrowcount"></a>スプリッターウンド::ゲットローカウント

現在のペインの行数を返します。

```
int GetRowCount() const;
```

### <a name="return-value"></a>戻り値

分割ウィンドウの現在の行数を返します。 静的分割ウィンドウの場合、これは行の最大数でもあります。

## <a name="csplitterwndgetrowinfo"></a><a name="getrowinfo"></a>スプリッターウンド::ゲットロウインフォ

指定した行の情報を返します。

```
void GetRowInfo(
    int row,
    int& cyCur,
    int& cyMin) const;
```

### <a name="parameters"></a>パラメーター

*行*<br/>
行を指定します。

*シクル*<br/>
行の現在の高さをピクセル単位で設定する**int**への参照。

*サイミン*<br/>
行の現在の最小の高さをピクセル単位で設定する**int**への参照。

### <a name="remarks"></a>解説

指定した行に関する情報を取得します。 *cyCur*パラメータは指定された行の現在の高さで塗られ *、cyMin*は行の最小の高さで塗りつぶされます。

## <a name="csplitterwndgetscrollstyle"></a><a name="getscrollstyle"></a>スプリッターウンド:::ゲットスクロールスタイル

分割ウィンドウの共有スクロール バー スタイルを返します。

```
DWORD GetScrollStyle() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、次のウィンドウ スタイル フラグの 1 つ以上。

- WS_HSCROLL分割線が現在共有水平スクロール バーを管理している場合。

- WS_VSCROLL分割線が現在、共有垂直スクロール バーを管理している場合。

0 の場合、分割ウィンドウは現在、共有スクロール バーを管理しません。

## <a name="csplitterwndidfromrowcol"></a><a name="idfromrowcol"></a>スプリッターウンド::IdFromRowCol

指定した行と列のペインの子ウィンドウ ID を取得します。

```
int IdFromRowCol(
    int row,
    int col) const;
```

### <a name="parameters"></a>パラメーター

*行*<br/>
分割ウィンドウの行を指定します。

*col*<br/>
分割ウィンドウの列を指定します。

### <a name="return-value"></a>戻り値

ペインの子ウィンドウ ID。

### <a name="remarks"></a>解説

このメンバー関数は、ペインとしてビュー以外を作成するために使用され、ペインが存在する前に呼び出される場合があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#5](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_3.cpp)]

## <a name="csplitterwndischildpane"></a><a name="ischildpane"></a>スプリッタンド::イスプリットペイン

*pWnd*が現在この分割ウィンドウの子ペインかどうかを判断します。

```
BOOL IsChildPane(
    CWnd* pWnd,
    int* pRow,
    int* pCol);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
テストする[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトへのポインター。

*pRow*<br/>
行番号を格納する**int**へのポインター。

*pCol*<br/>
列番号を格納する**int**へのポインター。

### <a name="return-value"></a>戻り値

0 以外の場合 *、pWnd*は現在この分割ウィンドウの子ペインであり *、pRow*と*pCol*は分割ウィンドウのペインの位置で埋められます。 *pWnd*がこの分割ウィンドウの子ペインでない場合は、0 が返されます。

### <a name="remarks"></a>解説

6.0 より前の Visual C++ バージョンでは、この関数は次のように定義されていました。

`BOOL IsChildPane(CWnd* pWnd, int& row, int& col);`

このバージョンは現在廃止され、使用しないでください。

## <a name="csplitterwndistracking"></a><a name="istracking"></a>スプリッターウンド::イズトラッキング

ウィンドウ内の分割バーが現在移動中かどうかを調べます。

```
BOOL IsTracking();
```

### <a name="return-value"></a>戻り値

分割操作が進行中の場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="csplitterwndondrawsplitter"></a><a name="ondrawsplitter"></a>スプリッタ分割::オンドロースプリッター

分割ウィンドウのイメージをレンダリングします。

```
virtual void OnDrawSplitter(
    CDC* pDC,
    ESplitType nType,
    const CRect& rect);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
描画するデバイス コンテキストへのポインター。 *pDC*が NULL の場合[、CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow)がフレームワークによって呼び出され、分割ウィンドウは描画されません。

*nType*<br/>
の値`enum ESplitType`は、次のいずれかになります。

- `splitBox`分割線のドラッグ ボックス。

- `splitBar`2 つの分割ウィンドウの間に表示されるバー。

- `splitIntersection`分割ウィンドウの交差部分。 この要素は、Windows 95/98 で実行されている場合は呼び出されません。

- `splitBorder`分割ウィンドウの境界線。

*Rect*<br/>
分割ウィンドウのサイズと形状を指定する[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトへの参照。

### <a name="remarks"></a>解説

このメンバー関数は、フレームワークによって、分割ウィンドウの正確な特性を描画および指定するために呼び出されます。 分割`OnDrawSplitter`ウィンドウのさまざまなグラフィカル コンポーネントの画像の高度なカスタマイズをオーバーライドします。 既定のイメージは、分割バーの交差がブレンドされるという点で、Windows 用 Microsoft Works または Windows 95/98 のスプリッターと似ています。

動的分割ウィンドウの詳細については、[記事「複数のドキュメントの種類、ビュー、およびフレーム ウィンドウ](../../mfc/multiple-document-types-views-and-frame-windows.md)」の「スプリッタ ウィンドウ」、テクニカル ノート`CSplitterWnd` [29、](../../mfc/tn029-splitter-windows.md)およびクラスの概要を参照してください。

## <a name="csplitterwndoninverttracker"></a><a name="oninverttracker"></a>Cスプリッターウンド::オンインバートトラッカー

分割ウィンドウのイメージをフレーム ウィンドウと同じサイズおよびシェイプにレンダリングします。

```
virtual void OnInvertTracker(const CRect& rect);
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
追跡用の`CRect`四角形を指定するオブジェクトへの参照。

### <a name="remarks"></a>解説

このメンバー関数は、分割子のサイズ変更時にフレームワークによって呼び出されます。 分割`OnInvertTracker`ウィンドウの画像の高度なカスタマイズをオーバーライドします。 既定のイメージは、分割バーの交差がブレンドされるという点で、Windows 用 Microsoft Works または Windows 95/98 のスプリッターと似ています。

動的分割ウィンドウの詳細については、[記事「複数のドキュメントの種類、ビュー、およびフレーム ウィンドウ](../../mfc/multiple-document-types-views-and-frame-windows.md)」の「スプリッタ ウィンドウ」、テクニカル ノート`CSplitterWnd` [29、](../../mfc/tn029-splitter-windows.md)およびクラスの概要を参照してください。

## <a name="csplitterwndrecalclayout"></a><a name="recalclayout"></a>CSplitterWnd::再計算レイアウト

行または列のサイズを調整した後に、分割ウィンドウを再表示する呼び出し。

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>解説

このメンバー関数を呼び出すと、行と列のサイズを調整した後に分割ウィンドウが正しく再表示されます、 [SetRowInfo](#setrowinfo)と[SetColumnInfo](#setcolumninfo)メンバー関数です。 分割ウィンドウが表示される前に作成プロセスの一部として行と列のサイズを変更する場合、このメンバー関数を呼び出す必要はありません。

ユーザーが分割ウィンドウのサイズを変更したり、分割を移動したりするたびに、フレームワークはこのメンバー関数を呼び出します。

### <a name="example"></a>例

  [「次](#setcolumninfo)の例」を参照してください。

## <a name="csplitterwndsetactivepane"></a><a name="setactivepane"></a>スプリッタウンド::セットアクティブペイン

枠内のアクティブなペインに設定します。

```
virtual void SetActivePane(
    int row,
    int col,
    CWnd* pWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*行*<br/>
*pWnd*が NULL の場合は、アクティブになるペイン内の行を指定します。

*col*<br/>
*pWnd*が NULL の場合は、アクティブになるペイン内の列を指定します。

*Pwnd*<br/>
`CWnd` オブジェクトを指すポインターです。 NULL の場合、*行*と*col*で指定されたペインがアクティブに設定されます。 NULL でない場合は、アクティブに設定されているペインを指定します。

### <a name="remarks"></a>解説

このメンバー関数は、フレームワークによって呼び出され、ユーザーがフレーム ウィンドウ内のペインにフォーカスを変更したときに、ペインをアクティブとして設定します。 明示的に呼び出`SetActivePane`して、指定したビューにフォーカスを変更できます。

行と列を指定**するか、または** *pWnd*を指定してペインを指定します。

## <a name="csplitterwndsetcolumninfo"></a><a name="setcolumninfo"></a>分割された項目::列の設定

指定した列情報を設定する呼び出し。

```
void SetColumnInfo(
    int col,
    int cxIdeal,
    int cxMin);
```

### <a name="parameters"></a>パラメーター

*col*<br/>
分割ウィンドウの列を指定します。

*cx理想*<br/>
分割ウィンドウの列の理想的な幅をピクセル単位で指定します。

*cxMin*<br/>
分割ウィンドウの列の最小幅をピクセル単位で指定します。

### <a name="remarks"></a>解説

列の新しい最小幅と理想的な幅を設定します。 列の最小値によって、列が小さすぎて完全に表示できない場合が決まります。

フレームワークは、分割ウィンドウを表示するときに、最適なサイズに従って、ペインを列と行に配置し、分割ウィンドウのクライアント領域の左上から右下隅まで作業します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#6](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_4.cpp)]

## <a name="csplitterwndsetrowinfo"></a><a name="setrowinfo"></a>スプリッターウンド::セットローインフォ

指定された行情報を設定する呼び出し。

```
void SetRowInfo(
    int row,
    int cyIdeal,
    int cyMin);
```

### <a name="parameters"></a>パラメーター

*行*<br/>
分割ウィンドウ行を指定します。

*シイディアル*<br/>
分割ウィンドウの行の理想的な高さをピクセル単位で指定します。

*サイミン*<br/>
分割ウィンドウの行の最小の高さをピクセル単位で指定します。

### <a name="remarks"></a>解説

行の新しい最小の高さと理想的な高さを設定します。 行の最小値によって、行が小さすぎて完全に表示できない場合が決まります。

フレームワークは、分割ウィンドウを表示するときに、最適なサイズに従って、ペインを列と行に配置し、分割ウィンドウのクライアント領域の左上から右下隅まで作業します。

## <a name="csplitterwndsetscrollstyle"></a><a name="setscrollstyle"></a>スプリッタウンド::セットスクロールスタイル

分割ウィンドウの共有スクロール バーのサポートに対する新しいスクロール スタイルを指定します。

```
void SetScrollStyle(DWORD dwStyle);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
分割ウィンドウの共有スクロール バーのサポートの新しいスクロール スタイルは、次のいずれかの値になります。

- WS_HSCROLL水平共有スクロール バーを作成/表示します。

- WS_VSCROLL垂直共有スクロール バーを作成/表示します。

### <a name="remarks"></a>解説

スクロール バーが作成されると、そのスタイルなしで呼び出`SetScrollStyle`されても、スクロール バーは破棄されません。代わりに、これらのスクロールバーは非表示になります。 これにより、スクロール バーは非表示であっても状態を保持できます。 呼び`SetScrollStyle`出した後、すべての変更を有効にするために[RecalcLayout](#recalclayout)を呼び出す必要があります。

## <a name="csplitterwndsplitcolumn"></a><a name="splitcolumn"></a>分割列::分割列

フレーム ウィンドウが垂直方向に分割される位置を示します。

```
virtual BOOL SplitColumn(int cxBefore);
```

### <a name="parameters"></a>パラメーター

*cx前*<br/>
分割が行われる前の位置 (ピクセル単位)。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、垂直分割ウィンドウが作成されるときに呼び出されます。 `SplitColumn`は、分割が発生する既定の場所を示します。

`SplitColumn`は、動的分割ウィンドウのロジックを実装するためにフレームワークによって呼び出されます (つまり、スプリッター ウィンドウにSPLS_DYNAMIC_SPLITスタイルがある場合)。 仮想関数[CreateView](#createview)と共にカスタマイズして、より高度な動的スプリッタを実装できます。

## <a name="csplitterwndsplitrow"></a><a name="splitrow"></a>スプリッタローンド::スプリットロー

フレーム ウィンドウが水平方向に分割される位置を示します。

```
virtual BOOL SplitRow(int cyBefore);
```

### <a name="parameters"></a>パラメーター

*サイフォア*<br/>
分割が行われる前の位置 (ピクセル単位)。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、水平分割ウィンドウが作成されるときに呼び出されます。 `SplitRow`は、分割が発生する既定の場所を示します。

`SplitRow`は、動的分割ウィンドウのロジックを実装するためにフレームワークによって呼び出されます (つまり、スプリッター ウィンドウにSPLS_DYNAMIC_SPLITスタイルがある場合)。 仮想関数[CreateView](#createview)と共にカスタマイズして、より高度な動的スプリッタを実装できます。

## <a name="csplitterwndondraw"></a><a name="ondraw"></a>スプリッタウンド::オンドロー

分割ウィンドウを描画するためにフレームワークによって呼び出されます。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
デバイス コンテキストへのポインター。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[MFC サンプル ビューレックス](../../overview/visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[Cビュークラス](../../mfc/reference/cview-class.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)
