---
description: '詳細情報: CMFCOutlookBarTabCtrl クラス'
title: CMFCOutlookBarTabCtrl Class
ms.date: 10/18/2018
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
ms.openlocfilehash: b969fbb592fc3098dc8d287004fab90da6f30111
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333482"
---
# <a name="cmfcoutlookbartabctrl-class"></a>CMFCOutlookBarTabCtrl Class

Microsoft Outlook の **ナビゲーション ウィンドウ** と同じ外観を持つタブ コントロールです。
詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

## <a name="syntax"></a>構文

```
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|既定のコンストラクターです。|
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCOutlookBarTabCtrl:: AddControl](#addcontrol)|Windows コントロールを Outlook バーの新しいタブとして追加します。|
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|ユーザーがタブの名前を変更したときに表示される編集ボックスのサイズを決定するために、フレームワークによって呼び出されます (をオーバーライド `CMFCBaseTabCtrl::CalcRectEdit` します)。|
|[CMFCOutlookBarTabCtrl:: CanShowFewerPageButtons](#canshowfewerpagebuttons)|サイズ変更操作中にフレームワークによって呼び出され、現在表示されている数よりも多くの Outlook バータブページボタンを表示できるかどうかを判断します。|
|[CMFCOutlookBarTabCtrl:: CanShowMorePageButtons](#canshowmorepagebuttons)|サイズ変更操作中にフレームワークによって呼び出され、現在表示されているものよりも多くの Outlook バータブページボタンを表示できるかどうかを決定します。|
|[CMFCOutlookBarTabCtrl:: Create](#create)|Outlook バータブコントロールを作成します。|
|`CMFCOutlookBarTabCtrl::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|[CMFCOutlookBarTabCtrl:: EnableAnimation](#enableanimation)|アクティブなタブ間の切り替え中に発生するアニメーションを有効にするかどうかを指定します。|
|[CMFCOutlookBarTabCtrl:: Enableinplace Edit](#enableinplaceedit)|ユーザーが Outlook バーのタブボタンのテキストラベルを変更できるかどうかを指定します。 ( [CMFCBaseTabCtrl:: Enableinplace edit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit)をオーバーライドします)。|
|[CMFCOutlookBarTabCtrl:: EnableScrollButtons](#enablescrollbuttons)|ユーザーが Outlook バーペイン上のボタンをスクロールできるようにするボタンを有効にするために、フレームワークによって呼び出されます。|
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|指定したポイントを含むペインを識別します。 ( [CMFCBaseTabCtrl:: FindTargetWnd](../../mfc/reference/cmfcbasetabctrl-class.md#findtargetwnd)をオーバーライドします)。|
|[CMFCOutlookBarTabCtrl:: GetBorderSize](#getbordersize)|Outlook タブコントロールの境界線のサイズを返します。|
|`CMFCOutlookBarTabCtrl::GetTabArea`|タブコントロールのタブ領域のサイズと位置を取得します。 ( [CMFCBaseTabCtrl:: GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea)をオーバーライドします)。|
|`CMFCOutlookBarTabCtrl::GetThisClass`|このクラス型に関連付けられている [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[CMFCOutlookBarTabCtrl:: GetVisiblePageButtons](#getvisiblepagebuttons)||
|[CMFCOutlookBarTabCtrl:: IsAnimation](#isanimation)|アクティブなタブ間の切り替え中に発生するアニメーションを有効にするかどうかを決定します。|
|[CMFCOutlookBarTabCtrl:: IsMode2003](#ismode2003)|Outlook バータブコントロールが、Microsoft Outlook 2003 をエミュレートするモードであるかどうかを判断します。|
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|ポイントがタブ領域内にあるかどうかを判断します。 ( [CMFCBaseTabCtrl:: isp/area](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea)をオーバーライドします)。|
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|タブが切り離し可能であるかどうかを判断します。 ( [CMFCBaseTabCtrl:: IsTabDetachable](../../mfc/reference/cmfcbasetabctrl-class.md#istabdetachable)をオーバーライドします)。|
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|タブが挿入または削除されると、フレームワークによって呼び出されます。 ( `CMFCBaseTabCtrl::OnChangeTabs`をオーバーライドします)。|
|[CMFCOutlookBarTabCtrl:: OnShowFewerPageButtons](#onshowfewerpagebuttons)|表示されているタブページのボタンの数を減らすために、フレームワークによって呼び出されます。|
|[CMFCOutlookBarTabCtrl:: OnShowMorePageButtons](#onshowmorepagebuttons)|表示されているタブページのボタンの数を増やすために、フレームワークによって呼び出されます。|
|[CMFCOutlookBarTabCtrl:: OnShowOptions](#onshowoptions)|**ナビゲーションウィンドウ** の [オプション] ダイアログを表示します。|
|`CMFCOutlookBarTabCtrl::RecalcLayout`|タブコントロールの内部レイアウトを再計算します。 ( [CMFCBaseTabCtrl:: RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout)をオーバーライドします。)|
|[CMFCOutlookBarTabCtrl:: SetActiveTab](#setactivetab)|アクティブなタブを設定します ( [CMFCBaseTabCtrl:: SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab)をオーバーライドします)。|
|[CMFCOutlookBarTabCtrl:: SetBorderSize](#setbordersize)|Outlook タブコントロールの境界線のサイズを設定します。|
|[CMFCOutlookBarTabCtrl:: SetPageButtonTextAlign](#setpagebuttontextalign)|Outlook バーのタブボタンのテキストラベルの配置を設定します。|
|[CMFCOutlookBarTabCtrl:: SetToolbarImageList](#settoolbarimagelist)|Outlook 2003 モードの Outlook バーの下部に表示されるアイコンを含むビットマップを設定します (「 [Cmfcoutlookbar クラス](../../mfc/reference/cmfcoutlookbar-class.md)」を参照してください)。|
|[CMFCOutlookBarTabCtrl:: SetVisiblePageButtons](#setvisiblepagebuttons)||

## <a name="remarks"></a>解説

ドッキングがサポートされている Outlook バーを作成するには、オブジェクトを使用し `CMFCOutlookBar` て outlook バータブコントロールをホストします。 詳細については、「 [Cmfcoutlookbar クラス](../../mfc/reference/cmfcoutlookbar-class.md)」を参照してください。

## <a name="example"></a>例

次の例は、オブジェクトを初期化し、クラスのさまざまなメソッドを使用する方法を示して `CMFCOutlookBarTabCtrl` `CMFCOutlookBarTabCtrl` います。 この例では、outlook バーのタブページのボタンでテキストラベルの埋め込み先編集を有効にする方法、アニメーションを有効にする方法、ユーザーが outlook バーウィンドウのボタンをスクロールできるようにするスクロールハンドルを有効にする方法、outlook タブコントロールの境界線のサイズを設定する方法、および Outlook バーのタブボタンにテキストラベルの配置を設定 このコードスニペットは、 [Outlook Demo サンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_OutlookDemo#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_1.cpp)]
[!code-cpp[NVC_MFC_OutlookDemo#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)

[CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxoutlookbartabctrl

## <a name="cmfcoutlookbartabctrladdcontrol"></a><a name="addcontrol"></a> CMFCOutlookBarTabCtrl:: AddControl

Windows コントロールを Outlook バーの新しいタブとして追加します。

```cpp
void AddControl(
    CWnd* pWndCtrl,
    LPCTSTR lpszName,
    int nImageID=-1,
    BOOL bDetachable=TRUE,
    DWORD dwControlBarStyle=AFX_CBRS_FLOAT |  AFX_CBRS_CLOSE | AFX_CBRS_RESIZE |  CBRS_AFX_AUTOHIDE);
```

### <a name="parameters"></a>パラメーター

*pWndCtrl*<br/>
から追加するコントロールへのポインター。

*lpszName*<br/>
からタブの名前を指定します。

*bDetachable 可能*<br/>
からTRUE の場合、ページは切り離し可能として作成されます。

*nImageID*<br/>
から新しいタブに表示されるイメージの内部イメージリスト内のイメージインデックス。

*dwControlBarStyle*<br/>
からラップされたドッキングペインの AFX_ CBRS_ * スタイルを指定します。

### <a name="remarks"></a>解説

Outlook バーの新しいページとしてコントロールを追加するには、この関数を使用します。

この関数 [は、CMFCBaseTabCtrl:: AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab)で内部的にを呼び出します。

*Bdetachable* を TRUE に設定した場合、は `AddControl` 内部でオブジェクトを作成 `CDockablePaneAdapter` し、追加されたコントロールをラップします。 このメソッドは、タブ付きウィンドウのランタイムクラスをのランタイムクラスに、フローティングフレームのランタイムクラスをに自動的に設定し `CMFCOutlookBar` `CMultiPaneFrameWnd` ます。

### <a name="example"></a>例

クラスのメソッドを使用する方法を次の例に示し `AddControl` `CMFCOutlookBarTabCtrl` ます。 このコードスニペットは、 [Outlook Demo サンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_OutlookDemo#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_3.cpp)]

## <a name="cmfcoutlookbartabctrlcanshowfewerpagebuttons"></a><a name="canshowfewerpagebuttons"></a> CMFCOutlookBarTabCtrl:: CanShowFewerPageButtons

サイズ変更操作中にフレームワークによって呼び出され、現在表示されている数よりも多くの Outlook バータブページボタンを表示できるかどうかを判断します。

```
virtual BOOL CanShowFewerPageButtons() const;
```

### <a name="return-value"></a>戻り値

複数のボタンがある場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

Outlook バータブコントロールでは、使用可能な領域に応じて、表示のタブを動的に追加または削除します。 このメソッドは、このプロセスを支援するためにフレームワークによって使用されます。

## <a name="cmfcoutlookbartabctrlcanshowmorepagebuttons"></a><a name="canshowmorepagebuttons"></a> CMFCOutlookBarTabCtrl:: CanShowMorePageButtons

サイズ変更操作中にフレームワークによって呼び出され、現在表示されているものよりも多くの Outlook バータブページボタンを表示できるかどうかを決定します。

```
virtual BOOL CanShowMorePageButtons() const;
```

### <a name="return-value"></a>戻り値

現在表示されていないボタンがある場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

Outlook バータブコントロールでは、使用できる領域の大きさに応じて、画面のタブを動的に追加または削除します。 このメソッドは、このプロセスを支援するためにフレームワークによって使用されます。

## <a name="cmfcoutlookbartabctrlcreate"></a><a name="create"></a> CMFCOutlookBarTabCtrl:: Create

Outlook バータブコントロールを作成します。

```
virtual BOOL Create(
    const CRect& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
から初期のサイズと位置をピクセル単位で指定します。

*pParentWnd*<br/>
から親ウィンドウをポイントします。 NULL にすることはできません。

*nID*<br/>
からコントロール ID。

### <a name="return-value"></a>戻り値

コントロールが正常に作成された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

通常、outlook バータブコントロールは、 [Cmfcoutlookbar クラス](../../mfc/reference/cmfcoutlookbar-class.md) がプロセスの WM_CREATE メッセージを制御するときに作成されます。

## <a name="cmfcoutlookbartabctrlenableanimation"></a><a name="enableanimation"></a> CMFCOutlookBarTabCtrl:: EnableAnimation

アクティブなタブ間の切り替え中に発生するアニメーションを有効にするかどうかを指定します。

```
static void EnableAnimation(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
からアニメーションを有効にするか無効にするかを指定します。

### <a name="remarks"></a>解説

アニメーションを有効または無効にするには、この関数を呼び出します。 ユーザーがタブページを開くと、アニメーションが有効になっている場合、ページのキャプションが上または下にスライドします。 アニメーションが無効になっている場合は、ページがすぐにアクティブになります。

既定では、アニメーションが有効になっています。

## <a name="cmfcoutlookbartabctrlenableinplaceedit"></a><a name="enableinplaceedit"></a> CMFCOutlookBarTabCtrl:: Enableinplace Edit

ユーザーが Outlook バーのタブページボタンのテキストラベルを変更できるかどうかを指定します。

```
virtual void EnableInPlaceEdit(BOOL bEnable);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
TRUE の場合は、テキストラベルの埋め込み先編集を有効にします。 FALSE の場合は、埋め込み先編集を無効にします。

### <a name="remarks"></a>解説

タブページのボタンのテキストラベルのインプレース編集を有効または無効にするには、この関数を呼び出します。 既定では、埋め込み先編集は無効になっています。

## <a name="cmfcoutlookbartabctrlenablescrollbuttons"></a><a name="enablescrollbuttons"></a> CMFCOutlookBarTabCtrl:: EnableScrollButtons

ユーザーが Outlook バーペイン上のボタンをスクロールできるようにするスクロールハンドルを有効にするために、フレームワークによって呼び出されます。

```cpp
void EnableScrollButtons(
    BOOL bEnable = TRUE,
    BOOL bIsUp = TRUE,
    BOOL bIsDown = TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
からスクロールボタンを表示するかどうかを決定します。

*bIsUp*<br/>
から上のスクロールバーを表示するかどうかを決定します。

*bIsDown*<br/>
から下部のスクロールバーを表示するかどうかを決定します。

### <a name="remarks"></a>解説

スクロールボタンの表示を有効にします。 このメソッドは、アクティブなタブがスクロールボタンを復元するために変更されたときにフレームワークによって呼び出されます。

## <a name="cmfcoutlookbartabctrlgetbordersize"></a><a name="getbordersize"></a> CMFCOutlookBarTabCtrl:: GetBorderSize

Outlook タブコントロールの境界線のサイズを返します。

```
int GetBorderSize() const;
```

### <a name="return-value"></a>戻り値

境界線のサイズ (ピクセル単位)。

## <a name="cmfcoutlookbartabctrlgetvisiblepagebuttons"></a><a name="getvisiblepagebuttons"></a> CMFCOutlookBarTabCtrl:: GetVisiblePageButtons

```
int GetVisiblePageButtons() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcoutlookbartabctrlisanimation"></a><a name="isanimation"></a> CMFCOutlookBarTabCtrl:: IsAnimation

アクティブなタブ間の切り替え中に発生するアニメーションを有効にするかどうかを指定します。

```
static BOOL IsAnimation();
```

### <a name="return-value"></a>戻り値

アニメーションが有効な場合は0以外の場合は。それ以外の場合は0です。

### <a name="remarks"></a>解説

アニメーションを有効または無効にするには、 [CMFCOutlookBarTabCtrl:: EnableAnimation](#enableanimation) 関数を呼び出します。

## <a name="cmfcoutlookbartabctrlismode2003"></a><a name="ismode2003"></a> CMFCOutlookBarTabCtrl:: IsMode2003

Outlook バータブコントロールが、Microsoft Outlook 2003 をエミュレートするモードであるかどうかを判断します。

```
BOOL IsMode2003() const;
```

### <a name="return-value"></a>戻り値

Outlook バータブコントロールが Outlook 2003 モードの場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

この値は、 [Cmfcoutlookbar:: SetMode2003](../../mfc/reference/cmfcoutlookbar-class.md#setmode2003)によって設定されます。

## <a name="cmfcoutlookbartabctrlonshowfewerpagebuttons"></a><a name="onshowfewerpagebuttons"></a> CMFCOutlookBarTabCtrl:: OnShowFewerPageButtons

表示されているタブページのボタンの数を減らすために、フレームワークによって呼び出されます。

```
virtual void OnShowFewerPageButtons();
```

### <a name="remarks"></a>解説

このメソッドは、コントロールのサイズを変更するときに、表示するページタブのボタンの数を調整します。

## <a name="cmfcoutlookbartabctrlonshowmorepagebuttons"></a><a name="onshowmorepagebuttons"></a> CMFCOutlookBarTabCtrl:: OnShowMorePageButtons

表示されているタブページのボタンの数を増やすために、フレームワークによって呼び出されます。

```
virtual void OnShowMorePageButtons();
```

### <a name="remarks"></a>解説

このメソッドは、コントロールのサイズが変更されたときに表示されるタブページのボタンの数を調整します。

## <a name="cmfcoutlookbartabctrlonshowoptions"></a><a name="onshowoptions"></a> CMFCOutlookBarTabCtrl:: OnShowOptions

[ **ナビゲーションウィンドウのオプション** ] ダイアログボックスを表示します。

```
virtual void OnShowOptions();
```

### <a name="remarks"></a>解説

[ **ナビゲーションウィンドウのオプション** ] ダイアログボックスを使用すると、表示するタブページのボタンと、表示される順序を選択できます。

このメソッドは、ユーザーがコントロールのカスタマイズメニューから **ナビゲーションウィンドウ** の [オプション] メニュー項目を選択したときに、フレームワークによって呼び出されます。

## <a name="cmfcoutlookbartabctrlsetactivetab"></a><a name="setactivetab"></a> CMFCOutlookBarTabCtrl:: SetActiveTab

アクティブなタブを設定します。アクティブなタブは、開いているもので、その内容が表示されます。

```
virtual BOOL SetActiveTab(int iTab);
```

### <a name="parameters"></a>パラメーター

*iTab*<br/>
から開くタブの0から始まるインデックス。

### <a name="return-value"></a>戻り値

指定したタブが正常に開かれた場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

[アクティブ] タブを設定した場合の視覚効果は、アニメーションを有効にしたかどうかによって異なります。 詳細については、「 [CMFCOutlookBarTabCtrl:: EnableAnimation](#enableanimation)」を参照してください。

## <a name="cmfcoutlookbartabctrlsetbordersize"></a><a name="setbordersize"></a> CMFCOutlookBarTabCtrl:: SetBorderSize

Outlook タブコントロールの境界線のサイズを設定します。

```cpp
void SetBorderSize(int nBorderSize);
```

### <a name="parameters"></a>パラメーター

*nBorderSize*<br/>
から新しい境界線のサイズをピクセル単位で指定します。

### <a name="remarks"></a>解説

新しい罫線のサイズを設定し、outlook のウィンドウレイアウトを再計算します。

## <a name="cmfcoutlookbartabctrlsetpagebuttontextalign"></a><a name="setpagebuttontextalign"></a> CMFCOutlookBarTabCtrl:: SetPageButtonTextAlign

Outlook バーのタブボタンのテキストラベルの配置を設定します。

```cpp
void SetPageButtonTextAlign(
    UINT uiAlign,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>パラメーター

*uiAlign*<br/>
からテキストの配置を指定します。

*より描画*<br/>
からTRUE の場合、outlook ウィンドウは再描画されます。

### <a name="remarks"></a>解説

ページボタンのテキストの配置を変更するには、この関数を使用します。

*Uialign* には、次のいずれかの値を指定できます。

|定数|説明|
|--------------|-------------|
|TA_LEFT|左揃え|
|TA_CENTER|中央揃え|
|TA_RIGHT|右揃え|

既定値は TA_CENTER です。

## <a name="cmfcoutlookbartabctrlsettoolbarimagelist"></a><a name="settoolbarimagelist"></a> CMFCOutlookBarTabCtrl:: SetToolbarImageList

Outlook 2003 モードの Outlook バーの下部に表示されるアイコンを含むビットマップを設定します。

```
BOOL SetToolbarImageList(
    UINT uiID,
    int cx,
    COLORREF clrTransp=RGB(255, 0, 255));
```

### <a name="parameters"></a>パラメーター

*uiID*<br/>
から読み込むイメージのリソース ID を指定します。

*シリーズ*<br/>
からイメージリスト内のイメージの幅をピクセル単位で指定します。

*clrTransp*<br/>
から透明色を指定する RGB 値。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返します。それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

Microsoft Office 2003 モードのツールバーボタンに画像が表示されるイメージリストをアタッチするには、この関数を使用します。 イメージインデックスは、ページインデックスに対応している必要があります。

Microsoft Office 2003 モードでない場合は、このメソッドを呼び出さないでください。 詳細については、「 [Cmfcoutlookbar クラス](../../mfc/reference/cmfcoutlookbar-class.md)」を参照してください。

## <a name="cmfcoutlookbartabctrlsetvisiblepagebuttons"></a><a name="setvisiblepagebuttons"></a> CMFCOutlookBarTabCtrl:: SetVisiblePageButtons

```cpp
void SetVisiblePageButtons(int nVisiblePageButtons);
```

### <a name="parameters"></a>パラメーター

から *nVisiblePageButtons*<br/>

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md)<br/>
[CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CMFCOutlookBarPane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md)
