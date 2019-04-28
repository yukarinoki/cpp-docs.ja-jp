---
title: CMFCToolBarEditBoxButton クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: ac07ff4e6bf97518e2c659a9d6df9bd721b6b806
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62218259"
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
|[CMFCToolBarEditBoxButton::CanBeStretched](#canbestretched)|ユーザーがボタンをカスタマイズするときに拡張できるかどうかを指定します。 (上書き[CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched))。|
|[CMFCToolBarEditBoxButton::CopyFrom](#copyfrom)|現在のボタンには、別のツール バー ボタンのプロパティをコピーします。 (上書き[CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom))。|
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::CreateEdit](#createedit)|ボタンには、新しい編集コントロールを作成します。|
|`CMFCToolBarEditBoxButton::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|[CMFCToolBarEditBoxButton::GetByCmd](#getbycmd)|最初に取得`CMFCToolBarEditBoxButton`を指定したコマンド ID を持つアプリケーションでのオブジェクト|
|[CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall)|指定したコマンド ID を持つ最初の編集ボックス ツールバー コントロールのテキストを取得します。|
|[CMFCToolBarEditBoxButton::GetContextMenuID](#getcontextmenuid)|ボタンに関連付けられているショートカット メニューのリソース ID を取得します。|
|[CMFCToolBarEditBoxButton::GetEditBorder](#geteditborder)|エディット ボックス ボタンの編集部分の外接する四角形を取得します。|
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::GetEditBox](#geteditbox)|ボタンの埋め込まれたエディット コントロールへのポインターを返します。|
|[CMFCToolBarEditBoxButton::GetHwnd](#gethwnd)|ツール バー ボタンに関連付けられているウィンドウ ハンドルを取得します。 (上書き[CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd))。|
|[CMFCToolBarEditBoxButton::GetInvalidateRect](#getinvalidaterect)|再描画する必要がある、ボタンのクライアント領域の領域を取得します。 (上書き[CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect))。|
|`CMFCToolBarEditBoxButton::GetThisClass`|ポインターを取得する、framework によって使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|
|[CMFCToolBarEditBoxButton::HaveHotBorder](#havehotborder)|ユーザーがボタンをクリックすると、ボタンの境界線が表示されるかどうかを判断します。 (上書き[CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder))。|
|[CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode)|エディット ボックス ボタンのフラット スタイルかどうかを判断します。|
|[CMFCToolBarEditBoxButton::NotifyCommand](#notifycommand)|ボタンを処理するかどうかを指定します、 [WM_COMMAND](/windows/desktop/menurc/wm-command)メッセージ。 (上書き[CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand))。|
|[CMFCToolBarEditBoxButton::OnAddToCustomizePage](#onaddtocustomizepage)|ボタンが追加されたときに、フレームワークによって呼び出されます、**カスタマイズ** ダイアログ ボックス。 (上書き[CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage))。|
|`CMFCToolBarEditBoxButton::OnCalculateSize`|指定したデバイス コンテキストおよびドッキング状態のボタンのサイズを計算するためにフレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize))。|
|[CMFCToolBarEditBoxButton::OnChangeParentWnd](#onchangeparentwnd)|新しいツールバーにボタンが挿入されたときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd))。|
|[CMFCToolBarEditBoxButton::OnClick](#onclick)|ユーザーがマウス ボタンをクリックすると、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick))。|
|[CMFCToolBarEditBoxButton::OnCtlColor](#onctlcolor)|親ツールバー WM_CTLCOLOR メッセージを処理するときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor))。|
|`CMFCToolBarEditBoxButton::OnDraw`|指定したスタイルとオプションを使用して、ボタンを描画するためにフレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw))。|
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|ボタンを描画するためにフレームワークによって呼び出されます、**コマンド**のウィンドウ、**カスタマイズ** ダイアログ ボックス。 (上書き[CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist))。|
|[CMFCToolBarEditBoxButton::OnGlobalFontsChanged](#onglobalfontschanged)|グローバルのフォントが変更されたときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged))。|
|[CMFCToolBarEditBoxButton::OnMove](#onmove)|親ツールバーを移動すると、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove))。|
|[CMFCToolBarEditBoxButton::OnShow](#onshow)|フレームワークによって呼び出されます、ボタンが表示または非表示します。 (上書き[CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow))。|
|[CMFCToolBarEditBoxButton::OnSize](#onsize)|親ツールバーのサイズが変更またはとサイズを変更するボタンの位置が変更されときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize))。|
|[CMFCToolBarEditBoxButton::OnUpdateToolTip](#onupdatetooltip)|親ツールバーは、そのツールヒント テキストを更新するときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip))。|
|`CMFCToolBarEditBoxButton::Serialize`|アーカイブからこのオブジェクトを読み取りまたはアーカイブに書き込みます。 (上書き[CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize))。|
|`CMFCToolBarEditBoxButton::SetACCData`|設定`CAccessibilityData`ツール バー ボタンのアクセシビリティ データを持つオブジェクト。 (上書き[CMFCToolBarButton::SetACCData](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata))。|
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContents](#setcontents)|ボタンの編集コントロールにテキストを設定します。|
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall)|指定したコマンド ID を持つし、そのボタンの編集コントロールのテキストを設定するエディット コントロールのボタンを検索します。|
|[CMFCToolBarEditBoxButton::SetContextMenuID](#setcontextmenuid)|ボタンに関連付けられているショートカット メニューのリソース ID を指定します。|
|[CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode)|アプリケーションでは、エディット ボックス ボタンのフラット スタイルの外観を指定します。|
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetStyle](#setstyle)|ボタンのスタイルを指定します。 (上書き[CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle))。|

## <a name="remarks"></a>Remarks

エディット ボックス ボタンをツールバーに追加するには、次の手順を実行します。

1. 親ツール バー リソースでボタンのダミー リソース ID を予約します。

2. `CMFCToolBarEditBoxButton` オブジェクトを構築します。

3. AFX_WM_RESETTOOLBAR メッセージを処理するメッセージ ハンドラーで、ダミー ボタンを置き換える新しいコンボ ボックス ボタンを使用して[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)します。

詳細については、「[チュートリアル:コントロールのツールバーに追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)します。

## <a name="example"></a>例

`CMFCToolBarEditBoxButton` クラスのさまざまなメソッドの使用方法を次の例に示します。 例では、指定ことユーザーことができます、ボタンをカスタマイズするときに拡張、ユーザーがボタンをクリックすると、ボタンの境界線が表示されることを指定、テキスト ボックス コントロールにテキストを設定、アプリケーションでのエディット ボックス ボタンのフラット スタイルの外観を指定する方法を示しています。アプリケーションでは、編集ボックス コントロールのツールバーのスタイルを指定します。

[!code-cpp[NVC_MFC_RibbonApp#40](../../mfc/reference/codesnippet/cpp/cmfctoolbareditboxbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

`CMFCToolBarEditBoxButton`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxtoolbareditboxbutton.h

##  <a name="canbestretched"></a>  CMFCToolBarEditBoxButton::CanBeStretched

ユーザーがボタンをカスタマイズするときに拡張できるかどうかを指定します。

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>戻り値

このメソッドは、TRUE を返します。

### <a name="remarks"></a>Remarks

既定では、フレームワークにツール バー ボタンをカスタマイズするときに拡張するユーザーはできません。 このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)) によって、ユーザーが編集ボックスのツールバーをカスタマイズするときに拡張できるようにします。

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

*uiID*<br/>
[in]コントロールの ID を指定します

*画像を*<br/>
[in]ツール バー イメージの 0 から始まるインデックスを指定します。 イメージにある、 [CMFCToolBarImages クラス](../../mfc/reference/cmfctoolbarimages-class.md)オブジェクトを[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)クラスを保持します。

*dwStyle*<br/>
[in]エディット コントロールのスタイルを指定します。

*iWidth*<br/>
[in]編集コントロールのピクセル単位の幅を指定します。

### <a name="remarks"></a>Remarks

既定のコンス トラクターでは、次の組み合わせをエディット コントロールのスタイルを設定します。

WS_CHILD | WS_VISIBLE | ES_AUTOHSCROLL

コントロールの既定の幅は、150 ピクセルです。

##  <a name="copyfrom"></a>  CMFCToolBarEditBoxButton::CopyFrom

現在のボタンには、別のツール バー ボタンのプロパティをコピーします。

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>パラメーター

*src*<br/>
[in]コピー元のソースボタンへの参照。

### <a name="remarks"></a>Remarks

このツール バー ボタンに別のツール バー ボタンをコピーするには、このメソッドを呼び出します。 *src*型でなければなりません`CMFCToolBarEditBoxButton`します。

##  <a name="createedit"></a>  CMFCToolBarEditBoxButton::CreateEdit

ボタンには、新しい編集コントロールを作成します。

```
virtual CEdit* CreateEdit(
    CWnd* pWndParent,
    const CRect& rect);
```

### <a name="parameters"></a>パラメーター

*pWndParent*<br/>
[in]エディット コントロールの親ウィンドウを指定します。 NULL は指定できません。

*rect*<br/>
[in]編集コントロールのサイズと位置を指定します。

### <a name="return-value"></a>戻り値

新しく作成されたエディット コントロールへのポインターコントロールの作成とアタッチが失敗する場合は NULL になります。

### <a name="remarks"></a>Remarks

構築する、 `CMFCToolBarEditBoxButton` 2 つのステップ内のオブジェクト。 最初のコンス トラクターを呼び出します`CreateEdit`、Windows のエディット コントロールを作成しにアタッチする`CMFCToolBarEditBoxButton`オブジェクト。

##  <a name="getbycmd"></a>  CMFCToolBarEditBoxButton::GetByCmd

最初に取得`CMFCToolBarEditBoxButton`を指定したコマンド ID を持つアプリケーションでのオブジェクト

```
static CMFCToolBarEditBoxButton* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>パラメーター

*uiCmd*<br/>
[in]取得するボタンのコマンド ID。

### <a name="return-value"></a>戻り値

最初の`CMFCToolBarEditBoxButton`をこのようなオブジェクトが存在しない場合、指定したコマンド ID、または NULL を持つアプリケーションのオブジェクト。

### <a name="remarks"></a>Remarks

この共有ユーティリティ メソッドがなどのメソッドによって使用されます[CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall)と[CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall)最初の編集ボックスのツールバーのテキストを取得または設定するには指定したコマンド ID を持つコントロール

##  <a name="getcontentsall"></a>  CMFCToolBarEditBoxButton::GetContentsAll

指定したコマンド ID を持つ最初の編集ボックス ツールバー コントロールのテキストを取得します。

```
static CString __stdcall GetContentsAll(UINT uiCmd);
```

### <a name="parameters"></a>パラメーター

*uiCmd*<br/>
[in]元のコンテンツを取得するボタンのコマンド ID。

### <a name="return-value"></a>戻り値

A`CString`を指定したコマンド ID を持つ最初の編集ボックス ツールバー コントロールのテキストを格納しているオブジェクト

### <a name="remarks"></a>Remarks

ない場合は、このメソッドは空の文字列を返します`CMFCToolBarEditBoxButton`オブジェクトは、指定したコマンド ID を持つ

##  <a name="getcontextmenuid"></a>  CMFCToolBarEditBoxButton::GetContextMenuID

ボタンに関連付けられているショートカット メニューのリソース ID を取得します。

```
UINT GetContextMenuID();
```

### <a name="return-value"></a>戻り値

ボタンに関連付けられているショートカット メニューがあるない場合に、ボタンまたは 0 に関連付けられているショートカット メニューのリソース ID。

### <a name="remarks"></a>Remarks

フレームワークでは、リソース ID を使用して、ユーザーがボタンを右クリックすると、ショートカット メニューを作成します。

##  <a name="geteditborder"></a>  CMFCToolBarEditBoxButton::GetEditBorder

エディット ボックス ボタンの編集部分の外接する四角形を取得します。

```
virtual void GetEditBorder(CRect& rectBorder);
```

### <a name="parameters"></a>パラメーター

*rectBorder*<br/>
[out]参照、`CRect`を外接する四角形を受け取るオブジェクト。

### <a name="remarks"></a>Remarks

このメソッドは、クライアント座標で、編集コントロールの外接する四角形を取得します。 各方向に四角形のサイズは、1 ピクセルずつ拡大されます。

[CMFCVisualManager::OnDrawEditBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondraweditborder)メソッドは、周りの境界線を描画するときにこのメソッドを呼び出して、`CMFCToolBarEditBoxButton`オブジェクト。

##  <a name="geteditbox"></a>  CMFCToolBarEditBoxButton::GetEditBox

ポインターを返します、 [CEdit クラス](../../mfc/reference/cedit-class.md)ボタンに埋め込まれているコントロール。

```
CEdit* GetEditBox() const;
```

### <a name="return-value"></a>戻り値

ポインター、 [CEdit クラス](../../mfc/reference/cedit-class.md)ボタンが含まれるコントロール。 NULL である場合、`CEdit`コントロールがまだ作成されていません。

### <a name="remarks"></a>Remarks

作成する、`CEdit`呼び出してコントロール[CMFCToolBarEditBoxButton::CreateEdit](#createedit)します。

##  <a name="gethwnd"></a>  CMFCToolBarEditBoxButton::GetHwnd

ツール バー ボタンに関連付けられているウィンドウ ハンドルを取得します。

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>戻り値

ボタンに関連付けられているウィンドウ ハンドル。

### <a name="remarks"></a>Remarks

このメソッドは、 [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd)エディット ボックス ボタンの編集コントロールの一部のウィンドウ ハンドルを返すことによってメソッド。

##  <a name="getinvalidaterect"></a>  CMFCToolBarEditBoxButton::GetInvalidateRect

再描画する必要がある、ボタンのクライアント領域の領域を取得します。

```
virtual const CRect GetInvalidateRect() const;
```

### <a name="return-value"></a>戻り値

A`CRect`再描画する必要があるリージョンを指定するオブジェクト。

### <a name="remarks"></a>Remarks

このメソッドが基底クラスの実装によって拡張[CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect)リージョン内のテキスト ラベルの領域を含めることによって。

##  <a name="havehotborder"></a>  CMFCToolBarEditBoxButton::HaveHotBorder

ユーザーがボタンをクリックすると、ボタンの境界線が表示されるかどうかを判断します。

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>戻り値

ボタン 0 以外の場合は、選択されたときの境界線を表示します。それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

このメソッドが基底クラスの実装によって拡張[CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder)コントロールを表示する場合は、0 以外の値を返すことによって。

##  <a name="isflatmode"></a>  CMFCToolBarEditBoxButton::IsFlatMode

エディット ボックス ボタンのフラット スタイルかどうかを判断します。

```
static BOOL __stdcall IsFlatMode();
```

### <a name="return-value"></a>戻り値

フラット スタイルのボタンにある、0 以外の場合それ以外の場合、0 を返します。

### <a name="remarks"></a>Remarks

既定では、エディット ボックス ボタンはフラット スタイルがあります。 使用して、 [CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode)アプリケーションのフラット スタイルの外観を変更するメソッド。

##  <a name="notifycommand"></a>  CMFCToolBarEditBoxButton::NotifyCommand

ボタンを処理するかどうかを指定します、 [WM_COMMAND](/windows/desktop/menurc/wm-command)メッセージ。

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>パラメーター

*iNotifyCode*<br/>
[in]コマンドに関連付けられている通知メッセージ。

### <a name="return-value"></a>戻り値

TRUE の場合、ボタンの処理、WM_COMMAND メッセージ、または FALSE を示す親ツールバーで、メッセージを処理する必要があります。

### <a name="remarks"></a>Remarks

送信しようとしてある場合に、フレームワークはこのメソッドを呼び出して、 [WM_COMMAND](/windows/desktop/menurc/wm-command)メッセージを親ウィンドウ。

このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) 処理することによって、 [EN_UPDATE](/windows/desktop/Controls/en-update)通知します。 このオブジェクトと同じコマンド ID を持つ各編集ボックスのテキスト ラベルをこのオブジェクトのテキスト ラベルを設定します。

##  <a name="onaddtocustomizepage"></a>  CMFCToolBarEditBoxButton::OnAddToCustomizePage

ボタンが追加されたときに、フレームワークによって呼び出されます、**カスタマイズ** ダイアログ ボックス。

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>Remarks

このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)) をこのオブジェクトと同じコマンド ID を持つ任意のツールバーで、編集ボックス コントロールからプロパティをコピーしています。 ツールバーがこのオブジェクトと同じコマンド ID を持つ編集ボックス コントロールを持たない場合、このメソッドは何もはしません。

詳細については、**カスタマイズ**ダイアログ ボックスを参照してください[CMFCToolBarsCustomizeDialog クラス](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)します。

##  <a name="onchangeparentwnd"></a>  CMFCToolBarEditBoxButton::OnChangeParentWnd

新しいツールバーにボタンが挿入されたときに、フレームワークによって呼び出されます。

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>パラメーター

*pWndParent*<br/>
[in]新しい親ウィンドウへのポインター。

### <a name="remarks"></a>Remarks

このメソッドは、基本クラスの実装 ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) 内部の再作成して`CEdit`オブジェクト。

##  <a name="onclick"></a>  CMFCToolBarEditBoxButton::OnClick

ユーザーがマウス ボタンをクリックすると、フレームワークによって呼び出されます。

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
[in]使用されていません。

*bDelay*<br/>
[in]使用されていません。

### <a name="return-value"></a>戻り値

ボタンをクリックしてメッセージを処理する場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

このメソッドは、基本クラスの実装 ( [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)) 場合は、0 以外の値を返すことによって、内部`CEdit`オブジェクトが表示されます。

##  <a name="onctlcolor"></a>  CMFCToolBarEditBoxButton::OnCtlColor

親ツールバー WM_CTLCOLOR メッセージを処理するときに、フレームワークによって呼び出されます。

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]ボタンを表示するデバイス コンテキスト。

*nCtlColor*<br/>
[in]使用されていません。

### <a name="return-value"></a>戻り値

グローバルのウィンドウのブラシへのハンドル。

### <a name="remarks"></a>Remarks

このメソッドは、基本クラスの実装 ( [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)) それぞれグローバル テキストと背景の色を指定されたデバイス コンテキストのテキストと背景色を設定します。

アプリケーションに使用できるグローバル オプションの詳細については、次を参照してください。 [AFX_GLOBAL_DATA 構造体](../../mfc/reference/afx-global-data-structure.md)します。

##  <a name="onglobalfontschanged"></a>  CMFCToolBarEditBoxButton::OnGlobalFontsChanged

グローバルのフォントが変更されたときに、フレームワークによって呼び出されます。

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>Remarks

このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) のグローバルのフォントのコントロールのフォントを変更することで。

アプリケーションに使用できるグローバル オプションの詳細については、次を参照してください。 [AFX_GLOBAL_DATA 構造体](../../mfc/reference/afx-global-data-structure.md)します。

##  <a name="onmove"></a>  CMFCToolBarEditBoxButton::OnMove

親ツールバーを移動すると、フレームワークによって呼び出されます。

```
virtual void OnMove();
```

### <a name="remarks"></a>Remarks

このメソッドは、既定のクラスの実装 ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)) 内部の位置を更新して`CEdit`オブジェクト

##  <a name="onshow"></a>  CMFCToolBarEditBoxButton::OnShow

フレームワークによって呼び出されます、ボタンが表示または非表示します。

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*bShow*<br/>
[in]ボタンが表示されているかどうかを指定します。 このパラメーターが TRUE の場合、ボタンが表示されます。 それ以外の場合、ボタンは表示されません。

### <a name="remarks"></a>Remarks

このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) 場合、ボタンを表示することによって*bShow*は TRUE です。 それ以外の場合、このメソッドは、ボタンを非表示にします。

##  <a name="onsize"></a>  CMFCToolBarEditBoxButton::OnSize

親ツールバーのサイズが変更またはとサイズを変更するボタンの位置が変更されときに、フレームワークによって呼び出されます。

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>パラメーター

*iSize*<br/>
[in]ピクセル単位で、ボタンの新しい幅。

### <a name="remarks"></a>Remarks

このメソッドは、既定のクラスの実装をオーバーライド[CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)、内部の位置とサイズを更新して`CEdit`オブジェクト。

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

*pWndParent*<br/>
[in]使用されていません。

*iButtonIndex*<br/>
[in]使用されていません。

*wndToolTip*<br/>
[in]ツールヒント テキストを表示するコントロール。

*str*<br/>
[out]A`CString`更新されたツールヒント テキストを受け取るオブジェクト。

### <a name="return-value"></a>戻り値

メソッドは、ツールヒントのテキストを更新する場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) ボタンの編集部分に関連付けられているツールヒント テキストを表示することで。 場合、内部`CEdit`オブジェクトが NULL かのウィンドウ ハンドル、`CEdit`オブジェクトが既存のウィンドウを識別しない場合、このメソッドは何も実行し、FALSE を返します。

##  <a name="setcontents"></a>  CMFCToolBarEditBoxButton::SetContents

テキスト ボックス コントロールにテキストを設定します。

```
virtual void SetContents(const CString& sContents);
```

### <a name="parameters"></a>パラメーター

*sContents*<br/>
[in]設定する新しいテキストを指定します。

##  <a name="setcontentsall"></a>  CMFCToolBarEditBoxButton::SetContentsAll

検索、 [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md)オブジェクトを指定したコマンド ID があり、そのテキスト ボックス内の指定したテキストを設定します。

```
static BOOL SetContentsAll(
    UINT uiCmd,
    const CString& strContents);
```

### <a name="parameters"></a>パラメーター

*uiCmd*<br/>
[in]テキストを変更するコントロールのコマンド ID を指定します。

*strContents*<br/>
[in]設定する新しいテキストを指定します。

### <a name="return-value"></a>戻り値

テキストが設定された場合、0 以外の場合0 の場合、`CMFCToolBarEditBoxButton`指定したコマンド ID を持つコントロールが存在しません。

##  <a name="setcontextmenuid"></a>  CMFCToolBarEditBoxButton::SetContextMenuID

ボタンに関連付けられているショートカット メニューのリソース ID を指定します。

```
void SetContextMenuID(UINT uiResID);
```

### <a name="parameters"></a>パラメーター

*uiCmd*<br/>
[in]ショートカット メニューのリソース ID。

### <a name="remarks"></a>Remarks

フレームワークでは、リソース ID を使用して、ユーザーがツール バー ボタンを右クリックしたときに、ショートカット メニューを作成します。

##  <a name="setflatmode"></a>  CMFCToolBarEditBoxButton::SetFlatMode

アプリケーションでは、エディット ボックス ボタンのフラット スタイルの外観を指定します。

```
static void __stdcall SetFlatMode(BOOL bFlat = TRUE);
```

### <a name="parameters"></a>パラメーター

*bFlat*<br/>
[in]エディット ボックス ボタンのフラット スタイル。 このパラメーターが TRUE の場合は、フラット スタイルの外観が有効にします。それ以外の場合、フラット スタイルの外観が無効です。

### <a name="remarks"></a>Remarks

エディット ボックス ボタンの既定のフラット スタイルは、TRUE です。 使用して、 [CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode)アプリケーションのフラット スタイルの外観を取得します。

##  <a name="setstyle"></a>  CMFCToolBarEditBoxButton::SetStyle

編集ボックス コントロールのツールバーのスタイルを指定します。

```
virtual void SetStyle(UINT nStyle);
```

### <a name="parameters"></a>パラメーター

*nStyle*<br/>
[in]新しいスタイルを設定します。

### <a name="remarks"></a>Remarks

このメソッドは、設定[CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle)に*nStyle*も無効になります、テキスト ボックス、アプリケーションは、カスタマイズ モードであるし、カスタマイズ モード (参照で、アプリケーションがないようにする場合[CMFCToolBar::SetCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode)と[CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode))。 参照してください[ツール バー コントロールのスタイル](../../mfc/reference/toolbar-control-styles.md)有効なスタイルのフラグの一覧についてはします。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CEdit クラス](../../mfc/reference/cedit-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)
