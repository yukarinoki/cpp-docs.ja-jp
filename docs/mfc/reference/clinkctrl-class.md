---
title: CLinkCtrl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CLinkCtrl
- AFXCMN/CLinkCtrl
- AFXCMN/CLinkCtrl::CLinkCtrl
- AFXCMN/CLinkCtrl::Create
- AFXCMN/CLinkCtrl::CreateEx
- AFXCMN/CLinkCtrl::GetIdealHeight
- AFXCMN/CLinkCtrl::GetIdealSize
- AFXCMN/CLinkCtrl::GetItem
- AFXCMN/CLinkCtrl::GetItemID
- AFXCMN/CLinkCtrl::GetItemState
- AFXCMN/CLinkCtrl::GetItemUrl
- AFXCMN/CLinkCtrl::HitTest
- AFXCMN/CLinkCtrl::SetItem
- AFXCMN/CLinkCtrl::SetItemID
- AFXCMN/CLinkCtrl::SetItemState
- AFXCMN/CLinkCtrl::SetItemUrl
dev_langs:
- C++
helpviewer_keywords:
- CLinkCtrl [MFC], CLinkCtrl
- CLinkCtrl [MFC], Create
- CLinkCtrl [MFC], CreateEx
- CLinkCtrl [MFC], GetIdealHeight
- CLinkCtrl [MFC], GetIdealSize
- CLinkCtrl [MFC], GetItem
- CLinkCtrl [MFC], GetItemID
- CLinkCtrl [MFC], GetItemState
- CLinkCtrl [MFC], GetItemUrl
- CLinkCtrl [MFC], HitTest
- CLinkCtrl [MFC], SetItem
- CLinkCtrl [MFC], SetItemID
- CLinkCtrl [MFC], SetItemState
- CLinkCtrl [MFC], SetItemUrl
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a167b228b054a24a812ce5099f396521adda0d08
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43690422"
---
# <a name="clinkctrl-class"></a>CLinkCtrl クラス
Windows コモン SysLink コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CLinkCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CLinkCtrl::CLinkCtrl](#clinkctrl)|`CLinkCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CLinkCtrl::Create](#create)|リンク コントロールを作成し、それにアタッチします、`CLinkCtrl`オブジェクト。|  
|[適用](#createex)|拡張スタイルを使用してリンク コントロールを作成しにアタッチします、`CLinkCtrl`オブジェクト。|  
|[CLinkCtrl::GetIdealHeight](#getidealheight)|リンク コントロールの適切な高さを取得します。|  
|[CLinkCtrl::GetIdealSize](#getidealsize)|リンクの指定した幅に応じて、現在のリンク コントロールのリンク テキストの適切な高さを計算します。|  
|[CLinkCtrl::GetItem](#getitem)|状態とリンク コントロールの項目の属性を取得します。|  
|[CLinkCtrl::GetItemID](#getitemid)|リンク コントロールの項目の ID を取得します。|  
|[CLinkCtrl::GetItemState](#getitemstate)|リンク コントロールの項目の状態を取得します。|  
|[CLinkCtrl::GetItemUrl](#getitemurl)|リンク コントロールの項目で表される URL を取得します。|  
|[CLinkCtrl::HitTest](#hittest)|ユーザーが指定したリンクをクリックするかどうかを判断します。|  
|[CLinkCtrl::SetItem](#setitem)|状態とリンク コントロールの項目の属性を設定します。|  
|[CLinkCtrl::SetItemID](#setitemid)|リンク コントロールの項目の ID を設定します。|  
|[CLinkCtrl::SetItemState](#setitemstate)|リンク コントロールの項目の状態を設定します。|  
|[CLinkCtrl::SetItemUrl](#setitemurl)|リンク コントロールの項目で表される URL を設定します。|  
  
## <a name="remarks"></a>Remarks  
 "リンク コントロール ウィンドウにハイパー テキスト リンクを埋め込むには便利な方法を提供します。 実際のコントロールは、テキストをレンダリングし、ユーザーが埋め込みリンクをクリックすると、適切なアプリケーションを起動するウィンドウです。 複数のリンクは、1 つのコントロール内でサポートし、0 から始まるインデックスを使用してアクセスできます。  
  
 このコントロール (つまり、`CLinkCtrl`クラス) は Windows xp 以降を実行中のプログラムでのみ使用できます。  
  
 詳細については、次を参照してください。 [SysLink コントロール](/windows/desktop/Controls/syslink-overview)Windows SDK に含まれています。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CLinkCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="clinkctrl"></a>  CLinkCtrl::CLinkCtrl  
 `CLinkCtrl` オブジェクトを構築します。  
  
```  
CLinkCtrl();
```  
  
##  <a name="create"></a>  CLinkCtrl::Create  
 リンク コントロールを作成し、それにアタッチします、`CLinkCtrl`オブジェクト。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszLinkMarkup,   
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);

 
virtual BOOL Create(DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszLinkMarkup*  
 表示するテキストをマークされた項目を含む 0 で終わる文字列へのポインター。 詳細については、」のセクション「マークアップとリンク アクセス」を参照してください。 [SysLink コントロールの概要](/windows/desktop/Controls/syslink-overview)します。  
  
 *dwStyle*  
 リンク コントロールのスタイルを指定します。 コントロールのスタイルの任意の組み合わせを適用します。 参照してください[コモン コントロール スタイル](/windows/desktop/Controls/common-control-styles)で、`Windows SDK`詳細についてはします。  
  
 *rect*  
 リンク コントロールのサイズと位置を指定します。 いずれかのことができます、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](../../mfc/reference/rect-structure1.md)構造体。  
  
 *pParentWnd*  
 リンク コントロールの親ウィンドウを指定します。 NULL は指定できません。  
  
 *nID*  
 リンク コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は TRUE。それ以外の場合は FALSE です。  
  
### <a name="remarks"></a>Remarks  
 構築する、 `CLinkCtrl` 2 つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出すし、呼び出して`Create`、リンク コントロールを作成しにアタッチする`CLinkCtrl`オブジェクト。 コントロールで拡張ウィンドウ スタイルを使用する場合は、呼び出す[適用](#createex)の代わりに`Create`します。  
  
 2 番目の形式、`Create`メソッドが非推奨とされます。 指定する最初のフォームを使用して、 *lpszLinkMarkup*パラメーター。  
  
### <a name="example"></a>例  
 次のコード例は、という名前の 2 つの変数を定義します。`m_Link1`と`m_Link2`、2 つのリンク コントロールのアクセスに使用します。  
  
 [!code-cpp[NVC_MFC_CLinkCtrl_s1#2](../../mfc/reference/codesnippet/cpp/clinkctrl-class_1.h)]  
  
### <a name="example"></a>例  
 次のコード例では、別のリンク コントロールの場所に基づき、1 つのリンク コントロールを作成します。 リソース ローダーは、アプリケーションの起動時に最初のリンク コントロールを作成します。 アプリケーションでは、OnInitDialog メソッドに入ると、最初のリンク コントロールの位置を基準とした 2 つ目のリンク コントロールを作成します。 表示されるテキストに合わせて 2 つ目のリンク コントロールがサイズ変更します。  
  
 [!code-cpp[NVC_MFC_CLinkCtrl_s1#1](../../mfc/reference/codesnippet/cpp/clinkctrl-class_2.cpp)]  
  
##  <a name="createex"></a>  適用  
 拡張スタイルを使用してリンク コントロールを作成しにアタッチします、`CLinkCtrl`オブジェクト。  
  
```  
virtual BOOL CreateEx(
    LPCTSTR lpszLinkMarkup,   
    DWORD dwExStyle,  
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);

 
virtual BOOL CreateEx(DWORD  dwExStyle,
    DWORD  dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT  nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszLinkMarkup*  
 表示するテキストをマークされた項目を含む 0 で終わる文字列へのポインター。 詳細については、」のセクション「マークアップとリンク アクセス」を参照してください。 [SysLink コントロールの概要](/windows/desktop/Controls/syslink-overview)します。  
  
 *dwExStyle*  
 リンク コントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧は、次を参照してください。、 *dwExStyle*パラメーターを[CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK に含まれています。  
  
 *dwStyle*  
 リンク コントロールのスタイルを指定します。 コントロールのスタイルの任意の組み合わせを適用します。 詳細については、次を参照してください。[コモン コントロール スタイル](/windows/desktop/Controls/common-control-styles)Windows SDK に含まれています。  
  
 *rect*  
 リンク コントロールのサイズと位置を指定します。 いずれかのことができます、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](../../mfc/reference/rect-structure1.md)構造体。  
  
 *pParentWnd*  
 リンク コントロールの親ウィンドウを指定します。 NULL は指定できません。  
  
 *nID*  
 リンク コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は TRUE。それ以外の場合は FALSE です。  
  
### <a name="remarks"></a>Remarks  
 使用`CreateEx`の代わりに[作成](#create)拡張 Windows スタイルの定数を適用します。  
  
 2 番目の形式、`CreateEx`メソッドが非推奨とされます。 指定する最初のフォームを使用して、 *lpszLinkMarkup*パラメーター。  
  
##  <a name="getidealheight"></a>  CLinkCtrl::GetIdealHeight  
 リンク コントロールの適切な高さを取得します。  
  
```  
int GetIdealHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ピクセル単位で、コントロールの適切な高さ。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装[LM_GETIDEALHEIGHT](/windows/desktop/Controls/lm-getidealheight)」の説明に従って、Windows SDK。  
  
##  <a name="getidealsize"></a>  CLinkCtrl::GetIdealSize  
 リンクの指定した幅に応じて、現在のリンク コントロールのリンク テキストの適切な高さを計算します。  
  
```  
int GetIdealSize(
    int cxMaxWidth,   
    SIZE* pSize) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*cxMaxWidth*|ピクセル単位で、リンクの最大の幅。|  
|[out]\* *pSize*|Windows へのポインター[サイズ](https://msdn.microsoft.com/library/windows/desktop/dd145106)構造体。 このメソッドが戻るとき、 *cy*のメンバー、`SIZE`構造で指定されているリンクのテキスト幅の理想的なリンクのテキストの高さに含まれる*cxMaxWidth*します。 *Cx*構造体のメンバーには、実際に必要なリンクのテキストの幅が含まれています。|  
  
### <a name="return-value"></a>戻り値  
 ピクセル単位で、リンク テキストの適切な高さ。 戻り値は、の値として同じ、 *cy*のメンバー、`SIZE`構造体。  
  
### <a name="remarks"></a>Remarks  
 例については、`GetIdealSize`メソッド例を参照してください。 [CLinkCtrl::Create](#create)します。  
  
 このメソッドは、送信、 [LM_GETIDEALSIZE](/windows/desktop/Controls/lm-getidealsize)メッセージは、Windows SDK で説明します。  
  
##  <a name="getitem"></a>  CLinkCtrl::GetItem  
 状態とリンク コントロールの項目の属性を取得します。  
  
```  
BOOL GetItem(PLITEM pItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pItem*  
 ポインターを[LITEM](/windows/desktop/api/commctrl/ns-commctrl-taglitem)項目情報を受け取る構造体。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、true を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装[LM_GETITEM](/windows/desktop/Controls/lm-getitem)」の説明に従って、Windows SDK。  
  
##  <a name="getitemid"></a>  CLinkCtrl::GetItemID  
 リンク コントロールの項目の ID を取得します。  
  
```  
BOOL GetItemID(
    int iLink,  
    CString& strID) const;  
  
BOOL GetItemID(
    int iLink,  
    LPWSTR szID,  
    UINT cchID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *iLink*  
 リンク コントロールの項目のインデックス。  
  
 *strID*  
 A [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)指定した項目の ID を表すオブジェクト。  
  
 *szID*  
 指定した項目の ID を含む null で終わる文字列。  
  
 *cchID*  
 文字のサイズ、 *szID*バッファー。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、true を返します。  
  
> [!NOTE]
>  この関数は、場合も FALSE を返しますのバッファー *szID または strID* MAX_LINKID_TEXT 未満です。  
  
### <a name="remarks"></a>Remarks  
 特定のリンク コントロールの項目の ID を取得します。 詳細については、Win32 メッセージを参照してください。 [LM_GETITEM](/windows/desktop/Controls/lm-getitem) Windows SDK に含まれています。  
  
##  <a name="getitemstate"></a>  CLinkCtrl::GetItemState  
 リンク コントロールの項目の状態を取得します。  
  
```  
BOOL GetItemState(
    int iLink,  
    UINT* pnState,  
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *iLink*  
 リンク コントロールの項目のインデックス。  
  
 *pnState*  
 指定した状態の項目の値。  
  
 *対象*  
 取得するには、どの状態項目を記述するフラグの組み合わせ。 値の一覧は、の説明を参照して、`state`内のメンバー、 [LITEM](/windows/desktop/api/commctrl/ns-commctrl-taglitem)構造体。 使用可能な項目はで許可されているものとまったく同じ`state`します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、true を返します。  
  
### <a name="remarks"></a>Remarks  
 特定のリンク コントロールの項目の指定した状態の項目の値を取得します。 詳細については、Win32 メッセージを参照してください。 [LM_GETITEM](/windows/desktop/Controls/lm-getitem) Windows SDK に含まれています。  
  
##  <a name="getitemurl"></a>  CLinkCtrl::GetItemUrl  
 リンク コントロールの項目で表される URL を取得します。  
  
```  
BOOL GetItemUrl(
    int iLink,  
    CString& strUrl) const;  
  
BOOL GetItemUrl(
    int iLink,  
    LPWSTR szUrl,  
    UINT cchUrl) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *iLink*  
 リンク コントロールの項目のインデックス。  
  
 *strUrl*  
 A [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトの指定した項目によって表される URL を含む  
  
 *szUrl*  
 指定した項目によって表される URL を含む null で終わる文字列  
  
 *cchUrl*  
 文字のサイズ、 *szURL*バッファー。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、true を返します。  
  
> [!NOTE]
>  この関数は、場合も FALSE を返しますのバッファー *szUrl または strUrl* MAX_LINKID_TEXT 未満です。  
  
### <a name="remarks"></a>Remarks  
 指定したリンク コントロールの項目で表される URL を取得します。 詳細については、Win32 メッセージを参照してください。 [LM_GETITEM](/windows/desktop/Controls/lm-getitem) Windows SDK に含まれています。  
  
##  <a name="hittest"></a>  CLinkCtrl::HitTest  
 ユーザーが指定したリンクをクリックしたかどうかを決定します。  
  
```  
BOOL HitTest(PLHITTESTINFO phti) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *phti*  
 ポインター、`LHITTESTINFO`ユーザーがクリックされたリンクに関する情報を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、true を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装[LM_HITTEST](/windows/desktop/Controls/lm-hittest)」の説明に従って、Windows SDK。  
  
##  <a name="setitem"></a>  CLinkCtrl::SetItem  
 状態とリンク コントロールの項目の属性を設定します。  
  
```  
BOOL SetItem(PLITEM pItem);
```  
  
### <a name="parameters"></a>パラメーター  
 *pItem*  
 ポインターを[LITEM](/windows/desktop/api/commctrl/ns-commctrl-taglitem)設定情報を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、true を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装[LM_SETITEM](/windows/desktop/Controls/lm-setitem)」の説明に従って、Windows SDK。  
  
##  <a name="setitemid"></a>  CLinkCtrl::SetItemID  
 リンク コントロールの項目の ID を取得します。  
  
```  
BOOL SetItemID(
    int iLink,  
    LPCWSTR szID);
```  
  
### <a name="parameters"></a>パラメーター  
 *iLink*  
 リンク コントロールの項目のインデックス。  
  
 *szID*  
 指定した項目の ID を含む null で終わる文字列。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、true を返します。  
  
### <a name="remarks"></a>Remarks  
 特定のリンク コントロールの項目の ID を設定します。 詳細については、Win32 メッセージを参照してください。 [LM_SETITEM](/windows/desktop/Controls/lm-setitem) Windows SDK に含まれています。  
  
##  <a name="setitemstate"></a>  CLinkCtrl::SetItemState  
 リンク コントロールの項目の状態を取得します。  
  
```  
BOOL SetItemState(
    int iLink,  
    UINT state,  
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED);
```  
  
### <a name="parameters"></a>パラメーター  
 *iLink*  
 リンク コントロールの項目のインデックス。  
  
 *pnState*  
 設定されている指定された状態の項目の値。  
  
 *対象*  
 設定されている状態の項目を記述するフラグの組み合わせ。 値の一覧は、の説明を参照して、`state`内のメンバー、 [LITEM](/windows/desktop/api/commctrl/ns-commctrl-taglitem)構造体。 使用可能な項目はで許可されているものとまったく同じ`state`します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、true を返します。  
  
### <a name="remarks"></a>Remarks  
 特定のリンク コントロールの項目の指定した状態の項目の値を設定します。 詳細については、Win32 メッセージを参照してください。 [LM_SETITEM](/windows/desktop/Controls/lm-setitem) Windows SDK に含まれています。  
  
##  <a name="setitemurl"></a>  CLinkCtrl::SetItemUrl  
 リンク コントロールの項目で表される URL を設定します。  
  
```  
BOOL SetItemUrl(
    int iLink,  
    LPCWSTR szUrl);
```  
  
### <a name="parameters"></a>パラメーター  
 *iLink*  
 リンク コントロールの項目のインデックス。  
  
 *szUrl*  
 指定した項目によって表される URL を含む null で終わる文字列  
  
### <a name="return-value"></a>戻り値  
 成功した場合、true を返します。  
  
### <a name="remarks"></a>Remarks  
 指定したリンク コントロールの項目で表される URL を設定します。 詳細については、Win32 メッセージを参照してください。 [LM_SETITEM](/windows/desktop/Controls/lm-setitem) Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)
