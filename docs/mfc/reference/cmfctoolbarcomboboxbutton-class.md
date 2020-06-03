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
ms.openlocfilehash: 995d7d0db55889130e1cad9585b8fc87285ffd27
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754013"
---
# <a name="cmfctoolbarcomboboxbutton-class"></a>CMFCToolBarComboBoxButton クラス

コンボ ボックス コントロール ( [CComboBox クラス](../../mfc/reference/ccombobox-class.md)) を含むツール バー ボタン。

## <a name="syntax"></a>構文

```
class CMFCToolBarComboBoxButton : public CMFCToolBarButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コンボボックスボタン::CMFCツールバーコンボボックスボタン](#cmfctoolbarcomboboxbutton)|`CMFCToolBarComboBoxButton` を構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コンボボックスボタン::アイテムの追加](#additem)|コンボ ボックス リストの末尾に項目を追加します。|
|[コンボボックスボタン::並べ替えアイテム](#addsorteditem)|コンボ ボックスのリストに項目を追加します。 リスト内のアイテムの順序は、 で`Compare`指定されます。|
|[コンボボックスボタン::比較](#compare)|2 つの項目を比較します。 コンボ ボックス リスト`AddSortedItems`に追加する項目を並べ替えるために呼び出されます。|
|[コンボボックスボタン::編集](#createedit)|コンボ ボックス ボタンの新しいエディット コントロールを作成します。|
|[コンボボックスボタン::DeleteItem](#deleteitem)|コンボ ボックスリストから項目を削除します。|
|[コンボボックスボタン::アイテムを検索します。](#finditem)|指定した文字列を含む項目のインデックスを返します。|
|[コンボボックスボタン::ゲットバイコマンド](#getbycmd)|指定したコマンド ID を持つコンボ ボックス ボタンへのポインターを返します。|
|[コンボボックスボタン::コンボボックスを取得します。](#getcombobox)|コンボ ボックス ボタンに埋め込まれているコンボ ボックス コントロールへのポインターを返します。|
|[コンボボックスボタン::カウントを取得します。](#getcount)|コンボ ボックスリスト内の項目数を返します。|
|[コンボボックスボタン::すべてのカウントを取得します。](#getcountall)|指定したコマンド ID を持つコンボ ボックス ボタンを検索します。 そのボタンのコンボ ボックス リスト内の項目数を返します。|
|[コンボボックスボタン::ゲットカーセル](#getcursel)|コンボ ボックスリストで選択されている項目のインデックスを返します。|
|[コンボボックスボタン::ゲットカーセルオール](#getcurselall)|指定したコマンド ID を持つコンボ ボックス ボタンを検索し、そのボタンのコンボ ボックス リストで選択されている項目のインデックスを返します。|
|[コンボボックスボタン::取得編集](#geteditctrl)|コンボ ボックス ボタンに埋め込まれているエディット コントロールへのポインターを返します。|
|[コンボボックスボタン::取得アイテム](#getitem)|コンボ ボックス リスト内の指定したインデックスに関連付けられている文字列を返します。|
|[コンボボックスボタン::ゲットアイテムすべて](#getitemall)|指定したコマンド ID を持つコンボ ボックス ボタンを検索し、そのボタンのコンボ ボックス リスト内のインデックスに関連付けられている文字列を返します。|
|[コンボボックスボタン::アイテムデータ](#getitemdata)|コンボ ボックスリストの指定したインデックスに関連付けられている 32 ビット値を返します。|
|[コンボボックスボタン::アイテムデータすべて](#getitemdataall)|指定したコマンド ID を持つコンボ ボックス ボタンを検索し、そのボタンのコンボ ボックス リストのインデックスに関連付けられている 32 ビット値を返します。|
|[コンボボックスボタン::アイテムデータプラーオール](#getitemdataptrall)|指定したコマンド ID を持つコンボ ボックス ボタンを検索します。 ボタンのコンボ ボックス リスト内のインデックスに関連付けられている 32 ビット値を取得し、32 ビット値をポインターとして返します。|
|[コンボボックスボタン::テキストを取得します。](#gettext)|コンボ ボックスのエディット コントロールからテキストを返します。|
|[コンボボックスボタン::テキストをすべて取得します。](#gettextall)|指定したコマンド ID を持つコンボ ボックス ボタンを検索し、そのボタンのエディット コントロールからテキストを返します。|
|[コンボボックスボタン::イズセンターバート](#iscentervert)|アプリケーションのコンボ ボックス ボタンをツールバーの上部に中央揃えまたは配置するかどうかを指定します。|
|[コンボボックスボタン::イズフラットモード](#isflatmode)|アプリケーションのコンボ ボックス ボタンがフラットな外観かどうかを判断します。|
|[コンボボックスボタン::すべてのアイテムを削除します](#removeallitems)|コンボ ボックスのリスト ボックスおよびエディット コントロールからすべての項目を削除します。|
|[コンボボックスボタン::アイテムを選択します。](#selectitem)|コンボ ボックス内の項目をインデックス、32 ビット値、または文字列に従って選択し、コンボ ボックス コントロールに選択内容を通知します。|
|[コンボボックスボタン::アイテムすべて](#selectitemall)|指定したコマンド ID を持つコンボ ボックス ボタンを検索します。 その`SelectItem`ボタンのコンボ ボックス内の項目を、その文字列、インデックス、または 32 ビット値に従って選択する呼び出し。|
|[コンボボックスボタン::セットセンターバート](#setcentervert)|アプリケーションのコンボ ボックス ボタンを垂直方向に中央揃えするか、ツールバーの上部に揃えて配置するかを指定します。|
|[コンボボックスボタン::セットドロップダウンハイト](#setdropdownheight)|ドロップダウン リスト ボックスの高さを設定します。|
|[コンボボックスボタン::セットフラットモード](#setflatmode)|アプリケーションのコンボ ボックス ボタンがフラットな外観かどうかを指定します。|

## <a name="remarks"></a>解説

ツールバーにコンボ ボックス ボタンを追加するには、次の手順を実行します。

1. 親ツール バー リソースでボタンのダミー リソース ID を予約します。

2. `CMFCToolBarComboBoxButton` オブジェクトを構築します。

3. AFX_WM_RESETTOOLBAR メッセージを処理するメッセージ ハンドラーで[、CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)を使用して、ダミー ボタンを新しいコンボ ボックス ボタンに置き換えます。

詳細については、「[チュートリアル : ツールバーにコントロールを配置](../../mfc/walkthrough-putting-controls-on-toolbars.md)する 」を参照してください。 コンボ ボックスツール バー ボタンの例については、プロジェクトの例を参照してください。

## <a name="example"></a>例

`CMFCToolBarComboBoxButton` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、エディット コンボ ボックスを有効にし、アプリケーションでコンボ ボックス ボタンの垂直方向の位置を設定し、ドロップダウンしたときのリスト ボックスの高さを設定し、アプリケーションのコンボ ボックス ボタンのフラット スタイルの外観を設定し、コンボ ボックス ボタンのエディット ボックスにテキストを設定する方法を示します。 このコード スニペットは[、Visual Studio のデモ のサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_VisualStudioDemo#36](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_1.cpp)]
[!code-cpp[NVC_MFC_VisualStudioDemo#37](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[コンボボックスボタン](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxツールバーコンボボックスボタン.h

## <a name="cmfctoolbarcomboboxbuttonadditem"></a><a name="additem"></a>コンボボックスボタン::アイテムの追加

リスト ボックスに一意の項目を追加します。

```
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]リスト ボックスに追加する項目のテキスト。

*dw データ*<br/>
[in]リスト ボックスに追加する項目に関連付けられたデータ。

### <a name="return-value"></a>戻り値

リスト ボックスの最後の項目のインデックス。

### <a name="remarks"></a>解説

リスト ボックスのスタイルを並べ替えるときは、このメソッドを使用しないでください。

項目のテキストがリスト ボックスに既に存在する場合、新しいデータは既存の項目と共に保存されます。 アイテムの検索では、大文字と小文字が区別されます。

## <a name="cmfctoolbarcomboboxbuttonaddsorteditem"></a><a name="addsorteditem"></a>コンボボックスボタン::並べ替えアイテム

[Compare](#compare)メソッドで定義されている順序で項目をリスト ボックスに追加します。

```
virtual INT_PTR AddSortedItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]リスト ボックスに追加する項目のテキスト。

*dw データ*<br/>
[in]リスト ボックスに追加する項目に関連付けられたデータ。

### <a name="return-value"></a>戻り値

リスト ボックスに追加された項目のインデックス。

### <a name="remarks"></a>解説

この関数を使用して、リスト ボックスに特定の順序で項目を追加します。

## <a name="cmfctoolbarcomboboxbuttoncanbestretched"></a><a name="canbestretched"></a>コンボボックスボタン::缶詰ストレッチ

コンボ ボックス ボタンのサイズを変更できるかどうかを示します。

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>戻り値

TRUE を返します。

## <a name="cmfctoolbarcomboboxbuttoncmfctoolbarcomboboxbutton"></a><a name="cmfctoolbarcomboboxbutton"></a>コンボボックスボタン::CMFCツールバーコンボボックスボタン

オブジェクトを構築[します](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)。

```
CMFCToolBarComboBoxButton(
    UINT uiID,
    int iImage,
    DWORD dwStyle=CBS_DROPDOWNLIST,
    int iWidth=0);
```

### <a name="parameters"></a>パラメーター

*Uiid*<br/>
[in]新しいボタンのコマンド ID。

*iイメージ*<br/>
[in]新しいボタンに関連付けられているイメージのイメージ インデックス。

*Dwstyle*<br/>
[in]新しいボタンのスタイル。

*幅*<br/>
[in]新しいボタンの幅 (ピクセル単位)。

### <a name="remarks"></a>解説

既定の幅は 150 ピクセルです。

ツールバーボタンスタイルのリストについては、「[ツールバーコントロールのスタイル](../../mfc/reference/toolbar-control-styles.md)」を参照してください。

## <a name="cmfctoolbarcomboboxbuttoncleardata"></a><a name="cleardata"></a>コンボボックスボタン::データをクリア

ユーザー定義データを削除します。

```
virtual void ClearData();
```

### <a name="remarks"></a>解説

既定では、このメソッドは何も実行しません。 ユーザー定義データを削除する場合は、派生クラスでこのメソッドをオーバーライドします。

## <a name="cmfctoolbarcomboboxbuttoncompare"></a><a name="compare"></a>コンボボックスボタン::比較

2 つの文字列を比較します。

```
virtual int Compare(
    LPCTSTR lpszItem1,
    LPCTSTR lpszItem2);
```

### <a name="parameters"></a>パラメーター

*1*<br/>
[in]比較する最初の文字列。

*2*<br/>
[in]比較する 2 番目の文字列。

### <a name="return-value"></a>戻り値

文字列間の大文字小文字を区別する辞書の関係を示す値。 可能な値を次の表に示します。

|値|説明|
|-----------|-----------------|
|\<0|最初の文字列は 2 番目の文字列より小さいです。|
|0|最初の文字列は 2 番目の文字列と同じです。|
|>0|最初の文字列は 2 番目の文字列より大きくなっています。|

### <a name="remarks"></a>解説

リスト ボックス内の項目の並べ替え方法を変更するには、このメソッドをオーバーライドします。

比較では大文字と小文字が区別されます。

このメソッドは[、メソッドから](#addsorteditem)呼び出されます。

## <a name="cmfctoolbarcomboboxbuttoncopyfrom"></a><a name="copyfrom"></a>コンボボックスボタン::コピーフロ

指定した`CMFCToolBarComboBoxButton`オブジェクトの状態を現在のオブジェクトにコピーします。

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>パラメーター

*src*<br/>
[in]ソース`CMFCToolBarComboBoxButton`オブジェクト。

## <a name="cmfctoolbarcomboboxbuttoncreatecombo"></a><a name="createcombo"></a>コンボボックスボタン::コンボを作成します。

コンボ ボックス ボタンの新しいコンボ ボックスを作成します。

```
virtual CComboBox* CreateCombo(
    CWnd* pWndParent,
    const CRect& rect);
```

### <a name="parameters"></a>パラメーター

*親の子*<br/>
[in]ボタンの親ウィンドウへのポインター。

*Rect*<br/>
[in]コンボ ボックスの外接する四角形。

### <a name="return-value"></a>戻り値

メソッドが正常に終了した場合は、新しいコンボ ボックスへのポインター。それ以外の場合は NULL。

## <a name="cmfctoolbarcomboboxbuttoncreateedit"></a><a name="createedit"></a>コンボボックスボタン::編集

コンボ ボックス ボタンの新しいエディット ボックスを作成します。

```
virtual CMFCToolBarComboBoxEdit* CreateEdit(
    CWnd* pWndParent,
    const CRect& rect,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>パラメーター

*親の子*<br/>
[in]ボタンの親ウィンドウへのポインター。

*Rect*<br/>
[in]新しい編集ボックスの外接する四角形。

*ドウエディットスタイル*<br/>
[in]新しいエディット ボックスのコントロール スタイル。

### <a name="return-value"></a>戻り値

メソッドが正常に終了した場合は、新しいエディット ボックスへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

コンボ ボックス ボタンの新しいエディット ボックスを作成するときに、フレームワークはこのメソッドを呼び出します。 このメソッドをオーバーライドして[、CMFC ツール バー コンボ ボックスの](../../mfc/reference/cmfctoolbarcomboboxedit-class.md)作成方法を変更します。

## <a name="cmfctoolbarcomboboxbuttondeleteitem"></a><a name="deleteitem"></a>コンボボックスボタン::DeleteItem

リスト ボックスから指定した項目を削除します。

```
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);
BOOL DeleteItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]削除する項目の 0 から始まるインデックス。

*dw データ*<br/>
[in]削除するアイテムに関連付けられているデータ。

*lpszText*<br/>
[in]削除する項目のテキスト。 同じテキストを持つ複数の項目がある場合、最初の項目は削除されます。

### <a name="return-value"></a>戻り値

アイテムが見つかり、正常に削除された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfctoolbarcomboboxbuttonduplicatedata"></a><a name="duplicatedata"></a>コンボボックスボタン::D

ユーザー定義データを複製します。

```
virtual void DuplicateData();
```

### <a name="remarks"></a>解説

既定では、このメソッドは何も実行しません。 ユーザー定義データをコピーする場合は、派生クラスでこのメソッドをオーバーライドします。

## <a name="cmfctoolbarcomboboxbuttonenablewindow"></a><a name="enablewindow"></a>コンボボックスボタン::ウィンドウを有効にする

編集ボックスとコンボ ボックスを有効または無効にします。

```
virtual void EnableWindow(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]編集ボックスとコンボ ボックスを有効にする場合は TRUE。FALSE を指定すると、編集ボックスとコンボ ボックスが無効になります。

### <a name="remarks"></a>解説

無効にすると、コントロールはアクティブになれませんし、ユーザー入力を受け入れることができません。

## <a name="cmfctoolbarcomboboxbuttonexporttomenubutton"></a><a name="exporttomenubutton"></a>コンボボックスボタン::メニューボタンをエクスポートします。

コンボ ボックス ボタンのコマンド ID を使用して、アプリケーションの文字列テーブルから指定したメニューに文字列をコピーします。

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>パラメーター

*メニューボタン*<br/>
[アウト]メニュー ボタンへの参照。

### <a name="return-value"></a>戻り値

常に TRUE。

## <a name="cmfctoolbarcomboboxbuttonfinditem"></a><a name="finditem"></a>コンボボックスボタン::アイテムを検索します。

指定した文字列を含むリスト ボックスの最初の項目のインデックスを返します。

```
int FindItem(LPCTSTR lpszText) const;
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
[in]リスト ボックス内で検索する文字列。

### <a name="return-value"></a>戻り値

項目のインデックス。をクリックするか、アイテムが見つからない場合はCB_ERRします。

### <a name="remarks"></a>解説

## <a name="cmfctoolbarcomboboxbuttongetbycmd"></a><a name="getbycmd"></a>コンボボックスボタン::ゲットバイコマンド

指定したコマンド ID を持つコンボ ボックス ボタンへのポインターを取得します。

```
static CMFCToolBarComboBoxButton* GetByCmd(
    UINT uiCmd,
    BOOL bIsFocus=FALSE);
```

### <a name="parameters"></a>パラメーター

*Uicmd*<br/>
[in]コンボ ボックス ボタンのコマンド ID。

*ビスフォーカス*<br/>
[in]フォーカスのあるボタンのみを検索する場合は TRUE。すべてのボタンを検索する場合は FALSE。

### <a name="return-value"></a>戻り値

コンボ ボックス ボタンへのポインター。ボタンが見つからない場合は NULL。

### <a name="remarks"></a>解説

## <a name="cmfctoolbarcomboboxbuttongetcombobox"></a><a name="getcombobox"></a>コンボボックスボタン::コンボボックスを取得します。

コンボ ボックス ボタンのコンボ ボックスへのポインターを返します。

```
CComboBox* GetComboBox() const;
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合は[、CComboBox クラス](../../mfc/reference/ccombobox-class.md)オブジェクトへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

## <a name="cmfctoolbarcomboboxbuttongetcontextmenuid"></a><a name="getcontextmenuid"></a>コンボボックスボタン::コンテキストメニューID

コンボ ボックス ボタンのショートカット メニュー リソース ID を取得します。

```
UINT GetContextMenuID();
```

### <a name="return-value"></a>戻り値

ショートカット メニューのリソース ID。

## <a name="cmfctoolbarcomboboxbuttongetcount"></a><a name="getcount"></a>コンボボックスボタン::カウントを取得します。

リスト ボックス内の項目数を返します。

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>戻り値

リスト ボックス内の項目の数。

### <a name="remarks"></a>解説

## <a name="cmfctoolbarcomboboxbuttongetcountall"></a><a name="getcountall"></a>コンボボックスボタン::すべてのカウントを取得します。

指定したコマンド ID を持つコンボ ボックス ボタンのリスト ボックス内の項目数を取得します。

```
static int GetCountAll(UINT uiCmd);
```

### <a name="parameters"></a>パラメーター

*Uicmd*<br/>
[in]コンボ ボックス ボタンのコマンド ID。

### <a name="return-value"></a>戻り値

リスト ボックス内の項目の数。それ以外の場合は、コンボ ボックス ボタンが見つからない場合はCB_ERR。

### <a name="remarks"></a>解説

## <a name="cmfctoolbarcomboboxbuttongetcursel"></a><a name="getcursel"></a>コンボボックスボタン::ゲットカーセル

リスト ボックス内で現在選択されている項目のインデックスを取得します。

```
int GetCurSel() const;
```

### <a name="return-value"></a>戻り値

リスト ボックス内で現在選択されている項目のインデックス。をクリックするか、アイテムが選択されていない場合はCB_ERRします。

### <a name="remarks"></a>解説

リスト ボックスインデックスは 0 から始まります。

## <a name="cmfctoolbarcomboboxbuttongetcurselall"></a><a name="getcurselall"></a>コンボボックスボタン::ゲットカーセルオール

指定したコマンド ID を持つコンボ ボックス ボタンのリスト ボックスで、現在選択されている項目のインデックスを返します。

```
static int GetCurSelAll(UINT uiCmd);
```

### <a name="parameters"></a>パラメーター

*Uicmd*<br/>
[in]コンボ ボックス ボタンのコマンド ID。

### <a name="return-value"></a>戻り値

リスト ボックス内で現在選択されている項目のインデックス。選択されていない場合は、項目が選択されていないか、コンボ ボックス ボタンが見つからない場合は、CB_ERR。

### <a name="remarks"></a>解説

リスト ボックスインデックスは 0 から始まります。

## <a name="cmfctoolbarcomboboxbuttongeteditctrl"></a><a name="geteditctrl"></a>コンボボックスボタン::取得編集

コンボ ボックス ボタンのエディット ボックスへのポインターを返します。

```
virtual CEdit* GetEditCtrl();
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合はエディット ボックスへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

## <a name="cmfctoolbarcomboboxbuttongethwnd"></a><a name="gethwnd"></a>コンボボックスボタン::ゲットワード

コンボ ボックスのウィンドウ ハンドルを返します。

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>戻り値

コンボ ボックスがウィンドウ オブジェクトに関連付けられていない場合は、ウィンドウ ハンドルを返します。

## <a name="cmfctoolbarcomboboxbuttongetitem"></a><a name="getitem"></a>コンボボックスボタン::取得アイテム

リスト ボックス内の指定したインデックスにある項目に関連付けられた文字列を返します。

```
LPCTSTR GetItem(int iIndex=-1) const;
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]リスト ボックス内の項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

項目に関連付けられている文字列へのポインター。それ以外の場合は、インデックス パラメーターが無効な場合、またはインデックス パラメーターが -1 で、コンボ ボックスに選択された項目がない場合は NULL。

### <a name="remarks"></a>解説

インデックス パラメータ -1 は、現在選択されている項目の文字列を返します。

## <a name="cmfctoolbarcomboboxbuttongetitemall"></a><a name="getitemall"></a>コンボボックスボタン::ゲットアイテムすべて

指定したコマンド ID を持つコンボ ボックス ボタンのリスト ボックス内の指定したインデックスにある項目に関連付けられた文字列を返します。

```
static LPCTSTR GetItemAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>パラメーター

*Uicmd*<br/>
[in]コンボ ボックス ボタンのコマンド ID。

*をクリックします。*<br/>
[in]リスト ボックス内の項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、項目の文字列へのポインター。それ以外の場合は、インデックスが無効な場合、コンボ ボックス ボタンが見つからない場合、またはインデックスが -1 で、コンボ ボックス内に選択された項目がない場合は NULL。

### <a name="remarks"></a>解説

インデックス値 -1 は、現在選択されている項目の文字列を返します。

## <a name="cmfctoolbarcomboboxbuttongetitemdata"></a><a name="getitemdata"></a>コンボボックスボタン::アイテムデータ

リスト ボックス内の特定のインデックスにある項目に関連付けられたデータを返します。

```
DWORD_PTR GetItemData(int iIndex=-1) const;
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]リスト ボックス内の項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

アイテムに関連付けられているデータ。アイテムが存在しない場合は 0。

### <a name="remarks"></a>解説

index パラメーター -1 は、現在選択されている項目に関連付けられているデータを返します。

## <a name="cmfctoolbarcomboboxbuttongetitemdataall"></a><a name="getitemdataall"></a>コンボボックスボタン::アイテムデータすべて

特定のコマンド ID を持つコンボ ボックス ボタンのリスト ボックス内の特定のインデックスにある項目に関連付けられたデータを返します。

```
static DWORD_PTR GetItemDataAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>パラメーター

*Uicmd*<br/>
[in]コンボ ボックス ボタンのコマンド ID。

*をクリックします。*<br/>
[in]リスト ボックス内の項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、項目に関連付けられたデータ。指定したインデックスが無効な場合は 0、コンボ ボックス ボタンが見つからない場合はCB_ERR。

### <a name="remarks"></a>解説

index パラメーター -1 は、現在選択されている項目に関連付けられているデータを返します。

## <a name="cmfctoolbarcomboboxbuttongetitemdataptrall"></a><a name="getitemdataptrall"></a>コンボボックスボタン::アイテムデータプラーオール

特定のコマンド ID を持つコンボ ボックス ボタンのリスト ボックス内の特定のインデックスにある項目に関連付けられたデータを返します。 このデータはポインタとして返されます。

```
static void* GetItemDataPtrAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>パラメーター

*Uicmd*<br/>
[in]コンボ ボックス ボタンのコマンド ID。

*をクリックします。*<br/>
[in]リスト ボックス内の項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

メソッドが正常に実行された場合は、項目に関連付けられたポインター。それ以外の場合は -1、エラーが発生した場合は NULL、コンボ ボックス ボタンが見つからない場合は NULL。

### <a name="remarks"></a>解説

## <a name="cmfctoolbarcomboboxbuttongetprompt"></a><a name="getprompt"></a>コンボボックスボタン::プロンプトを取得します。

コンボ ボックス ボタンのプロンプト文字列を返します。

```
virtual CString GetPrompt() const;
```

### <a name="return-value"></a>戻り値

プロンプト文字列。

### <a name="remarks"></a>解説

このメソッドは現在実装されていません。

## <a name="cmfctoolbarcomboboxbuttongettext"></a><a name="gettext"></a>コンボボックスボタン::テキストを取得します。

エディット ボックス内のテキストを取得します。

```
LPCTSTR GetText() const;
```

### <a name="return-value"></a>戻り値

エディット ボックス内のテキスト。

### <a name="remarks"></a>解説

## <a name="cmfctoolbarcomboboxbuttongettextall"></a><a name="gettextall"></a>コンボボックスボタン::テキストをすべて取得します。

指定したコマンド ID を持つコンボ ボックス ボタンのエディット ボックス内のテキストを取得します。

```
static LPCTSTR GetTextAll(UINT uiCmd);
```

### <a name="parameters"></a>パラメーター

*Uicmd*<br/>
[in]特定のコンボ ボックス ボタンのコマンド ID。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、エディット ボックス内のテキスト。それ以外の場合は NULL。

### <a name="remarks"></a>解説

## <a name="cmfctoolbarcomboboxbuttonhasfocus"></a><a name="hasfocus"></a>コンボボックスボタン::ハズフォーカス

コンボ ボックスに現在フォーカスがあるかどうかを示します。

```
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>戻り値

コンボ ボックスに現在フォーカスがある場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、コンボ ボックスの子ウィンドウにフォーカスがある場合にも TRUE を返します。

## <a name="cmfctoolbarcomboboxbuttoniscentervert"></a><a name="iscentervert"></a>コンボボックスボタン::イズセンターバート

アプリケーションのコンボ ボックス ボタンの垂直方向の位置を返します。

```
static BOOL IsCenterVert();
```

### <a name="return-value"></a>戻り値

ボタンが中央揃えの場合は TRUE。FALSE の場合、ボタンが上部に配置されます。

### <a name="remarks"></a>解説

## <a name="cmfctoolbarcomboboxbuttonisflatmode"></a><a name="isflatmode"></a>コンボボックスボタン::イズフラットモード

アプリケーションのコンボ ボックス ボタンのフラット スタイルの外観を返します。

```
static BOOL IsFlatMode();
```

### <a name="return-value"></a>戻り値

ボタンがフラットなスタイルを持つ場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

コンボ ボックス ボタンの既定のフラット スタイルは FALSE です。

## <a name="cmfctoolbarcomboboxbuttonisownerof"></a><a name="isownerof"></a>コンボボックスボタン::イスオーナーの

指定したハンドルがコンボ ボックス ボタンに関連付けられているか、その子の 1 つに関連付けられているかを示します。

```
virtual BOOL IsOwnerOf(HWND hwnd);
```

### <a name="parameters"></a>パラメーター

*Hwnd*<br/>
[in]ウィンドウ ハンドル。

### <a name="return-value"></a>戻り値

ハンドルがコンボ ボックス ボタンまたはその子の 1 つと関連付けられている場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfctoolbarcomboboxbuttonisribbonbutton"></a><a name="isribbonbutton"></a>コンボボックスボタン::ボタン

コンボ ボックス ボタンがリボン パネル上に存在するかどうかを示します。

```
BOOL IsRibbonButton() const;
```

### <a name="return-value"></a>戻り値

常に FALSE です。

### <a name="remarks"></a>解説

既定では、このメソッドは常に FALSE を返します。

## <a name="cmfctoolbarcomboboxbuttoniswindowvisible"></a><a name="iswindowvisible"></a>コンボボックスボタン::イズウィンドウ表示

コンボ ボックス ボタンの表示状態を返します。

```
virtual BOOL IsWindowVisible();
```

### <a name="return-value"></a>戻り値

コンボ ボックス ボタンの表示状態。

## <a name="cmfctoolbarcomboboxbuttonnotifycommand"></a><a name="notifycommand"></a>コンボボックスボタン::コマンドを通知します。

コンボ ボックス ボタンがメッセージを処理するかどうかを示します。

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>パラメーター

*コード*<br/>
[in]コマンドに関連付けられている通知メッセージ。

### <a name="return-value"></a>戻り値

コンボ ボックス ボタンがメッセージを処理するかどうかを指定します。

## <a name="cmfctoolbarcomboboxbuttononaddtocustomizepage"></a><a name="onaddtocustomizepage"></a>コンボボックスボタン::アドオンカスタマイズページ

ボタンが **[カスタマイズ**] ダイアログ ボックスに追加されたときに、フレームワークによって呼び出されます。

```
virtual void OnAddToCustomizePage();
```

## <a name="cmfctoolbarcomboboxbuttononcalculatesize"></a><a name="oncalculatesize"></a>コンボボックスボタン::計算サイズ

ボタンのサイズを計算するために、フレームワークによって呼び出されます。

```
virtual SIZE OnCalculateSize(
    CDC* pDC,
    const CSize& sizeDefault,
    BOOL bHorz);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]コンボ ボックス ボタンを表示するデバイス コンテキスト。

*サイズデフォルト*<br/>
[in]コンボ ボックス ボタンの既定のサイズ。

*bHorz*<br/>
[in]親ツール バーのドッキング状態。 TRUE は、ツールバーが水平にドッキングされている場合は FALSE、ツールバーが垂直にドッキングされている場合は FALSE。

### <a name="return-value"></a>戻り値

コンボ`SIZE`ボックス ボタンのサイズをピクセル単位で格納する構造体。

## <a name="cmfctoolbarcomboboxbuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>コンボボックスボタン::オンチェンジペアレント

コンボ ボックス ボタンが新しいツール バーに挿入されたときに、フレームワークによって呼び出されます。

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>パラメーター

*親の子*<br/>
[in]新しい親ツール バーへのポインター。

## <a name="cmfctoolbarcomboboxbuttononclick"></a><a name="onclick"></a>コンボボックスボタン::クリック時

ユーザーがコンボ ボックス ボタンをクリックしたときに、フレームワークによって呼び出されます。

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
[in]コンボ ボックス ボタンの親ウィンドウへのポインター。

*bディレイ*<br/>
[in]派生クラスで使用するために予約されています。

### <a name="return-value"></a>戻り値

メソッドがイベントを処理する場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfctoolbarcomboboxbuttononctlcolor"></a><a name="onctlcolor"></a>コンボボックスボタン::オンCtlカラー

ユーザーが親ツール バーの色を変更してコンボ ボックス ボタンの色を設定したときに、フレームワークによって呼び出されます。

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]コンボ ボックス ボタンを表示するデバイス コンテキスト。

*をクリックします。*<br/>
[in]未使用。

### <a name="return-value"></a>戻り値

コンボ ボックス ボタンの背景を描画するためにフレームワークが使用するブラシへのハンドル。

### <a name="remarks"></a>解説

このメソッドは、コンボ ボックス ボタンのテキストの色も設定します。

## <a name="cmfctoolbarcomboboxbuttonondraw"></a><a name="ondraw"></a>コンボボックスボタン::ドロー

指定したスタイルとオプションを使用してコンボ ボックス ボタンを描画するために、フレームワークによって呼び出されます。

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

*Rect*<br/>
[in]ボタンの外接する四角形。

*pイメージズ*<br/>
[in]ボタンに関連付けられているイメージのコレクション。

*bHorz*<br/>
[in]親ツール バーのドッキング状態。 TRUE は、ツールバーが水平にドッキングされている場合は FALSE、ツールバーが垂直にドッキングされている場合は FALSE。

*モードをカスタマイズする*<br/>
[in]アプリケーションがカスタマイズ モードであるかどうか。

*bハイライト*<br/>
[in]コンボ ボックス ボタンを強調表示して描画するかどうかを指定します。

*ボーダーを描く*<br/>
[in]枠線付きのコンボ ボックス ボタンを描画するかどうかを指定します。

*ボタン*<br/>
[in]シェーディングされた無効なボタンを描画する場合は TRUE。無効なイメージ コレクションを使用する場合は FALSE。

## <a name="cmfctoolbarcomboboxbuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a>コンボボックスボタン::オンドローオンカスタマイザスリスト

[**カスタマイズ**] ダイアログ ボックスの **[コマンド**] ウィンドウにコンボ ボックス ボタンを描画するために、フレームワークによって呼び出されます。

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]コンボ ボックス ボタンを表示するデバイス コンテキスト。

*Rect*<br/>
[in]コンボ ボックス ボタンの外接する四角形。

*b選択済み*<br/>
[in]コンボ ボックス ボタンが選択されている場合は TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

コンボ ボックス ボタンの幅 (ピクセル単位)。

## <a name="cmfctoolbarcomboboxbuttononglobalfontschanged"></a><a name="onglobalfontschanged"></a>コンボボックスボタン::オングローバルフォント変更

アプリケーションのフォントが変更されたときにコンボ ボックス ボタンのフォントを設定するために、フレームワークによって呼び出されます。

```
virtual void OnGlobalFontsChanged();
```

## <a name="cmfctoolbarcomboboxbuttononmove"></a><a name="onmove"></a>コンボボックスボタン::移動中

親ツール バーが移動したときにコンボ ボックス ボタンの位置を変更するために、フレームワークによって呼び出されます。

```
virtual void OnMove();
```

## <a name="cmfctoolbarcomboboxbuttononshow"></a><a name="onshow"></a>コンボボックスボタン::オンショー

コンボ ボックス ボタンが非表示または表示されるときに、フレームワークによって呼び出されます。

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*bショー*<br/>
[in]コンボ ボックス ボタンを表示または非表示にするかどうかを指定します。

## <a name="cmfctoolbarcomboboxbuttononsize"></a><a name="onsize"></a>コンボボックスボタン::オンサイズ

親ツール バーのサイズが変更されたときにコンボ ボックス ボタンのサイズを変更するために、フレームワークによって呼び出されます。

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>パラメーター

*iサイズ*<br/>
[in]コンボ ボックス ボタンの新しい幅。

## <a name="cmfctoolbarcomboboxbuttononupdatetooltip"></a><a name="onupdatetooltip"></a>コンボボックスボタン::オンアップデートツールチップ

ユーザーがコンボ ボックス ボタンのツール ヒントを変更したときに、フレームワークによって呼び出されます。

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>パラメーター

*親の子*<br/>
[in]コンボ ボックス ボタンの親ウィンドウへのポインター。

*ボタンインデックス*<br/>
[in]コンボ ボックス ボタンの ID です。

*wnd ツールヒント*<br/>
[in]コンボ ボックス ボタンに関連付けるツール ヒント。

*Str*<br/>
[in]ツール ヒントテキスト。

### <a name="return-value"></a>戻り値

メソッドがイベントを処理する場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfctoolbarcomboboxbuttonremoveallitems"></a><a name="removeallitems"></a>コンボボックスボタン::すべてのアイテムを削除します

リスト ボックスと編集ボックスからすべてのアイテムを削除します。

```cpp
void RemoveAllItems();
```

### <a name="remarks"></a>解説

コンボ ボックスのリスト ボックスおよびエディット コントロールからすべての項目を削除します。

## <a name="cmfctoolbarcomboboxbuttonselectitem"></a><a name="selectitem"></a>コンボボックスボタン::アイテムを選択します。

リスト ボックス内の項目を選択します。

```
BOOL SelectItem(
    int iIndex,
    BOOL bNotify=TRUE);

BOOL SelectItem(DWORD_PTR dwData);
BOOL SelectItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]リスト ボックス内の項目の 0 から始まるインデックス。

*通知する*<br/>
[in]選択項目のコンボ ボックス ボタンを通知する場合は TRUE。それ以外の場合は FALSE。

*dw データ*<br/>
[in]リスト ボックス内の項目に関連付けられているデータ。

*lpszText*<br/>
[in]リスト ボックス内の項目のテキスト。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfctoolbarcomboboxbuttonselectitemall"></a><a name="selectitemall"></a>コンボボックスボタン::アイテムすべて

指定したコマンド ID を持つコンボ ボックス ボタンのリスト ボックス内の項目を選択します。

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

*Uicmd*<br/>
[in]リスト ボックスを含むコンボ ボックス ボタンのコマンド ID。

*をクリックします。*<br/>
[in]リスト ボックス内の項目の 0 から始まるインデックス。 値 -1 を指定すると、リスト ボックス内の現在の選択項目はすべて削除され、編集ボックスの選択が解除されます。

*dw データ*<br/>
[in]リスト ボックス内の項目のデータ。

*lpszText*<br/>
[in]リスト ボックス内の項目のテキスト。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfctoolbarcomboboxbuttonserialize"></a><a name="serialize"></a>コンボボックスボタン::シリアル化

このオブジェクトをアーカイブから読み取るか、アーカイブに書き込みます。

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*ar*<br/>
[イン、アウト]シリアル`CArchive`化するオブジェクト。

### <a name="remarks"></a>解説

オブジェクト内の`CArchive`設定によって、このメソッドがアーカイブに対して読み取りまたは書き込みを行うかどうかが決まります。

## <a name="cmfctoolbarcomboboxbuttonsetaccdata"></a><a name="setaccdata"></a>コンボボックスボタン::セットアックデータ

コンボ ボックス`CAccessibilityData`ボタンのユーザー補助データを使用して、指定したオブジェクトにデータを設定します。

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>パラメーター

*親*<br/>
[in]コンボ ボックス ボタンの親ウィンドウ。

*データ*<br/>
[アウト]コンボ`CAccessibilityData`ボックス ボタンからユーザー補助データを受け取るオブジェクト。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfctoolbarcomboboxbuttonsetcentervert"></a><a name="setcentervert"></a>コンボボックスボタン::セットセンターバート

アプリケーションのコンボ ボックス ボタンの垂直方向の位置を設定します。

```
static void SetCenterVert(BOOL bCenterVert=TRUE);
```

### <a name="parameters"></a>パラメーター

*bセンターバート*<br/>
[in]ツールバーのコンボ ボックス ボタンを中央揃えする場合は TRUE。FALSE を指定すると、コンボ ボックス ボタンがツール バーの上部に揃えて配置されます。

### <a name="remarks"></a>解説

既定では、コンボ ボックス ボタンは上端に揃えられます。

## <a name="cmfctoolbarcomboboxbuttonsetcontextmenuid"></a><a name="setcontextmenuid"></a>コンボボックスボタン::コンテキストメニューID

コンボ ボックス ボタンのショートカット メニュー リソース ID を設定します。

```cpp
void SetContextMenuID(UINT uiResID);
```

### <a name="parameters"></a>パラメーター

*UIResID*<br/>
[in]ショートカット メニューのリソース ID。

## <a name="cmfctoolbarcomboboxbuttonsetdropdownheight"></a><a name="setdropdownheight"></a>コンボボックスボタン::セットドロップダウンハイト

ドロップダウンしたときのリスト ボックスの高さを設定します。

```cpp
void SetDropDownHeight(int nHeight);
```

### <a name="parameters"></a>パラメーター

*nHeight*<br/>
[in]リスト ボックスの高さ (ピクセル単位)。

### <a name="remarks"></a>解説

既定の高さは 150 ピクセルです。

## <a name="cmfctoolbarcomboboxbuttonsetflatmode"></a><a name="setflatmode"></a>コンボボックスボタン::セットフラットモード

アプリケーションのコンボ ボックス ボタンのフラット スタイルの外観を設定します。

```
static void SetFlatMode(BOOL bFlat=TRUE);
```

### <a name="parameters"></a>パラメーター

*bフラット*<br/>
[in]フラット スタイルの外観の場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

コンボ ボックス ボタンの既定のフラット スタイルは FALSE です。

## <a name="cmfctoolbarcomboboxbuttonsetstyle"></a><a name="setstyle"></a>コンボボックスボタン::セットスタイル

コンボ ボックス ボタンに指定したスタイルを設定し、無効でない場合はコントロールを再描画します。

```
virtual void SetStyle(UINT nStyle);
```

### <a name="parameters"></a>パラメーター

*nStyle*<br/>
[in]ツール バー スタイルのビットごとの組み合わせ (OR)。

### <a name="remarks"></a>解説

ツールバーボタンスタイルのリストについては、「[ツールバーコントロールのスタイル](../../mfc/reference/toolbar-control-styles.md)」を参照してください。

## <a name="cmfctoolbarcomboboxbuttonsettext"></a><a name="settext"></a>コンボボックスボタン::テキストを設定します。

コンボ ボックス ボタンのエディット ボックス内のテキストを設定します。

```cpp
void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
[in]エディット ボックスのテキストを含む文字列へのポインター。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[Cコンボボックスクラス](../../mfc/reference/ccombobox-class.md)<br/>
[ボタンを置き換える](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)
