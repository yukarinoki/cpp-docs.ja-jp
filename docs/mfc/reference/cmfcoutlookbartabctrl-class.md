---
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
ms.openlocfilehash: 309b74126f57e76aa6399f57382d88fee4400700
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369663"
---
# <a name="cmfcoutlookbartabctrl-class"></a>CMFCOutlookBarTabCtrl Class

Microsoft Outlook の **ナビゲーション ウィンドウ** と同じ外観を持つタブ コントロールです。
詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

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
|[コントロールの追加](#addcontrol)|Windows コントロールを Outlook バーの新しいタブとして追加します。|
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|ユーザーがタブの名前を変更したときに表示されるエディット ボックスのサイズを決定するために、フレームワークによって`CMFCBaseTabCtrl::CalcRectEdit`呼び出されます。|
|[ページボタンを表示する回数を減らす](#canshowfewerpagebuttons)|サイズ変更操作中にフレームワークによって呼び出され、現在表示されているよりも表示できる Outlook バー タブ ページ ボタンの数が少ないかどうかを判断します。|
|[ページボタンを表示する](#canshowmorepagebuttons)|サイズ変更操作中にフレームワークによって呼び出され、現在表示されている Outlook バー タブ ページ ボタンの数を超える表示が可能かどうかを判断します。|
|[をクリックします。](#create)|Outlook バータブコントロールを作成します。|
|`CMFCOutlookBarTabCtrl::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|[アニメーションを有効にする](#enableanimation)|アクティブなタブ間の切り替え中に発生するアニメーションを有効にするかどうかを指定します。|
|[をクリックして、インプレースを有効にします。](#enableinplaceedit)|ユーザーが Outlook バーのタブ ボタンのテキスト ラベルを変更できるかどうかを指定します。 (オーバーライドします[。](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit)|
|[を有効にするスクロール ボタン](#enablescrollbuttons)|ユーザーが Outlook バー ペインのボタンをスクロールできるようにするボタンを有効にするために、フレームワークによって呼び出されます。|
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|指定したポイントを含むペインを識別します。 (オーバーライドします[。](../../mfc/reference/cmfcbasetabctrl-class.md#findtargetwnd)|
|[をクリックします。](#getbordersize)|Outlook タブ コントロールの境界線のサイズを返します。|
|`CMFCOutlookBarTabCtrl::GetTabArea`|タブ コントロールのタブ領域のサイズと位置を取得します。 (オーバーライドします[。](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea)|
|`CMFCOutlookBarTabCtrl::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[ボタンをクリックします。](#getvisiblepagebuttons)||
|[をクリックします。](#isanimation)|アクティブなタブ間の切り替え中に発生するアニメーションを有効にするかどうかを指定します。|
|[をクリックします。](#ismode2003)|Outlook バーのタブ コントロールが、Outlook 2003 をエミュレートするモードかどうかを判断します。|
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|ポイントがタブ領域内にあるかどうかを判断します。 (オーバーライドします[。](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea)|
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|タブが取り外し可能かどうかを判断します。 (オーバーライドします[。](../../mfc/reference/cmfcbasetabctrl-class.md#istabdetachable)|
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|タブが挿入または削除されたときに、フレームワークによって呼び出されます。 ( `CMFCBaseTabCtrl::OnChangeTabs`をオーバーライドします)。|
|[ページボタンを表示します。](#onshowfewerpagebuttons)|表示されるタブ ページ ボタンの数を減らすには、フレームワークによって呼び出されます。|
|[ページボタンを表示します。](#onshowmorepagebuttons)|表示されるタブ ページ ボタンの数を増やすために、フレームワークによって呼び出されます。|
|[オプションを表示します。](#onshowoptions)|**[ナビゲーション ウィンドウのオプション]** ダイアログ ボックスを表示します。|
|`CMFCOutlookBarTabCtrl::RecalcLayout`|タブ コントロールの内部レイアウトを再計算します。 ([オーバーライドします。](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout)|
|[タブを設定します。](#setactivetab)|アクティブなタブを設定します ([オーバーライド](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab)します。|
|[を設定します。](#setbordersize)|Outlook タブ コントロールの境界線のサイズを設定します。|
|[テキスト整列](#setpagebuttontextalign)|Outlook バーのタブ ボタンのテキスト ラベルの配置を設定します。|
|[一覧をクリックします。](#settoolbarimagelist)|Outlook 2003 モードの Outlook バーの下部に表示されるアイコンを含むビットマップを設定します[(CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)を参照)。|
|[ページボタンをクリックします。](#setvisiblepagebuttons)||

## <a name="remarks"></a>解説

ドッキングサポートを持つ Outlook バーを作成するには、`CMFCOutlookBar`オブジェクトを使用して Outlook バー タブ コントロールをホストします。 詳細については、「[クラス」を参照](../../mfc/reference/cmfcoutlookbar-class.md)してください。

## <a name="example"></a>例

次の例は、`CMFCOutlookBarTabCtrl`オブジェクトを初期化し、クラス内のさまざまなメソッドを使用`CMFCOutlookBarTabCtrl`する方法を示しています。 この例では、Outlook バーのタブ ページ ボタンでテキスト ラベルをインプレース編集できるようにする方法、アニメーションを有効にする方法、スクロール ハンドルを有効にして Outlook バー ウィンドウのボタンをスクロールする方法、Outlook タブ コントロールの境界線サイズを設定する方法、および Outlook バーのタブ ボタンでテキスト ラベルの配置を設定する方法を示します。 このコード スニペットは[Outlook デモ のサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_OutlookDemo#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_1.cpp)]
[!code-cpp[NVC_MFC_OutlookDemo#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)

[CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxoutlookbartabctrl.h

## <a name="cmfcoutlookbartabctrladdcontrol"></a><a name="addcontrol"></a>コントロールの追加

Windows コントロールを Outlook バーの新しいタブとして追加します。

```
void AddControl(
    CWnd* pWndCtrl,
    LPCTSTR lpszName,
    int nImageID=-1,
    BOOL bDetachable=TRUE,
    DWORD dwControlBarStyle=AFX_CBRS_FLOAT |  AFX_CBRS_CLOSE | AFX_CBRS_RESIZE |  CBRS_AFX_AUTOHIDE);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]追加するコントロールへのポインター。

*名前を指定します。*<br/>
[in]タブの名前を指定します。

*b取り外し可能*<br/>
[in]TRUE の場合、ページはデタッチ可能として作成されます。

*イメージID*<br/>
[in]新しいタブに表示するイメージの内部イメージ リスト内のイメージ インデックス。

*コントロール バースタイル*<br/>
[in]ラップされたドッキング ペインのAFX_ CBRS_* スタイルを指定します。

### <a name="remarks"></a>解説

この関数を使用して、コントロールを Outlook バーの新しいページとして追加します。

この関数は内部的に[呼](../../mfc/reference/cmfcbasetabctrl-class.md#addtab)び出します。

*bDetachable*を TRUE に`AddControl`設定すると、内部的`CDockablePaneAdapter`にオブジェクトが作成され、追加されたコントロールがラップされます。 タブ付きウィンドウのランタイム クラスが自動的にのランタイム クラスに`CMFCOutlookBar`設定され、フローティング フレームのランタイム`CMultiPaneFrameWnd`クラスが に設定されます。

### <a name="example"></a>例

クラスでメソッドを使用する方法を`AddControl`次の例に`CMFCOutlookBarTabCtrl`示します。 このコード スニペットは[Outlook デモ のサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_OutlookDemo#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_3.cpp)]

## <a name="cmfcoutlookbartabctrlcanshowfewerpagebuttons"></a><a name="canshowfewerpagebuttons"></a>ページボタンを表示する回数を減らす

サイズ変更操作中にフレームワークによって呼び出され、現在表示されている Outlook バー タブ ページ ボタンの数が、現在表示されている数より少ないかどうかを判断します。

```
virtual BOOL CanShowFewerPageButtons() const;
```

### <a name="return-value"></a>戻り値

複数のボタンがある場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

Outlook バー タブ コントロールは、使用可能な空き容量に応じて、表示に対してタブを動的に追加または削除します。 このメソッドは、そのプロセスを支援するためにフレームワークによって使用されます。

## <a name="cmfcoutlookbartabctrlcanshowmorepagebuttons"></a><a name="canshowmorepagebuttons"></a>ページボタンを表示する

サイズ変更操作中にフレームワークによって呼び出され、現在表示されている Outlook バー タブ のボタンを表示できる数より多く表示できるかどうかを判断します。

```
virtual BOOL CanShowMorePageButtons() const;
```

### <a name="return-value"></a>戻り値

現在表示されていないボタンがある場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

Outlook バー タブ コントロールは、使用可能なスペースに応じて、タブを動的に追加または削除します。 このメソッドは、そのプロセスを支援するためにフレームワークによって使用されます。

## <a name="cmfcoutlookbartabctrlcreate"></a><a name="create"></a>をクリックします。

Outlook バータブコントロールを作成します。

```
virtual BOOL Create(
    const CRect& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
[in]初期サイズと位置をピクセル単位で指定します。

*pParentWnd*<br/>
[in]親ウィンドウへのポイント。 NULL にすることはできません。

*nID*<br/>
[in]コントロール ID。

### <a name="return-value"></a>戻り値

コントロールが正常に作成された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

通常、Outlook バーのタブ コントロールは[、CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)がプロセスのWM_CREATE メッセージを制御するときに作成されます。

## <a name="cmfcoutlookbartabctrlenableanimation"></a><a name="enableanimation"></a>アニメーションを有効にする

アクティブなタブ間の切り替え中に発生するアニメーションを有効にするかどうかを指定します。

```
static void EnableAnimation(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]アニメーションを有効にするか無効にするかを指定します。

### <a name="remarks"></a>解説

アニメーションを有効または無効にします。 ユーザーがタブ ページを開くと、アニメーションが有効になっている場合、ページのキャプションが上下にスライドします。 アニメーションが無効になっている場合、ページはすぐにアクティブになります。

デフォルトでは、アニメーションは有効になっています。

## <a name="cmfcoutlookbartabctrlenableinplaceedit"></a><a name="enableinplaceedit"></a>をクリックして、インプレースを有効にします。

ユーザーが Outlook バーのタブ ページ ボタンのテキスト ラベルを変更できるかどうかを指定します。

```
virtual void EnableInPlaceEdit(BOOL bEnable);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
TRUE の場合は、テキスト ラベルのインプレース編集を有効にします。 FALSE の場合、インプレース編集を無効にします。

### <a name="remarks"></a>解説

タブ ページ ボタンでテキスト ラベルのインプレース編集を有効または無効にします。 既定では、インプレース編集は無効になっています。

## <a name="cmfcoutlookbartabctrlenablescrollbuttons"></a><a name="enablescrollbuttons"></a>を有効にするスクロール ボタン

ユーザーが Outlook バー ペインのボタンをスクロールできるようにするスクロール ハンドルを有効にするために、フレームワークによって呼び出されます。

```
void EnableScrollButtons(
    BOOL bEnable = TRUE,
    BOOL bIsUp = TRUE,
    BOOL bIsDown = TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]スクロール ボタンを表示するかどうかを決定します。

*ビイアップ*<br/>
[in]上部のスクロール バーを表示するかどうかを指定します。

*ビスダウン*<br/>
[in]下部のスクロール バーを表示するかどうかを指定します。

### <a name="remarks"></a>解説

スクロール ボタンの表示を有効にします。 このメソッドは、アクティブなタブがスクロール ボタンを復元するように変更されたときに、フレームワークによって呼び出されます。

## <a name="cmfcoutlookbartabctrlgetbordersize"></a><a name="getbordersize"></a>をクリックします。

Outlook タブ コントロールの境界線のサイズを返します。

```
int GetBorderSize() const;
```

### <a name="return-value"></a>戻り値

境界線のサイズ (ピクセル単位)。

## <a name="cmfcoutlookbartabctrlgetvisiblepagebuttons"></a><a name="getvisiblepagebuttons"></a>ボタンをクリックします。

```
int GetVisiblePageButtons() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcoutlookbartabctrlisanimation"></a><a name="isanimation"></a>をクリックします。

アクティブなタブ間の切り替え中に発生するアニメーションを有効にするかどうかを指定します。

```
static BOOL IsAnimation();
```

### <a name="return-value"></a>戻り値

アニメーションが有効な場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

アニメーションを有効または無効にするには[、](#enableanimation)関数を呼び出します。

## <a name="cmfcoutlookbartabctrlismode2003"></a><a name="ismode2003"></a>をクリックします。

Outlook バーのタブ コントロールが、Outlook 2003 をエミュレートするモードかどうかを判断します。

```
BOOL IsMode2003() const;
```

### <a name="return-value"></a>戻り値

True Outlook バータブ コントロールが Outlook 2003 モードである場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

この値は[、CMFCOutlookBar::SetMode2003](../../mfc/reference/cmfcoutlookbar-class.md#setmode2003)によって設定されます。

## <a name="cmfcoutlookbartabctrlonshowfewerpagebuttons"></a><a name="onshowfewerpagebuttons"></a>ページボタンを表示します。

表示されるタブ ページ ボタンの数を減らすには、フレームワークによって呼び出されます。

```
virtual void OnShowFewerPageButtons();
```

### <a name="remarks"></a>解説

このメソッドは、コントロールのサイズを変更するときに、表示されるページ タブ ボタンの数を調整します。

## <a name="cmfcoutlookbartabctrlonshowmorepagebuttons"></a><a name="onshowmorepagebuttons"></a>ページボタンを表示します。

表示されるタブ ページ ボタンの数を増やすために、フレームワークによって呼び出されます。

```
virtual void OnShowMorePageButtons();
```

### <a name="remarks"></a>解説

このメソッドは、コントロールのサイズを変更するときに表示されるタブ ページ ボタンの数を調整します。

## <a name="cmfcoutlookbartabctrlonshowoptions"></a><a name="onshowoptions"></a>オプションを表示します。

**[ナビゲーション ウィンドウのオプション]** ダイアログ ボックスを表示します。

```
virtual void OnShowOptions();
```

### <a name="remarks"></a>解説

[**ナビゲーション ウィンドウのオプション]** ダイアログ ボックスでは、表示するタブ ページ ボタンと表示順序を選択できます。

このメソッドは、ユーザーがコントロールのカスタマイズ メニューから **[ナビゲーション ウィンドウ オプション]** メニュー項目を選択したときに、フレームワークによって呼び出されます。

## <a name="cmfcoutlookbartabctrlsetactivetab"></a><a name="setactivetab"></a>タブを設定します。

アクティブなタブを設定します。アクティブなタブは、その内容が表示されている開いているタブです。

```
virtual BOOL SetActiveTab(int iTab);
```

### <a name="parameters"></a>パラメーター

*Itab*<br/>
[in]開くタブの 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

指定されたタブが正常に開かれた場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

アクティブなタブを設定する視覚効果は、アニメーションを有効にしたかどうかによって異なります。 詳細については、「[アニメーションを有効に](#enableanimation)する」を参照してください。

## <a name="cmfcoutlookbartabctrlsetbordersize"></a><a name="setbordersize"></a>を設定します。

Outlook タブ コントロールの境界線のサイズを設定します。

```
void SetBorderSize(int nBorderSize);
```

### <a name="parameters"></a>パラメーター

*ウィンドウサイズ*<br/>
[in]新しい境界線のサイズをピクセル単位で指定します。

### <a name="remarks"></a>解説

新しい境界線のサイズを設定し、Outlook ウィンドウレイアウトを再計算します。

## <a name="cmfcoutlookbartabctrlsetpagebuttontextalign"></a><a name="setpagebuttontextalign"></a>テキスト整列

Outlook バーのタブ ボタンのテキスト ラベルの配置を設定します。

```
void SetPageButtonTextAlign(
    UINT uiAlign,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>パラメーター

*uiAlign*<br/>
[in]テキストの配置を指定します。

*引き出し*<br/>
[in]TRUE の場合、見通しウィンドウが再描画されます。

### <a name="remarks"></a>解説

この機能を使用して、ページボタンのテキスト配置を変更します。

*uiAlign*は、次のいずれかの値を指定できます。

|定数|意味|
|--------------|-------------|
|TA_LEFT|左揃え|
|TA_CENTER|中央揃え|
|TA_RIGHT|右揃え|

既定値は TA_CENTER です。

## <a name="cmfcoutlookbartabctrlsettoolbarimagelist"></a><a name="settoolbarimagelist"></a>一覧をクリックします。

Outlook 2003 モードで Outlook バーの下部に表示されるアイコンを含むビットマップを設定します。

```
BOOL SetToolbarImageList(
    UINT uiID,
    int cx,
    COLORREF clrTransp=RGB(255, 0, 255));
```

### <a name="parameters"></a>パラメーター

*Uiid*<br/>
[in]読み込むイメージのリソース ID を指定します。

*Cx*<br/>
[in]イメージ リスト内のイメージの幅をピクセル単位で指定します。

*clrトランスプ*<br/>
[in]透明色を指定する RGB 値。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返します。それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

この関数を使用して、Microsoft Office 2003 モードのツール バー ボタンにイメージを表示するイメージ リストを添付します。 イメージ インデックスはページ インデックスに対応する必要があります。

このメソッドは、Microsoft Office 2003 モードでない場合は呼び出されません。 詳細については、「[クラス」を参照](../../mfc/reference/cmfcoutlookbar-class.md)してください。

## <a name="cmfcoutlookbartabctrlsetvisiblepagebuttons"></a><a name="setvisiblepagebuttons"></a>ページボタンをクリックします。

```
void SetVisiblePageButtons(int nVisiblePageButtons);
```

### <a name="parameters"></a>パラメーター

[in]*見えないページのボタン*<br/>

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfcbasetabctrl-class.md)<br/>
[クラス](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[クラス](../../mfc/reference/cmfcoutlookbarpane-class.md)
