---
title: CMFCToolBarComboBoxButton クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::AddItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::AddSortedItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::Compare
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::CreateEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::DeleteItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::FindItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetByCmd
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetComboBox
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCount
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCountAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCurSel
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCurSelAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetEditCtrl
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemData
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemDataAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemDataPtrAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetText
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetTextAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::IsCenterVert
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::IsFlatMode
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::RemoveAllItems
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SelectItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SelectItemAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetCenterVert
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetDropDownHeight
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetFlatMode
helpviewer_keywords:
- CMFCToolBarComboBoxButton [MFC], CMFCToolBarComboBoxButton
- CMFCToolBarComboBoxButton [MFC], AddItem
- CMFCToolBarComboBoxButton [MFC], AddSortedItem
- CMFCToolBarComboBoxButton [MFC], Compare
- CMFCToolBarComboBoxButton [MFC], CreateEdit
- CMFCToolBarComboBoxButton [MFC], DeleteItem
- CMFCToolBarComboBoxButton [MFC], FindItem
- CMFCToolBarComboBoxButton [MFC], GetByCmd
- CMFCToolBarComboBoxButton [MFC], GetComboBox
- CMFCToolBarComboBoxButton [MFC], GetCount
- CMFCToolBarComboBoxButton [MFC], GetCountAll
- CMFCToolBarComboBoxButton [MFC], GetCurSel
- CMFCToolBarComboBoxButton [MFC], GetCurSelAll
- CMFCToolBarComboBoxButton [MFC], GetEditCtrl
- CMFCToolBarComboBoxButton [MFC], GetItem
- CMFCToolBarComboBoxButton [MFC], GetItemAll
- CMFCToolBarComboBoxButton [MFC], GetItemData
- CMFCToolBarComboBoxButton [MFC], GetItemDataAll
- CMFCToolBarComboBoxButton [MFC], GetItemDataPtrAll
- CMFCToolBarComboBoxButton [MFC], GetText
- CMFCToolBarComboBoxButton [MFC], GetTextAll
- CMFCToolBarComboBoxButton [MFC], IsCenterVert
- CMFCToolBarComboBoxButton [MFC], IsFlatMode
- CMFCToolBarComboBoxButton [MFC], RemoveAllItems
- CMFCToolBarComboBoxButton [MFC], SelectItem
- CMFCToolBarComboBoxButton [MFC], SelectItemAll
- CMFCToolBarComboBoxButton [MFC], SetCenterVert
- CMFCToolBarComboBoxButton [MFC], SetDropDownHeight
- CMFCToolBarComboBoxButton [MFC], SetFlatMode
ms.assetid: 32fa39f7-8e4e-4f0a-a31d-7b540d969a6c
ms.openlocfilehash: e3c124103aa95d9db5095e438a6b21d46c7cb35d
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58772073"
---
# <a name="cmfctoolbarcomboboxbutton-class"></a>CMFCToolBarComboBoxButton クラス

コンボ ボックス コントロールを含むツール バー ボタン ( [CComboBox クラス](../../mfc/reference/ccombobox-class.md))。

## <a name="syntax"></a>構文

```
class CMFCToolBarComboBoxButton : public CMFCToolBarButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton](#cmfctoolbarcomboboxbutton)|`CMFCToolBarComboBoxButton` を構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCToolBarComboBoxButton::AddItem](#additem)|コンボ ボックスの一覧の末尾に項目を追加します。|
|[CMFCToolBarComboBoxButton::AddSortedItem](#addsorteditem)|コンボ ボックスの一覧に項目を追加します。 リスト内の項目の順序によって指定されます`Compare`します。|
|[CMFCToolBarComboBoxButton::Compare](#compare)|2 つの項目を比較します。 呼ばれる並べ替えに項目を`AddSortedItems`コンボ ボックスの一覧に追加します。|
|[CMFCToolBarComboBoxButton::CreateEdit](#createedit)|コンボ ボックス ボタンの新しい編集コントロールを作成します。|
|[CMFCToolBarComboBoxButton::DeleteItem](#deleteitem)|コンボ ボックスの一覧から項目を削除します。|
|[CMFCToolBarComboBoxButton::FindItem](#finditem)|指定した文字列が含まれている項目のインデックスを返します。|
|[CMFCToolBarComboBoxButton::GetByCmd](#getbycmd)|指定したコマンド ID に置き換えます。 コンボ ボックス ボタンへのポインターを返します|
|[CMFCToolBarComboBoxButton::GetComboBox](#getcombobox)|コンボ ボックス ボタンに埋め込まれているコンボ ボックス コントロールへのポインターを返します。|
|[CMFCToolBarComboBoxButton::GetCount](#getcount)|コンボ ボックスの一覧で項目の数を返します。|
|[CMFCToolBarComboBoxButton::GetCountAll](#getcountall)|コンボ ボックス ボタンを持つ指定したコマンド ID を検索します。 コンボ ボックスでそのボタンのボックスの一覧の項目の数を返します。|
|[CMFCToolBarComboBoxButton::GetCurSel](#getcursel)|コンボ ボックス リストで選択した項目のインデックスを返します。|
|[CMFCToolBarComboBoxButton::GetCurSelAll](#getcurselall)|コンボ ボックス ボタンを指定したコマンド ID があり、そのボタンのボックスの一覧をコンボ ボックスで選択した項目のインデックスを返しますを検索します。|
|[CMFCToolBarComboBoxButton::GetEditCtrl](#geteditctrl)|コンボ ボックス ボタンに埋め込まれたエディット コントロールへのポインターを返します。|
|[CMFCToolBarComboBoxButton::GetItem](#getitem)|コンボ ボックスで指定したインデックスに関連付けられている文字列のボックスの一覧を返します。|
|[CMFCToolBarComboBoxButton::GetItemAll](#getitemall)|コンボ ボックス ボタンを指定したコマンド ID を持つし、そのボタンのコンボ ボックスの一覧内のインデックスに関連付けられている文字列を返しますを検索します。|
|[CMFCToolBarComboBoxButton::GetItemData](#getitemdata)|コンボ ボックスで指定したインデックスに関連付けられている 32 ビット値のボックスの一覧を返します。|
|[CMFCToolBarComboBoxButton::GetItemDataAll](#getitemdataall)|コンボ ボックス ボタンを指定したコマンド ID を持つし、そのボタンのコンボ ボックスの一覧内のインデックスに関連付けられている 32 ビット値を返しますを検索します。|
|[CMFCToolBarComboBoxButton::GetItemDataPtrAll](#getitemdataptrall)|コンボ ボックス ボタンを持つ指定したコマンド ID を検索します。 取得しますが 32 ビットの値には、そのボタン、およびポインターとして 32 ビットの値を返しますのコンボ ボックスの一覧内のインデックスが関連付けられています。|
|[CMFCToolBarComboBoxButton::GetText](#gettext)|コンボ ボックスの編集コントロールからテキストを返します。|
|[CMFCToolBarComboBoxButton::GetTextAll](#gettextall)|コンボ ボックス ボタンを指定したコマンド ID があり、そのボタンの編集コントロールからテキストを返しますを検索します。|
|[CMFCToolBarComboBoxButton::IsCenterVert](#iscentervert)|アプリケーションのコンボ ボックス ボタンを中央に配置またはツールバーの上部に揃えて配置するかどうかを判断します。|
|[CMFCToolBarComboBoxButton::IsFlatMode](#isflatmode)|アプリケーションのコンボ ボックス ボタンはフラットに表示するかどうかを判断します。|
|[CMFCToolBarComboBoxButton::RemoveAllItems](#removeallitems)|一覧からすべての項目のボックスし、コンボ ボックスのコントロールの編集を削除します。|
|[CMFCToolBarComboBoxButton::SelectItem](#selectitem)|に従って、そのインデックス、32 ビット値、または文字列、コンボ ボックスで項目を選択し、選択範囲のコンボ ボックス コントロールを通知します。|
|[CMFCToolBarComboBoxButton::SelectItemAll](#selectitemall)|コンボ ボックス ボタンを持つ指定したコマンド ID を検索します。 呼び出し`SelectItem`に従って、文字列、キーワード、または 32 ビット値には、そのボタンのコンボ ボックス項目を選択します。|
|[CMFCToolBarComboBoxButton::SetCenterVert](#setcentervert)|アプリケーションのコンボ ボックス ボタンを垂直方向の中央またはツールバーの上部に揃えて配置するかどうかを指定します。|
|[CMFCToolBarComboBoxButton::SetDropDownHeight](#setdropdownheight)|ドロップダウン リスト ボックスの高さを設定します。|
|[CMFCToolBarComboBoxButton::SetFlatMode](#setflatmode)|アプリケーションのコンボ ボックス ボタンにフラットな外観があるかどうかを指定します。|

## <a name="remarks"></a>Remarks

ツールバーにコンボ ボックス ボタンを追加するには、次の手順を実行します。

1. 親ツール バー リソースでボタンのダミー リソース ID を予約します。

2. `CMFCToolBarComboBoxButton` オブジェクトを構築します。

3. AFX_WM_RESETTOOLBAR メッセージを処理するメッセージ ハンドラーで、ダミー ボタンを置き換える新しいコンボ ボックス ボタンを使用して[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)します。

詳細については、「[チュートリアル:コントロールのツールバーに追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)します。 コンボ ボックスのツールバーのボタンの例は、VisualStudioDemo プロジェクト例を参照してください。

## <a name="example"></a>例

`CMFCToolBarComboBoxButton` クラスのさまざまなメソッドの使用方法を次の例に示します。 例では、編集とコンボ ボックスを有効にする、アプリケーションでボックスのボタンのコンボの垂直位置を設定、にドロップしたときに、リスト ボックスの高さを設定、アプリケーションでのフラット スタイルのコンボ ボックス ボタンの外観を設定する方法を示しています。、エディット ボックス、コンボ ボックス ボタンでテキストを設定します。 このコード スニペットの一部、 [Visual Studio のデモ サンプル](../../overview/visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_VisualStudioDemo#36](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_1.cpp)]
[!code-cpp[NVC_MFC_VisualStudioDemo#37](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxtoolbarcomboboxbutton.h

##  <a name="additem"></a>  CMFCToolBarComboBoxButton::AddItem

リスト ボックスに一意の項目を追加します。

```
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>パラメーター

*lpszItem*<br/>
[in]リスト ボックスに追加する項目のテキスト。

*dwData*<br/>
[in]リスト ボックスに追加する項目に関連付けられたデータ。

### <a name="return-value"></a>戻り値

リスト ボックスの最後の項目のインデックス。

### <a name="remarks"></a>Remarks

リスト ボックスのスタイルが並べ替えられる場合は、このメソッドを使用しないでください。

項目のテキストのリスト ボックスが既にいる場合、既存の項目に新しいデータが格納されます。 項目の検索は大文字小文字を区別します。

##  <a name="addsorteditem"></a>  CMFCToolBarComboBoxButton::AddSortedItem

定義されている順序でリスト ボックスに項目を追加、[比較](#compare)メソッド。

```
virtual INT_PTR AddSortedItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>パラメーター

*lpszItem*<br/>
[in]リスト ボックスに追加する項目のテキスト。

*dwData*<br/>
[in]リスト ボックスに追加する項目に関連付けられたデータ。

### <a name="return-value"></a>戻り値

リスト ボックスに追加された項目のインデックス。

### <a name="remarks"></a>Remarks

特定の順序でリスト ボックスに項目を追加するのにには、この関数を使用します。

##  <a name="canbestretched"></a>  CMFCToolBarComboBoxButton::CanBeStretched

コンボ ボックス ボタンのサイズを変更できるかどうかを示します。

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>戻り値

TRUE を返します。

##  <a name="cmfctoolbarcomboboxbutton"></a>  CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton

構築、 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)オブジェクト。

```
CMFCToolBarComboBoxButton(
    UINT uiID,
    int iImage,
    DWORD dwStyle=CBS_DROPDOWNLIST,
    int iWidth=0);
```

### <a name="parameters"></a>パラメーター

*uiID*<br/>
[in]新しいボタンのコマンド ID。

*画像を*<br/>
[in]新しいボタンに関連付けられているイメージのイメージのインデックス。

*dwStyle*<br/>
[in]新しいボタンのスタイル。

*iWidth*<br/>
[in]新しいボタンのピクセル単位の幅。

### <a name="remarks"></a>Remarks

既定の幅は、150 ピクセルです。

ツール バー ボタンのスタイルの一覧については、次を参照してください[ツール バー コントロールのスタイル。](../../mfc/reference/toolbar-control-styles.md)

##  <a name="cleardata"></a>  CMFCToolBarComboBoxButton::ClearData

ユーザー定義データを削除します。

```
virtual void ClearData();
```

### <a name="remarks"></a>Remarks

既定では、このメソッドは何もしません。 ユーザー定義データを削除する場合は、派生クラスでこのメソッドをオーバーライドします。

##  <a name="compare"></a>  CMFCToolBarComboBoxButton::Compare

2 つの文字列を比較します。

```
virtual int Compare(
    LPCTSTR lpszItem1,
    LPCTSTR lpszItem2);
```

### <a name="parameters"></a>パラメーター

*lpszItem1*<br/>
[in]比較する最初の文字列。

*lpszItem2*<br/>
[in]比較する 2 つ目の文字列。

### <a name="return-value"></a>戻り値

辞書式の大文字小文字を区別、文字列関係を示す値。 次の表では、使用可能な値を示します。

|[値]|説明|
|-----------|-----------------|
|\<0|最初の文字列は小さく、1 つ目です。|
|0|最初の文字列では、2 番目と同じです。|
|>0|最初の文字列は、2 番目より大きいです。|

### <a name="remarks"></a>Remarks

リスト ボックス内の項目の並べ替え方法を変更するには、このメソッドをオーバーライドします。

比較では大文字小文字を区別します。

このメソッドの呼び出し元のみ、 [AddSortedItem](#addsorteditem)メソッド。

##  <a name="copyfrom"></a>  CMFCToolBarComboBoxButton::CopyFrom

指定した状態をコピー`CMFCToolBarComboBoxButton`を現在のオブジェクト。

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>パラメーター

*src*<br/>
[in]ソース`CMFCToolBarComboBoxButton`オブジェクト。

##  <a name="createcombo"></a>  CMFCToolBarComboBoxButton::CreateCombo

コンボ ボックス ボタンの新しいコンボ ボックスを作成します。

```
virtual CComboBox* CreateCombo(
    CWnd* pWndParent,
    const CRect& rect);
```

### <a name="parameters"></a>パラメーター

*pWndParent*<br/>
[in]ボタンの親ウィンドウへのポインター。

*rect*<br/>
[in]コンボ ボックスの外接する四角形。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、新しいコンボ ボックスへのポインターそれ以外の場合は NULL です。

##  <a name="createedit"></a>  CMFCToolBarComboBoxButton::CreateEdit

コンボ ボックス ボタンの新しい編集ボックスを作成します。

```
virtual CMFCToolBarComboBoxEdit* CreateEdit(
    CWnd* pWndParent,
    const CRect& rect,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>パラメーター

*pWndParent*<br/>
[in]ボタンの親ウィンドウへのポインター。

*rect*<br/>
[in]新しい編集ボックスの外接する四角形。

*dwEditStyle*<br/>
[in]新しい編集ボックスのスタイルを制御します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、新しい編集ボックスへのポインターそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

フレームワークは、コンボ ボックス ボタンの新しい編集ボックスの作成時に、このメソッドを呼び出します。 変更するには、このメソッドをオーバーライドする方法[CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md)が作成されます。

##  <a name="deleteitem"></a>  CMFCToolBarComboBoxButton::DeleteItem

リスト ボックスから、指定した項目を削除します。

```
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);
  BOOL DeleteItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*iIndex*<br/>
[in]削除する項目の 0 から始まるインデックス。

*dwData*<br/>
[in]削除する項目に関連付けられたデータ。

*lpszText*<br/>
[in]削除する項目のテキスト。 同じテキストで複数の項目がある場合は、最初の項目が削除されます。

### <a name="return-value"></a>戻り値

TRUE の場合、項目が見つかり、正常に削除されました。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

##  <a name="duplicatedata"></a>  CMFCToolBarComboBoxButton::DuplicateData

ユーザー定義データを重複します。

```
virtual void DuplicateData();
```

### <a name="remarks"></a>Remarks

既定では、このメソッドは何もしません。 ユーザー定義データをコピーする場合は、派生クラスでこのメソッドをオーバーライドします。

##  <a name="enablewindow"></a>  CMFCToolBarComboBoxButton::EnableWindow

有効または編集し、コンボ ボックスを無効にします。

```
virtual void EnableWindow(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
[in]編集し、コンボ ボックスを有効にする場合は TRUE編集し、コンボ ボックスを無効にする場合は FALSE。

### <a name="remarks"></a>Remarks

無効にすると、コントロールがアクティブになることはできず、ユーザー入力を受け入れることはできません。

##  <a name="exporttomenubutton"></a>  CMFCToolBarComboBoxButton::ExportToMenuButton

コピー コンボ ボックス ボタンのコマンドを使用して指定されたメニューには、アプリケーションの文字列テーブルから文字列の id。

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>パラメーター

*メニュー ボタン*<br/>
[out]メニュー ボタンへの参照。

### <a name="return-value"></a>戻り値

常に TRUE です。

##  <a name="finditem"></a>  CMFCToolBarComboBoxButton::FindItem

指定した文字列を含むリスト ボックスで、最初の項目のインデックスを返します。

```
int FindItem(LPCTSTR lpszText) const;
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
[in]リスト ボックスで検索するテキスト。

### <a name="return-value"></a>戻り値

項目のインデックスまたは、CB_ERR 項目が見つからない場合。

### <a name="remarks"></a>Remarks

##  <a name="getbycmd"></a>  CMFCToolBarComboBoxButton::GetByCmd

指定したコマンド ID を持つコンボ ボックス ボタンにポインターを取得します。

```
static CMFCToolBarComboBoxButton* GetByCmd(
    UINT uiCmd,
    BOOL bIsFocus=FALSE);
```

### <a name="parameters"></a>パラメーター

*uiCmd*<br/>
[in]コンボ ボックス ボタンのコマンド ID。

*bIsFocus*<br/>
[in]フォーカスされたボタンをのみ検索する場合は Trueすべてのボタンを検索する場合は FALSE。

### <a name="return-value"></a>戻り値

コンボ ボックス ボタン; へのポインターまたは、ボタンが見つからない場合は NULL です。

### <a name="remarks"></a>Remarks

##  <a name="getcombobox"></a>  CMFCToolBarComboBoxButton::GetComboBox

コンボ ボックス ボタンに含まれるコンボ ボックスへのポインターを返します。

```
CComboBox* GetComboBox() const;
```

### <a name="return-value"></a>戻り値

ポインター、 [CComboBox クラス](../../mfc/reference/ccombobox-class.md)オブジェクトのメソッドが成功したかどうかは、それ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

##  <a name="getcontextmenuid"></a>  CMFCToolBarComboBoxButton::GetContextMenuID

コンボ ボックス ボタンのショートカット メニューのリソース ID を取得します。

```
UINT GetContextMenuID();
```

### <a name="return-value"></a>戻り値

ショートカット メニューの リソース id。

##  <a name="getcount"></a>  CMFCToolBarComboBoxButton::GetCount

リスト ボックス項目の数を返します。

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>戻り値

リスト ボックス内の項目の数。

### <a name="remarks"></a>Remarks

##  <a name="getcountall"></a>  CMFCToolBarComboBoxButton::GetCountAll

指定したコマンド ID を持つコンボ ボックス ボタンのリスト ボックスで項目の数を取得します。

```
static int GetCountAll(UINT uiCmd);
```

### <a name="parameters"></a>パラメーター

*uiCmd*<br/>
[in]コンボ ボックス ボタンのコマンド ID。

### <a name="return-value"></a>戻り値

リスト ボックス内の項目の数それ以外の場合、CB_ERR 場合は、コンボ ボックス ボタンが見つかりません。

### <a name="remarks"></a>Remarks

##  <a name="getcursel"></a>  CMFCToolBarComboBoxButton::GetCurSel

リスト ボックスで現在選択されている項目のインデックスを取得します。

```
int GetCurSel() const;
```

### <a name="return-value"></a>戻り値

リスト ボックスで現在選択されている項目のインデックスまたは、CB_ERR 項目が選択されていない場合。

### <a name="remarks"></a>Remarks

リスト ボックスのインデックスは 0 から始まります。

##  <a name="getcurselall"></a>  CMFCToolBarComboBoxButton::GetCurSelAll

指定したコマンド ID を持つボックス ボタンをコンボ ボックスで現在選択されている項目のインデックスを返します

```
static int GetCurSelAll(UINT uiCmd);
```

### <a name="parameters"></a>パラメーター

*uiCmd*<br/>
[in]コンボ ボックス ボタンのコマンド ID。

### <a name="return-value"></a>戻り値

リスト ボックスで現在選択されている項目のインデックスそれ以外の場合、項目が選択されていない場合、CB_ERR またはコンボ ボックス ボタンは存在しません。

### <a name="remarks"></a>Remarks

リスト ボックスのインデックスは 0 から始まります。

##  <a name="geteditctrl"></a>  CMFCToolBarComboBoxButton::GetEditCtrl

コンボ ボックス ボタンに含まれる編集ボックスへのポインターを返します。

```
virtual CEdit* GetEditCtrl();
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、エディット ボックスへのポインターそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

##  <a name="gethwnd"></a>  CMFCToolBarComboBoxButton::GetHwnd

コンボ ボックスのウィンドウ ハンドルを返します。

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>戻り値

ウィンドウのハンドル、またはコンボ ボックスはウィンドウのオブジェクトに関連付けられていない場合は NULL です。

##  <a name="getitem"></a>  CMFCToolBarComboBoxButton::GetItem

リスト ボックスで指定したインデックス位置にある項目に関連付けられている文字列を返します。

```
LPCTSTR GetItem(int iIndex=-1) const;
```

### <a name="parameters"></a>パラメーター

*iIndex*<br/>
[in]リスト ボックス内の項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

アイテムに関連付けられている文字列へのポインターそれ以外の場合、インデックス パラメーターが有効でない場合、またはインデックスのパラメーターが-1 とコンボ ボックスで選択した項目がない場合は NULL です。

### <a name="remarks"></a>Remarks

-1 のインデックスのパラメーターは、現在選択されている項目の文字列を返します。

##  <a name="getitemall"></a>  CMFCToolBarComboBoxButton::GetItemAll

指定したコマンド ID を持つコンボ ボックス ボタンのリスト ボックスで指定したインデックス位置にある項目に関連付けられている文字列を返します

```
static LPCTSTR GetItemAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>パラメーター

*uiCmd*<br/>
[in]コンボ ボックス ボタンのコマンド ID。

*iIndex*<br/>
[in]リスト ボックス内の項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、項目の文字列へのポインターそれ以外の場合、インデックスが有効でない場合は、NULL、コンボ ボックス ボタンが見つからない、またはインデックスが-1 とコンボ ボックスで選択した項目がない場合。

### <a name="remarks"></a>Remarks

-1 のインデックス値は、現在選択されている項目の文字列を返します。

##  <a name="getitemdata"></a>  CMFCToolBarComboBoxButton::GetItemData

リスト ボックスで指定したインデックス位置にある項目に関連付けられているデータを返します。

```
DWORD_PTR GetItemData(int iIndex=-1) const;
```

### <a name="parameters"></a>パラメーター

*iIndex*<br/>
[in]リスト ボックス内の項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

項目に関連付けられたデータまたは、項目が存在しない場合は 0。

### <a name="remarks"></a>Remarks

-1 のインデックスのパラメーターは、現在選択されている項目に関連付けられたデータを返します。

##  <a name="getitemdataall"></a>  CMFCToolBarComboBoxButton::GetItemDataAll

特定のコマンド ID を持つコンボ ボックス ボタンのリスト ボックスで指定したインデックス位置にある項目に関連付けられているデータを返します

```
static DWORD_PTR GetItemDataAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>パラメーター

*uiCmd*<br/>
[in]コンボ ボックス ボタンのコマンド ID。

*iIndex*<br/>
[in]リスト ボックス内の項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、アイテムに関連付けられているデータそれ以外の場合、指定したインデックスが有効でない場合は 0 または CB_ERR 場合は、コンボ ボックス ボタンは存在しません。

### <a name="remarks"></a>Remarks

-1 のインデックスのパラメーターは、現在選択されている項目に関連付けられたデータを返します。

##  <a name="getitemdataptrall"></a>  CMFCToolBarComboBoxButton::GetItemDataPtrAll

特定のコマンド ID を持つコンボ ボックス ボタンのリスト ボックスで指定したインデックス位置にある項目に関連付けられているデータを返します このデータは、ポインターとして返されます。

```
static void* GetItemDataPtrAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>パラメーター

*uiCmd*<br/>
[in]コンボ ボックス ボタンのコマンド ID。

*iIndex*<br/>
[in]リスト ボックス内の項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

メソッドが成功した場合に、項目に関連付けられたポインターそれ以外の場合、-1 の場合にエラーが発生すると、または NULL の場合は、コンボ ボックス ボタンが見つかりません。

### <a name="remarks"></a>Remarks

##  <a name="getprompt"></a>  CMFCToolBarComboBoxButton::GetPrompt

コンボ ボックス ボタンの表示名の文字列を返します。

```
virtual CString GetPrompt() const;
```

### <a name="return-value"></a>戻り値

プロンプト文字列です。

### <a name="remarks"></a>Remarks

このメソッドは現在実装されていません。

##  <a name="gettext"></a>  CMFCToolBarComboBoxButton::GetText

編集ボックスにテキストを取得します。

```
LPCTSTR GetText() const;
```

### <a name="return-value"></a>戻り値

エディット ボックス内のテキスト。

### <a name="remarks"></a>Remarks

##  <a name="gettextall"></a>  CMFCToolBarComboBoxButton::GetTextAll

指定したコマンド ID を持つコンボ ボックス ボタンの編集ボックスにテキストを取得します。

```
static LPCTSTR GetTextAll(UINT uiCmd);
```

### <a name="parameters"></a>パラメーター

*uiCmd*<br/>
[in]特定のコンボ ボックス ボタンのコマンド ID。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、編集ボックス内のテキストそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

##  <a name="hasfocus"></a>  CMFCToolBarComboBoxButton::HasFocus

コンボ ボックスで現在フォーカスがあるかどうかを示します。

```
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>戻り値

コンボ ボックスがフォーカスを持っている場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

このメソッドは、現在、コンボ ボックスの任意の子ウィンドウにフォーカスがある場合にも TRUE を返します。

##  <a name="iscentervert"></a>  CMFCToolBarComboBoxButton::IsCenterVert

アプリケーションでは、コンボ ボックス ボタンの垂直位置を返します。

```
static BOOL IsCenterVert();
```

### <a name="return-value"></a>戻り値

ボタンの中心は、TRUE を返します。上部にあるボタンを配置する場合は FALSE。

### <a name="remarks"></a>Remarks

##  <a name="isflatmode"></a>  CMFCToolBarComboBoxButton::IsFlatMode

アプリケーションのフラット スタイルのコンボ ボックス ボタンの外観を返します。

```
static BOOL IsFlatMode();
```

### <a name="return-value"></a>戻り値

ボタンがフラット スタイルの場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

既定のフラット スタイルのコンボ ボックス ボタンには FALSE です。

##  <a name="isownerof"></a>  CMFCToolBarComboBoxButton::IsOwnerOf

指定したハンドルがコンボ ボックス ボタン、またはその子のいずれかに関連付けられているかどうかを示します。

```
virtual BOOL IsOwnerOf(HWND hwnd);
```

### <a name="parameters"></a>パラメーター

*hwnd*<br/>
[in]ウィンドウ ハンドル。

### <a name="return-value"></a>戻り値

ハンドルがコンボ ボックス ボタン、またはその子のいずれかに関連付けられている場合は TRUE。それ以外の場合、FALSE です。

##  <a name="isribbonbutton"></a>  CMFCToolBarComboBoxButton::IsRibbonButton

コンボ ボックス ボタンがリボン パネルにあるかどうかを示します。

```
BOOL IsRibbonButton() const;
```

### <a name="return-value"></a>戻り値

常に FALSE です。

### <a name="remarks"></a>Remarks

既定では、このメソッド常に FALSE を返します、つまり、コンボ ボックス ボタンがリボン パネルに表示されることはありません。

##  <a name="iswindowvisible"></a>  CMFCToolBarComboBoxButton::IsWindowVisible

表示状態のコンボ ボックス ボタンを返します。

```
virtual BOOL IsWindowVisible();
```

### <a name="return-value"></a>戻り値

コンボ ボックス ボタンの表示状態。

##  <a name="notifycommand"></a>  CMFCToolBarComboBoxButton::NotifyCommand

コンボ ボックス ボタンがメッセージを処理するかどうかを示します。

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>パラメーター

*iNotifyCode*<br/>
[in]コマンドに関連付けられている通知メッセージ。

### <a name="return-value"></a>戻り値

コンボ ボックス ボタンであるかどうか、メッセージを処理します。

##  <a name="onaddtocustomizepage"></a>  CMFCToolBarComboBoxButton::OnAddToCustomizePage

ボタンが追加されたときに、フレームワークによって呼び出されます、**カスタマイズ** ダイアログ ボックス。

```
virtual void OnAddToCustomizePage();
```

##  <a name="oncalculatesize"></a>  CMFCToolBarComboBoxButton::OnCalculateSize

ボタンのサイズを計算するためにフレームワークによって呼び出されます。

```
virtual SIZE OnCalculateSize(
    CDC* pDC,
    const CSize& sizeDefault,
    BOOL bHorz);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]コンボ ボックス ボタンを表示しているデバイス コンテキスト。

*sizeDefault*<br/>
[in]コンボ ボックス ボタンの既定のサイズ。

*bHorz*<br/>
[in]親ツールバーのドッキング状態。 ツールバーは水平方向と FALSE、ツールバーが垂直方向にドッキングされているとき、ドッキングされている場合は TRUE。

### <a name="return-value"></a>戻り値

A`SIZE`コンボ ボックス ボタンのピクセル単位の大きさを格納する構造体。

##  <a name="onchangeparentwnd"></a>  CMFCToolBarComboBoxButton::OnChangeParentWnd

新しいツールバーにコンボ ボックス ボタンが挿入されたときに、フレームワークによって呼び出されます。

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>パラメーター

*pWndParent*<br/>
[in]新しい親ツールバーへのポインター。

##  <a name="onclick"></a>  CMFCToolBarComboBoxButton::OnClick

ユーザーがコンボ ボックス ボタンをクリックしたときに、フレームワークによって呼び出されます。

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
[in]コンボ ボックス ボタンの親ウィンドウへのポインター。

*bDelay*<br/>
[in]派生クラスで使用するために予約されています。

### <a name="return-value"></a>戻り値

メソッドがイベントを処理する場合は TRUE。それ以外の場合、FALSE です。

##  <a name="onctlcolor"></a>  CMFCToolBarComboBoxButton::OnCtlColor

親ツールバーのコンボ ボックス ボタンの色を設定する色を変更したときに、フレームワークによって呼び出されます。

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]コンボ ボックス ボタンを表示しているデバイス コンテキスト。

*nCtlColor*<br/>
[in]使用されていません。

### <a name="return-value"></a>戻り値

フレームワークを使用してコンボ ボックス ボタンの背景を描画するブラシへのハンドルします。

### <a name="remarks"></a>Remarks

このメソッドでは、コンボ ボックス ボタン テキストの色も設定します。

##  <a name="ondraw"></a>  CMFCToolBarComboBoxButton::OnDraw

指定したスタイルとオプションを使用してコンボ ボックス ボタンを描画するためにフレームワークによって呼び出されます。

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz = TRUE,
    BOOL bCustomizeMode = FALSE,
    BOOL bHighlight = FALSE,
    BOOL bDrawBorder = TRUE,
    BOOL bGrayDisabledButtons = TRUE);
```

### <a name="parameters"></a>パラメーター

*Pdc*<br/>
[in]ボタンを表示するデバイス コンテキスト。

*rect*<br/>
[in]ボタンの外接する四角形。

*pImages*<br/>
[in]ボタンに関連付けられているイメージのコレクション。

*bHorz*<br/>
[in]親ツールバーのドッキング状態。 ツールバーは水平方向と FALSE、ツールバーが垂直方向にドッキングされているとき、ドッキングされている場合は TRUE。

*bCustomizeMode*<br/>
[in]かどうか、アプリケーションはカスタマイズ モードです。

*bHighlight*<br/>
[in]強調表示されているコンボ ボックス ボタンを描画するかどうか。

*bDrawBorder*<br/>
[in]境界線付きのコンボ ボックス ボタンを描画するかどうか。

*bGrayDisabledButtons*<br/>
[in]無効になっているボタンの影を描画する場合は True無効なイメージのコレクションを使用する場合は FALSE。

##  <a name="ondrawoncustomizelist"></a>  CMFCToolBarComboBoxButton::OnDrawOnCustomizeList

コンボ ボックス ボタンを描画するためにフレームワークによって呼び出されます、**コマンド**のウィンドウ、**カスタマイズ** ダイアログ ボックス。

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]コンボ ボックス ボタンを表示しているデバイス コンテキスト。

*rect*<br/>
[in]コンボ ボックス ボタンの外接する四角形。

*bSelected*<br/>
[in]コンボ ボックス ボタンがオンの場合は TRUE。それ以外の場合、FALSE です。

### <a name="return-value"></a>戻り値

コンボ ボックス ボタンのピクセル単位の幅。

##  <a name="onglobalfontschanged"></a>  CMFCToolBarComboBoxButton::OnGlobalFontsChanged

アプリケーションのフォントが変更されたときに、コンボ ボックス ボタンのフォントを設定するためにフレームワークによって呼び出されます。

```
virtual void OnGlobalFontsChanged();
```

##  <a name="onmove"></a>  CMFCToolBarComboBoxButton::OnMove

親ツールバーを移動すると、コンボ ボックス ボタンの場所を変更するためにフレームワークによって呼び出されます。

```
virtual void OnMove();
```

##  <a name="onshow"></a>  CMFCToolBarComboBoxButton::OnShow

コンボ ボックス ボタンを非表示または表示されるときに、フレームワークによって呼び出されます。

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*bShow*<br/>
[in]コンボ ボックス ボタンを表示または非表示するかどうか。

##  <a name="onsize"></a>  CMFCToolBarComboBoxButton::OnSize

親ツールバーのサイズが変更されたときに、コンボ ボックス ボタンのサイズを変更するためにフレームワークによって呼び出されます。

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>パラメーター

*iSize*<br/>
[in]コンボ ボックス ボタンの新しい幅。

##  <a name="onupdatetooltip"></a>  CMFCToolBarComboBoxButton::OnUpdateToolTip

コンボ ボックス ボタンのツールヒントを変更したときに、フレームワークによって呼び出されます。

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>パラメーター

*pWndParent*<br/>
[in]コンボ ボックス ボタンの親ウィンドウへのポインター。

*iButtonIndex*<br/>
[in]コンボ ボックス ボタンの ID。

*wndToolTip*<br/>
[in]コンボ ボックス ボタンに関連付けるツールヒント。

*str*<br/>
[in]ツールヒントのテキスト。

### <a name="return-value"></a>戻り値

メソッドがイベントを処理する場合は TRUE。それ以外の場合、FALSE です。

##  <a name="removeallitems"></a>  CMFCToolBarComboBoxButton::RemoveAllItems

リストと編集ボックスからすべての項目を削除します。

```
void RemoveAllItems();
```

### <a name="remarks"></a>Remarks

一覧からすべての項目のボックスし、コンボ ボックスのコントロールの編集を削除します。

##  <a name="selectitem"></a>  CMFCToolBarComboBoxButton::SelectItem

リスト ボックス内の項目を選択します。

```
BOOL SelectItem(
    int iIndex,
    BOOL bNotify=TRUE);

BOOL SelectItem(DWORD_PTR dwData);
BOOL SelectItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*iIndex*<br/>
[in]リスト ボックス内の項目の 0 から始まるインデックス。

*bNotify*<br/>
[in]選択範囲のコンボ ボックス ボタンに通知する場合は TRUEそれ以外の場合は FALSE です。

*dwData*<br/>
[in]リスト ボックス内の項目に関連付けられたデータ。

*lpszText*<br/>
[in]リスト ボックス内の項目のテキスト。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

##  <a name="selectitemall"></a>  CMFCToolBarComboBoxButton::SelectItemAll

指定したコマンド ID を持つコンボ ボックス ボタンのリスト ボックスに項目を選択します。

```
static BOOL SelectItemAll(
    UINT uiCmd,
    int iIndex);

static BOOL SelectItemAll(
    UINT uiCmd,
    DWORD_PTR dwData);

static BOOL SelectItemAll(
    UINT uiCmd,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*uiCmd*<br/>
[in]リスト ボックスを含むコンボ ボックス ボタンのコマンド ID。

*iIndex*<br/>
[in]リスト ボックス内の項目の 0 から始まるインデックス。 値-1 は、リスト ボックス内の現在の選択を削除し、編集ボックスをクリアします。

*dwData*<br/>
[in]リスト ボックス内の項目のデータ。

*lpszText*<br/>
[in]リスト ボックス内の項目のテキスト。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

##  <a name="serialize"></a>  CMFCToolBarComboBoxButton::Serialize

アーカイブからこのオブジェクトを読み取りまたはアーカイブに書き込みます。

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*ar*<br/>
[入力、出力]`CArchive`シリアル化するオブジェクト。

### <a name="remarks"></a>Remarks

設定、`CArchive`オブジェクトは、このメソッドの読み取りまたはアーカイブに書き込みかどうかを判断します。

##  <a name="setaccdata"></a>  CMFCToolBarComboBoxButton::SetACCData

指定した設定`CAccessibilityData`コンボ ボックス ボタンからのユーザー補助データを使用してオブジェクト。

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>パラメーター

*pParent*<br/>
[in]コンボ ボックス ボタンの親ウィンドウ。

*data*<br/>
[out]A`CAccessibilityData`コンボ ボックス ボタンからのアクセシビリティ データを受け取るオブジェクト。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE です。

##  <a name="setcentervert"></a>  CMFCToolBarComboBoxButton::SetCenterVert

アプリケーションでは、コンボ ボックス ボタンの垂直位置を設定します。

```
static void SetCenterVert(BOOL bCenterVert=TRUE);
```

### <a name="parameters"></a>パラメーター

*bCenterVert*<br/>
[in]ツールバーのコンボ ボックス ボタンを中央揃えする場合は TRUEツールバーの上部にコンボ ボックス ボタンを配置する場合は FALSE。

### <a name="remarks"></a>Remarks

既定では、コンボ ボックス ボタンが上部に配置されます。

##  <a name="setcontextmenuid"></a>  CMFCToolBarComboBoxButton::SetContextMenuID

コンボ ボックス ボタンのショートカット メニューのリソース ID を設定します。

```
void SetContextMenuID(UINT uiResID);
```

### <a name="parameters"></a>パラメーター

*uiResID*<br/>
[in]ショートカット メニューのリソース id。

##  <a name="setdropdownheight"></a>  CMFCToolBarComboBoxButton::SetDropDownHeight

にドロップしたときに、リスト ボックスの高さを設定します。

```
void SetDropDownHeight(int nHeight);
```

### <a name="parameters"></a>パラメーター

*nHeight*<br/>
[in]リスト ボックスのピクセル単位の高さ。

### <a name="remarks"></a>Remarks

既定の高さは、150 ピクセルです。

##  <a name="setflatmode"></a>  CMFCToolBarComboBoxButton::SetFlatMode

アプリケーションのフラット スタイルのコンボ ボックス ボタンの外観を設定します。

```
static void SetFlatMode(BOOL bFlat=TRUE);
```

### <a name="parameters"></a>パラメーター

*bFlat*<br/>
[in]フラット スタイルの外観以外の場合は TRUE。それ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

既定のフラット スタイルのコンボ ボックス ボタンには FALSE です。

##  <a name="setstyle"></a>  CMFCToolBarComboBoxButton::SetStyle

コンボ ボックス ボタンに指定したスタイルを設定しては無効になっていない場合は、コントロールを再描画します。

```
virtual void SetStyle(UINT nStyle);
```

### <a name="parameters"></a>パラメーター

*nStyle*<br/>
[in]ツール バー スタイルのビットごとの組み合わせ (OR)。

### <a name="remarks"></a>Remarks

ツール バー ボタンのスタイルの一覧については、次を参照してください[ツール バー コントロールのスタイル。](../../mfc/reference/toolbar-control-styles.md)

##  <a name="settext"></a>  CMFCToolBarComboBoxButton::SetText

ボックス ボタン、コンボ ボックスの編集ボックスにテキストを設定します。

```
void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
[in]編集ボックスのテキストを含む文字列へのポインター。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CComboBox クラス](../../mfc/reference/ccombobox-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[チュートリアル: ツールバーのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)
