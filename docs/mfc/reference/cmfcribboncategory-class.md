---
title: CMFCRibbonCategory クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonCategory
- AFXRIBBONCATEGORY/CMFCRibbonCategory
- AFXRIBBONCATEGORY/CMFCRibbonCategory::CMFCRibbonCategory
- AFXRIBBONCATEGORY/CMFCRibbonCategory::AddHidden
- AFXRIBBONCATEGORY/CMFCRibbonCategory::AddPanel
- AFXRIBBONCATEGORY/CMFCRibbonCategory::CopyFrom
- AFXRIBBONCATEGORY/CMFCRibbonCategory::FindByData
- AFXRIBBONCATEGORY/CMFCRibbonCategory::FindByID
- AFXRIBBONCATEGORY/CMFCRibbonCategory::FindPanelWithElem
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetContextID
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetData
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetDroppedDown
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetElements
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetElementsByID
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetFirstVisibleElement
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetFocused
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetHighlighted
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetImageCount
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetImageSize
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetItemIDsList
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetLastVisibleElement
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetLargeImages
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetMaxHeight
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetName
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetPanel
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetPanelCount
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetPanelFromPoint
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetPanelIndex
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetParentButton
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetParentMenuBar
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetParentRibbonBar
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetRect
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetSmallImages
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetTabColor
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetTabRect
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetTextTopLine
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetVisibleElements
- AFXRIBBONCATEGORY/CMFCRibbonCategory::HighlightPanel
- AFXRIBBONCATEGORY/CMFCRibbonCategory::HitTest
- AFXRIBBONCATEGORY/CMFCRibbonCategory::HitTestEx
- AFXRIBBONCATEGORY/CMFCRibbonCategory::HitTestScrollButtons
- AFXRIBBONCATEGORY/CMFCRibbonCategory::IsActive
- AFXRIBBONCATEGORY/CMFCRibbonCategory::IsVisible
- AFXRIBBONCATEGORY/CMFCRibbonCategory::IsWindows7Look
- AFXRIBBONCATEGORY/CMFCRibbonCategory::NotifyControlCommand
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnCancelMode
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnDraw
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnDrawImage
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnDrawMenuBorder
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnKey
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnLButtonDown
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnLButtonUp
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnMouseMove
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnRTLChanged
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnScrollHorz
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnUpdateCmdUI
- AFXRIBBONCATEGORY/CMFCRibbonCategory::RecalcLayout
- AFXRIBBONCATEGORY/CMFCRibbonCategory::RemovePanel
- AFXRIBBONCATEGORY/CMFCRibbonCategory::ReposPanels
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetCollapseOrder
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetData
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetKeys
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetName
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetTabColor
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCategory [MFC], CMFCRibbonCategory
- CMFCRibbonCategory [MFC], AddHidden
- CMFCRibbonCategory [MFC], AddPanel
- CMFCRibbonCategory [MFC], CopyFrom
- CMFCRibbonCategory [MFC], FindByData
- CMFCRibbonCategory [MFC], FindByID
- CMFCRibbonCategory [MFC], FindPanelWithElem
- CMFCRibbonCategory [MFC], GetContextID
- CMFCRibbonCategory [MFC], GetData
- CMFCRibbonCategory [MFC], GetDroppedDown
- CMFCRibbonCategory [MFC], GetElements
- CMFCRibbonCategory [MFC], GetElementsByID
- CMFCRibbonCategory [MFC], GetFirstVisibleElement
- CMFCRibbonCategory [MFC], GetFocused
- CMFCRibbonCategory [MFC], GetHighlighted
- CMFCRibbonCategory [MFC], GetImageCount
- CMFCRibbonCategory [MFC], GetImageSize
- CMFCRibbonCategory [MFC], GetItemIDsList
- CMFCRibbonCategory [MFC], GetLastVisibleElement
- CMFCRibbonCategory [MFC], GetLargeImages
- CMFCRibbonCategory [MFC], GetMaxHeight
- CMFCRibbonCategory [MFC], GetName
- CMFCRibbonCategory [MFC], GetPanel
- CMFCRibbonCategory [MFC], GetPanelCount
- CMFCRibbonCategory [MFC], GetPanelFromPoint
- CMFCRibbonCategory [MFC], GetPanelIndex
- CMFCRibbonCategory [MFC], GetParentButton
- CMFCRibbonCategory [MFC], GetParentMenuBar
- CMFCRibbonCategory [MFC], GetParentRibbonBar
- CMFCRibbonCategory [MFC], GetRect
- CMFCRibbonCategory [MFC], GetSmallImages
- CMFCRibbonCategory [MFC], GetTabColor
- CMFCRibbonCategory [MFC], GetTabRect
- CMFCRibbonCategory [MFC], GetTextTopLine
- CMFCRibbonCategory [MFC], GetVisibleElements
- CMFCRibbonCategory [MFC], HighlightPanel
- CMFCRibbonCategory [MFC], HitTest
- CMFCRibbonCategory [MFC], HitTestEx
- CMFCRibbonCategory [MFC], HitTestScrollButtons
- CMFCRibbonCategory [MFC], IsActive
- CMFCRibbonCategory [MFC], IsVisible
- CMFCRibbonCategory [MFC], IsWindows7Look
- CMFCRibbonCategory [MFC], NotifyControlCommand
- CMFCRibbonCategory [MFC], OnCancelMode
- CMFCRibbonCategory [MFC], OnDraw
- CMFCRibbonCategory [MFC], OnDrawImage
- CMFCRibbonCategory [MFC], OnDrawMenuBorder
- CMFCRibbonCategory [MFC], OnKey
- CMFCRibbonCategory [MFC], OnLButtonDown
- CMFCRibbonCategory [MFC], OnLButtonUp
- CMFCRibbonCategory [MFC], OnMouseMove
- CMFCRibbonCategory [MFC], OnRTLChanged
- CMFCRibbonCategory [MFC], OnScrollHorz
- CMFCRibbonCategory [MFC], OnUpdateCmdUI
- CMFCRibbonCategory [MFC], RecalcLayout
- CMFCRibbonCategory [MFC], RemovePanel
- CMFCRibbonCategory [MFC], ReposPanels
- CMFCRibbonCategory [MFC], SetCollapseOrder
- CMFCRibbonCategory [MFC], SetData
- CMFCRibbonCategory [MFC], SetKeys
- CMFCRibbonCategory [MFC], SetName
- CMFCRibbonCategory [MFC], SetTabColor
ms.assetid: 99ba25b6-d060-4fdd-bfab-3c46c22981bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44caf81fd73567e9c206bdfe62869f5fc145fd33
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039107"
---
# <a name="cmfcribboncategory-class"></a>CMFCRibbonCategory クラス
`CMFCRibbonCategory`クラスのグループを含むリボン タブ[リボン パネル](../../mfc/reference/cmfcribbonpanel-class.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonCategory : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonCategory::CMFCRibbonCategory](#cmfcribboncategory)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonCategory::AddHidden](#addhidden)|リボン カテゴリを非表示の要素を追加します。|  
|[CMFCRibbonCategory::AddPanel](#addpanel)|リボン カテゴリを新しいパネルを追加します。|  
|[CMFCRibbonCategory::CopyFrom](#copyfrom)||  
|[CMFCRibbonCategory::FindByData](#findbydata)||  
|[CMFCRibbonCategory::FindByID](#findbyid)||  
|[CMFCRibbonCategory::FindPanelWithElem](#findpanelwithelem)||  
|[CMFCRibbonCategory::GetContextID](#getcontextid)|リボン カテゴリのコンテキスト ID を返します。|  
|[CMFCRibbonCategory::GetData](#getdata)|リボン カテゴリに関連付けられているユーザー定義データを返します。|  
|[CMFCRibbonCategory::GetDroppedDown](#getdroppeddown)||  
|[CMFCRibbonCategory::GetElements](#getelements)||  
|[CMFCRibbonCategory::GetElementsByID](#getelementsbyid)||  
|[CMFCRibbonCategory::GetFirstVisibleElement](#getfirstvisibleelement)|リボン カテゴリに属している最初の可視要素を取得します。|  
|[CMFCRibbonCategory::GetFocused](#getfocused)|フォーカスされた要素を返します。|  
|[CMFCRibbonCategory::GetHighlighted](#gethighlighted)|強調表示された要素を返します。|  
|[CMFCRibbonCategory::GetImageCount](#getimagecount)||  
|[CMFCRibbonCategory::GetImageSize](#getimagesize)||  
|[CMFCRibbonCategory::GetItemIDsList](#getitemidslist)||  
|[CMFCRibbonCategory::GetLastVisibleElement](#getlastvisibleelement)|リボン カテゴリに属している最後の可視要素を取得します。|  
|[CMFCRibbonCategory::GetLargeImages](#getlargeimages)|リボン カテゴリを使用する大きいイメージのリストへの参照を返します。|  
|[CMFCRibbonCategory::GetMaxHeight](#getmaxheight)||  
|[CMFCRibbonCategory::GetName](#getname)||  
|[CMFCRibbonCategory::GetPanel](#getpanel)|指定したインデックス位置にあるリボン パネルへのポインターを返します。|  
|[CMFCRibbonCategory::GetPanelCount](#getpanelcount)|リボン カテゴリには、リボン パネルの数を返します。|  
|[CMFCRibbonCategory::GetPanelFromPoint](#getpanelfrompoint)||  
|[CMFCRibbonCategory::GetPanelIndex](#getpanelindex)|指定されたリボン パネルのインデックスを返します。|  
|[CMFCRibbonCategory::GetParentButton](#getparentbutton)||  
|[CMFCRibbonCategory::GetParentMenuBar](#getparentmenubar)||  
|[CMFCRibbonCategory::GetParentRibbonBar](#getparentribbonbar)||  
|[CMFCRibbonCategory::GetRect](#getrect)||  
|[CMFCRibbonCategory::GetSmallImages](#getsmallimages)|カテゴリで使用される小さいイメージのリストへの参照を返します。|  
|[CMFCRibbonCategory::GetTabColor](#gettabcolor)|リボンのカテゴリ タブの現在の色を返します。|  
|[CMFCRibbonCategory::GetTabRect](#gettabrect)||  
|[CMFCRibbonCategory::GetTextTopLine](#gettexttopline)||  
|[CMFCRibbonCategory::GetVisibleElements](#getvisibleelements)|リボン カテゴリに属しているすべての可視要素を取得します。|  
|[CMFCRibbonCategory::HighlightPanel](#highlightpanel)||  
|[CMFCRibbonCategory::HitTest](#hittest)||  
|[CMFCRibbonCategory::HitTestEx](#hittestex)||  
|[CMFCRibbonCategory::HitTestScrollButtons](#hittestscrollbuttons)||  
|[CMFCRibbonCategory::IsActive](#isactive)||  
|[CMFCRibbonCategory::IsVisible](#isvisible)|リボン カテゴリを表示するかどうかを決定します。|  
|[CMFCRibbonCategory::IsWindows7Look](#iswindows7look)|親のリボンに外観が Windows 7 スタイル (小さな四角形のアプリケーション ボタン) があるかどうかを示します|  
|[CMFCRibbonCategory::NotifyControlCommand](#notifycontrolcommand)||  
|[CMFCRibbonCategory::OnCancelMode](#oncancelmode)||  
|[CMFCRibbonCategory::OnDraw](#ondraw)||  
|[CMFCRibbonCategory::OnDrawImage](#ondrawimage)||  
|[CMFCRibbonCategory::OnDrawMenuBorder](#ondrawmenuborder)||  
|[CMFCRibbonCategory::OnKey](#onkey)|ユーザーがキーボード ボタンを押したときに、フレームワークによって呼び出されます。|  
|[CMFCRibbonCategory::OnLButtonDown](#onlbuttondown)||  
|[CMFCRibbonCategory::OnLButtonUp](#onlbuttonup)||  
|[CMFCRibbonCategory::OnMouseMove](#onmousemove)||  
|[CMFCRibbonCategory::OnRTLChanged](#onrtlchanged)||  
|[CMFCRibbonCategory::OnScrollHorz](#onscrollhorz)||  
|[CMFCRibbonCategory::OnUpdateCmdUI](#onupdatecmdui)||  
|[CMFCRibbonCategory::RecalcLayout](#recalclayout)||  
|[CMFCRibbonCategory::RemovePanel](#removepanel)||  
|[CMFCRibbonCategory::ReposPanels](#repospanels)||  
|[CMFCRibbonCategory::SetCollapseOrder](#setcollapseorder)|リボン カテゴリ内にあるリボン パネルの折りたたみ順序を定義します。|  
|[CMFCRibbonCategory::SetData](#setdata)|リボン カテゴリには、ユーザー定義データを格納します。|  
|[CMFCRibbonCategory::SetKeys](#setkeys)|Keytip をリボン カテゴリに割り当てます。|  
|[CMFCRibbonCategory::SetName](#setname)||  
|[Cmfcribboncategory::settabcolor](#settabcolor)|リボン カテゴリの色を設定します。|  
  
## <a name="remarks"></a>Remarks  
 通常、カテゴリを作成していないリボン直接呼び出すことによって[CMFCRibbonBar::AddCategory](../../mfc/reference/cmfcribbonbar-class.md#addcategory)、新しく作成されたリボン カテゴリへのポインターが返されます。 呼び出してパネルをカテゴリに追加する[CMFCRibbonCategory::AddPanel](#addpanel)です。  
  
 `CMFCRibbonTab`クラスがリボン カテゴリを描画します。 派生[CMFCRibbonBaseElement クラス](../../mfc/reference/cmfcribbonbaseelement-class.md)です。  
  
 次の例では、リボン カテゴリを作成し、パネルを追加する方法を示します。  
  
 `// Create a new ribbon category and get a pointer to it`  
  
 `CMFCRibbonCategory* pCategory = m_wndRibbonBar.AddCategory`  
  
 `(_T("&Write"),           // Category name`  
  
 `IDB_WRITE,              // Category small images (16 x 16)`  
  
 `IDB_WRITE_LARGE);   // Category large images (32 x 32)`  
  
 `// Add a panel to the new category`  
  
 `CMFCRibbonPanel* pPanel = pCategory->AddPanel (`  
  
 `_T("Clipboard"),                       // Panel name`  
  
 `m_PanelIcons.ExtractIcon (0));  // Panel icon`  
  
 次の図は、RibbonApp サンプル アプリケーションから [Home] カテゴリの図を示します。  
  
 ![CMFCRibbonCategory イメージ](../../mfc/reference/media/cmfcribboncategory.png "cmfcribboncategory")  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCRibbonCategory`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxribboncategory.h  
  
##  <a name="addhidden"></a>  CMFCRibbonCategory::AddHidden  
 [カスタマイズ] ダイアログ ボックスに表示されるリボン要素の配列に指定されたリボン要素を追加します。  
  
```  
void AddHidden(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pElem*  
 リボン要素へのポインター。  
  
### <a name="remarks"></a>Remarks  
 [カスタマイズ] ダイアログ ボックスのリボン要素は、クイック アクセス ツールバーに追加できるコマンドです。  
  
##  <a name="addpanel"></a>  CMFCRibbonCategory::AddPanel  
 リボン カテゴリをリボン パネルを作成します。  
  
```  
CMFCRibbonPanel* AddPanel(
    LPCTSTR lpszPanelName,  
    HICON hIcon = 0,  
    CRuntimeClass* pRTI = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszPanelName*  
 新しいリボン パネルの名前へのポインター。  
  
 [in]*hIcon*  
 新しいリボン パネルの既定のアイコンへのハンドルします。  
  
 [in]*pRTI*  
 カスタム リボン パネルのランタイム クラス情報へのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、新しいリボン パネルへのポインターそれ以外の場合`NULL`パネルが作成されていない場合。  
  
### <a name="remarks"></a>Remarks  
 カスタム リボン パネルを作成する場合は、ランタイム クラス情報を指定する必要があります*pRTI*です。 カスタム リボン パネル クラスから派生する必要があります、`CMFCRibbonPanel`クラスです。  
  
 リボン要素を表示する十分な空き領域がある場合は、リボン パネルの既定のアイコンが表示されます。  
  
### <a name="example"></a>例  
 次の例で使用する方法、`AddPanel`メソッドで、`CMFCRibbonCategory`クラスです。  
  
 [!code-cpp[NVC_MFC_RibbonApp#10](../../mfc/reference/codesnippet/cpp/cmfcribboncategory-class_1.cpp)]  
  
##  <a name="cmfcribboncategory"></a>  CMFCRibbonCategory::CMFCRibbonCategory  
 構築して初期化、 [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md)オブジェクト。  
  
```  
CMFCRibbonCategory(
    CMFCRibbonBar* pParenrRibbonBar,  
    LPCTSTR lpszName,  
    UINT uiSmallImagesResID,  
    UINT uiLargeImagesResID,  
    CSize sizeSmallImage = CSize(16,
    16),  
    CSize sizeLargeImage = CSize(32,
    32));
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pParenrRibbonBar*  
 リボン カテゴリの親リボン バーへのポインター。  
  
 [in]*lpszName*  
 リボン カテゴリの名前です。  
  
 [in]*uiSmallImagesResID*  
 リボン カテゴリ内のリボン要素で使用される小さいイメージのイメージ リストのリソース ID です。  
  
 [in]*uiLargeImagesResID*  
 リボン カテゴリ内のリボン要素によって使用されているサイズの大きなイメージのイメージ リストのリソース ID です。  
  
 [in]*sizeSmallImage*  
 既定のリボン カテゴリ内のリボン要素の小さいイメージのサイズ。  
  
 [in]*sizeLargeImage*  
 既定のリボン カテゴリ内のリボン要素の大きいイメージのサイズ。  
  
##  <a name="copyfrom"></a>  CMFCRibbonCategory::CopyFrom  
 指定した状態をコピー [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md)現在[CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md)オブジェクト。  
  
```  
virtual void CopyFrom(CMFCRibbonCategory& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*src*  
 ソース `CMFCRibbonCategory` オブジェクト。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="findbydata"></a>  CMFCRibbonCategory::FindByData  
 指定されたデータに関連付けられているリボン要素を取得します。  
  
```  
CMFCRibbonBaseElement* FindByData(
    DWORD_PTR dwData,  
    BOOL bVisibleOnly = TRUE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*dwData*  
 リボン要素に関連付けられたデータ。  
  
 [in]*bVisibleOnly*  
 `TRUE` 検索にすばやくアクセスできるリボン要素を含める`FALSE`検索にすばやくアクセスできるリボン要素を除外します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、リボン要素へのポインターそれ以外の場合`NULL`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="findbyid"></a>  CMFCRibbonCategory::FindByID  
 指定されたコマンド ID に関連付けられているリボン要素を取得します。  
  
```  
CMFCRibbonBaseElement* FindByID(
    UINT uiCmdID,  
    BOOL bVisibleOnly = TRUE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiCmdID*  
 リボン要素に関連付けられているコマンド ID。  
  
 [in]*bVisibleOnly*  
 `TRUE` 検索にすばやくアクセスできるリボン要素を含める`FALSE`検索にすばやくアクセスできるリボン要素を除外します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、リボン要素へのポインターそれ以外の場合`NULL`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="findpanelwithelem"></a>  CMFCRibbonCategory::FindPanelWithElem  
 指定されたリボン要素を含むリボン パネルを取得します。  
  
```  
CMFCRibbonPanel* FindPanelWithElem(const CMFCRibbonBaseElement* pElement);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pElement*  
 リボン要素へのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、リボン パネルへのポインターそれ以外の場合`NULL`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getcontextid"></a>  CMFCRibbonCategory::GetContextID  
 リボン カテゴリのコンテキスト ID を取得します。  
  
```  
UINT GetContextID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リボン カテゴリのコンテキスト ID です。  
  
### <a name="remarks"></a>Remarks  
 リボン カテゴリは、コンテキスト リボン カテゴリではない場合、コンテキスト ID は 0 です。  
  
##  <a name="getdata"></a>  CMFCRibbonCategory::GetData  
 リボン カテゴリに関連付けられているユーザー定義データを取得します。  
  
```  
DWORD_PTR GetData() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リボン カテゴリに関連付けられているユーザー定義データ。  
  
##  <a name="getdroppeddown"></a>  CMFCRibbonCategory::GetDroppedDown  
 ポップアップ メニューが表示されているリボン要素へのポインターを取得します。  
  
```  
CMFCRibbonBaseElement* GetDroppedDown();
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、リボン要素へのポインターそれ以外の場合`NULL`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getelements"></a>  CMFCRibbonCategory::GetElements  
 リボン カテゴリ内のすべてのリボン要素を取得します。  
  
```  
void GetElements(
    CArray <CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力].*arElements*  
 参照、 [CArray](../../mfc/reference/carray-class.md)リボン要素のです。  
  
### <a name="remarks"></a>Remarks  
 配列には、クイック アクセス ツールバーで使用するよう設計されているリボン要素が含まれています。  
  
##  <a name="getelementsbyid"></a>  CMFCRibbonCategory::GetElementsByID  
 指定されたコマンド ID に関連付けられているすべてのリボン要素を取得します。  
  
```  
void GetElementsByID(
    UINT uiCmdID,  
    CArray <CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiCmdID*  
 リボン要素に関連付けられているコマンド ID。  
  
 [入力、出力].*arElements*  
 参照、 [CArray](../../mfc/reference/carray-class.md)リボン要素のです。  
  
### <a name="remarks"></a>Remarks  
 配列には、クイック アクセス ツールバーで使用するよう設計されているリボン要素が含まれています。  
  
##  <a name="getfirstvisibleelement"></a>  CMFCRibbonCategory::GetFirstVisibleElement  
 リボン カテゴリに属している最初の可視要素を取得します。  
  
```  
CMFCRibbonBaseElement* GetFirstVisibleElement() const;  
```  
  
### <a name="return-value"></a>戻り値  
 最初の可視要素へのポインターあります`NULL`カテゴリに表示されている要素があるない場合。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getfocused"></a>  CMFCRibbonCategory::GetFocused  
 フォーカスされた要素を返します。  
  
```  
CMFCRibbonBaseElement* GetFocused();
```  
  
### <a name="return-value"></a>戻り値  
 フォーカスのある要素へのポインターまたは`NULL`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="gethighlighted"></a>  CMFCRibbonCategory::GetHighlighted  
 強調表示された要素を返します。  
  
```  
CMFCRibbonBaseElement* GetHighlighted();
```  
  
### <a name="return-value"></a>戻り値  
 強調表示されている要素へのポインターまたは`NULL`要素が強調表示されていない場合。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getimagecount"></a>  CMFCRibbonCategory::GetImageCount  
 リボン カテゴリに含まれている指定されたイメージ リスト内のイメージの数を取得します。  
  
```  
int GetImageCount(BOOL bIsLargeImage) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bIsLargeImage*  
 `TRUE` 大きいイメージ リスト内のイメージの数`FALSE`小さいイメージ リスト内のイメージの数。  
  
### <a name="return-value"></a>戻り値  
 指定したイメージ リスト内のイメージの数。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getimagesize"></a>  CMFCRibbonCategory::GetImageSize  
 リボン カテゴリに含まれている指定されたイメージ リスト内のイメージのサイズを取得します。  
  
```  
CSize GetImageSize(BOOL bIsLargeImage) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bIsLargeImage*  
 `TRUE` 大きなイメージのサイズ`FALSE`小さいイメージのサイズ。  
  
### <a name="return-value"></a>戻り値  
 指定したイメージ リスト内のイメージのサイズ。  
  
### <a name="remarks"></a>Remarks  
 取得したサイズには、グローバルのイメージ スケール係数が含まれます。  
  
##  <a name="getitemidslist"></a>  CMFCRibbonCategory::GetItemIDsList  
 リボン カテゴリに含まれているリボン要素のコマンド Id を取得します。  
  
```  
void GetItemIDsList(
    CList<UINT, UINT>& lstItems,  
    BOOL bHiddenOnly = FALSE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*lstItems*  
 リボン カテゴリ内のリボン要素のコマンド Id の一覧。  
  
 [in]*bHiddenOnly*  
 `TRUE` リボン カテゴリ内のリボン パネルに表示されるリボン要素を除外するには`FALSE`リボン カテゴリにすべてのリボン要素を含める。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getlargeimages"></a>  CMFCRibbonCategory::GetLargeImages  
 リボン カテゴリに含まれている大きいイメージの一覧を取得します。  
  
```  
CMFCToolBarImages& GetLargeImages();
```  
  
### <a name="return-value"></a>戻り値  
 リボン カテゴリに含まれている大きいイメージの一覧です。  
  
##  <a name="getlastvisibleelement"></a>  CMFCRibbonCategory::GetLastVisibleElement  
 リボン カテゴリに属している最後の可視要素を取得します。  
  
```  
CMFCRibbonBaseElement* GetLastVisibleElement() const;  
```  
  
### <a name="return-value"></a>戻り値  
 最後の可視要素へのポインターあります`NULL`カテゴリに表示されている要素がない場合。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getmaxheight"></a>  CMFCRibbonCategory::GetMaxHeight  
 リボン カテゴリに含まれているリボン パネルの最大の高さを取得します。  
  
```  
int GetMaxHeight(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 リボン パネル用のデバイス コンテキストへのポインター。  
  
### <a name="return-value"></a>戻り値  
 リボン カテゴリに含まれているリボン パネルの最大の高さ。  
  
### <a name="remarks"></a>Remarks  
 取得した値には、リボン パネルの上部と下部の余白の高さが含まれています。  
  
##  <a name="getname"></a>  CMFCRibbonCategory::GetName  
 リボン カテゴリの名前を取得します。  
  
```  
LPCTSTR GetName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リボン カテゴリの名前。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getpanel"></a>  CMFCRibbonCategory::GetPanel  
 指定したインデックス位置にあるリボン パネルへのポインターを返します。  
  
```  
CMFCRibbonPanel* GetPanel(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nIndex*  
 リボン パネルの 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定したインデックス位置にあるリボン パネルへのポインター。  
  
### <a name="remarks"></a>Remarks  
 場合、例外がスローされます*nIndex*が範囲外です。  
  
##  <a name="getpanelcount"></a>  CMFCRibbonCategory::GetPanelCount  
 リボン カテゴリには、リボン パネルの数を返します。  
  
```  
int GetPanelCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リボン カテゴリ内のリボン パネルの数。  
  
##  <a name="getpanelfrompoint"></a>  CMFCRibbonCategory::GetPanelFromPoint  
 指定したポイントが含まれる場合は、リボン パネルへのポインターを取得します。  
  
```  
CMFCRibbonPanel* GetPanelFromPoint(CPoint point) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ポイント*  
 ウィンドウの左上隅に対して相対的で、ポインターの x 座標と y を調整します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、リボン パネルへのポインターそれ以外の場合`NULL`です。  
  
### <a name="remarks"></a>Remarks  
 リボン カテゴリに含まれているリボン パネルのみがテストされます。  
  
##  <a name="getpanelindex"></a>  CMFCRibbonCategory::GetPanelIndex  
 指定されたリボン パネルの 0 から始まるインデックスを取得します。  
  
```  
int GetPanelIndex(const CMFCRibbonPanel* pPanel) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pPanel*  
 リボン パネルへのポインター。  
  
### <a name="return-value"></a>戻り値  
 指定されたリボン パネル、メソッドが成功した場合の 0 から始まるインデックスそれ以外の場合は-1。  
  
### <a name="remarks"></a>Remarks  
 リボン カテゴリに含まれているリボン パネルだけが検索されます。  
  
##  <a name="getparentbutton"></a>  CMFCRibbonCategory::GetParentButton  
 リボン カテゴリの親のリボン要素を取得します。  
  
```  
CMFCRibbonBaseElement* GetParentButton() const;  
```  
  
### <a name="return-value"></a>戻り値  
 親のリボン要素へのポインターを返しますまたは`NULL`親要素が存在しない場合。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getparentmenubar"></a>  CMFCRibbonCategory::GetParentMenuBar  
 親メニュー バーへのポインターを返します、`CMFCRibbonCategory`オブジェクト。  
  
```  
CMFCRibbonPanelMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>戻り値  
 内容を返します、`m_pParentMenuBar`メンバーを保護します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getparentribbonbar"></a>  CMFCRibbonCategory::GetParentRibbonBar  
 リボン カテゴリの親のリボン バーを取得します。  
  
```  
CMFCRibbonBar* GetParentRibbonBar() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リボン カテゴリの親のリボン バーへのポインター。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getrect"></a>  CMFCRibbonCategory::GetRect  
 リボン カテゴリを表示する四角形を取得します。  
  
```  
CRect GetRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リボン カテゴリを表示する四角形。  
  
### <a name="remarks"></a>Remarks  
 リボン カテゴリを表示する四角形は、カテゴリ タブには含まれません。  
  
##  <a name="getsmallimages"></a>  CMFCRibbonCategory::GetSmallImages  
 リボン カテゴリに含まれている小さいイメージの一覧を取得します。  
  
```  
CMFCToolBarImages& GetSmallImages();
```  
  
### <a name="return-value"></a>戻り値  
 リボン カテゴリに含まれている小さいイメージの一覧。  
  
##  <a name="gettabcolor"></a>  CMFCRibbonCategory::GetTabColor  
 リボンのカテゴリ タブの現在の色を返します。  
  
```  
AFX_RibbonCategoryColor GetTabColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リボンのカテゴリ タブの現在の色。  
  
### <a name="remarks"></a>Remarks  
 返される値には、次の列挙値のいずれかを指定できます。  
  
-   AFX_CategoryColor_Red  
  
-   AFX_CategoryColor_Orange  
  
-   AFX_CategoryColor_Yellow  
  
-   AFX_CategoryColor_Green  
  
-   AFX_CategoryColor_Blue  
  
-   AFX_CategoryColor_Indigo  
  
-   AFX_CategoryColor_Violet  
  
##  <a name="gettabrect"></a>  CMFCRibbonCategory::GetTabRect  
 リボンのカテゴリ タブを表示する四角形を取得します。  
  
```  
CRect GetTabRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リボンのカテゴリ タブを表示する四角形。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="gettexttopline"></a>  CMFCRibbonCategory::GetTextTopLine  
 大きなイメージを表示するリボン カテゴリにリボン ボタンのテキストの垂直方向の位置を取得します。  
  
```  
int GetTextTopLine() const;  
```  
  
### <a name="return-value"></a>戻り値  
 大きなイメージを表示するリボン ボタンのピクセル単位でのテキストの垂直方向の位置。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getvisibleelements"></a>  CMFCRibbonCategory::GetVisibleElements  
 リボン カテゴリに属しているすべての可視要素を取得します。  
  
```  
void GetVisibleElements(
    CArray <CMFCRibbonBaseElement*,  
    CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>パラメーター  
 *arElements*  
 すべての可視要素の配列です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="highlightpanel"></a>  CMFCRibbonCategory::HighlightPanel  
 指定されたリボン パネルを強調表示されます。  
  
```  
CMFCRibbonPanel* HighlightPanel(
    CMFCRibbonPanel* pHLPanel,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pHLPanel*  
 強調表示するリボン パネルへのポインター。  
  
 [in]*ポイント*  
 ウィンドウの左上隅に対して相対的で、ポインターの x 座標と y を調整します。  
  
### <a name="return-value"></a>戻り値  
 強調表示されていたリボン パネルへのポインターそれ以外の場合`NULL`リボン パネルが強調表示されていない場合、このメソッドが呼び出される場合。  
  
### <a name="remarks"></a>Remarks  
 リボン パネルを強調表示の詳細については、次を参照してください。 [CMFCRibbonPanel::Highlight](../../mfc/reference/cmfcribbonpanel-class.md#highlight)です。  
  
##  <a name="hittest"></a>  CMFCRibbonCategory::HitTest  
 指定したポイントが含まれる場合は、リボン要素へのポインターを取得します。  
  
```  
CMFCRibbonBaseElement* HitTest(
    CPoint point,  
    BOOL bCheckPanelCaption = FALSE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ポイント*  
 ウィンドウの左上隅に対して相対的で、マウス ポインターの x 座標と y を調整します。  
  
 [in]*bCheckPanelCaption*  
 `TRUE` リボン パネルのキャプションをテストするには`FALSE`をリボン パネルのキャプションを除外します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、リボン要素へのポインターそれ以外の場合`NULL`です。  
  
### <a name="remarks"></a>Remarks  
 リボン カテゴリに含まれているリボン要素のみがテストされます。  
  
##  <a name="hittestex"></a>  CMFCRibbonCategory::HitTestEx  
 指定したポイントが含まれる場合は、リボン要素の 0 から始まるインデックスを取得します。  
  
```  
int HitTestEx(CPoint point) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ポイント*  
 ウィンドウの左上隅に対して相対的で、マウス ポインターの x 座標と y を調整します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、リボン要素の 0 から始まるインデックスそれ以外の場合は-1。  
  
### <a name="remarks"></a>Remarks  
 リボン カテゴリに含まれているリボン要素のみがテストされます。  
  
##  <a name="hittestscrollbuttons"></a>  CMFCRibbonCategory::HitTestScrollButtons  
 ポイントがリボン カテゴリの左側または右側のスクロール ボタン内にある場合は、そのボタンにポインターを返します。  
  
```  
CMFCRibbonBaseElement* HitTestScrollButtons(CPoint point) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ポイント*  
 テストする点です。  
  
### <a name="return-value"></a>戻り値  
 場合*ポイント*が左側のいずれかの外接する四角形またはリボン カテゴリの右スクロール ボタン内に、そのボタンにポインターを返しますまたは、それを返します`NULL`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="isactive"></a>  CMFCRibbonCategory::IsActive  
 リボン カテゴリは、リボン バーのアクティブなカテゴリであるかどうかを示します。  
  
```  
BOOL IsActive() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` リボン カテゴリがアクティブなカテゴリである場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 アクティブなリボン カテゴリには、リボン パネルが表示されます。  
  
##  <a name="isvisible"></a>  CMFCRibbonCategory::IsVisible  
 リボン カテゴリを表示するかどうかを示します。  
  
```  
BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` リボン カテゴリを表示する場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 表示されるリボンのカテゴリは、カテゴリ タブを表示します。  
  
##  <a name="iswindows7look"></a>  CMFCRibbonCategory::IsWindows7Look  
 親リボンが Windows 7 (小さな四角形のアプリケーション ボタン) の形式を持つかどうかを示します。  
  
```  
BOOL IsWindows7Look() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、親リボンがある Windows 7 を検索します。それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="notifycontrolcommand"></a>  CMFCRibbonCategory::NotifyControlCommand  
 すべてを WM_NOTIFY コマンド メッセージを配信`CMFCRibbonPanel`内の要素、`CMFCRibbonCategory`メッセージが処理されるまでです。  
  
```  
virtual BOOL NotifyControlCommand(
    BOOL bAccelerator,  
    int nNotifyCode,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bAccelerator*  
 `TRUE` このコマンドは、アクセラレータから送信された場合または`FALSE`それ以外の場合。  
  
 [in]*nNotifyCode*  
 通知コード。  
  
 [in]*wParam*  
 メッセージの WPARAM フィールドです。  
  
 [in]*lParam*  
 メッセージの LPARAM フィールドです。  
  
### <a name="return-value"></a>戻り値  
 返します`TRUE`メッセージが処理された場合または`FALSE`しない場合。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="oncancelmode"></a>  CMFCRibbonCategory::OnCancelMode  
 すべてのページで [キャンセル] モードを呼び出す、`CMFCRibbonPanel`の要素、`CMFCRibbonCategory`です。  
  
```  
virtual void OnCancelMode();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="ondraw"></a>  CMFCRibbonCategory::OnDraw  
 リボン カテゴリを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 リボン カテゴリのデバイス コンテキストへのポインター。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="ondrawimage"></a>  CMFCRibbonCategory::OnDrawImage  
 リボン カテゴリに、指定されたイメージを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnDrawImage(
    CDC* pDC,  
    CRect rect,  
    CMFCRibbonBaseElement* pElement,  
    BOOL bIsLargeImage,  
    BOOL nImageIndex,  
    BOOL bCenter);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 イメージのデバイス コンテキストへのポインター。  
  
 [in]*rect*  
 イメージの四角形を表示します。  
  
 [in]*pElement*  
 イメージを含むリボン要素へのポインター。  
  
 [in]*bIsLargeImage*  
 `TRUE` イメージが、大きなサイズの場合`FALSE`イメージのサイズが小さい場合。  
  
 [in]*nImageIndex*  
 リボン カテゴリに含まれているイメージ配列内のイメージの 0 から始まるインデックス。  
  
 [in]*bCenter*  
 `TRUE` 中央に表示する四角形; 内の画像`FALSE`に表示する四角形の左上隅にイメージを描画します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功した場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="ondrawmenuborder"></a>  CMFCRibbonCategory::OnDrawMenuBorder  
 ポップアップ メニューの境界線を描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawMenuBorder(
    CDC* pDC,  
    CMFCRibbonPanelMenuBar* pMenuBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 このパラメーターは使用されません。  
  
 [in]*pMenuBar*  
 このパラメーターは使用されません。  
  
### <a name="remarks"></a>Remarks  
 既定では、このメソッドは何も行いません。 ポップアップ メニューの枠線を描画するには、このメソッドをオーバーライドします。  
  
##  <a name="onkey"></a>  CMFCRibbonCategory::OnKey  
 ユーザーがキーボード ボタンを押したときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>パラメーター  
 *nChar*  
 ユーザーが押されたキーの仮想キー コード。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onlbuttondown"></a>  CMFCRibbonCategory::OnLButtonDown  
 ユーザーがマウスの左ボタンを押したときに指定されたポイントの下でリボン要素を取得するためにフレームワークによって呼び出されます。  
  
```  
virtual CMFCRibbonBaseElement* OnLButtonDown(CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ポイント*  
 ウィンドウの左上隅に対して相対的で、マウス ポインターの x 座標と y を調整します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、リボン要素へのポインターそれ以外の場合`NULL`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onlbuttonup"></a>  CMFCRibbonCategory::OnLButtonUp  
 ユーザーがマウスの左ボタンを離すし、ポインターがリボン カテゴリの上に、フレームワークによって呼び出されます。  
  
```  
virtual void OnLButtonUp(CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ポイント*  
 ウィンドウの左上隅に対して相対的で、ポインターの x 座標と y を調整します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onmousemove"></a>  CMFCRibbonCategory::OnMouseMove  
 リボン カテゴリの表示を更新するためにリボン バーにポインターを動かしたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnMouseMove(CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ポイント*  
 ウィンドウの左上隅に対して相対的で、ポインターの x 座標と y を調整します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onrtlchanged"></a>  CMFCRibbonCategory::OnRTLChanged  
 レイアウトの方向を変更するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bIsRTL*  
 `TRUE` レイアウトが右から左の場合`FALSE`レイアウトが左から右への場合。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、すべてのリボン パネルおよびリボン カテゴリに含まれているリボン要素のレイアウトを調整します。  
  
##  <a name="onscrollhorz"></a>  CMFCRibbonCategory::OnScrollHorz  
 リボン カテゴリを水平方向にスクロールします。  
  
```  
virtual BOOL OnScrollHorz(
    BOOL bScrollLeft,  
    int nScrollOffset = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bScrollLeft*  
 `TRUE` 左にスクロールするには`FALSE`を右側にスクロールします。  
  
 [in]*nScrollOffset*  
 スクロールの距離 (ピクセル単位)。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` リボン カテゴリは、水平方向に移動した場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onupdatecmdui"></a>  CMFCRibbonCategory::OnUpdateCmdUI  
 呼び出し、`OnUpdateCmdUI`内の各メンバー関数、`CMFCRibbonPanel`の要素、`CMFCRibbonCategory`を有効にするにまたはそれらのユーザー インターフェイス要素を無効にします。  
  
```  
virtual void OnUpdateCmdUI(
    CMFCRibbonCmdUI* pCmdUI,  
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*対応付けられました。*  
 ポインター、`CMFCRibbonCmdUI`を有効にするユーザー インターフェイス要素があるか、無効にするを指定するオブジェクト。  
  
 [in]*pTarget*  
 有効にするか、ユーザー インターフェイス要素の無効化を制御するウィンドウへのポインター。  
  
 [in]*持たず*  
 `TRUE` handler を持たない場合、ユーザー インターフェイス項目を無効にするのには、メッセージ マップで定義されています。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="recalclayout"></a>  CMFCRibbonCategory::RecalcLayout  
 リボン カテゴリのすべてのコントロールのレイアウトを調整します。  
  
```  
virtual void RecalcLayout(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 リボン カテゴリのデバイス コンテキストへのポインター。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="removepanel"></a>  CMFCRibbonCategory::RemovePanel  
 リボン カテゴリから、リボン パネルを削除します。  
  
```cpp  
BOOL RemovePanel(
    int nIndex,  
    BOOL bDelete = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nIndex*  
 削除するのには、パネルのインデックス番号します。 呼び出すことによって取得、 [CMFCRibbonCategory::GetPanelIndex](#getpanelindex)メソッドです。  
  
 [in]*bDelete*  
 `TRUE` パネル オブジェクト メモリ; から削除するには`FALSE`オブジェクトを削除する、パネルは削除されません。  
  
### <a name="return-value"></a>戻り値  
 メソッドが正常に実行された場合は `TRUE`、それ以外の場合は `FALSE`。  
  
##  <a name="repospanels"></a>  CMFCRibbonCategory::ReposPanels  
 リボン カテゴリに含まれているリボン パネル上のすべてのコントロールのレイアウトを調整します。  
  
```  
virtual void ReposPanels(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 リボン カテゴリに含まれているリボン パネル用のデバイス コンテキストへのポインター。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setcollapseorder"></a>  CMFCRibbonCategory::SetCollapseOrder  
 リボン カテゴリのリボン パネルを折りたたむに順序を定義します。  
  
```  
void SetCollapseOrder(const CArray<int,int>& arCollapseOrder);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*arCollapseOrder*  
 折りたたみ順序を指定します。 配列には、リボン パネルの 0 から始まるインデックスが含まれています。  
  
### <a name="remarks"></a>Remarks  
 ライブラリでは、折りたたみ順序を定義します。 ただし、折りたたみ順序を指定するインデックスの一覧でカテゴリを提供することによって、この動作をカスタマイズできます。  
  
 カテゴリをリボン パネルを折りたたむことが検出されると、指定されたリスト内の次の要素を検索します。 リストが空、または十分な要素が指定されていません、カテゴリは、内部アルゴリズム使用します。  
  
 たとえば、カテゴリは、3 つのリボン パネルを持つし、すべてのパネルが完全に折りたたまれた状態になるまで何回かを折りたたむことができます。 次の折りたたみ順序を設定することができます: 0、0、2、2 です。 この場合、カテゴリは、2 回に、[0] パネルには折りたたま、パネル 2 の 2 倍です。 インデックス 1、パネルは折りたたまれていない状態のままになります。  
  
### <a name="example"></a>例  
 次の例で使用する方法、`SetCollapseOrder`メソッドで、`CMFCRibbonCategory`クラスです。 この例では、折りたたみ順序を表す配列を作成する方法とリボン カテゴリを折りたたみ順序を設定する方法を示します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#13](../../mfc/reference/codesnippet/cpp/cmfcribboncategory-class_2.cpp)]  
  
##  <a name="setdata"></a>  CMFCRibbonCategory::SetData  
 リボン カテゴリに関連するユーザー定義データを設定します。  
  
```  
void SetData(DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*dwData*  
 ユーザー定義データ。  
  
##  <a name="setkeys"></a>  CMFCRibbonCategory::SetKeys  
 Keytip をリボン カテゴリに割り当てます。  
  
```  
void SetKeys(LPCTSTR lpszKeys);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszKeys*  
 Keytip テキストです。  
  
### <a name="remarks"></a>Remarks  
 Alt キーまたは F10 キーを押すと、キー ヒントが表示されます。  
  
##  <a name="setname"></a>  CMFCRibbonCategory::SetName  
 リボン カテゴリには、名前と keytip を割り当てます。  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszName*  
 名前とリボン カテゴリのキー ヒント。  
  
### <a name="remarks"></a>Remarks  
 リボン カテゴリの keytip を設定するには、追加する keytip の文字が続き、改行エスケープ シーケンス*lpszName*です。  
  
##  <a name="settabcolor"></a>  Cmfcribboncategory::settabcolor  
 リボン カテゴリの色を設定します。  
  
```  
void SetTabColor(AFX_RibbonCategoryColor color);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*色*  
 リボン カテゴリの新しい色を指定します。  
  
### <a name="remarks"></a>Remarks  
 色は、次の値のいずれかになります。  
  
-   AFX_CategoryColor_None  
  
-   AFX_CategoryColor_Red  
  
-   AFX_CategoryColor_Orange  
  
-   AFX_CategoryColor_Yellow  
  
-   AFX_CategoryColor_Green  
  
-   AFX_CategoryColor_Blue  
  
-   AFX_CategoryColor_Indigo  
  
-   AFX_CategoryColor_Violet  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)
