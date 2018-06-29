---
title: 関数クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CScrollBar
- AFXWIN/CScrollBar
- AFXWIN/CScrollBar::CScrollBar
- AFXWIN/CScrollBar::Create
- AFXWIN/CScrollBar::EnableScrollBar
- AFXWIN/CScrollBar::GetScrollBarInfo
- AFXWIN/CScrollBar::GetScrollInfo
- AFXWIN/CScrollBar::GetScrollLimit
- AFXWIN/CScrollBar::GetScrollPos
- AFXWIN/CScrollBar::GetScrollRange
- AFXWIN/CScrollBar::SetScrollInfo
- AFXWIN/CScrollBar::SetScrollPos
- AFXWIN/CScrollBar::SetScrollRange
- AFXWIN/CScrollBar::ShowScrollBar
dev_langs:
- C++
helpviewer_keywords:
- CScrollBar [MFC], CScrollBar
- CScrollBar [MFC], Create
- CScrollBar [MFC], EnableScrollBar
- CScrollBar [MFC], GetScrollBarInfo
- CScrollBar [MFC], GetScrollInfo
- CScrollBar [MFC], GetScrollLimit
- CScrollBar [MFC], GetScrollPos
- CScrollBar [MFC], GetScrollRange
- CScrollBar [MFC], SetScrollInfo
- CScrollBar [MFC], SetScrollPos
- CScrollBar [MFC], SetScrollRange
- CScrollBar [MFC], ShowScrollBar
ms.assetid: f3735ca5-73ea-46dc-918b-4d824c9fe47f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 86827a2f01e387eb6e7c8b2184567cb204f184e6
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079122"
---
# <a name="cscrollbar-class"></a>関数クラス
Windows のスクロール バー コントロールの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CScrollBar : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CScrollBar::CScrollBar](#cscrollbar)|`CScrollBar` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CScrollBar::Create](#create)|Windows のスクロール バーを作成しにアタッチ、`CScrollBar`オブジェクト。|  
|[CScrollBar::EnableScrollBar](#enablescrollbar)|スクロール バーの矢印の一方または両方を有効または無効にします。|  
|[CScrollBar::GetScrollBarInfo](#getscrollbarinfo)|スクロール バーの使用に関する情報を取得、`SCROLLBARINFO`構造体。|  
|[CScrollBar::GetScrollInfo](#getscrollinfo)|スクロール バーの情報を取得します。|  
|[CScrollBar::GetScrollLimit](#getscrolllimit)|スクロール バーの制限値を取得します|  
|[CScrollBar::GetScrollPos](#getscrollpos)|スクロール ボックスの現在位置を取得します。|  
|[CScrollBar::GetScrollRange](#getscrollrange)|指定されたスクロール バーの現在の最小値と最大のスクロール バーの位置を取得します。|  
|[CScrollBar::SetScrollInfo](#setscrollinfo)|スクロール バーの情報を設定します。|  
|[CScrollBar::SetScrollPos](#setscrollpos)|スクロール ボックスの現在の位置を設定します。|  
|[CScrollBar::SetScrollRange](#setscrollrange)|指定されたスクロール バーの最小位置と最大位置の値を設定します。|  
|[CScrollBar::ShowScrollBar](#showscrollbar)|スクロール バーの表示と非表示を切り替えます。|  
  
## <a name="remarks"></a>Remarks  
 2 つの手順では、スクロール バー コントロールを作成します。 最初に、コンス トラクターを呼び出す`CScrollBar`構築するために、`CScrollBar`オブジェクト、し、呼び出し、[作成](#create)Windows のスクロール バー コントロールを作成し、アタッチにメンバー関数、`CScrollBar`オブジェクト。  
  
 作成する場合、 `CScrollBar` (ダイアログ リソースを使って)、ダイアログ ボックス内のオブジェクト、`CScrollBar`が自動的に破棄されると、ユーザーがダイアログ ボックスを閉じます。  
  
 作成する場合、`CScrollBar`ウィンドウ内でオブジェクトを破棄しても必要があります。  
  
 作成する場合、`CScrollBar`スタック上のオブジェクトは自動的に破棄します。 作成する場合、`CScrollBar`を使用して、ヒープ上のオブジェクト、**新しい**関数を呼び出す必要があります**削除**をユーザーが、Windows のスクロール バーが終了するときに破棄するオブジェクト。  
  
 メモリを割り当てる場合、`CScrollBar`オブジェクト、オーバーライド、`CScrollBar`デストラクターが、割り当てを破棄します。  
  
 使用しての関連情報について`CScrollBar`を参照してください[コントロール](../../mfc/controls-mfc.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CScrollBar`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  
  
##  <a name="create"></a>  CScrollBar::Create  
 Windows のスクロール バーを作成しにアタッチ、`CScrollBar`オブジェクト。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwStyle*  
 スクロールを示すバーのスタイル。 任意の組み合わせを適用[スクロール バー スタイル](../../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles)スクロール バーをします。  
  
 *rect*  
 スクロール バーのサイズと位置を指定します。 いずれかになります、`RECT`構造体、または`CRect`オブジェクト。  
  
 *pParentWnd*  
 Scroll を指定バーの親ウィンドウで、通常、`CDialog`オブジェクト。 なければなりません**NULL**です。  
  
 *nID*  
 スクロール バーのコントロール id です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 構築する、 `CScrollBar` 2 つのステップ内のオブジェクト。 最初に、構築コンス トラクターを呼び出し、`CScrollBar`オブジェクト以外の場合は、呼び出す`Create`を作成し、関連付けられている Windows のスクロール バーを初期化およびにアタッチする、`CScrollBar`オブジェクト。  
  
 次の適用[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)スクロール バーを。  
  
- **WS_CHILD**常に  
  
- **WS_VISIBLE**通常  
  
- **WS_DISABLED**ことはほとんどありません  
  
- **WS_GROUP**コントロールをグループ化  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CScrollBar#1](../../mfc/reference/codesnippet/cpp/cscrollbar-class_1.cpp)]  
  
##  <a name="cscrollbar"></a>  CScrollBar::CScrollBar  
 `CScrollBar` オブジェクトを構築します。  
  
```  
CScrollBar();
```  
  
### <a name="remarks"></a>Remarks  
 オブジェクトを構築した後、**作成**メンバー関数を作成し、Windows のスクロール バーを初期化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CScrollBar#2](../../mfc/reference/codesnippet/cpp/cscrollbar-class_2.h)]  
  
##  <a name="enablescrollbar"></a>  CScrollBar::EnableScrollBar  
 スクロール バーの矢印の一方または両方を有効または無効にします。  
  
```  
BOOL EnableScrollBar(UINT nArrowFlags = ESB_ENABLE_BOTH);
```  
  
### <a name="parameters"></a>パラメーター  
 *nArrowFlags*  
 どちらの矢印は、有効または無効にし、スクロール バーの矢印を有効または無効にするかどうかを指定します。 このパラメーターには、次の値のいずれかを指定できます。  
  
- **ESB_ENABLE_BOTH**スクロール バーの両方の矢印を有効にします。  
  
- **ESB_DISABLE_LTUP**水平スクロール バーの左側の矢印または上向きの矢印の垂直スクロール バーを無効にします。  
  
- **ESB_DISABLE_RTDN**水平スクロール バーの右矢印または下向きの矢印の垂直スクロール バーを無効にします。  
  
- **ESB_DISABLE_BOTH**スクロール バーの両方の矢印を無効にします。  
  
### <a name="return-value"></a>戻り値  
 矢印が有効にまたは指定; として無効になっている場合は 0 以外。それ以外の場合 0 で、矢印が既に要求された状態であるか、エラーが発生したことを示します。  
  
### <a name="example"></a>例  
  例を参照して[CScrollBar::SetScrollRange](#setscrollrange)です。  
  
##  <a name="getscrollbarinfo"></a>  CScrollBar::GetScrollBarInfo  
 情報を取得する、 **SCROLLBARINFO**構造体がスクロール バーについて保持します。  
  
```  
BOOL GetScrollBarInfo(PSCROLLBARINFO pScrollInfo) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pScrollInfo*  
 ポインター、 [SCROLLBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb787535)構造体。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数の機能をエミュレートする、 [SBM_SCROLLBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb787545)メッセージ、Windows SDK で説明します。  
  
##  <a name="getscrollinfo"></a>  CScrollBar::GetScrollInfo  
 `SCROLLINFO` 構造体がスクロール バーについて保持している情報を取得します。  
  
```  
BOOL GetScrollInfo(
    LPSCROLLINFO lpScrollInfo,  
    UINT nMask = SIF_ALL);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpScrollInfo*  
 ポインター、 [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537)構造体。 この構造体の詳細については、Windows SDK を参照してください。  
  
 *いる*  
 取得するスクロール バーのパラメーターを指定します。 一般的な使用、SIF_ALL、SIF_PAGE、SIF_POS、SIF_TRACKPOS、および SIF_RANGE の組み合わせを指定します。 参照してください`SCROLLINFO`いる値についての詳細。  
  
### <a name="return-value"></a>戻り値  
 メッセージには、任意の値が取得されると場合、戻り値は**TRUE**です。 以外の場合は**FALSE**です。  
  
### <a name="remarks"></a>Remarks  
 `GetScrollInfo` 32 ビットのスクロール位置を使用するアプリケーションを有効にします。  
  
 [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537)構造体には、スクロール バーの最小値と最大スクロール位置、ページ サイズおよびスクロール ボックス (つまみ) の位置を含むに関する情報が含まれています。 参照してください、`SCROLLINFO`構造の既定値の変更の詳細については、Windows SDK のトピックを構造体。  
  
 MFC のウィンドウ メッセージ ハンドラーをスクロール バーの位置を示す[CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)と[ために](../../mfc/reference/cwnd-class.md#onvscroll)、位置データの 16 ビットのみを提供します。 `GetScrollInfo` および`SetScrollInfo`スクロール バーの位置データの 32 ビットを提供します。 したがって、アプリケーションが呼び出すことができます`GetScrollInfo`いずれかの処理中に`CWnd::OnHScroll`または`CWnd::OnVScroll`32 ビットのスクロール バーの位置のデータを取得します。  
  
### <a name="example"></a>例  
  例を参照して[CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)です。  
  
##  <a name="getscrolllimit"></a>  CScrollBar::GetScrollLimit  
 最大スクロール スクロール バーの位置を取得します。  
  
```  
int GetScrollLimit();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、スクロール バーの最大の位置を指定しますそれ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
  例を参照して[CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)です。  
  
##  <a name="getscrollpos"></a>  CScrollBar::GetScrollPos  
 スクロール ボックスの現在位置を取得します。  
  
```  
int GetScrollPos() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、スクロール ボックスの現在位置を指定しますそれ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 現在の位置は、現在のスクロールの範囲に依存する相対値です。 たとえば、スクロールの範囲は 100 ~ 200、スクロール ボックスは、バーの途中で、現在の位置が 150。  
  
### <a name="example"></a>例  
  例を参照して[CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)です。  
  
##  <a name="getscrollrange"></a>  CScrollBar::GetScrollRange  
 指定されたスクロール バーの現在の最小値と最大のスクロール バーの位置で指定された場所にコピーして*lpMinPos*と*最大位置*です。  
  
```  
void GetScrollRange(
    LPINT lpMinPos,  
    LPINT lpMaxPos) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lpMinPos*  
 最小の位置を受け取る整数変数へのポインター。  
  
 *最大位置*  
 最大の位置を受け取る整数変数へのポインター。  
  
### <a name="remarks"></a>Remarks  
 スクロール バー コントロールの既定の範囲が空 (両方の値が 0) です。  
  
### <a name="example"></a>例  
  例を参照して[CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)です。  
  
##  <a name="setscrollinfo"></a>  CScrollBar::SetScrollInfo  
 情報を設定、`SCROLLINFO`構造体がスクロール バーについて保持します。  
  
```  
BOOL SetScrollInfo(
    LPSCROLLINFO lpScrollInfo,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpScrollInfo*  
 ポインター、 [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537)構造体。  
  
 *bRedraw*  
 新しい情報を反映するように、スクロール バーを再描画されるかどうかを指定します。 場合*bRedraw*は**TRUE**、スクロール バーを再描画します。 場合は**FALSE**が再描画されません。 スクロール バーは、既定では再描画されます。  
  
### <a name="return-value"></a>戻り値  
 成功すると、戻り値が**TRUE**です。 以外の場合は**FALSE**です。  
  
### <a name="remarks"></a>Remarks  
 必要な値を指定する必要があります、`SCROLLINFO`フラグの値を含むパラメーターを構成します。  
  
 `SCROLLINFO`構造体には、スクロール バーの最小値と最大スクロール位置、ページ サイズおよびスクロール ボックス (つまみ) の位置を含むに関する情報が含まれています。 参照してください、 [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537)構造の既定値の変更の詳細については、Windows SDK のトピックを構造体。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CScrollBar#3](../../mfc/reference/codesnippet/cpp/cscrollbar-class_3.cpp)]  
  
##  <a name="setscrollpos"></a>  CScrollBar::SetScrollPos  
 によって指定されるスクロール ボックスの現在の位置を設定*nPos*し、指定した場合は、新しい位置を反映するように、スクロール バーを再描画します。  
  
```  
int SetScrollPos(
    int nPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *nPos*  
 スクロール ボックスの新しい位置を指定します。 スクロールの範囲でなければなりません。  
  
 *bRedraw*  
 新しい位置を反映するように、スクロール バーを再描画されるかどうかを指定します。 場合*bRedraw*は**TRUE**、スクロール バーを再描画します。 場合は**FALSE**が再描画されません。 スクロール バーは、既定では再描画されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、スクロール ボックスの前の位置を指定しますそれ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 設定*bRedraw*に**FALSE**するたびに、スクロール バーは、短い間隔で 2 回再描画されるスクロール バーをしなくても済むようにを別の関数の後続の呼び出しで再描画されます。  
  
### <a name="example"></a>例  
  例を参照して[CScrollBar::SetScrollRange](#setscrollrange)です。  
  
##  <a name="setscrollrange"></a>  CScrollBar::SetScrollRange  
 指定されたスクロール バーの最小位置と最大位置の値を設定します。  
  
```  
void SetScrollRange(
    int nMinPos,  
    int nMaxPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *nMinPos*  
 最小スクロール位置を指定します。  
  
 *とき*  
 最大スクロール位置を指定します。  
  
 *bRedraw*  
 変更を反映するように、スクロール バーを再描画されるかどうかを指定します。 場合*bRedraw*は**TRUE**、スクロール バーが再描画される; 場合**FALSE**が再描画されません。 これは既定では再描画されます。  
  
### <a name="remarks"></a>Remarks  
 設定*nMinPos*と*とき*標準のスクロール バーを非表示にします。  
  
 スクロール バーの通知メッセージの処理中に、スクロール バーを非表示にするには、この関数を呼び出さないでください。  
  
 呼び出し`SetScrollRange`への呼び出しの直後に、`SetScrollPos`メンバー関数は、設定*bRedraw*で`SetScrollPos`をスクロール バーが 2 回再描画するを防ぐために 0 にします。  
  
 指定された値の差*nMinPos*と*とき*32,767 より大きくはできません。 スクロール バー コントロールの既定の範囲が空 (両方*nMinPos*と*とき*は 0) です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CScrollBar#4](../../mfc/reference/codesnippet/cpp/cscrollbar-class_4.cpp)]  
  
##  <a name="showscrollbar"></a>  CScrollBar::ShowScrollBar  
 スクロール バーの表示と非表示を切り替えます。  
  
```  
void ShowScrollBar(BOOL bShow = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bShow*  
 スクロール バーを表示するか非表示にするかどうかを指定します。 このパラメーターは、する場合**TRUE**、スクロール バーが表示されます。 それ以外の場合は表示されません。  
  
### <a name="remarks"></a>Remarks  
 アプリケーションは、スクロール バーの通知メッセージの処理中に、スクロール バーを非表示にするには、この関数を呼び出さないでください。  
  
### <a name="example"></a>例  
  例を参照して[CScrollBar::Create](#create)です。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CButton クラス](../../mfc/reference/cbutton-class.md)   
 [CComboBox クラス](../../mfc/reference/ccombobox-class.md)   
 [CEdit クラス](../../mfc/reference/cedit-class.md)   
 [CListBox クラス](../../mfc/reference/clistbox-class.md)   
 [CStatic クラス](../../mfc/reference/cstatic-class.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)
