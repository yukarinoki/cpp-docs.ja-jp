---
title: CMFCToolBarEditBoxButton クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CanBeStretched
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CopyFrom
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetByCmd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContentsAll
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetEditBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetHwnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetInvalidateRect
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::HaveHotBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::IsFlatMode
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::NotifyCommand
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnAddToCustomizePage
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnChangeParentWnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnClick
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnCtlColor
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnGlobalFontsChanged
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnMove
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnShow
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnSize
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnUpdateToolTip
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetFlatMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarEditBoxButton [MFC], CMFCToolBarEditBoxButton
- CMFCToolBarEditBoxButton [MFC], CanBeStretched
- CMFCToolBarEditBoxButton [MFC], CopyFrom
- CMFCToolBarEditBoxButton [MFC], GetByCmd
- CMFCToolBarEditBoxButton [MFC], GetContentsAll
- CMFCToolBarEditBoxButton [MFC], GetContextMenuID
- CMFCToolBarEditBoxButton [MFC], GetEditBorder
- CMFCToolBarEditBoxButton [MFC], GetHwnd
- CMFCToolBarEditBoxButton [MFC], GetInvalidateRect
- CMFCToolBarEditBoxButton [MFC], HaveHotBorder
- CMFCToolBarEditBoxButton [MFC], IsFlatMode
- CMFCToolBarEditBoxButton [MFC], NotifyCommand
- CMFCToolBarEditBoxButton [MFC], OnAddToCustomizePage
- CMFCToolBarEditBoxButton [MFC], OnChangeParentWnd
- CMFCToolBarEditBoxButton [MFC], OnClick
- CMFCToolBarEditBoxButton [MFC], OnCtlColor
- CMFCToolBarEditBoxButton [MFC], OnGlobalFontsChanged
- CMFCToolBarEditBoxButton [MFC], OnMove
- CMFCToolBarEditBoxButton [MFC], OnShow
- CMFCToolBarEditBoxButton [MFC], OnSize
- CMFCToolBarEditBoxButton [MFC], OnUpdateToolTip
- CMFCToolBarEditBoxButton [MFC], SetContextMenuID
- CMFCToolBarEditBoxButton [MFC], SetFlatMode
ms.assetid: b21d9b67-6bf7-4ca9-bd62-b237756e0ab3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0bddd7274feb9ecde268a94d7e9a6e857c906650
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfctoolbareditboxbutton-class"></a>CMFCToolBarEditBoxButton クラス
編集コントロールを含むツール バー ボタン ( [CEdit クラス](../../mfc/reference/cedit-class.md))。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCToolBarEditBoxButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton](#cmfctoolbareditboxbutton)|`CMFCToolBarEditBoxButton` オブジェクトを構築します。|  
|`CMFCToolBarEditBoxButton::~CMFCToolBarEditBoxButton`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarEditBoxButton::CanBeStretched](#canbestretched)|ユーザーがカスタマイズ中に、ボタンをストレッチできるかどうかを指定します。 (上書き[CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched))。|  
|[CMFCToolBarEditBoxButton::CopyFrom](#copyfrom)|現在のボタンに別のツール バー ボタンのプロパティをコピーします。 (上書き[CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom))。|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::CreateEdit](#createedit)|ボタンには、新しい編集コントロールを作成します。|  
|`CMFCToolBarEditBoxButton::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CMFCToolBarEditBoxButton::GetByCmd](#getbycmd)|最初に取得`CMFCToolBarEditBoxButton`指定されたコマンド ID を持つアプリケーションのオブジェクト|  
|[CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall)|指定されたコマンド ID を持つ最初の編集ボックス ツールバー コントロールのテキストを取得します。|  
|[CMFCToolBarEditBoxButton::GetContextMenuID](#getcontextmenuid)|ボタンに関連付けられているショートカット メニューのリソース ID を取得します。|  
|[CMFCToolBarEditBoxButton::GetEditBorder](#geteditborder)|エディット ボックス ボタンの編集部分の外接する四角形を取得します。|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::GetEditBox](#geteditbox)|ボタンに埋め込まれている編集コントロールへのポインターを返します。|  
|[CMFCToolBarEditBoxButton::GetHwnd](#gethwnd)|ツール バー ボタンに関連付けられているウィンドウ ハンドルを取得します。 (上書き[CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd))。|  
|[CMFCToolBarEditBoxButton::GetInvalidateRect](#getinvalidaterect)|再描画する必要があります、ボタンのクライアント領域の領域を取得します。 (上書き[CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect))。|  
|`CMFCToolBarEditBoxButton::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCToolBarEditBoxButton::HaveHotBorder](#havehotborder)|ユーザーがボタンをクリックしたときに、ボタンの境界線を表示するかどうかを判断します。 (上書き[CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder))。|  
|[CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode)|エディット ボックス ボタンのフラット スタイルかどうかを判断します。|  
|[CMFCToolBarEditBoxButton::NotifyCommand](#notifycommand)|ボタンを処理するかどうかを指定します、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)メッセージ。 (上書き[CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand))。|  
|[CMFCToolBarEditBoxButton::OnAddToCustomizePage](#onaddtocustomizepage)|ボタンが追加されたときに、フレームワークによって呼び出されます、**カスタマイズ** ダイアログ ボックス。 (上書き[CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage))。|  
|`CMFCToolBarEditBoxButton::OnCalculateSize`|指定したデバイス コンテキストとドッキングの状態のボタンのサイズを計算するためにフレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize))。|  
|[CMFCToolBarEditBoxButton::OnChangeParentWnd](#onchangeparentwnd)|新しいツールバーにボタンが挿入されたときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd))。|  
|[CMFCToolBarEditBoxButton::OnClick](#onclick)|ユーザーがマウス ボタンをクリックしたときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick))。|  
|[CMFCToolBarEditBoxButton::OnCtlColor](#onctlcolor)|親ツールバーを処理するときに、フレームワークによって呼び出されます、`WM_CTLCOLOR`メッセージ。 (上書き[CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor))。|  
|`CMFCToolBarEditBoxButton::OnDraw`|指定したスタイルとオプションを使用して、ボタンを描画するためにフレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw))。|  
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|ボタンを描画するためにフレームワークによって呼び出される、**コマンド**のペイン、**カスタマイズ** ダイアログ ボックス。 (上書き[CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist))。|  
|[CMFCToolBarEditBoxButton::OnGlobalFontsChanged](#onglobalfontschanged)|グローバルのフォントが変更されたときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged))。|  
|[CMFCToolBarEditBoxButton::OnMove](#onmove)|親ツールバーに移動すると、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove))。|  
|[CMFCToolBarEditBoxButton::OnShow](#onshow)|フレームワークによって呼び出されます、ボタンが表示または非表示します。 (上書き[CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow))。|  
|[CMFCToolBarEditBoxButton::OnSize](#onsize)|親ツールバーのサイズまたは位置が変更されに伴ってボタンのサイズを変更するときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize))。|  
|[CMFCToolBarEditBoxButton::OnUpdateToolTip](#onupdatetooltip)|親ツールバーは、そのツールヒント テキストを更新するときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip))。|  
|`CMFCToolBarEditBoxButton::Serialize`|アーカイブからこのオブジェクトを読み取りまたはアーカイブを書き込みます。 (上書き[CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize))。|  
|`CMFCToolBarEditBoxButton::SetACCData`|指定された設定`CAccessibilityData`ツール バー ボタンのアクセシビリティ データを持つオブジェクト。 (上書き[CMFCToolBarButton::SetACCData](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata))。|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContents](#setcontents)|ボタンの編集コントロールのテキストを設定します。|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall)|指定されたコマンド ID を持つし、そのボタンの編集コントロールのテキストを設定するエディット コントロールのボタンを検索します。|  
|[CMFCToolBarEditBoxButton::SetContextMenuID](#setcontextmenuid)|ボタンに関連付けられているショートカット メニューのリソース ID を指定します。|  
|[CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode)|アプリケーションでは、エディット ボックス ボタンのフラット スタイルの外観を指定します。|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetStyle](#setstyle)|ボタンのスタイルを指定します。 (上書き[CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle))。|  
  
## <a name="remarks"></a>コメント  
 ツールバーには、エディット ボックス ボタンを追加するには、次の手順を実行します。  
  
 1. 親ツール バー リソースでボタンのダミー リソース ID を予約します。  
  
 2. `CMFCToolBarEditBoxButton` オブジェクトを構築します。  
  
 3. 処理するメッセージ ハンドラーで、`AFX_WM_RESETTOOLBAR`メッセージで、ダミー ボタンを置き換える新しいコンボ ボックス ボタンを使用して、 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)です。  
  
 詳細については、次を参照してください。[チュートリアル: ツールバーにコントロールを配置する](../../mfc/walkthrough-putting-controls-on-toolbars.md)です。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCToolBarEditBoxButton`クラスです。 この例は、ユーザーことができますカスタマイズ中に、ボタンを拡大、ユーザーがボタンをクリックしたときに、ボタンの境界線が表示されることを指定、テキスト ボックス コントロールでテキストを設定、アプリケーションでのエディット ボックス ボタンのフラット スタイルの外観を指定を指定する方法を示しますいる場合、エディット ボックス コントロールのツールバーのスタイルを指定します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#40](../../mfc/reference/codesnippet/cpp/cmfctoolbareditboxbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 `CMFCToolBarEditBoxButton` 
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtoolbareditboxbutton.h  
  
##  <a name="canbestretched"></a>  CMFCToolBarEditBoxButton::CanBeStretched  
 ユーザーがカスタマイズ中に、ボタンをストレッチできるかどうかを指定します。  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このメソッドは `TRUE` を返します。  
  
### <a name="remarks"></a>コメント  
 既定では、フレームワークはユーザーがツール バー ボタンをカスタマイズするときに stretch をできません。 このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)) によって、ユーザーがカスタマイズ中にエディット ボックスのツールバー ボタンをストレッチできるようにします。  
  
##  <a name="cmfctoolbareditboxbutton"></a>  CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton  
 構築、 [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md)オブジェクト。  
  
```  
CMFCToolBarEditBoxButton(
    UINT uiID,  
    int iImage,  
    DWORD dwStyle=ES_AUTOHSCROLL,  
    int iWidth=0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiID`  
 コントロール ID を指定します  
  
 [入力] `iImage`  
 ツール バー イメージの 0 から始まるインデックスを指定します。 イメージが格納されて、 [CMFCToolBarImages クラス](../../mfc/reference/cmfctoolbarimages-class.md)オブジェクトを[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)クラスを保持します。  
  
 [入力] `dwStyle`  
 エディット コントロールのスタイルを指定します。  
  
 [入力] `iWidth`  
 エディット コントロールのピクセル単位の幅を指定します。  
  
### <a name="remarks"></a>コメント  
 既定のコンス トラクターは、次の組み合わせにエディット コントロールのスタイルを設定します。  
  
 `WS_CHILD | WS_VISIBLE | ES_AUTOHSCROLL`  
  
 コントロールの既定の幅は、150 ピクセルです。  
  
##  <a name="copyfrom"></a>  CMFCToolBarEditBoxButton::CopyFrom  
 現在のボタンに別のツール バー ボタンのプロパティをコピーします。  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `src`  
 コピー元のソース ボタンへの参照。  
  
### <a name="remarks"></a>コメント  
 このツール バー ボタンに別のツール バー ボタンをコピーするには、このメソッドを呼び出します。 `src` 型でなければなりません`CMFCToolBarEditBoxButton`です。  
  
##  <a name="createedit"></a>  CMFCToolBarEditBoxButton::CreateEdit  
 ボタンには、新しい編集コントロールを作成します。  
  
```  
virtual CEdit* CreateEdit(
    CWnd* pWndParent,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 `[in] pWndParent`  
 エディット コントロールの親ウィンドウを指定します。 NULL は指定できません。  
  
 `[in] rect`  
 エディット コントロールのサイズと位置を指定します。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたエディット コントロールへのポインター`NULL`コントロールの作成と添付ファイルが失敗した場合。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CMFCToolBarEditBoxButton` 2 つのステップ内のオブジェクト。 まず、コンス トラクターを呼び出します`CreateEdit`、Windows のエディット コントロールを作成しにアタッチする、`CMFCToolBarEditBoxButton`オブジェクト。  
  
##  <a name="getbycmd"></a>  CMFCToolBarEditBoxButton::GetByCmd  
 最初に取得`CMFCToolBarEditBoxButton`指定されたコマンド ID を持つアプリケーションのオブジェクト  
  
```  
static CMFCToolBarEditBoxButton* __stdcall GetByCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmd`  
 取得する ボタンのコマンド ID。  
  
### <a name="return-value"></a>戻り値  
 最初の`CMFCToolBarEditBoxButton`指定されたコマンド ID を持つアプリケーションのオブジェクトまたは`NULL`このようなオブジェクトが存在しない場合。  
  
### <a name="remarks"></a>コメント  
 など、この共有のユーティリティ メソッドをメソッドで使用される[CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall)と[CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall)を設定または最初の編集ボックスのツールバーのテキストを取得するには指定されたコマンド ID を持つコントロール  
  
##  <a name="getcontentsall"></a>  CMFCToolBarEditBoxButton::GetContentsAll  
 指定されたコマンド ID を持つ最初の編集ボックス ツールバー コントロールのテキストを取得します。  
  
```  
static CString __stdcall GetContentsAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmd`  
 元のコンテンツを取得するボタンのコマンド ID。  
  
### <a name="return-value"></a>戻り値  
 A`CString`指定されたコマンド ID を持つ最初の編集ボックス ツールバー コントロールのテキストを格納しているオブジェクト  
  
### <a name="remarks"></a>コメント  
 このメソッドがない場合は、空の文字列を返します`CMFCToolBarEditBoxButton`オブジェクトは、指定されたコマンド ID を持ちます。  
  
##  <a name="getcontextmenuid"></a>  CMFCToolBarEditBoxButton::GetContextMenuID  
 ボタンに関連付けられているショートカット メニューのリソース ID を取得します。  
  
```  
UINT GetContextMenuID();
```  
  
### <a name="return-value"></a>戻り値  
 ボタンに関連付けられているショートカット メニューがあるない場合に、ボタンまたは 0 に関連付けられているショートカット メニューのリソース ID です。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、リソース ID を使用して、ユーザーがボタンを右クリックすると、ショートカット メニューを作成します。  
  
##  <a name="geteditborder"></a>  CMFCToolBarEditBoxButton::GetEditBorder  
 エディット ボックス ボタンの編集部分の外接する四角形を取得します。  
  
```  
virtual void GetEditBorder(CRect& rectBorder);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `rectBorder`  
 参照、`CRect`外接する四角形を受け取るオブジェクトです。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、クライアント座標で、編集コントロールの外接する四角形を取得します。 1 ピクセルずつ各方向に四角形のサイズを展開します。  
  
 [CMFCVisualManager::OnDrawEditBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondraweditborder)の周りの境界線を描画するときに、メソッドがこのメソッドを呼び出して、`CMFCToolBarEditBoxButton`オブジェクト。  
  
##  <a name="geteditbox"></a>  CMFCToolBarEditBoxButton::GetEditBox  
 ポインターを返します、 [CEdit クラス](../../mfc/reference/cedit-class.md)ボタンに埋め込まれているコントロール。  
  
```  
CEdit* GetEditBox() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CEdit クラス](../../mfc/reference/cedit-class.md)ボタンが含まれるコントロール。 `NULL`場合、`CEdit`コントロールがまだ作成されていません。  
  
### <a name="remarks"></a>コメント  
 作成する、`CEdit`呼び出すことによってコントロール[CMFCToolBarEditBoxButton::CreateEdit](#createedit)です。  
  
##  <a name="gethwnd"></a>  CMFCToolBarEditBoxButton::GetHwnd  
 ツール バー ボタンに関連付けられているウィンドウ ハンドルを取得します。  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>戻り値  
 ボタンに関連付けられているウィンドウ ハンドル。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、 [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd)をエディット ボックス ボタンの編集コントロールの一部のウィンドウ ハンドルを返すメソッド。  
  
##  <a name="getinvalidaterect"></a>  CMFCToolBarEditBoxButton::GetInvalidateRect  
 再描画する必要があります、ボタンのクライアント領域の領域を取得します。  
  
```  
virtual const CRect GetInvalidateRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`CRect`の領域を再描画する必要がありますを指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメソッドが基底クラスの実装を拡張[CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect)領域のテキスト ラベルの領域を含めることによってです。  
  
##  <a name="havehotborder"></a>  CMFCToolBarEditBoxButton::HaveHotBorder  
 ユーザーがボタンをクリックしたときに、ボタンの境界線を表示するかどうかを判断します。  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ボタンが選択されている場合、境界線を表示する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドが基底クラスの実装を拡張[CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder)コントロールが表示されている場合は、0 以外の値を返すことによってです。  
  
##  <a name="isflatmode"></a>  CMFCToolBarEditBoxButton::IsFlatMode  
 エディット ボックス ボタンのフラット スタイルかどうかを判断します。  
  
```  
static BOOL __stdcall IsFlatMode();
```  
  
### <a name="return-value"></a>戻り値  
 ボタンにフラット スタイル; がある場合は 0 以外。それ以外の場合、0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定では、エディット ボックス ボタンにフラット スタイルがあります。 使用して、 [CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode)メソッドで、アプリケーションのフラット スタイルの外観を変更します。  
  
##  <a name="notifycommand"></a>  CMFCToolBarEditBoxButton::NotifyCommand  
 ボタンを処理するかどうかを指定します、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)メッセージ。  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iNotifyCode`  
 コマンドに関連付けられている通知メッセージです。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ボタンを処理する場合、`WM_COMMAND`メッセージ、または`FALSE`親ツールバーで、メッセージを処理する必要があることを表します。  
  
### <a name="remarks"></a>コメント  
 送信しようとしているときに、フレームワークはこのメソッドを呼び出して、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)メッセージを親ウィンドウ。  
  
 このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) 処理することで、 [EN_UPDATE](http://msdn.microsoft.com/library/windows/desktop/bb761687)通知します。 このオブジェクトと同じコマンド ID を持つ各編集ボックスのテキスト ラベルをこのオブジェクトのテキスト ラベルを設定します。  
  
##  <a name="onaddtocustomizepage"></a>  CMFCToolBarEditBoxButton::OnAddToCustomizePage  
 ボタンが追加されたときに、フレームワークによって呼び出されます、**カスタマイズ** ダイアログ ボックス。  
  
```  
virtual void OnAddToCustomizePage();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)) をこのオブジェクトと同じコマンド ID を持つ任意のツールバーで、編集ボックス コントロールからプロパティをコピーしています。 エディット ボックス コントロールをこのオブジェクトと同じコマンド ID を持つツールバーがない場合は、何も行われません。  
  
 詳細については、**カスタマイズ**ダイアログ ボックスを参照してください[CMFCToolBarsCustomizeDialog クラス](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)です。  
  
##  <a name="onchangeparentwnd"></a>  CMFCToolBarEditBoxButton::OnChangeParentWnd  
 新しいツールバーにボタンが挿入されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndParent`  
 新しい親ウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、基本クラスの実装 ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) 内部の再作成して`CEdit`オブジェクト。  
  
##  <a name="onclick"></a>  CMFCToolBarEditBoxButton::OnClick  
 ユーザーがマウス ボタンをクリックしたときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 使用されません。  
  
 [入力] `bDelay`  
 使用されません。  
  
### <a name="return-value"></a>戻り値  
 ボタンをクリックしてメッセージを処理する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、基本クラスの実装 ( [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)) 場合は、0 以外の値を返すことによって、内部`CEdit`オブジェクトを表示します。  
  
##  <a name="onctlcolor"></a>  CMFCToolBarEditBoxButton::OnCtlColor  
 親ツールバーを処理するときに、フレームワークによって呼び出されます、`WM_CTLCOLOR`メッセージ。  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 ボタンを表示しているデバイス コンテキスト。  
  
 [入力] `nCtlColor`  
 使用されません。  
  
### <a name="return-value"></a>戻り値  
 グローバルのウィンドウのブラシへのハンドル。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、基本クラスの実装 ( [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)) によって提供されているデバイス コンテキストのテキストと背景色をグローバルのテキストと、背景色に設定すると、それぞれします。  
  
 アプリケーションに使用できるグローバルのオプションの詳細については、次を参照してください。 [AFX_GLOBAL_DATA 構造体](../../mfc/reference/afx-global-data-structure.md)です。  
  
##  <a name="onglobalfontschanged"></a>  CMFCToolBarEditBoxButton::OnGlobalFontsChanged  
 グローバルのフォントが変更されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) のグローバルのフォントのコントロールのフォントを変更することによりします。  
  
 アプリケーションに使用できるグローバルのオプションの詳細については、次を参照してください。 [AFX_GLOBAL_DATA 構造体](../../mfc/reference/afx-global-data-structure.md)です。  
  
##  <a name="onmove"></a>  CMFCToolBarEditBoxButton::OnMove  
 親ツールバーに移動すると、フレームワークによって呼び出されます。  
  
```  
virtual void OnMove();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、既定のクラスの実装 ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)) 内部の位置を更新することによって`CEdit`オブジェクト  
  
##  <a name="onshow"></a>  CMFCToolBarEditBoxButton::OnShow  
 フレームワークによって呼び出されます、ボタンが表示または非表示します。  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bShow`  
 ボタンが表示されているかどうかを指定します。 このパラメーターは、する場合`TRUE` ボタンを表示します。 それ以外の場合、ボタンは表示されません。  
  
### <a name="remarks"></a>コメント  
 このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) 場合は、ボタンを表示することによって`bShow`は`TRUE`します。 それ以外の場合、このメソッドには、ボタンが非表示にします。  
  
##  <a name="onsize"></a>  CMFCToolBarEditBoxButton::OnSize  
 親ツールバーのサイズまたは位置が変更されに伴ってボタンのサイズを変更するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iSize`  
 ピクセル単位で、ボタンの新しい幅。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、既定のクラス実装[CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)、内部の位置とサイズを更新することによって`CEdit`オブジェクト。  
  
##  <a name="onupdatetooltip"></a>  CMFCToolBarEditBoxButton::OnUpdateToolTip  
 親ツールバーは、そのツールヒント テキストを更新するときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,  
    int iButtonIndex,  
    CToolTipCtrl& wndToolTip,  
    CString& str);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndParent`  
 使用されません。  
  
 [入力] `iButtonIndex`  
 使用されません。  
  
 [入力] `wndToolTip`  
 ツールヒントのテキストを表示するコントロール。  
  
 [出力] `str`  
 A`CString`更新されたツールヒント テキストを受け取るオブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 メソッドは、ツールヒント テキストを更新する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) ボタンの編集部分に関連付けられているツールヒント テキストを表示します。 場合、内部`CEdit`オブジェクトが`NULL`またはのウィンドウ ハンドル、`CEdit`オブジェクトは、既存のウィンドウを識別できません、このメソッドは何も実行し、返します`FALSE`です。  
  
##  <a name="setcontents"></a>  CMFCToolBarEditBoxButton::SetContents  
 テキスト ボックス コントロールのテキストを設定します。  
  
```  
virtual void SetContents(const CString& sContents);
```  
  
### <a name="parameters"></a>パラメーター  
 `[in] sContents`  
 設定する新しいテキストを指定します。  
  
##  <a name="setcontentsall"></a>  CMFCToolBarEditBoxButton::SetContentsAll  
 検索、 [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md)オブジェクトを指定されたコマンド ID を持ち、そのテキスト ボックス内の指定したテキストを設定します。  
  
```  
static BOOL SetContentsAll(
    UINT uiCmd,  
    const CString& strContents);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmd`  
 テキストの変更のコントロールのコマンド ID を指定します。  
  
 [入力] `strContents`  
 設定する新しいテキストを指定します。  
  
### <a name="return-value"></a>戻り値  
 テキストが設定された場合は 0 以外。0 の場合、`CMFCToolBarEditBoxButton`指定されたコマンド ID を持つコントロールは存在しません。  
  
##  <a name="setcontextmenuid"></a>  CMFCToolBarEditBoxButton::SetContextMenuID  
 ボタンに関連付けられているショートカット メニューのリソース ID を指定します。  
  
```  
void SetContextMenuID(UINT uiResID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmd`  
 ショートカット メニューのリソース ID です。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、リソース ID を使用して、ユーザーがツール バー ボタンを右クリックしたときに、ショートカット メニューを作成します。  
  
##  <a name="setflatmode"></a>  CMFCToolBarEditBoxButton::SetFlatMode  
 アプリケーションでは、エディット ボックス ボタンのフラット スタイルの外観を指定します。  
  
```  
static void __stdcall SetFlatMode(BOOL bFlat = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bFlat`  
 エディット ボックス ボタンのフラット スタイルです。 このパラメーターが場合`TRUE`、フラット スタイルの外観が有効です。 それ以外の場合、フラット スタイルの外観が無効になっています。  
  
### <a name="remarks"></a>コメント  
 エディット ボックス ボタンの既定のフラット スタイル`TRUE`です。 使用して、 [CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode)アプリケーションのフラット スタイルの外観を取得します。  
  
##  <a name="setstyle"></a>  CMFCToolBarEditBoxButton::SetStyle  
 編集ボックス コントロールのツールバーのスタイルを指定します。  
  
```  
virtual void SetStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nStyle`  
 新しいスタイルを設定します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは設定[CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle)に`nStyle`も無効になります、テキスト ボックスと、アプリケーションは、カスタマイズ モードのアプリケーションがカスタマイズ モードではないときに有効に、(を参照してください[CMFCToolBar:: SetCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode)と[CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode))。 参照してください[ツール バー コントロールのスタイル](../../mfc/reference/toolbar-control-styles.md)有効なスタイル フラグの一覧についてはします。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CEdit クラス](../../mfc/reference/cedit-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)



