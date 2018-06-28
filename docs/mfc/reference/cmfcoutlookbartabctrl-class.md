---
title: CMFCOutlookBarTabCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::AddControl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::Create
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableInPlaceEdit
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableScrollButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetVisiblePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsMode2003
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowOptions
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetActiveTab
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetPageButtonTextAlign
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetToolbarImageList
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetVisiblePageButtons
dev_langs:
- C++
helpviewer_keywords:
- CMFCOutlookBarTabCtrl [MFC], AddControl
- CMFCOutlookBarTabCtrl [MFC], CanShowFewerPageButtons
- CMFCOutlookBarTabCtrl [MFC], CanShowMorePageButtons
- CMFCOutlookBarTabCtrl [MFC], Create
- CMFCOutlookBarTabCtrl [MFC], EnableAnimation
- CMFCOutlookBarTabCtrl [MFC], EnableInPlaceEdit
- CMFCOutlookBarTabCtrl [MFC], EnableScrollButtons
- CMFCOutlookBarTabCtrl [MFC], GetBorderSize
- CMFCOutlookBarTabCtrl [MFC], GetVisiblePageButtons
- CMFCOutlookBarTabCtrl [MFC], IsAnimation
- CMFCOutlookBarTabCtrl [MFC], IsMode2003
- CMFCOutlookBarTabCtrl [MFC], OnShowFewerPageButtons
- CMFCOutlookBarTabCtrl [MFC], OnShowMorePageButtons
- CMFCOutlookBarTabCtrl [MFC], OnShowOptions
- CMFCOutlookBarTabCtrl [MFC], SetActiveTab
- CMFCOutlookBarTabCtrl [MFC], SetBorderSize
- CMFCOutlookBarTabCtrl [MFC], SetPageButtonTextAlign
- CMFCOutlookBarTabCtrl [MFC], SetToolbarImageList
- CMFCOutlookBarTabCtrl [MFC], SetVisiblePageButtons
ms.assetid: b1f2b3f7-cc59-49a3-99d8-7ff9b37c044b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d30ad25a21bf380dd7687ccd0da0fb261aeeb023
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37042314"
---
# <a name="cmfcoutlookbartabctrl-class"></a>CMFCOutlookBarTabCtrl Class
Microsoft Outlook の **ナビゲーション ウィンドウ** と同じ外観を持つタブ コントロールです。  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]    
## <a name="syntax"></a>構文  
  
```  
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|既定のコンストラクター|  
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCOutlookBarTabCtrl::AddControl](#addcontrol)|Outlook バーで、新しいタブとしては、Windows コントロールを追加します。|  
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|フレームワークによって呼び出されるとき、ユーザーに表示される編集ボックスのサイズを調べるための名前を変更タブです。(`CMFCBaseTabCtrl::CalcRectEdit` をオーバーライドします)。|  
|[CMFCOutlookBarTabCtrl::CanShowFewerPageButtons](#canshowfewerpagebuttons)|現在表示されているよりも少ない Outlook バー タブ ページのボタンを表示できる場合を判断するのにサイズ変更操作中に、フレームワークによって呼び出されます。|  
|[CMFCOutlookBarTabCtrl::CanShowMorePageButtons](#canshowmorepagebuttons)|現在表示されているよりもさらに Outlook バー タブのページ ボタンを表示できる場合を判断するのにサイズ変更操作中に、フレームワークによって呼び出されます。|  
|[CMFCOutlookBarTabCtrl::Create](#create)|Outlook バー タブのコントロールを作成します。|  
|`CMFCOutlookBarTabCtrl::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation)|アクティブなタブの間で切り替え中に実行されるアニメーションが有効になっているかどうかを指定します。|  
|[CMFCOutlookBarTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|ユーザーが Outlook バーのタブ ボタンのテキスト ラベルを変更できるかどうかを指定します。 (上書き[CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit))。|  
|[CMFCOutlookBarTabCtrl::EnableScrollButtons](#enablescrollbuttons)|ユーザーが Outlook バー ペイン上のボタン間をスクロールできるボタンを有効にするためにフレームワークによって呼び出されます。|  
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|指定したポイントを含むウィンドウを識別します。 (上書き[CMFCBaseTabCtrl::FindTargetWnd](../../mfc/reference/cmfcbasetabctrl-class.md#findtargetwnd))。|  
|[CMFCOutlookBarTabCtrl::GetBorderSize](#getbordersize)|Outlook のタブ コントロールの境界線のサイズを返します。|  
|`CMFCOutlookBarTabCtrl::GetTabArea`|タブ コントロールのタブ領域の位置とサイズを取得します。 (上書き[CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea))。|  
|`CMFCOutlookBarTabCtrl::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCOutlookBarTabCtrl::GetVisiblePageButtons](#getvisiblepagebuttons)||  
|[CMFCOutlookBarTabCtrl::IsAnimation](#isanimation)|アクティブなタブの間で切り替え中に実行されるアニメーションが有効になっているかどうかを判断します。|  
|[CMFCOutlookBarTabCtrl::IsMode2003](#ismode2003)|かどうか、Outlook バー タブのコントロールが Microsoft Outlook 2003 のエミュレーション モードを決定します。|  
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|ポイントがタブ領域の内部かどうかを判断します。 (上書き[CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea))。|  
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|タブが切り離し可能であるかどうかを判断します。 (上書き[CMFCBaseTabCtrl::IsTabDetachable](../../mfc/reference/cmfcbasetabctrl-class.md#istabdetachable))。|  
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|タブを挿入または削除されたときに、フレームワークによって呼び出されます。 (`CMFCBaseTabCtrl::OnChangeTabs` をオーバーライドします)。|  
|[CMFCOutlookBarTabCtrl::OnShowFewerPageButtons](#onshowfewerpagebuttons)|表示されているタブ ページ ボタンの数を削減するためにフレームワークによって呼び出されます。|  
|[CMFCOutlookBarTabCtrl::OnShowMorePageButtons](#onshowmorepagebuttons)|表示されているタブ ページ ボタンの数を増やすために、フレームワークによって呼び出されます。|  
|[CMFCOutlookBarTabCtrl::OnShowOptions](#onshowoptions)|表示、**ナビゲーション ウィンドウのオプション**ダイアログ。|  
|`CMFCOutlookBarTabCtrl::RecalcLayout`|タブ コントロールの内部レイアウトを再計算されます。 (上書き[CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout))。|  
|[CMFCOutlookBarTabCtrl::SetActiveTab](#setactivetab)|アクティブなタブを設定します。(上書き[CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab))。|  
|[CMFCOutlookBarTabCtrl::SetBorderSize](#setbordersize)|Outlook のタブ コントロールの境界線のサイズを設定します。|  
|[CMFCOutlookBarTabCtrl::SetPageButtonTextAlign](#setpagebuttontextalign)|Outlook バーのタブ ボタンのテキスト ラベルの配置を設定します。|  
|[CMFCOutlookBarTabCtrl::SetToolbarImageList](#settoolbarimagelist)|Outlook 2003 モードで、Outlook バーの下部に表示されるアイコンを含むビットマップを設定 (を参照してください[CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md))。|  
|[CMFCOutlookBarTabCtrl::SetVisiblePageButtons](#setvisiblepagebuttons)||  
  
## <a name="remarks"></a>Remarks  
 ドッキングのサポートのある Outlook バーを作成するには、使用、 `CMFCOutlookBar` Outlook バー タブ コントロールをホストするオブジェクト。 詳細については、次を参照してください。 [CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)です。  
  
## <a name="example"></a>例  
 次の例では、初期化、`CMFCOutlookBarTabCtrl`オブジェクトをさまざまなメソッドを使用して、`CMFCOutlookBarTabCtrl`クラスです。 例では、Outlook バーのタブのページ ボタンのテキスト ラベルのインプレース編集を有効にする、アニメーションを有効にする、ユーザーが Outlook バー ペイン上のボタンをスクロールして、Outlook タブ続きの境界線のサイズの設定を有効にするスクロール ハンドルを有効にする方法を示しています。ロール、および Outlook バーのタブ ボタンのテキスト ラベルの配置を設定します。 このコード スニペットの一部である、 [Outlook デモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_OutlookDemo#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_1.cpp)]  
[!code-cpp[NVC_MFC_OutlookDemo#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [から派生しているのではない](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxoutlookbartabctrl.h  
  
##  <a name="addcontrol"></a>  CMFCOutlookBarTabCtrl::AddControl  
 Outlook バーで、新しいタブとしては、Windows コントロールを追加します。  
  
```  
void AddControl(
    CWnd* pWndCtrl,  
    LPCTSTR lpszName,  
    int nImageID=-1,  
    BOOL bDetachable=TRUE,  
    DWORD dwControlBarStyle=AFX_CBRS_FLOAT |  AFX_CBRS_CLOSE | AFX_CBRS_RESIZE |  CBRS_AFX_AUTOHIDE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pWndCtrl*  
 追加するコントロールへのポインター。  
  
 [in]*lpszName*  
 タブの名前を指定します。  
  
 [in]*bDetachable*  
 場合`TRUE`のページが切り離し可能として作成されます。  
  
 [in]*nImageID*  
 新しいタブに表示されるイメージの内部のイメージ リストのイメージのインデックス。  
  
 [in]*dwControlBarStyle*  
 指定、afx _ `CBRS_`* ラップされたドッキング ペインのスタイル。  
  
### <a name="remarks"></a>Remarks  
 Outlook バーの新しいページにコントロールを追加するのにには、この関数を使用します。  
  
 この関数で内部的には[cmfcbasetabctrl::addtab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab)です。  
  
 設定した場合*bDetachable*に`TRUE`、`AddControl`内部的に作成、`CDockablePaneAdapter`オブジェクトを追加したコントロールをラップします。 ランタイム クラスにタブ付きウィンドウのランタイム クラスが自動的に設定`CMFCOutlookBar`とフローティング フレームのランタイム クラス`CMultiPaneFrameWnd`です。  
  
### <a name="example"></a>例  
 次の例で使用する方法、`AddControl`メソッドで、`CMFCOutlookBarTabCtrl`クラスです。 このコード スニペットの一部である、 [Outlook デモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_OutlookDemo#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_3.cpp)]  
  
##  <a name="canshowfewerpagebuttons"></a>  CMFCOutlookBarTabCtrl::CanShowFewerPageButtons  
 サイズ変更が、現在表示されているよりも少ない Outlook バー タブ ページのボタンを表示できるかどうかを決定する操作中に、フレームワークによって呼び出されます。  
  
```  
virtual BOOL CanShowFewerPageButtons() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 複数のボタンがある場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 Outlook バー タブ コントロールは動的に追加またはタブをどの程度のスペースが使用可能なに応じて表示から削除します。 このメソッドは、そのプロセスを支援するためにフレームワークによって使用されます。  
  
##  <a name="canshowmorepagebuttons"></a>  CMFCOutlookBarTabCtrl::CanShowMorePageButtons  
 サイズ変更が、現在表示されているよりもさらに Outlook バー タブのページ ボタンを表示できるかどうかを決定する操作中に、フレームワークによって呼び出されます。  
  
```  
virtual BOOL CanShowMorePageButtons() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 現在表示されていないボタンがある場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 Outlook バー タブ コントロールは、動的に追加または空き方法に応じて、表示からタブを削除します。 このメソッドは、そのプロセスを支援するためにフレームワークによって使用されます。  
  
##  <a name="create"></a>  CMFCOutlookBarTabCtrl::Create  
 Outlook バー タブのコントロールを作成します。  
  
```  
virtual BOOL Create(
    const CRect& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*rect*  
 初期サイズと位置をピクセル単位で指定します。  
  
 [in]*pParentWnd*  
 親ウィンドウへのポインター。 `NULL` にすることはできません。  
  
 [in]*nID*  
 コントロールの id。  
  
### <a name="return-value"></a>戻り値  
 コントロールが正常に作成されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 通常、outlook バー タブ コントロールが作成されたときに[CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)プロセスの WM_CREATE メッセージを制御します。  
  
##  <a name="enableanimation"></a>  CMFCOutlookBarTabCtrl::EnableAnimation  
 アクティブなタブの間で切り替え中に実行されるアニメーションが有効になっているかどうかを指定します。  
  
```  
static void EnableAnimation(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bEnable*  
 アニメーションを有効または無効になっているかどうかを指定します。  
  
### <a name="remarks"></a>Remarks  
 アニメーションを無効にするには、この関数を呼び出します。 ユーザーは、タブ ページを開き、ページのキャプションはアニメーションが有効になっている場合に上下をスライドします。 アニメーションが無効になっている場合、ページがアクティブになった直後にします。  
  
 既定では、アニメーションが有効にします。  
  
##  <a name="enableinplaceedit"></a>  CMFCOutlookBarTabCtrl::EnableInPlaceEdit  
 ユーザーが Outlook バーのタブのページ ボタンのテキスト ラベルを変更できるかどうかを指定します。  
  
```  
virtual void EnableInPlaceEdit(BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 *bEnable*  
 場合`TRUE`、テキスト ラベルのインプレース編集を有効にします。 場合`FALSE`、インプレース編集を無効にします。  
  
### <a name="remarks"></a>Remarks  
 この関数では、有効またはインプレースでのタブ ページ ボタンのテキスト ラベルの編集を無効にします。 既定では、インプレース編集は無効です。  
  
##  <a name="enablescrollbuttons"></a>  CMFCOutlookBarTabCtrl::EnableScrollButtons  
 ユーザーが Outlook バー ペイン上のボタン間をスクロールできるスクロール ハンドルを有効にするためにフレームワークによって呼び出されます。  
  
```  
void EnableScrollButtons(
    BOOL bEnable = TRUE,  
    BOOL bIsUp = TRUE,  
    BOOL bIsDown = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bEnable*  
 スクロール ボタンを表示するかどうかを判断します。  
  
 [in]*bIsUp*  
 上部のスクロール バーが表示されるかどうかを判断します。  
  
 [in]*bIsDown*  
 下部のスクロール バーが表示されるかどうかを判断します。  
  
### <a name="remarks"></a>Remarks  
 スクロール ボタンの表示を有効にします。 このメソッドは、スクロール ボタンを復元するアクティブなタブが変更されたときにフレームワークによって呼び出されます。  
  
##  <a name="getbordersize"></a>  CMFCOutlookBarTabCtrl::GetBorderSize  
 Outlook のタブ コントロールの境界線のサイズを返します。  
  
```  
int GetBorderSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 境界線のサイズ (ピクセル)。  
  
##  <a name="getvisiblepagebuttons"></a>  CMFCOutlookBarTabCtrl::GetVisiblePageButtons  

  
```  
int GetVisiblePageButtons() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="isanimation"></a>  CMFCOutlookBarTabCtrl::IsAnimation  
 アクティブなタブの間で切り替え中に実行されるアニメーションが有効になっているかどうかを指定します。  
  
```  
static BOOL IsAnimation();
```  
  
### <a name="return-value"></a>戻り値  
 アニメーションが有効である場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 呼び出す、 [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation)を有効にするにまたはアニメーションを無効にします。  
  
##  <a name="ismode2003"></a>  CMFCOutlookBarTabCtrl::IsMode2003  
 Outlook バー タブ コントロールが、Microsoft Outlook 2003 をエミュレートするモードにするかどうかを判断します。  
  
```  
BOOL IsMode2003() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` Outlook タブ コントロール バーが Outlook 2003 モードである場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 この値によって設定されます[CMFCOutlookBar::SetMode2003](../../mfc/reference/cmfcoutlookbar-class.md#setmode2003)です。  
  
##  <a name="onshowfewerpagebuttons"></a>  CMFCOutlookBarTabCtrl::OnShowFewerPageButtons  
 表示されているタブ ページ ボタンの数を削減するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnShowFewerPageButtons();
```  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、コントロールがサイズ変更されたときに表示されるページ タブのボタンの数を調整します。  
  
##  <a name="onshowmorepagebuttons"></a>  CMFCOutlookBarTabCtrl::OnShowMorePageButtons  
 表示されているタブ ページ ボタンの数を増やすために、フレームワークによって呼び出されます。  
  
```  
virtual void OnShowMorePageButtons();
```  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、コントロールがサイズ変更されたときに表示されているタブ ページ ボタンの数を調整します。  
  
##  <a name="onshowoptions"></a>  CMFCOutlookBarTabCtrl::OnShowOptions  
 表示、**ナビゲーション ウィンドウのオプション** ダイアログ ボックス。  
  
```  
virtual void OnShowOptions();
```  
  
### <a name="remarks"></a>Remarks  
 **ナビゲーション ウィンドウのオプション** ダイアログ ボックスで、ユーザーにタブ ページのボタンが、表示するかを選択および順序が表示されます。  
  
 このメソッドは、フレームワークによって、ユーザーを選択すると、**ナビゲーション ウィンドウのオプション**コントロールのカスタマイズ メニューからメニュー項目。  
  
##  <a name="setactivetab"></a>  CMFCOutlookBarTabCtrl::SetActiveTab  
 アクティブなタブを設定します。アクティブなタブは、そのコンテンツが表示されると、開いている 1 つです。  
  
```  
virtual BOOL SetActiveTab(int iTab);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*iTab*  
 開く タブの 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定したタブが正常に開かれた場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 アクティブなタブの設定の視覚効果は、アニメーションを有効にするかどうかによって異なります。 詳細については、次を参照してください。 [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation)です。  
  
##  <a name="setbordersize"></a>  CMFCOutlookBarTabCtrl::SetBorderSize  
 Outlook のタブ コントロールの境界線のサイズを設定します。  
  
```  
void SetBorderSize(int nBorderSize);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nBorderSize*  
 新しい境界線のサイズをピクセル単位で指定します。  
  
### <a name="remarks"></a>Remarks  
 新しい境界線のサイズを設定し、outlook のウィンドウ レイアウトを再計算します。  
  
##  <a name="setpagebuttontextalign"></a>  CMFCOutlookBarTabCtrl::SetPageButtonTextAlign  
 Outlook バーのタブ ボタンのテキスト ラベルの配置を設定します。  
  
```  
void SetPageButtonTextAlign(
    UINT uiAlign,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiAlign*  
 テキストの配置を指定します。  
  
 [in]*bRedraw*  
 場合`TRUE`outlook のウィンドウが再描画されます。  
  
### <a name="remarks"></a>Remarks  
 この関数を使用すると、ページのボタンのテキストの配置を変更できます。  
  
 *uiAlign*値は次のいずれかになります。  
  
|定数|説明|  
|--------------|-------------|  
|TA_LEFT|左揃え|  
|TA_CENTER|中央揃え|  
|TA_RIGHT|右揃え|  
  
 既定値は、TA_CENTER です。  
  
##  <a name="settoolbarimagelist"></a>  CMFCOutlookBarTabCtrl::SetToolbarImageList  
 Outlook 2003 モードで、Outlook バーの下部に表示されるアイコンを含むビットマップを設定します。  
  
```  
BOOL SetToolbarImageList(
    UINT uiID,  
    int cx,  
    COLORREF clrTransp=RGB(255, 0, 255));
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiID*  
 読み込むイメージのリソース ID を指定します。  
  
 [in]*cx*  
 イメージ リストには、ピクセル単位でイメージの幅を指定します。  
  
 [in]*clrTransp*  
 透明色を指定する RGB 値。  
  
### <a name="return-value"></a>戻り値  
 返します`TRUE`成功した場合、それ以外の場合を返します`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 この関数を使用すると、Microsoft Office 2003 モードでのツール バー ボタンに表示されるイメージがイメージ リストをアタッチできます。 イメージ インデックス ページのインデックスに対応します。  
  
 Microsoft Office 2003 モードではない場合、このメソッドを呼び出すことはできません。 詳細については、次を参照してください。 [CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)です。  
  
##  <a name="setvisiblepagebuttons"></a>  CMFCOutlookBarTabCtrl::SetVisiblePageButtons  

  
```  
void SetVisiblePageButtons(int nVisiblePageButtons);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nVisiblePageButtons*  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md)   
 [CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarPane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md)
