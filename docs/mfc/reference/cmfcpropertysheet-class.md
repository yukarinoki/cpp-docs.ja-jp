---
title: CMFCPropertySheet クラス
ms.date: 11/19/2018
f1_keywords:
- CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet::CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet::AddPage
- AFXPROPERTYSHEET/CMFCPropertySheet::AddPageToTree
- AFXPROPERTYSHEET/CMFCPropertySheet::AddTreeCategory
- AFXPROPERTYSHEET/CMFCPropertySheet::EnablePageHeader
- AFXPROPERTYSHEET/CMFCPropertySheet::GetHeaderHeight
- AFXPROPERTYSHEET/CMFCPropertySheet::GetLook
- AFXPROPERTYSHEET/CMFCPropertySheet::GetNavBarWidth
- AFXPROPERTYSHEET/CMFCPropertySheet::GetTab
- AFXPROPERTYSHEET/CMFCPropertySheet::InitNavigationControl
- AFXPROPERTYSHEET/CMFCPropertySheet::OnActivatePage
- AFXPROPERTYSHEET/CMFCPropertySheet::OnDrawPageHeader
- AFXPROPERTYSHEET/CMFCPropertySheet::OnRemoveTreePage
- AFXPROPERTYSHEET/CMFCPropertySheet::RemoveCategory
- AFXPROPERTYSHEET/CMFCPropertySheet::RemovePage
- AFXPROPERTYSHEET/CMFCPropertySheet::SetIconsList
- AFXPROPERTYSHEET/CMFCPropertySheet::SetLook
helpviewer_keywords:
- CMFCPropertySheet [MFC], CMFCPropertySheet
- CMFCPropertySheet [MFC], AddPage
- CMFCPropertySheet [MFC], AddPageToTree
- CMFCPropertySheet [MFC], AddTreeCategory
- CMFCPropertySheet [MFC], EnablePageHeader
- CMFCPropertySheet [MFC], GetHeaderHeight
- CMFCPropertySheet [MFC], GetLook
- CMFCPropertySheet [MFC], GetNavBarWidth
- CMFCPropertySheet [MFC], GetTab
- CMFCPropertySheet [MFC], InitNavigationControl
- CMFCPropertySheet [MFC], OnActivatePage
- CMFCPropertySheet [MFC], OnDrawPageHeader
- CMFCPropertySheet [MFC], OnRemoveTreePage
- CMFCPropertySheet [MFC], RemoveCategory
- CMFCPropertySheet [MFC], RemovePage
- CMFCPropertySheet [MFC], SetIconsList
- CMFCPropertySheet [MFC], SetLook
ms.assetid: 01d93573-9698-440f-a6a4-5bebbee879dc
ms.openlocfilehash: 6cdb2e966ca1878377fd26a6d4b9075090d32c3e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361805"
---
# <a name="cmfcpropertysheet-class"></a>CMFCPropertySheet クラス

`CMFCPropertySheet` クラスは、各プロパティ ページがページ タブ、ツール バー ボタン、ツリー コントロールのノード、またはリスト項目で示されるプロパティ シートをサポートします。

## <a name="syntax"></a>構文

```
class CMFCPropertySheet : public CPropertySheet
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCPropertySheet::CMFCPropertySheet](#cmfcpropertysheet)|`CMFCPropertySheet` オブジェクトを構築します。|
|`CMFCPropertySheet::~CMFCPropertySheet`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCPropertySheet::AddPage](#addpage)|プロパティ シートにページを追加します。|
|[CMFCPropertySheet::AddPageToTree](#addpagetotree)|ツリー コントロールに新しいプロパティ ページを追加します。|
|[CMFCPropertySheet::AddTreeCategory](#addtreecategory)|ツリー コントロールに新しいノードを追加します。|
|[CMFCPropertySheet::EnablePageHeader](#enablepageheader)|カスタム ヘッダーを描画する領域を各ページの上部に確保します。|
|[CMFCPropertySheet::GetHeaderHeight](#getheaderheight)|現在のヘッダーの高さを取得します。|
|[CMFCPropertySheet::GetLook](#getlook)|現在のプロパティ シートの外観を指定する列挙値を取得します。|
|[CMFCPropertySheet::GetNavBarWidth](#getnavbarwidth)|ナビゲーション バーの幅をピクセル単位で取得します。|
|[CMFCPropertySheet::GetTab](#gettab)|現在のプロパティ シート コントロールをサポートする内部タブ コントロール オブジェクトを取得します。|
|`CMFCPropertySheet::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol)|現在のプロパティ シート コントロールの外観を初期化します。|
|[CMFCPropertySheet::OnActivatePage](#onactivatepage)|プロパティ ページが有効になったときにフレームワークによって呼び出されます。|
|[CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader)|カスタム プロパティ ページのヘッダーを描画するためにフレームワークによって呼び出されます。|
|`CMFCPropertySheet::OnInitDialog`|[WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog)メッセージを処理します。 (C プロパティ シートをオーバーライドします[。::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|
|[CMFCPropertySheet::OnRemoveTreePage](#onremovetreepage)|ツリー コントロールからプロパティ ページを削除するためにフレームワークによって呼び出されます。|
|`CMFCPropertySheet::PreTranslateMessage`|ウィンドウ メッセージが変換メッセージおよびディスパッチ メッセージの Windows 関数にディスパッチされる前に、ウィンドウ[メッセージを](/windows/win32/api/winuser/nf-winuser-dispatchmessage)[変換](/windows/win32/api/winuser/nf-winuser-translatemessage)します。 ( `CPropertySheet::PreTranslateMessage`をオーバーライドします)。|
|[CMFCPropertySheet::RemoveCategory](#removecategory)|ツリー コントロールからノードを削除します。|
|[CMFCPropertySheet::RemovePage](#removepage)|プロパティ シートからプロパティ ページを削除します。|
|[CMFCPropertySheet::SetIconsList](#seticonslist)|Outlook ウィンドウのナビゲーション コントロールで使用されるイメージの一覧を指定します。|
|[CMFCPropertySheet::SetLook](#setlook)|プロパティ シートの外観を指定します。|

## <a name="remarks"></a>解説

`CMFCPropertySheet` クラスは、プロパティ シート (タブ ダイアログ ボックスとも呼ばれます) を表します。 `CMFCPropertySheet` クラスは、さまざまな方法でプロパティ ページを表示できます。

アプリケーションで `CMFCPropertySheet` クラスを使用するには、次の手順を実行します。

1. `CMFCPropertySheet` クラスから派生クラスを作成し、名前 (CMyPropertySheet など) を付けます。

1. 各プロパティ ページの[CMFC プロパティ ページ](../../mfc/reference/cmfcpropertypage-class.md)オブジェクトを構築します。

1. コンストラクターで[メソッド](#setlook)を呼び出します。 このメソッドのパラメーターで、プロパティ ページの表示方法として、プロパティ シートの上部または左側のタブ、Microsoft OneNote プロパティ シート スタイルのタブ、Microsoft Outlook ツール バー コントロールのボタン、ツリー コントロールのノード、プロパティ シートの左側の項目リストのいずれかを指定します。

1. Outlook ツール バーのスタイルでプロパティ シートを作成する場合は[、CMFCPropertySheet::SetIconsList](#seticonslist)メソッドを呼び出して、プロパティ ページとイメージ リストを関連付けます。

1. 各プロパティ ページの[メソッド](#addpage)を呼び出します。

1. `CMFCPropertySheet` コントロールを作成し、その `DoModal` メソッドを呼び出します。

## <a name="illustrations"></a>図

次の図は、埋め込みの Microsoft Outlook ツール バー スタイルのプロパティ シートを示しています。 プロパティ シートの左側に Outlook ツール バーが表示されます。

![CMFCPropertySheet カラー コントロール](../../mfc/reference/media/cmfcpropertysheet_color.png "CMFCPropertySheet カラー コントロール")

次の図は、[クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)オブジェクトを含むプロパティ シートを示しています。 このオブジェクトは、標準のコモン コントロール スタイルのプロパティ シートです。

![CMFCPropertySheet リストおよびプロパティ コントロール](../../mfc/reference/media/cmfcpropertysheet_list.png "CMFCPropertySheet リストおよびプロパティ コントロール")

次の図は、ツリー コントロール スタイルのプロパティ シートを示しています。

![プロパティツリー](../../mfc/reference/media/proptree.png "プロパティツリー")

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

[CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afx プロパティシート.h

## <a name="cmfcpropertysheetaddpage"></a><a name="addpage"></a>プロパティシート::ページの追加

プロパティ シートにページを追加します。

```
void AddPage(CPropertyPage* pPage);
```

### <a name="parameters"></a>パラメーター

*ページ*<br/>
[in]ページ オブジェクトへのポインター。 このパラメーターは NULL にはできません。

### <a name="remarks"></a>解説

このメソッドは、指定されたプロパティ ページをプロパティ シートの右端のタブとして追加します。 したがって、このメソッドを使用して、ページを左から右の順序で追加します。

プロパティ シートが Microsoft Outlook のスタイルの場合、フレームワークはプロパティ シートの左側にナビゲーション ボタンの一覧を表示します。 このメソッドは、プロパティ ページを追加した後、対応するボタンをリストに追加します。 プロパティ ページを表示するには、対応するボタンをクリックします。 プロパティ シートのスタイルの詳細については[、「CMFC プロパティ シート::SetLook](#setlook)」を参照してください。

## <a name="cmfcpropertysheetaddpagetotree"></a><a name="addpagetotree"></a>プロパティ シート::ページを追加します。

ツリー コントロールに新しいプロパティ ページを追加します。

```
void AddPageToTree(
    CMFCPropertySheetCategoryInfo* pCategory,
    CMFCPropertyPage* pPage,
    int nIconNum=-1,
    int nSelIconNum=-1);
```

### <a name="parameters"></a>パラメーター

*カテゴリ*<br/>
[in]親ツリー ノードへのポインター、または指定したページを最上位ノードに関連付ける場合は NULL。 このポインター[を取得](#addtreecategory)するには、メソッドを呼び出します。

*ページ*<br/>
[in]プロパティ ページ オブジェクトへのポインター。

*ニコンナム*<br/>
[in]アイコンの 0 から始まるインデックス、またはアイコンが使用されていない場合は -1。 ページが選択されていない場合、ツリー コントロールのプロパティ ページの横にアイコンが表示されます。 既定値は -1 です。

*ヌセアイコンヌ*<br/>
[in]アイコンの 0 から始まるインデックス、またはアイコンが使用されていない場合は -1。 ページが選択されると、ツリー コントロールのプロパティ ページの横にアイコンが表示されます。 既定値は -1 です。

### <a name="remarks"></a>解説

このメソッドは、プロパティ ページをツリー コントロールのリーフとして追加します。 プロパティ ページを追加するには、オブジェクト`CMFCPropertySheet`を作成し、*ルック*パラメーターを に設定して`CMFCPropertySheet::PropSheetLook_Tree`[CMFCPropertySheet::SetLook](#setlook)メソッドを呼び出し、このメソッドを使用してプロパティ ページを追加します。

## <a name="cmfcpropertysheetaddtreecategory"></a><a name="addtreecategory"></a>プロパティシート::ツリーカテゴリの追加

ツリー コントロールに新しいノードを追加します。

```
CMFCPropertySheetCategoryInfo* AddTreeCategory(
    LPCTSTR lpszLabel,
    int nIconNum=-1,
    int nSelectedIconNum=-1,
    const CMFCPropertySheetCategoryInfo* pParentCategory=NULL);
```

### <a name="parameters"></a>パラメーター

*ラベル*<br/>
[in]ノードの名前。

*ニコンナム*<br/>
[in]アイコンの 0 から始まるインデックス、またはアイコンが使用されていない場合は -1。 ページが選択されていない場合、ツリー コントロールのプロパティ ページの横にアイコンが表示されます。 既定値は -1 です。

*アイコンの数*<br/>
[in]アイコンの 0 から始まるインデックス、またはアイコンが使用されていない場合は -1。 ページが選択されると、ツリー コントロールのプロパティ ページの横にアイコンが表示されます。 既定値は -1 です。

*カテゴリ*<br/>
[in]親ツリー ノードへのポインター、または指定したページを最上位ノードに関連付ける場合は NULL。 このパラメーターを[設定します](#addtreecategory)。

### <a name="return-value"></a>戻り値

ツリー コントロール内の新しいノードへのポインター。

### <a name="remarks"></a>解説

このメソッドは、カテゴリとも呼ばれる新しいノードをツリー コントロールに追加するために使います。 ノードを追加するには、オブジェクトを`CMFCPropertySheet`作成し、*ルック*パラメーターを に設定して`CMFCPropertySheet::PropSheetLook_Tree`[CMFCPropertySheet::SetLook](#setlook)メソッドを呼び出し、このメソッドを使用してノードを追加します。

このメソッドの戻り値は、次の呼び出しで[使用](#addpagetotree)[します。](#addtreecategory)

## <a name="cmfcpropertysheetcmfcpropertysheet"></a><a name="cmfcpropertysheet"></a>プロパティシート::CMFC プロパティ シート

`CMFCPropertySheet` オブジェクトを構築します。

```
CMFCPropertySheet(
    UINT nIDCaption,
    CWnd* pParentWnd=NULL,
    UINT iSelectPage=0);

CMFCPropertySheet(
    LPCTSTR pszCaption,
    CWnd* pParentWnd=NULL,
    UINT iSelectPage=0);
```

### <a name="parameters"></a>パラメーター

*キャプション*<br/>
[in]プロパティ シートのキャプションを含む文字列。 Nll は指定できません。

*nIDキャプション*<br/>
[in]プロパティ シートのキャプションを含むリソース ID。

*pParentWnd*<br/>
[in]プロパティ シートの親ウィンドウへのポインター。 既定値は NULL です。

*ページを選択します。*<br/>
[in]最上位のプロパティ ページの 0 から始まるインデックス。 既定値は 0 です。

### <a name="remarks"></a>解説

詳細については[、CPropertySheet::CPropertySheet](../../mfc/reference/cpropertysheet-class.md#cpropertysheet)コンストラクターのパラメーターを参照してください。

## <a name="cmfcpropertysheetenablepageheader"></a><a name="enablepageheader"></a>プロパティ シート::ページ ヘッダーを有効にします。

カスタム ヘッダーを描画する領域を各ページの上部に確保します。

```
void EnablePageHeader(int nHeaderHeight);
```

### <a name="parameters"></a>パラメーター

*ヘッダーの高さ*<br/>
[in]ヘッダーの高さ (ピクセル単位)。

### <a name="remarks"></a>解説

*パラメーターの*値を使用してカスタム ヘッダーを描画するには、[メソッド](#ondrawpageheader)をオーバーライドします。

## <a name="cmfcpropertysheetgetheaderheight"></a><a name="getheaderheight"></a>プロパティシート::ゲットヘッダーの高さ

現在のヘッダーの高さを取得します。

```
int GetHeaderHeight() const;
```

### <a name="return-value"></a>戻り値

ヘッダーの高さ (ピクセル単位)。

### <a name="remarks"></a>解説

このメソッド[を](#enablepageheader)呼び出す前に、メソッドを呼び出します。

## <a name="cmfcpropertysheetgetlook"></a><a name="getlook"></a>プロパティシート::ゲットルック

現在のプロパティ シートの外観を指定する列挙値を取得します。

```
PropSheetLook GetLook() const;
```

### <a name="return-value"></a>戻り値

プロパティ シートの外観を指定する列挙値の 1 つ。 指定できる値の一覧については[、CMFC プロパティ シート](#setlook)の「解説」セクションの列挙テーブルを参照してください。

## <a name="cmfcpropertysheetgetnavbarwidth"></a><a name="getnavbarwidth"></a>プロパティシート::取得ナブバー幅

ナビゲーション バーの幅を取得します。

```
int GetNavBarWidth() const;
```

### <a name="return-value"></a>戻り値

軸スクロール バーの幅 (ピクセル単位)。

## <a name="cmfcpropertysheetgettab"></a><a name="gettab"></a>プロパティシート::ゲットタブ

現在のプロパティ シート コントロールをサポートする内部タブ コントロール オブジェクトを取得します。

```
CMFCTabCtrl& GetTab() const;
```

### <a name="return-value"></a>戻り値

内部タブ コントロール オブジェクト。

### <a name="remarks"></a>解説

プロパティ シートは、ツリー コントロール、ナビゲーション ボタンの一覧、タブ付きページのセットなど、さまざまなスタイルで表示されるように設定できます。

このメソッドを呼び出す前に、プロパティ シート コントロールの外観を設定する[CMFCPropertySheet::SetLook](#setlook)メソッドを呼び出します。 次に、[内部](#initnavigationcontrol)タブ コントロール オブジェクトを初期化するメソッドを呼び出します。 このメソッドは、タブ コントロール オブジェクトを取得し、そのオブジェクトを使用してプロパティ シートのタブを操作するために使います。

このメソッドは、プロパティ シート コントロールが Microsoft OneNote のスタイルに表示されるように設定されていない場合、デバッグ モードでアサートします。

## <a name="cmfcpropertysheetinitnavigationcontrol"></a><a name="initnavigationcontrol"></a>プロパティシート::イニトナビゲーションコントロール

現在のプロパティ シート コントロールの外観を初期化します。

```
virtual CWnd* InitNavigationControl();
```

### <a name="return-value"></a>戻り値

プロパティ シート コントロールのウィンドウへのポインター。

### <a name="remarks"></a>解説

プロパティ シート コントロールは、タブ付きページ、ツリー コントロール、ナビゲーション ボタンの一覧など、さまざまな形式で表示できます。 プロパティ シート コントロールの外観を指定するには[、CMFCPropertySheet::SetLook](#setlook)メソッドを使用します。

## <a name="cmfcpropertysheetonactivatepage"></a><a name="onactivatepage"></a>プロパティシート::オンアクティブページ

プロパティ ページが有効になったときにフレームワークによって呼び出されます。

```
virtual void OnActivatePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>パラメーター

*ページ*<br/>
[in]有効なプロパティ ページを表すプロパティ ページ オブジェクトへのポインター。

### <a name="remarks"></a>解説

既定では、このメソッドは、有効なプロパティ ページが表示されるようにします。 現在のプロパティ シートのスタイルに Outlook ペインが含まれている場合、このメソッドは対応する Outlook ボタンをチェック済みの状態に設定します。

## <a name="cmfcpropertysheetondrawpageheader"></a><a name="ondrawpageheader"></a>プロパティシート::ページヘッダー

カスタム プロパティ ページのヘッダーを描画するために、フレームワークによって呼び出されます。

```
virtual void OnDrawPageHeader(
    CDC* pDC,
    int nPage,
    CRect rectHeader);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*nページ*<br/>
[in]0 から始まるプロパティ ページ番号。

*ヘッダーを修正する*<br/>
[in]ヘッダーの描画先を指定する外接する四角形。

### <a name="remarks"></a>解説

既定では、このメソッドは何も実行しません。 このメソッドをオーバーライドする場合は、フレームワークがこのメソッドを呼び出す前に[、CMFCPropertySheet::EnablePageHeader](#enablepageheader)メソッドを呼び出します。

## <a name="cmfcpropertysheetonremovetreepage"></a><a name="onremovetreepage"></a>プロパティ シート::オンムースツリーページ

ツリー コントロールからプロパティ ページを削除するためにフレームワークによって呼び出されます。

```
virtual BOOL OnRemoveTreePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>パラメーター

*ページ*<br/>
[in]削除するプロパティ ページを表すプロパティ ページ オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcpropertysheetremovecategory"></a><a name="removecategory"></a>プロパティシート::カテゴリの削除

ツリー コントロールからノードを削除します。

```
void RemoveCategory(CMFCPropertySheetCategoryInfo* pCategory);
```

### <a name="parameters"></a>パラメーター

*カテゴリ*<br/>
[in]削除するカテゴリ (ノード) へのポインター。

### <a name="remarks"></a>解説

このメソッドは、ツリー コントロールからノード (カテゴリとも呼ばれます) を削除するために使います。 ツリー コントロールにノードを追加するには[、CMFCPropertySheet::AddTreeCategory](#addtreecategory)メソッドを使用します。

## <a name="cmfcpropertysheetremovepage"></a><a name="removepage"></a>プロパティシート::ページの削除

プロパティ シートからプロパティ ページを削除します。

```
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```

### <a name="parameters"></a>パラメーター

*ページ*<br/>
[in]削除するプロパティ ページを表すプロパティ ページ オブジェクトへのポインター。 Nll は指定できません。

*nページ*<br/>
[in]削除するページの 0 から始まるインデックス。

### <a name="remarks"></a>解説

このメソッドは、指定されたプロパティ ページを削除し、関連付けられているウィンドウを破棄します。 *pPage*パラメーターが指定するプロパティ ページ オブジェクトは[、CMFC プロパティ シート](../../mfc/reference/cmfcpropertysheet-class.md)ウィンドウが閉じるまで破棄されません。

## <a name="cmfcpropertysheetseticonslist"></a><a name="seticonslist"></a>プロパティシート::セットアイコンリスト

Outlook ウィンドウのナビゲーション コントロールで使用されるイメージの一覧を指定します。

```
BOOL SetIconsList(
    UINT uiImageListResID,
    int cx,
    COLORREF clrTransparent=RGB(255, 0, 255));
void SetIconsList(HIMAGELIST hIcons);
```

### <a name="parameters"></a>パラメーター

*を返します。*<br/>
[in]イメージ リストのリソース ID。

*Cx*<br/>
[in]イメージ リスト内のアイコンの幅 (ピクセル単位)。

*clr透明*<br/>
[in]透明なイメージの色。 この色であるイメージの部分は透明になります。 デフォルト値はカラー マゼンタ RGB(255,0,255)です。

*hIcons*<br/>
[in]既存のイメージ リストへのハンドル。

### <a name="return-value"></a>戻り値

最初のメソッドオーバーロード構文では、このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

プロパティ シートが Microsoft Outlook のスタイルの場合、フレームワークは、プロパティ シートの左側に、Outlook ペイン コントロールと呼ばれるナビゲーション ボタンの一覧を表示します。 このメソッドは、Outlook ペイン コントロールで使用するイメージ リストを設定するために使います。

このメソッドをサポートするメソッドの詳細については[、「CImageList::作成](../../mfc/reference/cimagelist-class.md#create)と[CImageList::Add](../../mfc/reference/cimagelist-class.md#add)」を参照してください。 プロパティ シートのスタイルを設定する方法の詳細については[、「CMFC プロパティ シート::SetLook](#setlook)」を参照してください。

## <a name="cmfcpropertysheetsetlook"></a><a name="setlook"></a>プロパティシート::セットルック

プロパティ シートの外観を指定します。

```
void SetLook(
    PropSheetLook look,
    int nNavControlWidth=100);
```

### <a name="parameters"></a>パラメーター

*ほら*<br/>
[in]プロパティ シートの外観を指定する列挙値の 1 つ。 プロパティ シートの既定のスタイルは`CMFCPropertySheet::PropSheetLook_Tabs`です。 詳細については、このトピックの「解説」の表を参照してください。

*ナブコントロール幅*<br/>
[in]ナビゲーション コントロールの幅 (ピクセル単位)。 既定値は 100 です。

### <a name="remarks"></a>解説

既定以外のスタイルでプロパティ シートを表示するには、プロパティ シート ウィンドウを作成する前に、このメソッドを呼び出します。

次の表は *、look*パラメーターで指定できる列挙値の一覧です。

|[値]|説明|
|-----------|-----------------|
|`CMFCPropertySheet::PropSheetLook_Tabs`|(デフォルト)各プロパティ ページのタブを表示します。 タブはプロパティ シートの上部に表示され、1 行に収まるよりも多くのタブがある場合は積み重ねられます。|
|`CMFCPropertySheet::PropSheetLook_OutlookBar`|ナビゲーション ボタンの一覧を、Outlook バーのスタイルで、プロパティ シートの左側に表示します。 リストの各ボタンは、プロパティ ページに対応しています。 リストの表示領域に収まるボタン数より多くのボタンがある場合、フレームワークはスクロール矢印を表示します。|
|`CMFCPropertySheet::PropSheetLook_Tree`|プロパティ シートの左側にツリー コントロールを表示します。 ツリー コントロールの親ノードまたは子ノードは、それぞれプロパティ ページに対応します。 ツリー コントロールの表示領域に収まる数を超えるノードがある場合、フレームワークはスクロール矢印を表示します。|
|`CMFCPropertySheet::PropSheetLook_OneNoteTabs`|各プロパティ ページのスタイルで、タブを表示します。 フレームワークは、プロパティ シートの上部にタブを表示し、1 行に収まるタブ数よりも多い場合はスクロール矢印を表示します。|
|`CMFCPropertySheet::PropSheetLook_List`|プロパティ シートの左側にリストを表示します。 各リスト項目は、プロパティ ページに対応します。 リストの表示領域に収まるよりも多くのリスト項目がある場合、フレームワークはスクロール矢印を表示します。|

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyPage クラス](../../mfc/reference/cmfcpropertypage-class.md)<br/>
[クラス](../../mfc/reference/cmfcoutlookbar-class.md)
