---
title: CToolTipCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CToolTipCtrl
- AFXCMN/CToolTipCtrl
- AFXCMN/CToolTipCtrl::CToolTipCtrl
- AFXCMN/CToolTipCtrl::Activate
- AFXCMN/CToolTipCtrl::AddTool
- AFXCMN/CToolTipCtrl::AdjustRect
- AFXCMN/CToolTipCtrl::Create
- AFXCMN/CToolTipCtrl::CreateEx
- AFXCMN/CToolTipCtrl::DelTool
- AFXCMN/CToolTipCtrl::GetBubbleSize
- AFXCMN/CToolTipCtrl::GetCurrentTool
- AFXCMN/CToolTipCtrl::GetDelayTime
- AFXCMN/CToolTipCtrl::GetMargin
- AFXCMN/CToolTipCtrl::GetMaxTipWidth
- AFXCMN/CToolTipCtrl::GetText
- AFXCMN/CToolTipCtrl::GetTipBkColor
- AFXCMN/CToolTipCtrl::GetTipTextColor
- AFXCMN/CToolTipCtrl::GetTitle
- AFXCMN/CToolTipCtrl::GetToolCount
- AFXCMN/CToolTipCtrl::GetToolInfo
- AFXCMN/CToolTipCtrl::HitTest
- AFXCMN/CToolTipCtrl::Pop
- AFXCMN/CToolTipCtrl::Popup
- AFXCMN/CToolTipCtrl::RelayEvent
- AFXCMN/CToolTipCtrl::SetDelayTime
- AFXCMN/CToolTipCtrl::SetMargin
- AFXCMN/CToolTipCtrl::SetMaxTipWidth
- AFXCMN/CToolTipCtrl::SetTipBkColor
- AFXCMN/CToolTipCtrl::SetTipTextColor
- AFXCMN/CToolTipCtrl::SetTitle
- AFXCMN/CToolTipCtrl::SetToolInfo
- AFXCMN/CToolTipCtrl::SetToolRect
- AFXCMN/CToolTipCtrl::SetWindowTheme
- AFXCMN/CToolTipCtrl::Update
- AFXCMN/CToolTipCtrl::UpdateTipText
dev_langs:
- C++
helpviewer_keywords:
- CToolTipCtrl [MFC], CToolTipCtrl
- CToolTipCtrl [MFC], Activate
- CToolTipCtrl [MFC], AddTool
- CToolTipCtrl [MFC], AdjustRect
- CToolTipCtrl [MFC], Create
- CToolTipCtrl [MFC], CreateEx
- CToolTipCtrl [MFC], DelTool
- CToolTipCtrl [MFC], GetBubbleSize
- CToolTipCtrl [MFC], GetCurrentTool
- CToolTipCtrl [MFC], GetDelayTime
- CToolTipCtrl [MFC], GetMargin
- CToolTipCtrl [MFC], GetMaxTipWidth
- CToolTipCtrl [MFC], GetText
- CToolTipCtrl [MFC], GetTipBkColor
- CToolTipCtrl [MFC], GetTipTextColor
- CToolTipCtrl [MFC], GetTitle
- CToolTipCtrl [MFC], GetToolCount
- CToolTipCtrl [MFC], GetToolInfo
- CToolTipCtrl [MFC], HitTest
- CToolTipCtrl [MFC], Pop
- CToolTipCtrl [MFC], Popup
- CToolTipCtrl [MFC], RelayEvent
- CToolTipCtrl [MFC], SetDelayTime
- CToolTipCtrl [MFC], SetMargin
- CToolTipCtrl [MFC], SetMaxTipWidth
- CToolTipCtrl [MFC], SetTipBkColor
- CToolTipCtrl [MFC], SetTipTextColor
- CToolTipCtrl [MFC], SetTitle
- CToolTipCtrl [MFC], SetToolInfo
- CToolTipCtrl [MFC], SetToolRect
- CToolTipCtrl [MFC], SetWindowTheme
- CToolTipCtrl [MFC], Update
- CToolTipCtrl [MFC], UpdateTipText
ms.assetid: 8973f70c-b73a-46c7-908d-758f364b9a97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9436f3809a337b732a2e95d9c30b9baa45c4e8ba
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123111"
---
# <a name="ctooltipctrl-class"></a>CToolTipCtrl Class
"ツールヒント コントロール" の機能をカプセル化しています。このコンロトールは、アプリケーションでツールの目的を説明する 1 行のテキストを表示する小さなポップアップ ウィンドウです。  
  
## <a name="syntax"></a>構文  
  
```  
class CToolTipCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CToolTipCtrl::CToolTipCtrl](#ctooltipctrl)|`CToolTipCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CToolTipCtrl::Activate](#activate)|アクティブにし、ツール ヒント コントロールが非アクティブ化します。|  
|[CToolTipCtrl::AddTool](#addtool)|ツール ヒント コントロールでツールを登録します。|  
|[CToolTipCtrl::AdjustRect](#adjustrect)|ツール ヒント コントロールのテキストの間の変換は、四角形とそのウィンドウの四角形を表示します。|  
|[CToolTipCtrl::Create](#create)|ツール ヒント コントロールを作成し、それにアタッチ、`CToolTipCtrl`オブジェクト。|  
|[CToolTipCtrl::CreateEx](#createex)|指定した Windows 拡張スタイルを使用して、ツール ヒント コントロールを作成しにアタッチ、`CToolTipCtrl`オブジェクト。|  
|[CToolTipCtrl::DelTool](#deltool)|ツール ヒント コントロールからツールを削除します。|  
|[CToolTipCtrl::GetBubbleSize](#getbubblesize)|ツール ヒントのサイズを取得します。|  
|[CToolTipCtrl::GetCurrentTool](#getcurrenttool)|サイズ、位置、および現在のツール ヒント コントロールが表示されるツールヒント ウィンドウのテキストなどの情報を取得します。|  
|[については](#getdelaytime)|初期、ポップアップ、および再表示必要時間を取得期間などのツールは、現在設定されているコントロールのヒントします。|  
|[CToolTipCtrl::GetMargin](#getmargin)|上、左、下、およびツール ヒントのウィンドウに設定されている右の余白を取得します。|  
|[CToolTipCtrl::GetMaxTipWidth](#getmaxtipwidth)|ツール ヒント ウィンドウの最大幅を取得します。|  
|[CToolTipCtrl::GetText](#gettext)|ツールは、ツール ヒント コントロールを保持するテキストを取得します。|  
|[CToolTipCtrl::GetTipBkColor](#gettipbkcolor)|ツール ヒント ウィンドウの背景色を取得します。|  
|[CToolTipCtrl::GetTipTextColor](#gettiptextcolor)|ツール ヒント ウィンドウのテキストの色を取得します。|  
|[CToolTipCtrl::GetTitle](#gettitle)|現在のツール ヒント コントロールのタイトルを取得します。|  
|[CToolTipCtrl::GetToolCount](#gettoolcount)|ツール ヒント コントロールで管理されているツールの数を取得します。|  
|[CToolTipCtrl::GetToolInfo](#gettoolinfo)|ツールのツール ヒント コントロールを保持する情報を取得します。|  
|[CToolTipCtrl::HitTest](#hittest)|指定したツールの外接する四角形内にあるかどうかを決定する点をテストします。 場合は、ツールに関する情報を取得します。|  
|[CToolTipCtrl::Pop](#pop)|ビューから表示されるツール ヒントのウィンドウを削除します。|  
|[CToolTipCtrl::Popup](#popup)|現在のツールヒント コントロールの最後のマウス メッセージの座標にある表示させます。|  
|[CToolTipCtrl::RelayEvent](#relayevent)|マウスのメッセージを処理するためのツール ヒント コントロールに渡します。|  
|[CToolTipCtrl::SetDelayTime](#setdelaytime)|初期、ポップアップ ウィンドウを設定し、ツール ヒント コントロールの期間を表示します。|  
|[CToolTipCtrl::SetMargin](#setmargin)|上、左、下、およびツール ヒント ウィンドウの右余白を設定します。|  
|[CToolTipCtrl::SetMaxTipWidth](#setmaxtipwidth)|ツール ヒント ウィンドウの最大幅を設定します。|  
|[CToolTipCtrl::SetTipBkColor](#settipbkcolor)|ツール ヒント ウィンドウの背景色を設定します。|  
|[CToolTipCtrl::SetTipTextColor](#settiptextcolor)|ツール ヒント ウィンドウのテキストの色を設定します。|  
|[CToolTipCtrl::SetTitle](#settitle)|ツール ヒントには、標準的なアイコンをクリックしてタイトルの文字列を追加します。|  
|[CToolTipCtrl::SetToolInfo](#settoolinfo)|ツールは、ツール ヒントを保持する情報を設定します。|  
|[CToolTipCtrl::SetToolRect](#settoolrect)|ツールの新しい外接する四角形を設定します。|  
|[CToolTipCtrl::SetWindowTheme](#setwindowtheme)|ツール ヒント ウィンドウの表示スタイルを設定します。|  
|[CToolTipCtrl::Update](#update)|現在のツールを再描画を強制します。|  
|[CToolTipCtrl::UpdateTipText](#updatetiptext)|ツールは、ツール ヒントのテキストを設定します。|  
  
## <a name="remarks"></a>Remarks  
 「ツール」は、子ウィンドウ、またはコントロール、またはウィンドウのクライアント領域内アプリケーションで定義された四角形領域など、のいずれかのウィンドウです。 ツール ヒントには、ほとんどの場合、および表示されるだけときにユーザー ツールの上にカーソルを置きます約半分のままに 2 つ目は表示されません。 ツール ヒントは、カーソルの近くが表示され、ユーザーがマウス ボタンをクリックするか、ツールから、カーソルを移動すると表示されなくなります。  
  
 `CToolTipCtrl` ツール ヒントのテキスト、それ自体には、ツール ヒント ウィンドウの幅およびツールヒントの背景色とテキストの色を囲む余白の幅、最初の時間とツール ヒントの期間を制御する機能を提供します。 1 つのツール ヒント コントロールは、1 つ以上のツールの情報を提供できます。  
  
 `CToolTipCtrl`クラスには、Windows の一般的なツール ヒント コントロールの機能が用意されています。 このコントロール (したがって、`CToolTipCtrl`クラス) は、Windows 95/98 および Windows NT version 3.51 の下で実行されているプログラムにのみ使用可能な以降。  
  
 ツール ヒントを有効にする方法の詳細については、次を参照してください。[ウィンドウのツール ヒントから派生していない CFrameWnd](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)です。  
  
 使用する方法についての`CToolTipCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CToolTipCtrl](../../mfc/using-ctooltipctrl.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolTipCtrl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="activate"></a>  CToolTipCtrl::Activate  
 この関数では、ツール ヒント コントロールをアクティブまたは非アクティブにします。  
  
```  
void Activate(BOOL bActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 *bActivate*  
 ツール ヒント コントロールをアクティブ化または非アクティブ化するかどうかを指定します。  
  
### <a name="remarks"></a>Remarks  
 場合*bActivate* true で、コントロールがアクティブにされた; FALSE の場合、これを非アクティブです。  
  
 コントロールに登録されているツールの上にカーソルがある場合、ツール ヒント コントロールがアクティブなとツール ヒント情報が表示されます。アクティブになっていない、ときにツール ヒント情報が表示されないであっても、ツールの上にカーソルが場合。  
  
### <a name="example"></a>例  
  例を参照して[CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)です。  
  
##  <a name="addtool"></a>  CToolTipCtrl::AddTool  
 ツール ヒント コントロールでツールを登録します。  
  
```  
BOOL AddTool(
    CWnd* pWnd,  
    UINT nIDText,  
    LPCRECT lpRectTool = NULL,  
    UINT_PTR nIDTool = 0);

 
BOOL AddTool(
    CWnd* pWnd,  
    LPCTSTR lpszText = LPSTR_TEXTCALLBACK,  
    LPCRECT lpRectTool = NULL,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWnd*  
 ツールが含まれるウィンドウへのポインター。  
  
 *nIDText*  
 このツールのテキストを含む文字列リソースの ID です。  
  
 *lpRectTool*  
 ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)ツールの座標を含む構造体の外接する四角形。 識別されるウィンドウのクライアント領域の左上隅に対する相対座標は、 *pWnd*です。  
  
 *nIDTool*  
 ツールの ID です。  
  
 *lpszText*  
 このツールのテキストへのポインター。 TTN_NEEDTEXT 通知のメッセージがウィンドウの親に移動してこのパラメーターに保持するようにする値が含まれている場合を*pWnd*を指します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 *LpRectTool*と*nIDTool*できるパラメーターは、どちらも、有効な場合、または*lpRectTool* null、 *nIDTool* 0 にする必要があります。  
  
 ツール ヒント コントロールは、1 つ以上のツールに関連付けることができます。 ツールの上にカーソルがときにツール ヒントに格納されている情報が表示されるようにツール ヒント コントロールでツールを登録するには、この関数を呼び出します。  
  
> [!NOTE]
>  静的なコントロールを使用して、ツール ヒントを設定することはできません`AddTool`です。  
  
### <a name="example"></a>例  
  例を参照して[CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)です。  
  
##  <a name="adjustrect"></a>  CToolTipCtrl::AdjustRect  
 ツールヒント コントロールのテキストの間の変換は、四角形とそのウィンドウの四角形を表示します。  
  
```  
BOOL AdjustRect(
    LPRECT lprc,  
    BOOL bLarger = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *lprc*  
 ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)ツール ヒント ウィンドウ四角形またはテキストの表示長方形のいずれかを保持する構造。  
  
 *き*  
 TRUE の場合、 *lprc*テキスト表示四角形を指定するために使用され、対応するウィンドウの四角形を受け取ります。 FALSE の場合、 *lprc*ウィンドウ四角形を指定するために使用され、対応するテキストの表示長方形を受け取ります。  
  
### <a name="return-value"></a>戻り値  
 四角形は正常に調整されました。 場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、そのウィンドウの四角形、または指定したテキストの表示長方形を表示するために必要なツール ヒント ウィンドウ四角形から、ツール ヒント コントロールのテキスト表示長方形を計算します。  
  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_ADJUSTRECT](http://msdn.microsoft.com/library/windows/desktop/bb760352)Windows SDK で説明されている。  
  
##  <a name="create"></a>  CToolTipCtrl::Create  
 ツール ヒント コントロールを作成し、それにアタッチ、`CToolTipCtrl`オブジェクト。  
  
```  
virtual BOOL Create(CWnd* pParentWnd, DWORD dwStyle = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *pParentWnd*  
 ツール ヒント コントロールの親ウィンドウを通常を指定します、`CDialog`です。 NULL は指定できません。  
  
 *dwStyle*  
 ツール ヒント コントロールのスタイルを指定します。 参照してください、**解説**詳細についてはします。  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、`CToolTipCtrl`オブジェクトが正常に作成された以外の場合はそれ以外の場合に 0 です。  
  
### <a name="remarks"></a>Remarks  
 構築する、 `CToolTipCtrl` 2 つの手順でします。 最初に、構築するコンス トラクターを呼び出し、`CToolTipCtrl`オブジェクト、およびを呼び出す`Create`ツール ヒント コントロールを作成してアタッチする、`CToolTipCtrl`オブジェクト。  
  
 *DwStyle*パラメーターの任意の組み合わせを指定できます[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)です。 さらに、ツール ヒント コントロールには 2 つのクラスに固有のスタイル: TTS_ALWAYSTIP と TTS_NOPREFIX です。  
  
|スタイル|説明|  
|-----------|-------------|  
|TTS_ALWAYSTIP|ツール ヒント コントロールのオーナー ウィンドウがアクティブまたは非アクティブなのかどうかに関係なく、ツールの上にカーソルがある場合、ツール ヒントが表示されることを指定します。 このスタイルしない場合は、ツール ヒント コントロールは、ツールのオーナー ウィンドウがアクティブの場合が非アクティブ時ではなく表示されます。|  
|TTS_NOPREFIX|このスタイルでは、システムがアンパサンド (&)、文字列から文字を削除できなくなります。 ツール ヒント コントロールが TTS_NOPREFIX スタイルを持たない場合、アプリケーション メニュー項目とは、ツール ヒント コントロールでテキストとして、同じ文字列を使用することにより、アンパサンド文字が自動的に削除します。|  
  
 ツール ヒント コントロールは、WS_POPUP と WS_EX_TOOLWINDOW ウィンドウ スタイルのかどうかを指定するにコントロールを作成するときに関係なくがします。  
  
 拡張ウィンドウ スタイルを使用して、ツール ヒント コントロールを作成するには、呼び出す[CToolTipCtrl::CreateEx](#createex)の代わりに`Create`です。  
  
### <a name="example"></a>例  
  例を参照して[CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)です。  
  
##  <a name="createex"></a>  CToolTipCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成し、関連付けること、`CToolTipCtrl`オブジェクト。  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwStyle = 0,  
    DWORD dwStyleEx = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *pParentWnd*  
 コントロールの親であるウィンドウへのポインター。  
  
 *dwStyle*  
 ツール ヒント コントロールのスタイルを指定します。 参照してください、**解説**のセクション[作成](#create)詳細についてはします。  
  
 *dwStyleEx*  
 作成されるコントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、 *dwExStyle*パラメーターを[について](http://msdn.microsoft.com/library/windows/desktop/ms632680)Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外。 それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 使用して`CreateEx`の代わりに`Create`Windows 拡張スタイル「はじめに」で指定された Windows の拡張スタイルを適用する**ws_ex**です。  
  
##  <a name="ctooltipctrl"></a>  CToolTipCtrl::CToolTipCtrl  
 `CToolTipCtrl` オブジェクトを構築します。  
  
```  
CToolTipCtrl();
```  
  
### <a name="remarks"></a>Remarks  
 呼び出す必要があります`Create`オブジェクトを構築した後です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog#74](../../mfc/codesnippet/cpp/ctooltipctrl-class_1.h)]  
  
##  <a name="deltool"></a>  CToolTipCtrl::DelTool  
 指定されたツールを削除*pWnd*と*nIDTool*ツール ヒント コントロールでサポートされているツールのコレクションからです。  
  
```  
void DelTool(
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWnd*  
 ツールが含まれるウィンドウへのポインター。  
  
 *nIDTool*  
 ツールの ID です。  
  
##  <a name="getbubblesize"></a>  CToolTipCtrl::GetBubbleSize  
 ツール ヒントのサイズを取得します。  
  
```  
CSize GetBubbleSize(LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *返すとき*  
 ツール ヒントへのポインター [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256)構造体。  
  
### <a name="return-value"></a>戻り値  
 ツール ヒントのサイズ。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_GETBUBBLESIZE](http://msdn.microsoft.com/library/windows/desktop/bb760387)Windows SDK で説明されている。  
  
##  <a name="getcurrenttool"></a>  CToolTipCtrl::GetCurrentTool  
 サイズ、位置、および現在のツール ヒント コントロールによって表示されるツールヒント ウィンドウのテキストなどの情報を取得します。  
  
```  
BOOL GetCurrentTool(LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[out]*返すとき*|ポインター、 [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256)現在ツールヒント ウィンドウに関する情報を受け取る構造体。|  
  
### <a name="return-value"></a>戻り値  
 情報が正常に取得される場合は TRUE。それ以外の場合は FALSE です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [TTM_GETCURRENTTOOL](http://msdn.microsoft.com/library/windows/desktop/bb760389) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例では、現在のツールヒント ウィンドウに関する情報を取得します。  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1#6](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_2.cpp)]  
  
##  <a name="getdelaytime"></a>  については  
 初期、ポップアップ ウィンドウを取得し、表示、ツール ヒント コントロールに現在設定されています。  
  
```  
int GetDelayTime(DWORD dwDuration) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *dwDuration*  
 どの期間の値を指定するフラグが取得されます。 このパラメーターには、次の値のいずれかを指定できます。  
  
- TTDT_AUTOPOP 取得時間、ツール ヒント ウィンドウの長さ場合に表示されるポインターが静止ツールの外接する四角形内で。  
  
- TTDT_INITIAL 取得ツール ヒント ウィンドウの前に、ツールの外接する四角形内で、ポインターを静止時間の長さが表示されます。  
  
- TTDT_RESHOW 取得ポインターとして表示する次のツール ヒントのウィンドウにかかる時間の長さ 1 つのツールから別に移動します。  
  
### <a name="return-value"></a>戻り値  
 指定された遅延時間 (ミリ秒)  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_GETDELAYTIME](http://msdn.microsoft.com/library/windows/desktop/bb760390)Windows SDK で説明されている。  
  
##  <a name="getmargin"></a>  CToolTipCtrl::GetMargin  
 上、左、下、および右余白のツール ヒント ウィンドウの設定を取得します。  
  
```  
void GetMargin(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lprc*  
 アドレス、`RECT`余白情報を受け取る。 メンバー、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造外接する四角形が定義されていません。 このメッセージのためには構造体のメンバーはように解釈されます。  
  
|メンバー|表現|  
|------------|--------------------|  
|`top`|上罫線とツールヒントのテキスト、(ピクセル単位) の一番上の距離。|  
|`left`|左罫線と (ピクセル単位) のツールヒントのテキストの左端の間の距離。|  
|`bottom`|下罫線と (ピクセル単位) のツールヒントのテキストの下部にある間の距離。|  
|`right`|右罫線と右端の位置 (ピクセル単位) のツールヒントのテキストの間の距離。|  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_GETMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb760391)Windows SDK で説明されている。  
  
##  <a name="getmaxtipwidth"></a>  CToolTipCtrl::GetMaxTipWidth  
 ツール ヒント ウィンドウの最大幅を取得します。  
  
```  
int GetMaxTipWidth() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ツール ヒント ウィンドウの最大の幅。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_GETMAXTIPWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760392)Windows SDK で説明されている。  
  
##  <a name="gettext"></a>  CToolTipCtrl::GetText  
 ツールは、ツール ヒント コントロールを保持するテキストを取得します。  
  
```  
void GetText(
    CString& str,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *str*  
 参照、`CString`ツールのテキストを受け取るオブジェクト。  
  
 *pWnd*  
 ツールが含まれるウィンドウへのポインター。  
  
 *nIDTool*  
 ツールの ID です。  
  
### <a name="remarks"></a>Remarks  
 *PWnd*と*nIDTool*パラメーターは、ツールを指定します。 ツールの登録済みを前回呼び出したとき、ツール ヒント コントロールに場合`CToolTipCtrl::AddTool`、によって参照されるオブジェクト、 *str*パラメーターには、ツールのテキストが割り当てられます。  
  
##  <a name="gettipbkcolor"></a>  CToolTipCtrl::GetTipBkColor  
 ツール ヒント ウィンドウの背景色を取得します。  
  
```  
COLORREF GetTipBkColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)背景色を表す値です。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_GETTIPBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760394)Windows SDK で説明されている。  
  
##  <a name="gettiptextcolor"></a>  CToolTipCtrl::GetTipTextColor  
 ツール ヒント ウィンドウのテキストの色を取得します。  
  
```  
COLORREF GetTipTextColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)テキストの色を表す値です。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_GETTIPTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760395)Windows SDK で説明されている。  
  
##  <a name="gettitle"></a>  CToolTipCtrl::GetTitle  
 現在のツール ヒント コントロールのタイトルを取得します。  
  
```  
void GetTitle(PTTGETTITLE pttgt) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[out]*pttgt*|ポインター、 [TTGETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760260)ツール ヒント コントロールに関する情報を格納する構造体。 このメソッドが戻るとき、 *pszTitle*のメンバー、 [TTGETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760260)タイトルのテキストへのポインターを構造体します。|  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [TTM_GETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760396) Windows SDK で説明するメッセージ。  
  
##  <a name="gettoolcount"></a>  CToolTipCtrl::GetToolCount  
 ツール ヒント コントロールに登録されているツールの数を取得します。  
  
```  
int GetToolCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ツールの数は、ツール ヒント コントロールに登録します。  
  
##  <a name="gettoolinfo"></a>  CToolTipCtrl::GetToolInfo  
 ツールのツール ヒント コントロールを保持する情報を取得します。  
  
```  
BOOL GetToolInfo(
    CToolInfo& ToolInfo,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *ToolInfo*  
 参照、`TOOLINFO`ツールのテキストを受け取るオブジェクト。  
  
 *pWnd*  
 ツールが含まれるウィンドウへのポインター。  
  
 *nIDTool*  
 ツールの ID です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 `hwnd`と`uId`のメンバー、 [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256)によって参照される構造*CToolInfo*ツールを識別します。 そのツールを以前の呼び出し、ツール ヒント コントロールに登録されている場合`AddTool`、`TOOLINFO`ツールに関する情報を含む構造体を格納します。  
  
##  <a name="hittest"></a>  CToolTipCtrl::HitTest  
 指定したツールの外接する四角形内にあるかどうかを特定し場合は、ツールに関する情報を取得する点をテストします。  
  
```  
BOOL HitTest(
    CWnd* pWnd,  
    CPoint pt,  
    LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pWnd*  
 ツールが含まれるウィンドウへのポインター。  
  
 *pt*  
 ポインター、`CPoint`をテストする点の座標を含むオブジェクト。  
  
 *返すとき*  
 ポインター [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256)ツールに関する情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 ヒット テスト情報で指定されたポイントが、ツールの外接する四角形内にある場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数は 0 以外の値を返す場合、構造体を指す*返すとき*点は含む四角形内のツールの情報が格納されます。  
  
 `TTHITTESTINFO`構造は次のように定義されます。  
  
 `typedef struct _TT_HITTESTINFO { // tthti`  
  
 `HWND hwnd;   // handle of tool or window with tool`  
  
 `POINT pt;    // client coordinates of point to test`  
  
 `TOOLINFO ti; // receives information about the tool`  
  
 `} TTHITTESTINFO, FAR * LPHITTESTINFO;`  
  
 `hwnd`  
 ツールのハンドルを指定します。  
  
 `pt`  
 場合は、ポイントは、ツールの外接する四角形は、点の座標を指定します。  
  
 `ti`  
 ツールに関する情報。 詳細については、`TOOLINFO`構造体は、「 [CToolTipCtrl::GetToolInfo](#gettoolinfo)です。  
  
##  <a name="pop"></a>  CToolTipCtrl::Pop  
 ビューから表示されるツール ヒントのウィンドウを削除します。  
  
```  
void Pop();
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_POP](http://msdn.microsoft.com/library/windows/desktop/bb760401)Windows SDK で説明されている。  
  
##  <a name="popup"></a>  CToolTipCtrl::Popup  
 現在のツールヒント コントロールの最後のマウス メッセージの座標にある表示させます。  
  
```  
void Popup();
```  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [TTM_POPUP](http://msdn.microsoft.com/library/windows/desktop/bb760402) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例では、ツールヒント ウィンドウが表示されます。  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1#7](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_3.cpp)]  
  
##  <a name="relayevent"></a>  CToolTipCtrl::RelayEvent  
 マウスのメッセージを処理するためのツール ヒント コントロールに渡します。  
  
```  
void RelayEvent(LPMSG lpMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpMsg*  
 ポインター、 [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958)リレーにメッセージを格納する構造体。  
  
### <a name="remarks"></a>Remarks  
 ツール ヒント コントロール メッセージを処理のみ次、によって送信される`RelayEvent`:  
  
|WM_LBUTTONDOWN|WM_MOUSEMOVE|  
|---------------------|-------------------|  
|した|WM_RBUTTONDOWN|  
|WM_MBUTTONDOWN|WM_RBUTTONUP|  
|WM_MBUTTONUP||  
  
### <a name="example"></a>例  
  例を参照して[CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)です。  
  
##  <a name="setdelaytime"></a>  CToolTipCtrl::SetDelayTime  
 ツール ヒント コントロールの遅延時間を設定します。  
  
```  
void SetDelayTime(UINT nDelay);

 
void SetDelayTime(
    DWORD dwDuration,  
    int iTime);
```  
  
### <a name="parameters"></a>パラメーター  
 *nDelay*  
 新しい時刻の遅延をミリ秒単位で指定します。  
  
 *dwDuration*  
 どの期間の値を指定するフラグが取得されます。 参照してください[については](#getdelaytime)有効な値の詳細についてはします。  
  
 *iTime*  
 指定された遅延時間 (ミリ秒)。  
  
### <a name="remarks"></a>Remarks  
 遅延時間は、ツール ヒントのウィンドウが表示されるまで、カーソルのツールのままにする必要があります時間の長さです。 既定の遅延時間は、500 ミリ秒です。  
  
##  <a name="setmargin"></a>  CToolTipCtrl::SetMargin  
 上、左、下、およびツール ヒント ウィンドウの右余白を設定します。  
  
```  
void SetMargin(LPRECT lprc);
```  
  
### <a name="parameters"></a>パラメーター  
 *lprc*  
 アドレス、`RECT`を設定する余白の情報を格納する構造体。 メンバー、`RECT`構造外接する四角形が定義されていません。 参照してください[CToolTipCtrl::GetMargin](#getmargin)余白情報の詳細についてはします。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_SETMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb760406)Windows SDK で説明されている。  
  
##  <a name="setmaxtipwidth"></a>  CToolTipCtrl::SetMaxTipWidth  
 ツール ヒント ウィンドウの最大幅を設定します。  
  
```  
int SetMaxTipWidth(int iWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 *iWidth*  
 設定する最大のツール ヒント ウィンドウの幅。  
  
### <a name="return-value"></a>戻り値  
 前のヒントの最大の幅。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_SETMAXTIPWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760408)Windows SDK で説明されている。  
  
##  <a name="settipbkcolor"></a>  CToolTipCtrl::SetTipBkColor  
 ツール ヒント ウィンドウの背景色を設定します。  
  
```  
void SetTipBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>パラメーター  
 *clr*  
 新しい背景色です。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_SETTIPBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760411)Windows SDK で説明されている。  
  
##  <a name="settiptextcolor"></a>  CToolTipCtrl::SetTipTextColor  
 ツール ヒント ウィンドウのテキストの色を設定します。  
  
```  
void SetTipTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>パラメーター  
 *clr*  
 新しいテキストの色。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_SETTIPTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760413)Windows SDK で説明されている。  
  
##  <a name="settitle"></a>  CToolTipCtrl::SetTitle  
 ツール ヒントには、標準的なアイコンをクリックしてタイトルの文字列を追加します。  
  
```  
BOOL SetTitle(
    UINT uIcon,  
    LPCTSTR lpstrTitle);
```  
  
### <a name="parameters"></a>パラメーター  
 *uIcon*  
 参照してください*アイコン*で[TTM_SETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760414) Windows SDK に含まれています。  
  
 *キャプションを表示*  
 タイトル文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_SETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760414)Windows SDK で説明されている。  
  
##  <a name="settoolinfo"></a>  CToolTipCtrl::SetToolInfo  
 ツールは、ツール ヒントを保持する情報を設定します。  
  
```  
void SetToolInfo(LPTOOLINFO lpToolInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 *返すとき*  
 ポインター、 [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256)構造を設定する情報を指定します。  
  
##  <a name="settoolrect"></a>  CToolTipCtrl::SetToolRect  
 ツールの新しい外接する四角形を設定します。  
  
```  
void SetToolRect(
    CWnd* pWnd,  
    UINT_PTR nIDTool,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWnd*  
 ツールが含まれるウィンドウへのポインター。  
  
 *nIDTool*  
 ツールの ID です。  
  
 *lpRect*  
 ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体の新しい外接する四角形を指定します。  
  
##  <a name="setwindowtheme"></a>  CToolTipCtrl::SetWindowTheme  
 ツール ヒント ウィンドウの表示スタイルを設定します。  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>パラメーター  
 *pszSubAppName*  
 設定する visual スタイルを表す Unicode 文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 戻り値は使用されません。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数の機能をエミュレートする、 [TTM_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb760418)メッセージ、Windows SDK で説明します。  
  
##  <a name="update"></a>  CToolTipCtrl::Update  
 現在のツールを再描画を強制します。  
  
```  
void Update();
```  
  
##  <a name="updatetiptext"></a>  CToolTipCtrl::UpdateTipText  
 このコントロールのツールのツールヒントのテキストを更新します。  
  
```  
void UpdateTipText(
    LPCTSTR lpszText,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);

 
void UpdateTipText(
    UINT nIDText,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszText*  
 このツールのテキストへのポインター。  
  
 *pWnd*  
 ツールが含まれるウィンドウへのポインター。  
  
 *nIDTool*  
 ツールの ID です。  
  
 *nIDText*  
 このツールのテキストを含む文字列リソースの ID です。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CToolBar クラス](../../mfc/reference/ctoolbar-class.md)
