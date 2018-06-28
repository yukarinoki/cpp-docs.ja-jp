---
title: CMFCOutlookBarPane クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::AddButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::CanBeAttached
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::ClearAll
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::Create
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnablePageScrollMode
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::GetRegularColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsBackgroundTexture
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsDrawShadedHighlight
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackImage
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetDefaultState
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetExtraSpace
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTextColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTransparentColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnableContextMenuItems
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveAllButtons
dev_langs:
- C++
helpviewer_keywords:
- CMFCOutlookBarPane [MFC], AddButton
- CMFCOutlookBarPane [MFC], CanBeAttached
- CMFCOutlookBarPane [MFC], ClearAll
- CMFCOutlookBarPane [MFC], Create
- CMFCOutlookBarPane [MFC], EnablePageScrollMode
- CMFCOutlookBarPane [MFC], GetRegularColor
- CMFCOutlookBarPane [MFC], IsBackgroundTexture
- CMFCOutlookBarPane [MFC], IsDrawShadedHighlight
- CMFCOutlookBarPane [MFC], RemoveButton
- CMFCOutlookBarPane [MFC], SetBackColor
- CMFCOutlookBarPane [MFC], SetBackImage
- CMFCOutlookBarPane [MFC], SetDefaultState
- CMFCOutlookBarPane [MFC], SetExtraSpace
- CMFCOutlookBarPane [MFC], SetTextColor
- CMFCOutlookBarPane [MFC], SetTransparentColor
- CMFCOutlookBarPane [MFC], EnableContextMenuItems
- CMFCOutlookBarPane [MFC], RemoveAllButtons
ms.assetid: 094e2ef3-a118-487e-a4cc-27626108fe08
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd073dc7876a755a8dc309efc7e11fb63521ab5a
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037903"
---
# <a name="cmfcoutlookbarpane-class"></a>CMFCOutlookBarPane クラス
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 派生したコントロール[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)Outlook バーに挿入できる ( [CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md))。 Outlook バー ペインには、大きいボタンの列があります。 ボタンのリストがペインより長い場合、ユーザーはリストを上下にスクロールできます。 ユーザーが Outlook バー ペインを Outlook バーから切り離すと、そのペインをフローティング状態にするかメイン フレーム ウィンドウにドッキングできます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCOutlookBarPane : public CMFCToolBar  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|既定のコンストラクター|  
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCOutlookBarPane::AddButton](#addbutton)|Outlook バー ペインに、ボタンを追加します。|  
|[CMFCOutlookBarPane::CanBeAttached](#canbeattached)|別のウィンドウまたはフレーム ウィンドウに、ウィンドウをドッキングできるかどうかを判断します。 (上書き[CBasePane::CanBeAttached](../../mfc/reference/cbasepane-class.md#canbeattached))。|  
|`CMFCOutlookBarPane::CanBeRestored`|システムが、カスタマイズ後ツールバーを元の状態に復元できるかどうかを判断します。 (上書き[CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored))。|  
|[CMFCOutlookBarPane::ClearAll](#clearall)|Outlook バー ペイン内のイメージで使用したリソースを解放します。|  
|[CMFCOutlookBarPane::Create](#create)|Outlook バー ペインを作成します。|  
|`CMFCOutlookBarPane::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|`CMFCOutlookBarPane::Dock`|Outlook バー ペインをドッキングするのには、フレームワークによって呼び出されます。 (`CPane::Dock` をオーバーライドします)。|  
|[CMFCOutlookBarPane::EnablePageScrollMode](#enablepagescrollmode)|ページで、またはボタンをクリックして、Outlook バー ペインのスクロール バーの矢印がボタンの一覧を進めるかどうかを指定します。|  
|[CMFCOutlookBarPane::GetRegularColor](#getregularcolor)|Outlook バー ペインの正規 (選択されていない) のテキストの色を返します。|  
|`CMFCOutlookBarPane::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCOutlookBarPane::IsBackgroundTexture](#isbackgroundtexture)|Outlook バー ペインに読み込まれる背景画像があるかどうかを判断します。|  
|`CMFCOutlookBarPane::IsChangeState`|フローティング ペインをドッキングできるかどうかを判断します。 (`CPane::IsChangeState` をオーバーライドします)。|  
|[CMFCOutlookBarPane::IsDrawShadedHighlight](#isdrawshadedhighlight)|ボタンが強調表示され、背景画像が表示されるときにボタンの境界線が影付きにするかどうかを判断します。|  
|`CMFCOutlookBarPane::OnBeforeFloat`|ペインが float 型に、フレームワークによって呼び出されます。 (上書き[CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat))。|  
|[CMFCOutlookBarPane::RemoveButton](#removebutton)|指定されたコマンド ID を持つボタンを削除します|  
|`CMFCOutlookBarPane::RestoreOriginalstate`|ツール バーを元の状態に戻します。 (上書き[CMFCToolBar::RestoreOriginalState](../../mfc/reference/cmfctoolbar-class.md#restoreoriginalstate))。|  
|[CMFCOutlookBarPane::SetBackColor](#setbackcolor)|背景色を設定します。|  
|[CMFCOutlookBarPane::SetBackImage](#setbackimage)|背景画像を設定します。|  
|[CMFCOutlookBarPane::SetDefaultState](#setdefaultstate)|ボタンの元のセットを Outlook バー ペインをリセットします。|  
|[CMFCOutlookBarPane::SetExtraSpace](#setextraspace)|Outlook バー ペインのボタンの周囲に使用するパディングのピクセルの数を設定します。|  
|[CMFCOutlookBarPane::SetTextColor](#settextcolor)|Outlook バー ペインの通常および強調表示されたテキストの色を設定します。|  
|[CMFCOutlookBarPane::SetTransparentColor](#settransparentcolor)|Outlook バー ペインの透明色を設定します。|  
|`CMFCOutlookBarPane::SmartUpdate`|Outlook バーを更新するには、内部的に使用します。 (`CMFCToolBar::SmartUpdate` をオーバーライドします)。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCOutlookBarPane::EnableContextMenuItems](#enablecontextmenuitems)|カスタマイズ モードで表示するショートカット メニュー項目を指定します。|  
|[CMFCOutlookBarPane::RemoveAllButtons](#removeallbuttons)|Outlook バー ペインからすべてのボタンを削除します。 (上書き[CMFCToolBar::RemoveAllButtons](../../mfc/reference/cmfctoolbar-class.md#removeallbuttons))。|  
  
## <a name="remarks"></a>Remarks  
 Outlook バーを実装する方法については、次を参照してください。 [CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)です。  
  
 Outlook バーの例は、OutlookDemo サンプル プロジェクトを参照してください。  
  
## <a name="example"></a>例  
 次の例でのさまざまなメソッドを使用する方法、`CMFCOutlookBarPane`クラスです。 この例では、Outlook バー ペインを作成、ページのスクロール モードを有効にする、ドッキング、有効にする、および Outlook バーの背景色を設定する方法を示します。 このコード スニペットの一部である、 [Outlook マルチ ビュー サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews#4](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxoutlookbarpane.h  
  
##  <a name="addbutton"></a>  CMFCOutlookBarPane::AddButton  
 Outlook バー ペインに、ボタンを追加します。  
  
```  
BOOL AddButton(
    UINT uiImage,  
    LPCTSTR lpszLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    UINT uiImage,  
    UINT uiLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    LPCTSTR szBmpFileName,  
    LPCTSTR szLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    HBITMAP hBmp,  
    LPCTSTR lpszLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    HICON hIcon,  
    LPCTSTR lpszLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1,  
    BOOL bAlphaBlend=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiImage*  
 ビットマップのリソース識別子を指定します。  
  
 [in]*lpszLabel*  
 ボタンのテキストを指定します。  
  
 [in]*iIdCommand*  
 ボタン コントロールの ID を指定します  
  
 [in]*iInsertAt*  
 Outlook バーのページ、ボタンを挿入する位置の 0 から始まるインデックスを指定します。  
  
 [in]*uiLabel*  
 文字列リソースの id です。  
  
 [in]*szBmpFileName*  
 読み込むディスク イメージ ファイルの名前を指定します。  
  
 [in]*szLabel*  
 ボタンのテキストを指定します。  
  
 [in]*hBmp*  
 ボタンのビットマップへのハンドル。  
  
 [in]*hIcon*  
 ボタンのアイコンへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ボタンが正常に追加された場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 Outlook バーのページに、新しいボタンを挿入するのにには、このメソッドを使用します。 アプリケーション リソースから、またはディスク ファイルから、ボタンのイメージを読み込むことができます。  
  
 によってページ ID が指定されている場合*uiPageID* -1 で、最初のページに、ボタンを挿入します。  
  
 によってインデックスが指定されている場合*iInsertAt* -1 で、ボタンがページの最後に追加します。  
  
##  <a name="canbeattached"></a>  CMFCOutlookBarPane::CanBeAttached  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="clearall"></a>  CMFCOutlookBarPane::ClearAll  
 Outlook バー ペインのイメージで使用されているリソースを解放します。  
  
```  
void ClearAll();
```  
  
### <a name="remarks"></a>Remarks  
 このメソッドを直接呼び出す[CMFCToolBarImages::Clear](../../mfc/reference/cmfctoolbarimages-class.md#clear)、Outlook バー ペインで使用されるイメージと呼ばれます。  
  
##  <a name="create"></a>  CMFCOutlookBarPane::Create  
 Outlook バー ペインを作成します。  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle=AFX_DEFAULT_TOOLBAR_STYLE,  
    UINT uiID=(UINT)-1,  
    DWORD dwControlBarStyle=0);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pParentWnd*  
 Outlook バー ペイン コントロールの親ウィンドウを指定します。 `NULL` にすることはできません。  
  
 [in]*dwStyle*  
 ウィンドウ スタイル。  ウィンドウ スタイルの一覧は、次を参照してください。[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)です。  
  
 [in]*uiID*  
 コントロールの id。 有効にするのには一意である必要があります、コントロールの状態を保存します。  
  
 [in]*dwControlBarStyle*  
 Outlook バーからデタッチされるときに、Outlook バー ペイン コントロールの動作を定義する特別なスタイルを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功した場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 構築するために、`CMFCOutlookBarPane`オブジェクト、まず、コンス トラクターを呼び出すし、呼び出す`Create`、Outlook バー ペインのコントロールを作成しにアタッチする、`CMFCOutlookBarPane`オブジェクト。  
  
 詳細については`dwControlBarStyle`を参照してください[cbasepane::createex](../../mfc/reference/cbasepane-class.md#createex)です。  
  
##  <a name="enablecontextmenuitems"></a>  CMFCOutlookBarPane::EnableContextMenuItems  
 カスタマイズ モードで表示するショートカット メニュー項目を指定します。  
  
```  
virtual BOOL EnableContextMenuItems(
    CMFCToolBarButton* pButton,  
    CMenu* pPopup);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pButton*  
 ユーザーがクリックしたツール バー ボタンへのポインター。  
  
 [in]*pPopup*  
 ショートカット メニューへのポインター。  
  
### <a name="return-value"></a>戻り値  
 返します`TRUE`、ショートカット メニューは、それ以外の表示されている必要がある場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 カスタマイズ モードに、フレームワークによって表示される framework 標準のショートカット メニューを変更するには、このメソッドをオーバーライドします。  
  
 既定の実装は、カスタマイズ モードをチェック ( [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)) に設定されている場合と`TRUE`、以外のすべてのショートカット メニュー項目を無効に**削除**です。 次に、入力パラメーターを渡すだけ`CMFCToolBar::EnableContextMenuItems`です。  
  
> [!NOTE]
> *コンテキスト メニュー*ショートカット メニューの同意語です。  
  
##  <a name="enablepagescrollmode"></a>  CMFCOutlookBarPane::EnablePageScrollMode  
 Outlook バー ペインのスクロール バーの矢印がページごとまたはボタンをクリックしてボタンのボタンの一覧を進めるかどうかを指定します。  
  
```  
void EnablePageScrollMode(BOOL bPageScroll=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bPageScroll*  
 場合`TRUE`ページのスクロール モードを有効にします。 場合`FALSE`ページのスクロール モードを無効にします。  
  
##  <a name="getregularcolor"></a>  CMFCOutlookBarPane::GetRegularColor  
 標準を返します (つまり、選択されていない) Outlook バー ペインのテキストの色。  
  
```  
DECLARE_MESSAGE_MAPCOLORREF GetRegularColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 色の RGB 値として現在のテキストの色。  
  
### <a name="remarks"></a>Remarks  
 使用して[CMFCOutlookBarPane::SetTextColor](#settextcolor)を Outlook バーの現在の (通常、選択された) テキストの色を設定します。 既定のテキストの色を取得するには呼び出すことによって、 [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371)で機能、`COLOR_WINDOW`インデックス。  
  
##  <a name="isbackgroundtexture"></a>  CMFCOutlookBarPane::IsBackgroundTexture  
 Outlook バー ペインに読み込まれる背景画像があるかどうかを判断します。  
  
```  
BOOL IsBackgroundTexture() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 表示する背景イメージがある場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 背景画像を追加するには呼び出すことによって[CMFCOutlookBarPane::SetBackImage](#setbackimage)関数。  
  
 使用して指定された色と背景を描画する背景イメージがない場合は、 [CMFCOutlookBarPane::SetBackColor](#setbackcolor)です。  
  
##  <a name="isdrawshadedhighlight"></a>  CMFCOutlookBarPane::IsDrawShadedHighlight  
 ボタンが強調表示され、背景画像が表示されるときにボタンの境界線が影付きにするかどうかを判断します。  
  
```  
BOOL IsDrawShadedHighlight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ボタンの境界線は網掛け; 場合それ以外の場合`FALSE`です。  
  
##  <a name="removeallbuttons"></a>  CMFCOutlookBarPane::RemoveAllButtons  
 Outlook バー ペインからすべてのボタンを削除します。  
  
```  
virtual void RemoveAllButtons();
```  
  
##  <a name="removebutton"></a>  CMFCOutlookBarPane::RemoveButton  
 指定されたコマンド ID を持つボタンを削除します  
  
```  
BOOL RemoveButton(UINT iIdCommand);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*iIdCommand*  
 削除するボタンのコマンド ID を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ボタンは正常に削除されました。`FALSE`場合は、指定されたコマンド ID が無効です。  
  
##  <a name="setbackcolor"></a>  CMFCOutlookBarPane::SetBackColor  
 Outlook バーの背景色を設定します。  
  
```  
void SetBackColor(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*色*  
 新しい背景色を指定します。  
  
### <a name="remarks"></a>Remarks  
 Outlook バーの現在の背景色を設定するには、この関数を呼び出します。 背景色は、背景画像がない場合にのみ使用されます。  
  
##  <a name="setbackimage"></a>  CMFCOutlookBarPane::SetBackImage  
 背景画像を設定します。  
  
```  
void SetBackImage(UINT uiImageID);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiImageID*  
 イメージのリソース ID を指定します  
  
### <a name="remarks"></a>Remarks  
 Outlook を設定するには、このメソッドを呼び出すバーの背景イメージ。 背景イメージの一覧が管理されている埋め込みによって[CMFCToolBarImages クラス](../../mfc/reference/cmfctoolbarimages-class.md)オブジェクト。  
  
##  <a name="setdefaultstate"></a>  CMFCOutlookBarPane::SetDefaultState  
 ボタンの元のセットを Outlook バー ペインをリセットします。  
  
```  
void SetDefaultState();
```  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、元のセットに Outlook バー ボタンを復元します。 同様に、このメソッドは`CMFCOutlookBarPane::RestoreOriginalstate`し Outlook バー ペインを再描画が開始されないことを除き、します。  
  
##  <a name="setextraspace"></a>  CMFCOutlookBarPane::SetExtraSpace  
 Outlook バー ペインのボタンの周囲に使用するパディングのピクセルの数を設定します。  
  
```  
void SetExtraSpace()  
```  
  
##  <a name="settextcolor"></a>  CMFCOutlookBarPane::SetTextColor  
 Outlook バー ペインの通常および強調表示されたテキストの色を設定します。  
  
```  
void SetTextColor(
    COLORREF clrRegText,  
    COLORREF clrSelText=0);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*clrRegText*  
 選択されていないテキストの新しい色を指定します。  
  
 [in]*clrSelText*  
 選択したテキストの新しい色を指定します。  
  
##  <a name="settransparentcolor"></a>  CMFCOutlookBarPane::SetTransparentColor  
 Outlook バー ペインの透明色を設定します。  
  
```  
void SetTransparentColor(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
 *色*  
 新しいの透明色を指定します。  
  
### <a name="remarks"></a>Remarks  
 透明のイメージを表示するには、透明色が必要です。 出現するすべてのイメージでは、この色は、背景色で描画されます。  前景色および背景画像の描画はありません。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarTabCtrl クラス](../../mfc/reference/cmfcoutlookbartabctrl-class.md)
