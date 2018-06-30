---
title: CSplitterWnd クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3d2b44c4e854a27bcc753c1403ea058b03906a8
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123150"
---
# <a name="csplitterwnd-class"></a>CSplitterWnd クラス
分割ウィンドウの機能が用意されています。分割ウィンドウとは複数のペインを持つウィンドウです。  
  
## <a name="syntax"></a>構文  
  
```  
class CSplitterWnd : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSplitterWnd::CSplitterWnd](#csplitterwnd)|構築するために呼び出し、`CSplitterWnd`オブジェクト。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSplitterWnd::ActivateNext](#activatenext)|次のペインまたは前のペインのコマンドを実行します。|  
|[CSplitterWnd::CanActivateNext](#canactivatenext)|次のペインまたは前のペイン コマンドが現在可能かどうかを確認します。|  
|[CSplitterWnd::Create](#create)|動的分割ウィンドウを作成し、アタッチするへの呼び出し、`CSplitterWnd`オブジェクト。|  
|[CSplitterWnd::CreateScrollBarCtrl](#createscrollbarctrl)|共有のスクロール バー コントロールを作成します。|  
|[CSplitterWnd::CreateStatic](#createstatic)|静的な分割ウィンドウを作成し、アタッチするへの呼び出し、`CSplitterWnd`オブジェクト。|  
|[CSplitterWnd::CreateView](#createview)|分割ウィンドウでウィンドウを作成する呼び出しです。|  
|[CSplitterWnd::DeleteColumn](#deletecolumn)|分割ウィンドウから列を削除します。|  
|[CSplitterWnd::DeleteRow](#deleterow)|分割ウィンドウから行を削除します。|  
|[CSplitterWnd::DeleteView](#deleteview)|分割ウィンドウからビューを削除します。|  
|[あると](#dokeyboardsplit)|キーボード分割コマンド、通常「ウィンドウの分割します」を実行します|  
|[CSplitterWnd::DoScroll](#doscroll)|分割ウィンドウの同期スクロールを実行します。|  
|[CSplitterWnd::DoScrollBy](#doscrollby)|指定されたピクセル数で分割ウィンドウをスクロールします。|  
|[CSplitterWnd::GetActivePane](#getactivepane)|フォーカスまたはフレームのアクティブなビューから、アクティブなペインを決定します。|  
|[CSplitterWnd::GetColumnCount](#getcolumncount)|現在のウィンドウの列数を返します。|  
|[CSplitterWnd::GetColumnInfo](#getcolumninfo)|指定された列に関する情報を返します。|  
|[CSplitterWnd::GetPane](#getpane)|指定した行と列にあるペインを返します。|  
|[CSplitterWnd::GetRowCount](#getrowcount)|現在のウィンドウの行の数を返します。|  
|[CSplitterWnd::GetRowInfo](#getrowinfo)|指定された行に関する情報を返します。|  
|[CSplitterWnd::GetScrollStyle](#getscrollstyle)|共有のスクロール バー スタイルを返します。|  
|[CSplitterWnd::IdFromRowCol](#idfromrowcol)|指定した行と列にあるウィンドウのウィンドウ ID の子を返します。|  
|[CSplitterWnd::IsChildPane](#ischildpane)|ウィンドウが、現在この分割ウィンドウの子ウィンドウかどうかを決定する呼び出しです。|  
|[CSplitterWnd::IsTracking](#istracking)|分割バーが移動されて現在かどうかを判断します。|  
|[CSplitterWnd::RecalcLayout](#recalclayout)|分割ウィンドウを表示し、行または列のサイズを調整した後の呼び出しです。|  
|[CSplitterWnd::SetActivePane](#setactivepane)|アクティブなフレーム内になるウィンドウを設定します。|  
|[CSplitterWnd::SetColumnInfo](#setcolumninfo)|指定された列の情報を設定する呼び出しです。|  
|[CSplitterWnd::SetRowInfo](#setrowinfo)|指定した行の情報を設定する呼び出しです。|  
|[CSplitterWnd::SetScrollStyle](#setscrollstyle)|スクロール バーのサポートを共有する分割ウィンドウの新しいスクロール バー スタイルを指定します。|  
|[CSplitterWnd::SplitColumn](#splitcolumn)|フレーム ウィンドウが垂直方向に分割される場所を示します。|  
|[CSplitterWnd::SplitRow](#splitrow)|フレーム ウィンドウが水平方向に分割される場所を示します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSplitterWnd::OnDraw](#ondraw)|分割ウィンドウを描画するためにフレームワークによって呼び出されます。|  
|[CSplitterWnd::OnDrawSplitter](#ondrawsplitter)|分割ウィンドウのイメージをレンダリングします。|  
|[CSplitterWnd::OnInvertTracker](#oninverttracker)|分割ウィンドウを作成するのには同じサイズ フレーム ウィンドウと図形のイメージをレンダリングします。|  
  
## <a name="remarks"></a>Remarks  
 ペインは、通常、アプリケーション固有のオブジェクトから派生した[CView](../../mfc/reference/cview-class.md)、いずれかのことができますが、 [CWnd](../../mfc/reference/cwnd-class.md)適切な子ウィンドウ ID を持つオブジェクト  
  
 A`CSplitterWnd`オブジェクトが親に埋め込まれた通常[CFrameWnd](../../mfc/reference/cframewnd-class.md)または[CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)オブジェクト。 作成、`CSplitterWnd`オブジェクト、次の手順を使用します。  
  
1.  埋め込み、`CSplitterWnd`親フレーム内のメンバー変数。  
  
2.  親フレームの[CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)メンバー関数。  
  
3.  オーバーライドされた内`OnCreateClient`、呼び出し、[作成](#create)または[CreateStatic](#createstatic)のメンバー関数`CSplitterWnd`です。  
  
 呼び出す、`Create`動的分割ウィンドウを作成するメンバー関数。 通常動的分割ウィンドウを作成し、スクロールして個別のペインやビュー、同じドキュメントの数が使用されます。 フレームワークは、スプリッターの最初のウィンドウを自動的に作成されます。フレームワークを作成のサイズを変更し、分割ウィンドウのコントロールの操作とその他のウィンドウを破棄します。  
  
 呼び出すと`Create`ウィンドウが完全に表示するのには小さすぎる場合を決定する行の最小の高さと列幅を指定します。 呼び出した後`Create`、呼び出すことにより、最小値を調整することができます、[ため](#setcolumninfo)と[小さ](#setrowinfo)メンバー関数。  
  
 使用しても、`SetColumnInfo`と`SetRowInfo`「最適」列の幅と行の「最適な」高さを設定するメンバー関数。 フレームワークには、分割ウィンドウが表示されたら、最初に、分割ウィンドウから、親フレームを表示します。 フレームワークは、分割ウィンドウのクライアント領域の右下隅を左上隅から作業をして、最適なディメンションに基づいて列と行でウィンドウをレイアウトします。  
  
 動的分割ウィンドウのすべてのウィンドウは、同じクラスでなければなりません。 動的分割ウィンドウをサポートする、よく知られたアプリケーションには、Microsoft Word や Microsoft Excel が含まれます。  
  
 使用して、`CreateStatic`メンバー関数を静的な分割ウィンドウを作成します。 ユーザーは、静的な分割ウィンドウ、いないの数や順序でのウィンドウのサイズだけを変更できます。  
  
 静的な分割を作成するときに、具体的にはすべて、静的な分割のウィンドウを作成してください。 親フレームの前にすべてのウィンドウを作成するかどうかを確認`OnCreateClient`メンバー関数の戻り値、または、フレームワークは、ウィンドウを正しく表示されません。  
  
 `CreateStatic`メンバー関数が自動的に 0 の行の最小の高さと列の幅と静的な分割を初期化します。 呼び出した後`Create`、呼び出すことにより、最小値を調整する、[ために使われます](#setcolumninfo)と[小さ](#setrowinfo)メンバー関数。 使用しても`SetColumnInfo`と`SetRowInfo`を呼び出した後`CreateStatic`を示すために最適なウィンドウ サイズを必要に応じて。  
  
 静的な分割の各ペインは、多くの場合、さまざまなクラスに属しています。 静的な分割ウィンドウの例については、グラフィックス エディターと Windows ファイル マネージャーを参照してください。  
  
 分割ウィンドウには、特殊なスクロール バー (とは別に、スクロール バー ペインが持っている) がサポートされています。 これらのスクロール バーの子である、`CSplitterWnd`オブジェクトおよびペインと共有します。  
  
 分割ウィンドウを作成するときに、これらの特殊なスクロール バーを作成します。 たとえば、`CSplitterWnd`を 1 つの行、2 つの列があり、WS_VSCROLL スタイル 2 つのペインで共有される垂直スクロール バーが表示されます。 ユーザーは、スクロール バーを移動したときは、付加が両方のウィンドウに送信されます。 ペインでは、スクロール バーの位置を設定、共有のスクロール バーが設定されます。  
  
 分割ウィンドウについてを参照してください。  
  
- [テクニカル ノート 29](../../mfc/tn029-splitter-windows.md)  
  
-   サポート技術情報の記事 Q262024: HOWTO: CSplitterWnd の子として使用する CPropertySheet  
  
 動的分割ウィンドウを作成する方法の詳細についてを参照してください。  
  
-   MFC サンプル[Scribble](../../visual-cpp-samples.md)  
  
-   MFC サンプル[VIEWEX](../../visual-cpp-samples.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSplitterWnd`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxext.h  
  
##  <a name="activatenext"></a>  CSplitterWnd::ActivateNext  
 次のペインまたは前のペインのコマンドを実行するためにフレームワークによって呼び出されます。  
  
```  
virtual void ActivateNext(BOOL bPrev = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bPrev*  
 どのウィンドウをアクティブ化することを示します。 **TRUE**の前です。**FALSE**次のです。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、高レベルのコマンドによって使用される、 [CView](../../mfc/reference/cview-class.md)に委任するクラス、`CSplitterWnd`実装します。  
  
##  <a name="canactivatenext"></a>  CSplitterWnd::CanActivateNext  
 次のペインまたは前のペイン コマンドが現在可能かどうかを確認するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL CanActivateNext(BOOL bPrev = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bPrev*  
 どのウィンドウをアクティブ化することを示します。 **TRUE**の前です。**FALSE**次のです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、高レベルのコマンドによって使用される、 [CView](../../mfc/reference/cview-class.md)に委任するクラス、`CSplitterWnd`実装します。  
  
##  <a name="create"></a>  CSplitterWnd::Create  
 動的分割ウィンドウを作成するには、**作成**メンバー関数。  
  
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
 *pParentWnd*  
 分割ウィンドウの親フレーム ウィンドウです。  
  
 *nMaxRows*  
 分割ウィンドウ内の行の最大数。 この値は、2 を超えない必要があります。  
  
 *nMaxCols*  
 分割ウィンドウ内の列の最大数。 この値は、2 を超えない必要があります。  
  
 *sizeMin*  
 これで、ペインが表示される最小サイズを指定します。  
  
 *pContext*  
 ポインター、 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)構造体。 ほとんどの場合、これを指定できます、 *pContext*親フレーム ウィンドウに渡されます。  
  
 *dwStyle*  
 ウィンドウ スタイルを指定します。  
  
 *nID*  
 ウィンドウの子ウィンドウ ID です。 ID は、分割ウィンドウがもう 1 つの分割ウィンドウ内に入れ子にしない限り、AFX_IDW_PANE_FIRST にすることができます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 埋め込むことができます、 `CSplitterWnd` 、親の[CFrameWnd](../../mfc/reference/cframewnd-class.md)または[CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)次の手順を実行してオブジェクト。  
  
1.  埋め込み、`CSplitterWnd`親フレーム内のメンバー変数。  
  
2.  親フレームの[CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)メンバー関数。  
  
3.  呼び出す、`Create`からのメンバー関数内でオーバーライドされた`OnCreateClient`です。  
  
 親フレーム内の分割ウィンドウを作成するときは、親のフレームを渡す*pContext*分割ウィンドウへのパラメーターです。 それ以外の場合、このパラメーターは NULL を指定できます。  
  
 動的分割ウィンドウの最初の行の最小の高さと列の幅が設定、 *sizeMin*パラメーター。 これらの最小値は、ペインが小さすぎて全体を表示するかどうかを決定するを変更することができます、[小さ](#setrowinfo)と[ため](#setcolumninfo)メンバー関数。  
  
 詳細動的分割ウィンドウについてを参照してください「分割ウィンドウ」アーティクル[複数のドキュメント タイプ、ビュー、およびフレーム ウィンドウ](../../mfc/multiple-document-types-views-and-frame-windows.md)、[テクニカル ノート 29:](../../mfc/tn029-splitter-windows.md)、および`CSplitterWnd`クラスの概要です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#125](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_1.cpp)]  
  
##  <a name="createscrollbarctrl"></a>  CSplitterWnd::CreateScrollBarCtrl  
 共有のスクロール バー コントロールを作成するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL CreateScrollBarCtrl(
    DWORD dwStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwStyle*  
 ウィンドウ スタイルを指定します。  
  
 *nID*  
 ウィンドウの子ウィンドウ ID です。 ID は、分割ウィンドウがもう 1 つの分割ウィンドウ内に入れ子にしない限り、AFX_IDW_PANE_FIRST にすることができます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 オーバーライド`CreateScrollBarCtrl`スクロール バーの横にある余分なコントロールを追加します。 既定の動作では、通常の Windows のスクロール バー コントロールを作成します。  
  
##  <a name="createstatic"></a>  CSplitterWnd::CreateStatic  
 静的な分割ウィンドウを作成するには、`CreateStatic`メンバー関数。  
  
```  
virtual BOOL CreateStatic(
    CWnd* pParentWnd,  
    int nRows,  
    int nCols,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,  
    UINT nID = AFX_IDW_PANE_FIRST);
```  
  
### <a name="parameters"></a>パラメーター  
 *pParentWnd*  
 分割ウィンドウの親フレーム ウィンドウです。  
  
 *nRows*  
 行の番号。 この値は、16 を超えない必要があります。  
  
 *nCols*  
 列の番号。 この値は、16 を超えない必要があります。  
  
 *dwStyle*  
 ウィンドウ スタイルを指定します。  
  
 *nID*  
 ウィンドウの子ウィンドウ ID です。 ID は、分割ウィンドウがもう 1 つの分割ウィンドウ内に入れ子にしない限り、AFX_IDW_PANE_FIRST にすることができます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 A`CSplitterWnd`は通常、親に埋め込まれて`CFrameWnd`または[CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)次の手順を実行してオブジェクト。  
  
1.  埋め込み、`CSplitterWnd`親フレーム内のメンバー変数。  
  
2.  親フレームの`OnCreateClient`メンバー関数。  
  
3.  呼び出す、`CreateStatic`からのメンバー関数内でオーバーライドされた[CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)です。  
  
 静的な分割ウィンドウには、さまざまなクラスの多くの場合、ペインが表示の固定数が含まれています。  
  
 静的な分割ウィンドウを作成するときに作成する必要がある同時にすべてのペインです。 [CreateView](#createview)メンバー関数は通常、この目的の使用も、他の nonview クラスを作成することができます。  
  
 静的な分割ウィンドウの最初の行の最小の高さと列の幅は 0 です。 これらの最小値は、調べる、ウィンドウが小さすぎて全体を表示するときにを変更することができます、[小さ](#setrowinfo)と[ために使われます](#setcolumninfo)メンバー関数。  
  
 に静的な分割ウィンドウをスクロール バーを追加する WS_HSCROLL と WS_VSCROLL スタイルを追加して*dwStyle*です。  
  
 アーティクルの「分割ウィンドウ」を参照してください[複数のドキュメント タイプ、ビュー、およびフレーム ウィンドウ](../../mfc/multiple-document-types-views-and-frame-windows.md)、[テクニカル ノート 29:](../../mfc/tn029-splitter-windows.md)、および`CSplitterWnd`の詳細については、静的な分割ウィンドウ クラスの概要です。  
  
##  <a name="createview"></a>  CSplitterWnd::CreateView  
 静的な分割ウィンドウのペインを作成します。  
  
```  
virtual BOOL CreateView(
    int row,  
    int col,  
    CRuntimeClass* pViewClass,  
    SIZE sizeInit,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>パラメーター  
 *行*  
 新しいビューを配置するための分割ウィンドウの行を指定します。  
  
 *col*  
 新しいビューを配置するための分割ウィンドウの列を指定します。  
  
 *pViewClass*  
 指定します、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)新しいビュー。  
  
 *sizeInit*  
 新しいビューの初期サイズを指定します。  
  
 *pContext*  
 ビューの作成に使用されるコンテキストの作成へのポインター (通常、 *pContext*オーバーライドされた親のフレームに渡された[CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)分割ウィンドウのメンバー関数作成されます)。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 分割ウィンドウを表示するために、フレームワーク前に、静的な分割ウィンドウのすべてのウィンドウを作成する必要があります。  
  
 フレームワークでは、動的分割ウィンドウのユーザーがウィンドウ、行、または列を分割時に、新しいウィンドウを作成するには、このメンバー関数も呼び出します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#4](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_2.cpp)]  
  
##  <a name="csplitterwnd"></a>  CSplitterWnd::CSplitterWnd  
 構築するために呼び出し、`CSplitterWnd`オブジェクト。  
  
```  
CSplitterWnd();
```  
  
### <a name="remarks"></a>Remarks  
 構築、 `CSplitterWnd` 2 つのステップ内のオブジェクト。 最初に、作成コンス トラクターを呼び出して、`CSplitterWnd`オブジェクト、およびを呼び出す、[作成](#create)分割ウィンドウを作成してにアタッチするメンバー関数、`CSplitterWnd`オブジェクト。  
  
##  <a name="deletecolumn"></a>  CSplitterWnd::DeleteColumn  
 分割ウィンドウから列を削除します。  
  
```  
virtual void DeleteColumn(int colDelete);
```  
  
### <a name="parameters"></a>パラメーター  
 *colDelete*  
 削除する列を指定します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、(分割ウィンドウは、SPLS_DYNAMIC_SPLIT スタイルを持つ) の場合は、動的分割ウィンドウのロジックを実装するためにフレームワークによって呼び出されます。 これはカスタマイズ可能な仮想関数と共に[CreateView](#createview)により高度な動的分割ウィンドウを実装します。  
  
##  <a name="deleterow"></a>  CSplitterWnd::DeleteRow  
 分割ウィンドウから行を削除します。  
  
```  
virtual void DeleteRow(int rowDelete);
```  
  
### <a name="parameters"></a>パラメーター  
 *行を削除します。*  
 削除する行を指定します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、(分割ウィンドウは、SPLS_DYNAMIC_SPLIT スタイルを持つ) の場合は、動的分割ウィンドウのロジックを実装するためにフレームワークによって呼び出されます。 これはカスタマイズ可能な仮想関数と共に[CreateView](#createview)により高度な動的分割ウィンドウを実装します。  
  
##  <a name="deleteview"></a>  CSplitterWnd::DeleteView  
 分割ウィンドウからビューを削除します。  
  
```  
virtual void DeleteView(
    int row,  
    int col);
```  
  
### <a name="parameters"></a>パラメーター  
 *行*  
 分割ウィンドウのビューを削除する行を指定します。  
  
 *col*  
 分割ウィンドウのビューを削除する列を指定します。  
  
### <a name="remarks"></a>Remarks  
 アクティブなビューが削除されている場合は次のビューがアクティブになります。 既定の実装は、ビューが自動前提としています。 削除[PostNcDestroy](../../mfc/reference/cwnd-class.md#postncdestroy)です。  
  
 このメンバー関数は、(分割ウィンドウは、SPLS_DYNAMIC_SPLIT スタイルを持つ) の場合は、動的分割ウィンドウのロジックを実装するためにフレームワークによって呼び出されます。 これはカスタマイズ可能な仮想関数と共に[CreateView](#createview)により高度な動的分割ウィンドウを実装します。  
  
##  <a name="dokeyboardsplit"></a>  あると  
 キーボード分割コマンド、通常「ウィンドウの分割します」を実行します  
  
```  
virtual BOOL DoKeyboardSplit();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、高レベルのコマンドによって使用される、 [CView](../../mfc/reference/cview-class.md)に委任するクラス、`CSplitterWnd`実装します。  
  
##  <a name="doscroll"></a>  CSplitterWnd::DoScroll  
 分割ウィンドウの同期スクロールを実行します。  
  
```  
virtual BOOL DoScroll(
    CView* pViewFrom,  
    UINT nScrollCode,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *pViewFrom*  
 スクロール メッセージが元のビューへのポインター。  
  
 *nScrollCode*  
 スクロール バーのコードをユーザーを示すには、要求のスクロールします。 このパラメーターは 2 つの部分で構成されます: を水平方向にスクロール発生の種類を決定するには、下位バイトおよび高位バイトのことで、垂直方向にスクロール発生の種類を決定します。  
  
- 下へスクロールする SB_BOTTOM。  
  
- 1 行下 SB_LINEDOWN 上にスクロールします。  
  
- 1 行上 SB_LINEUP 上にスクロールします。  
  
- 1 つ page down SB_PAGEDOWN スクロール。  
  
- 1 つのページを SB_PAGEUP スクロールします。  
  
- ページのトップへ SB_TOP にスクロールします。  
  
 *bDoScroll*  
 指定されたスクロール動作が発生したかどうかを判断します。 場合*bDoScroll*が TRUE (子ウィンドウが存在する場合とスクロールの範囲であれば、分割ウィンドウなど)、指定されたスクロール アクションが実行できますその場合*bDoScroll*場合は、FALSE (つまり、子ウィンドウ。存在するか、分割されたビューにスクロールの範囲がありません)、スクロールは発生しませんし、します。  
  
### <a name="return-value"></a>戻り値  
 同期されている場合は 0 以外のスクロールが発生します。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、ビューは、スクロール メッセージを受け取ったときに、分割ウィンドウの同期スクロールを実行するためにフレームワークによって呼び出されます。 同期スクロールを許可する前に、ユーザーに操作を要求するためにオーバーライドします。  
  
##  <a name="doscrollby"></a>  CSplitterWnd::DoScrollBy  
 指定されたピクセル数で分割ウィンドウをスクロールします。  
  
```  
virtual BOOL DoScrollBy(
    CView* pViewFrom,  
    CSize sizeScroll,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *pViewFrom*  
 スクロール メッセージが元のビューへのポインター。  
  
 *sizeScroll*  
 水平および垂直方向にスクロールするピクセル数です。  
  
 *bDoScroll*  
 指定されたスクロール動作が発生したかどうかを判断します。 場合*bDoScroll*が TRUE (子ウィンドウが存在する場合とスクロールの範囲であれば、分割ウィンドウなど)、指定されたスクロール アクションが実行できますその場合*bDoScroll*場合は、FALSE (つまり、子ウィンドウ。存在するか、分割されたビューにスクロールの範囲がありません)、スクロールは発生しませんし、します。  
  
### <a name="return-value"></a>戻り値  
 同期されている場合は 0 以外のスクロールが発生します。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 スクロール メッセージに対する応答として、フレームワークによって呼び出されます、同期を実行するには (ピクセル単位) で示されたの量で、分割ウィンドウのスクロール*sizeScroll*です。 正の値が右にスクロール ダウンを示します負の値を示すを左にスクロールします。  
  
 スクロールを許可する前に、ユーザーに操作を要求するためにオーバーライドします。  
  
##  <a name="getactivepane"></a>  CSplitterWnd::GetActivePane  
 フォーカスまたはフレームのアクティブなビューから、アクティブなペインを決定します。  
  
```  
virtual CWnd* GetActivePane(
    int* pRow = NULL,  
    int* pCol = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pRow*  
 ポインター、 **int**アクティブなペインの行番号を取得します。  
  
 *pCol*  
 ポインター、 **int**アクティブなペインの列数を取得します。  
  
### <a name="return-value"></a>戻り値  
 アクティブなペインへのポインター。 アクティブなウィンドウが存在しない場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、分割ウィンドウのアクティブなペインを調べるためにフレームワークによって呼び出されます。 アクティブなペインを取得する前に、ユーザーが操作を要求するをオーバーライドします。  
  
##  <a name="getcolumncount"></a>  CSplitterWnd::GetColumnCount  
 現在のウィンドウの列数を返します。  
  
```  
int GetColumnCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 分割ウィンドウの現在の列数を返します。 静的分割ウィンドウで、このにもなります列の最大数。  
  
##  <a name="getcolumninfo"></a>  CSplitterWnd::GetColumnInfo  
 指定された列に関する情報を返します。  
  
```  
void GetColumnInfo(
    int col,  
    int& cxCur,  
    int& cxMin) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *col*  
 列を指定します。  
  
 *cxCur*  
 参照、 **int**列の現在の幅に設定されます。  
  
 *cxMin*  
 参照、 **int**列の現在の最小の幅に設定されます。  
  
##  <a name="getpane"></a>  CSplitterWnd::GetPane  
 指定した行と列にあるペインを返します。  
  
```  
CWnd* GetPane(
    int row,  
    int col) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *行*  
 行を指定します。  
  
 *col*  
 列を指定します。  
  
### <a name="return-value"></a>戻り値  
 指定した行と列にあるペインを返します。 返されるペインは、通常、 [CView](../../mfc/reference/cview-class.md)-クラスを派生します。  
  
##  <a name="getrowcount"></a>  CSplitterWnd::GetRowCount  
 現在のウィンドウの行の数を返します。  
  
```  
int GetRowCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 分割ウィンドウの行の現在の数を返します。 静的な分割ウィンドウで、このにもなります行の最大数。  
  
##  <a name="getrowinfo"></a>  CSplitterWnd::GetRowInfo  
 指定された行に関する情報を返します。  
  
```  
void GetRowInfo(
    int row,  
    int& cyCur,  
    int& cyMin) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *行*  
 行を指定します。  
  
 *cyCur*  
 参照を**int**ピクセル単位で行の現在の高さに設定されます。  
  
 *cyMin*  
 参照を**int**現在の最小の高さ (ピクセル単位) の行に設定されます。  
  
### <a name="remarks"></a>Remarks  
 指定された行に関する情報を取得するには、このメンバー関数を呼び出します。 *CyCur*パラメーターは、指定された行の現在の高さで塗りつぶされますと*cyMin*行の高さの最小値が入力されます。  
  
##  <a name="getscrollstyle"></a>  CSplitterWnd::GetScrollStyle  
 分割ウィンドウで、共有のスクロール バー スタイルを返します。  
  
```  
DWORD GetScrollStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 1 つ以上の次のウィンドウ スタイル フラグの成功した場合。  
  
- WS_HSCROLL スプリッターが現在を管理する場合は、水平スクロール バーを共有します。  
  
- WS_VSCROLL スプリッターが現在を管理する場合は、垂直スクロール バーを共有します。  
  
 0 の場合、分割ウィンドウは、共有のスクロール バーを現在管理しません。  
  
##  <a name="idfromrowcol"></a>  CSplitterWnd::IdFromRowCol  
 子の指定した行と列にあるウィンドウのウィンドウ ID を取得します。  
  
```  
int IdFromRowCol(
    int row,  
    int col) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *行*  
 分割ウィンドウの行を指定します。  
  
 *col*  
 分割ウィンドウの列を指定します。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウの子ウィンドウ ID です。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、ビューでないペインの作成に使用して、ウィンドウが存在する前に呼び出すことができます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#5](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_3.cpp)]  
  
##  <a name="ischildpane"></a>  CSplitterWnd::IsChildPane  
 指定するかどうか*pWnd*分割ウィンドウの子ウィンドウでは現在します。  
  
```  
BOOL IsChildPane(
    CWnd* pWnd,  
    int* pRow,  
    int* pCol);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWnd*  
 ポインター、 [CWnd](../../mfc/reference/cwnd-class.md)をテストするオブジェクト。  
  
 *pRow*  
 ポインター、 **int**行番号を格納します。  
  
 *pCol*  
 ポインター、 **int**列の数を格納します。  
  
### <a name="return-value"></a>戻り値  
 ゼロ以外の場合、 *pWnd*この分割ウィンドウの子ウィンドウは、現在と*pRow*と*pCol*分割ウィンドウのウィンドウの位置が入ります。 場合*pWnd*が子ウィンドウ、分割ウィンドウの 0 が返されます。  
  
### <a name="remarks"></a>Remarks  
 バージョンでは Visual C 6.0 の前に、この関数として定義されました  
  
 `BOOL IsChildPane(CWnd* pWnd, int& row, int& col);`  
  
 このバージョンは廃止されておりは使用できません。  
  
##  <a name="istracking"></a>  CSplitterWnd::IsTracking  
 かどうかは、ウィンドウの分割バーが移動されている現在を決定するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsTracking();
```  
  
### <a name="return-value"></a>戻り値  
 分割操作の実行中である場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="ondrawsplitter"></a>  CSplitterWnd::OnDrawSplitter  
 分割ウィンドウのイメージをレンダリングします。  
  
```  
virtual void OnDrawSplitter(
    CDC* pDC,  
    ESplitType nType,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDC*  
 描画するためのデバイス コンテキストへのポインター。 場合*pDC*が NULL の場合、 [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow)が呼び出されたフレームワークおよびありません分割してウィンドウを描画します。  
  
 *タイプ*  
 値、`enum ESplitType`次のいずれかを指定することができます。  
  
- `splitBox` スプリッター ドラッグします。  
  
- `splitBar` 2 つの分割ウィンドウの間に表示するバーです。  
  
- `splitIntersection` 分割ウィンドウの交差部分です。 Windows 95/98 で実行されているときに、この要素は呼び出されません。  
  
- `splitBorder` 分割ウィンドウの境界線です。  
  
 *rect*  
 参照、 [CRect](../../atl-mfc-shared/reference/crect-class.md)分割ウィンドウの形状とサイズを指定するオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、描画し、分割ウィンドウの正確な特性を指定するためにフレームワークによって呼び出されます。 オーバーライド`OnDrawSplitter`分割ウィンドウのさまざまなグラフィック要素の外観の高度にカスタマイズできます。 分割バーの交差部分が混ざりという点で、既定のイメージは Windows や Microsoft Windows 95/98 の Microsoft Works では、スプリッターに似ています。  
  
 詳細動的分割ウィンドウについてを参照してください「分割ウィンドウ」アーティクル[複数のドキュメント タイプ、ビュー、およびフレーム ウィンドウ](../../mfc/multiple-document-types-views-and-frame-windows.md)、[テクニカル ノート 29:](../../mfc/tn029-splitter-windows.md)、および`CSplitterWnd`クラスの概要です。  
  
##  <a name="oninverttracker"></a>  CSplitterWnd::OnInvertTracker  
 分割ウィンドウを作成するのには同じサイズ フレーム ウィンドウと図形のイメージをレンダリングします。  
  
```  
virtual void OnInvertTracker(const CRect& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 *rect*  
 参照、`CRect`トラッキング四角形を指定するオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、分割ウィンドウのサイズ変更時に、フレームワークによって呼び出されます。 オーバーライド`OnInvertTracker`分割ウィンドウの画像の高度にカスタマイズできます。 分割バーの交差部分が混ざりという点で、既定のイメージは Windows や Microsoft Windows 95/98 の Microsoft Works では、スプリッターに似ています。  
  
 詳細動的分割ウィンドウについてを参照してください「分割ウィンドウ」アーティクル[複数のドキュメント タイプ、ビュー、およびフレーム ウィンドウ](../../mfc/multiple-document-types-views-and-frame-windows.md)、[テクニカル ノート 29:](../../mfc/tn029-splitter-windows.md)、および`CSplitterWnd`クラスの概要です。  
  
##  <a name="recalclayout"></a>  CSplitterWnd::RecalcLayout  
 分割ウィンドウを表示し、行または列のサイズを調整した後の呼び出しです。  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Remarks  
 行と列のサイズを調整した後に、分割ウィンドウを正しく再表示するには、このメンバー関数を呼び出す、[小さ](#setrowinfo)と[ため](#setcolumninfo)メンバー関数。 分割ウィンドウを表示するには、作成プロセスの一環として行と列のサイズを変更する場合、このメンバー関数を呼び出す必要はありません。  
  
 フレームワークは、ユーザーは、分割ウィンドウのサイズを変更したり、移動するたびに、このメンバー関数を呼び出します。  
  
### <a name="example"></a>例  
  例を参照して[CSplitterWnd::SetColumnInfo](#setcolumninfo)です。  
  
##  <a name="setactivepane"></a>  CSplitterWnd::SetActivePane  
 アクティブなフレーム内になるウィンドウを設定します。  
  
```  
virtual void SetActivePane(
    int row,  
    int col,  
    CWnd* pWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *行*  
 場合*pWnd*が NULL ではアクティブになる、ウィンドウ内の行を指定します。  
  
 *col*  
 場合*pWnd*が NULL ではアクティブになる、ウィンドウの列を指定します。  
  
 *pWnd*  
 ポインター、`CWnd`オブジェクト。 によって指定された NULL の場合、ウィンドウ*行*と*col*アクティブに設定されます。 NULL 以外の場合は、アクティブに設定されているウィンドウを指定します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、アクティブに設定ウィンドウをユーザーには、フレーム ウィンドウ内のペインにフォーカスが変更されたときに、フレームワークによって呼び出されます。 明示的に呼び出すことができます`SetActivePane`を指定されたビューにフォーカスを変更します。  
  
 行と列のいずれかを指定してウィンドウを指定**または**により*pWnd*です。  
  
##  <a name="setcolumninfo"></a>  CSplitterWnd::SetColumnInfo  
 指定された列の情報を設定する呼び出しです。  
  
```  
void SetColumnInfo(
    int col,  
    int cxIdeal,  
    int cxMin);
```  
  
### <a name="parameters"></a>パラメーター  
 *col*  
 分割ウィンドウの列を指定します。  
  
 *cxIdeal*  
 分割ウィンドウの列の最適の幅をピクセル単位で指定します。  
  
 *cxMin*  
 分割ウィンドウの列の最小幅をピクセル単位で指定します。  
  
### <a name="remarks"></a>Remarks  
 新しい幅の最小値と列の適切な幅を設定するには、このメンバー関数を呼び出します。 列の最小値は、列を完全に表示するのには小さすぎますが時期を決定します。  
  
 フレームワークは、分割ウィンドウを表示するときは、分割ウィンドウのクライアント領域の右下隅を左上隅から作業をして、最適なディメンションに基づいて列と行でウィンドウをレイアウトします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#6](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_4.cpp)]  
  
##  <a name="setrowinfo"></a>  CSplitterWnd::SetRowInfo  
 指定した行の情報を設定する呼び出しです。  
  
```  
void SetRowInfo(
    int row,  
    int cyIdeal,  
    int cyMin);
```  
  
### <a name="parameters"></a>パラメーター  
 *行*  
 分割ウィンドウの行を指定します。  
  
 *cyIdeal*  
 最適な分割ウィンドウの行の高さをピクセル単位で指定します。  
  
 *cyMin*  
 分割ウィンドウの行の最小の高さをピクセル単位で指定します。  
  
### <a name="remarks"></a>Remarks  
 新しい高さの最小値と、行の適切な高さを設定するには、このメンバー関数を呼び出します。 行の最小値は、行を完全に表示するのには小さすぎますが時期を決定します。  
  
 フレームワークは、分割ウィンドウを表示するときは、分割ウィンドウのクライアント領域の右下隅を左上隅から作業をして、最適なディメンションに基づいて列と行でウィンドウをレイアウトします。  
  
##  <a name="setscrollstyle"></a>  CSplitterWnd::SetScrollStyle  
 スクロールの共有新しいスタイル分割ウィンドウのスクロール バーのサポートを指定します。  
  
```  
void SetScrollStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwStyle*  
 スクロールの共有新しいスタイル分割ウィンドウのスクロール バーのサポートは、次の値のいずれかになります。  
  
- WS_HSCROLL 作成/表示の共有の水平スクロール バーです。  
  
- WS_VSCROLL 作成/表示共有垂直のスクロール バーです。  
  
### <a name="remarks"></a>Remarks  
 スクロール バーを作成した後は破棄されない場合でも`SetScrollStyle`; スタイルを呼び出す代わりに、スクロール バーが非表示になります。 これにより、隠れている場合でも、その状態を維持し、スクロール バーです。 呼び出した後`SetScrollStyle`を呼び出す必要がある[RecalcLayout](#recalclayout)のすべての変更を有効にします。  
  
##  <a name="splitcolumn"></a>  CSplitterWnd::SplitColumn  
 フレーム ウィンドウが垂直方向に分割される場所を示します。  
  
```  
virtual BOOL SplitColumn(int cxBefore);
```  
  
### <a name="parameters"></a>パラメーター  
 *cxBefore*  
 (ピクセル単位) で分割が発生する前に、の位置。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 垂直分割ウィンドウが作成されるときに呼び出されます。 `SplitColumn` 分割が発生する既定の場所を示します。  
  
 `SplitColumn` (分割ウィンドウは、SPLS_DYNAMIC_SPLIT スタイルを持つ) の場合は、動的分割ウィンドウのロジックを実装するためにフレームワークによって呼び出されます。 これはカスタマイズ可能な仮想関数と共に[CreateView](#createview)により高度な動的分割ウィンドウを実装します。  
  
##  <a name="splitrow"></a>  CSplitterWnd::SplitRow  
 フレーム ウィンドウが水平方向に分割される場所を示します。  
  
```  
virtual BOOL SplitRow(int cyBefore);
```  
  
### <a name="parameters"></a>パラメーター  
 *cyBefore*  
 (ピクセル単位) で分割が発生する前に、の位置。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 水平分割ウィンドウが作成されるときに呼び出されます。 `SplitRow` 分割が発生する既定の場所を示します。  
  
 `SplitRow` (分割ウィンドウは、SPLS_DYNAMIC_SPLIT スタイルを持つ) の場合は、動的分割ウィンドウのロジックを実装するためにフレームワークによって呼び出されます。 これはカスタマイズ可能な仮想関数と共に[CreateView](#createview)により高度な動的分割ウィンドウを実装します。  
  
##  <a name="ondraw"></a>  CSplitterWnd::OnDraw  
 分割ウィンドウを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDC*  
 デバイス コンテキストへのポインター。  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル VIEWEX](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CView クラス](../../mfc/reference/cview-class.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)
