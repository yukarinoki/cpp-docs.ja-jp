---
title: CMFCToolBarComboBoxButton クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 49142f4ad7ea9793bbe533be6430bce929adf9cc
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039194"
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
|[CMFCToolBarComboBoxButton::AddSortedItem](#addsorteditem)|コンボ ボックスの一覧に項目を追加します。 リスト内の項目の順序がで指定された`Compare`です。|  
|[CMFCToolBarComboBoxButton::Compare](#compare)|2 つの項目を比較します。 呼ばれるを並べ替えるアイテム`AddSortedItems`コンボ ボックスの一覧に追加します。|  
|[CMFCToolBarComboBoxButton::CreateEdit](#createedit)|コンボ ボックス ボタン、新しい編集コントロールを作成します。|  
|[CMFCToolBarComboBoxButton::DeleteItem](#deleteitem)|コンボ ボックスの一覧から項目を削除します。|  
|[CMFCToolBarComboBoxButton::FindItem](#finditem)|指定した文字列が含まれている項目のインデックスを返します。|  
|[CMFCToolBarComboBoxButton::GetByCmd](#getbycmd)|指定されたコマンド ID を持つコンボ ボックス ボタンへのポインターを返します|  
|[CMFCToolBarComboBoxButton::GetComboBox](#getcombobox)|コンボ ボックス ボタンに埋め込まれているコンボ ボックス コントロールへのポインターを返します。|  
|[CMFCToolBarComboBoxButton::GetCount](#getcount)|コンボ ボックス リストで項目の数を返します。|  
|[CMFCToolBarComboBoxButton::GetCountAll](#getcountall)|コンボ ボックス ボタンを持つ指定されたコマンド ID を検索します。 コンボ ボックスでそのボタンのボックス一覧の項目の数を返します。|  
|[CMFCToolBarComboBoxButton::GetCurSel](#getcursel)|コンボ ボックス リストで選択した項目のインデックスを返します。|  
|[CMFCToolBarComboBoxButton::GetCurSelAll](#getcurselall)|コンボ ボックス ボタンを指定されたコマンド ID を持ち、そのボタンのボックスの一覧をコンボ ボックスで選択した項目のインデックスを返しますを検索します。|  
|[CMFCToolBarComboBoxButton::GetEditCtrl](#geteditctrl)|コンボ ボックス ボタンに埋め込まれている編集コントロールへのポインターを返します。|  
|[CMFCToolBarComboBoxButton::GetItem](#getitem)|コンボ ボックスで指定したインデックスに関連付けられている文字列ボックスの一覧を返します。|  
|[CMFCToolBarComboBoxButton::GetItemAll](#getitemall)|コンボ ボックス ボタンを指定されたコマンド ID を持ち、そのボタンのコンボ ボックスの一覧内のインデックスに関連付けられている文字列を返しますを検索します。|  
|[CMFCToolBarComboBoxButton::GetItemData](#getitemdata)|コンボ ボックスで指定したインデックスに関連付けられている 32 ビット値のボックスの一覧を返します。|  
|[CMFCToolBarComboBoxButton::GetItemDataAll](#getitemdataall)|コンボ ボックス ボタンを指定されたコマンド ID を持ち、そのボタンのコンボ ボックスの一覧内のインデックスに関連付けられている 32 ビット値を返しますを検索します。|  
|[CMFCToolBarComboBoxButton::GetItemDataPtrAll](#getitemdataptrall)|コンボ ボックス ボタンを持つ指定されたコマンド ID を検索します。 取得は 32 ビット値には、そのボタン、および 32 ビットのポインターとして値を返しますのコンボ ボックスの一覧内のインデックスが関連付けられています。|  
|[CMFCToolBarComboBoxButton::GetText](#gettext)|コンボ ボックスのエディット コントロールからテキストを返します。|  
|[CMFCToolBarComboBoxButton::GetTextAll](#gettextall)|コンボ ボックス ボタンを指定されたコマンド ID を持ち、そのボタンの編集コントロールからテキストを返しますを検索します。|  
|[CMFCToolBarComboBoxButton::IsCenterVert](#iscentervert)|アプリケーションのコンボ ボックス ボタンを中央に配置またはツールバーの上部に固定されているかどうかを判断します。|  
|[CMFCToolBarComboBoxButton::IsFlatMode](#isflatmode)|アプリケーションのコンボ ボックス ボタンの外観をフラットかどうかを判断します。|  
|[CMFCToolBarComboBoxButton::RemoveAllItems](#removeallitems)|一覧からすべての項目 ボックスし、コンボ ボックスのコントロールの編集を削除します。|  
|[CMFCToolBarComboBoxButton::SelectItem](#selectitem)|そのインデックス、32 ビット値、または文字列、に従ってコンボ ボックスで項目を選択し、選択範囲のコンボ ボックス コントロールに通知します。|  
|[CMFCToolBarComboBoxButton::SelectItemAll](#selectitemall)|コンボ ボックス ボタンを持つ指定されたコマンド ID を検索します。 呼び出し`SelectItem`文字列、インデックス、または 32 ビットの値に従ってそのボタンのコンボ ボックスで項目を選択します。|  
|[CMFCToolBarComboBoxButton::SetCenterVert](#setcentervert)|アプリケーションのコンボ ボックス ボタンを垂直方向に中央揃えまたはツールバーの上部に固定されているかどうかを指定します。|  
|[CMFCToolBarComboBoxButton::SetDropDownHeight](#setdropdownheight)|ドロップダウン リスト ボックスの高さを設定します。|  
|[CMFCToolBarComboBoxButton::SetFlatMode](#setflatmode)|アプリケーションのコンボ ボックス ボタンの外観をフラットかどうかを指定します。|  
  
## <a name="remarks"></a>Remarks  
 ツールバーにコンボ ボックス ボタンを追加するには、次の手順を実行します。  
  
 1. 親ツール バー リソースでボタンのダミー リソース ID を予約します。  
  
 2. `CMFCToolBarComboBoxButton` オブジェクトを構築します。  
  
 3. AFX_WM_RESETTOOLBAR メッセージを処理するメッセージ ハンドラーで、ダミー ボタンを置き換える新しいコンボ ボックス ボタンを使用して[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)です。  
  
 詳細については、次を参照してください。[チュートリアル: ツールバーにコントロールを配置する](../../mfc/walkthrough-putting-controls-on-toolbars.md)です。 コンボ ボックスのツールバー ボタンの例は、プロジェクト VisualStudioDemo の例を参照してください。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCToolBarComboBoxButton`クラスです。 例では、編集し、コンボ ボックスを有効にする、アプリケーションで、垂直位置のコンボ ボックス ボタンを設定、にドロップしたときに、リスト ボックスの高さを設定、アプリケーションのコンボ ボックス ボタンのフラット スタイルの外観を設定する方法を示しています。、エディット ボックス、コンボ ボックス ボタンでテキストを設定します。 このコード スニペットの一部である、 [Visual Studio のデモ サンプル](../../visual-cpp-samples.md)です。  
  
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
 [in]*lpszItem*  
 リスト ボックスに追加する項目のテキスト。  
  
 [in]*dwData*  
 リスト ボックスに追加する項目に関連付けられているデータ。  
  
### <a name="return-value"></a>戻り値  
 リスト ボックスの最後の項目のインデックス。  
  
### <a name="remarks"></a>Remarks  
 リスト ボックス スタイルが並べ替えられるときに、このメソッドを使用しないでください。  
  
 項目のテキストが既に場合、リスト ボックスで、既存の項目に新しいデータが格納されます。 項目の検索では大文字小文字を区別します。  
  
##  <a name="addsorteditem"></a>  CMFCToolBarComboBoxButton::AddSortedItem  
 定義されている順序でリスト ボックスに項目を追加、[比較](#compare)メソッドです。  
  
```  
virtual INT_PTR AddSortedItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszItem*  
 リスト ボックスに追加する項目のテキスト。  
  
 [in]*dwData*  
 リスト ボックスに追加する項目に関連付けられているデータ。  
  
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
 `TRUE` を返します。  
  
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
 [in]*uiID*  
 新しいボタンのコマンド ID。  
  
 [in]*画像*  
 新しいボタンに関連付けられているイメージのイメージのインデックス。  
  
 [in]*dwStyle*  
 新しいボタンのスタイルです。  
  
 [in]*iWidth*  
 (ピクセル単位) は、新しいボタンの幅。  
  
### <a name="remarks"></a>Remarks  
 既定の幅は、150 ピクセルです。  
  
 ツール バー ボタンのスタイルの一覧については、次を参照してください[ツール バー コントロールのスタイル。](../../mfc/reference/toolbar-control-styles.md)  
  
##  <a name="cleardata"></a>  CMFCToolBarComboBoxButton::ClearData  
 ユーザー定義データを削除します。  
  
```  
virtual void ClearData();
```  
  
### <a name="remarks"></a>Remarks  
 既定では、このメソッドは何も行いません。 すべてのユーザー定義データを削除する場合は、派生クラスでは、このメソッドをオーバーライドします。  
  
##  <a name="compare"></a>  CMFCToolBarComboBoxButton::Compare  
 2 つの文字列を比較します。  
  
```  
virtual int Compare(
    LPCTSTR lpszItem1,  
    LPCTSTR lpszItem2);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszItem1*  
 比較する最初の文字列。  
  
 [in]*lpszItem2*  
 比較する 2 番目の文字列。  
  
### <a name="return-value"></a>戻り値  
 文字列の大文字小文字を区別辞書式関係を示す値です。 次の表は、使用可能な値を示します。  
  
|[値]|説明|  
|-----------|-----------------|  
|\<0|最初の文字列は小さく、秒を超える。|  
|0|最初の文字列では、2 番目と同じです。|  
|>0|最初の文字列は、2 番目より大きいです。|  
  
### <a name="remarks"></a>Remarks  
 リスト ボックスで項目の並べ替え方法を変更するには、このメソッドをオーバーライドします。  
  
 比較では大文字小文字を区別します。  
  
 このメソッドはからのみ呼び出さ、 [AddSortedItem](#addsorteditem)メソッドです。  
  
##  <a name="copyfrom"></a>  CMFCToolBarComboBoxButton::CopyFrom  
 指定した状態をコピー`CMFCToolBarComboBoxButton`を現在のオブジェクト。  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `src`  
 ソース `CMFCToolBarComboBoxButton` オブジェクト。  
  
##  <a name="createcombo"></a>  CMFCToolBarComboBoxButton::CreateCombo  
 コンボ ボックス ボタン用の新しいコンボ ボックスを作成します。  
  
```  
virtual CComboBox* CreateCombo(
    CWnd* pWndParent,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pWndParent*  
 ボタンの親ウィンドウへのポインター。  
  
 [in]*rect*  
 コンボ ボックスの外接する四角形。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、新しいコンボ ボックスへのポインターそれ以外の場合、`NULL`です。  
  
##  <a name="createedit"></a>  CMFCToolBarComboBoxButton::CreateEdit  
 コンボ ボックス ボタン用の新しい編集ボックスを作成します。  
  
```  
virtual CMFCToolBarComboBoxEdit* CreateEdit(
    CWnd* pWndParent,  
    const CRect& rect,  
    DWORD dwEditStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pWndParent*  
 ボタンの親ウィンドウへのポインター。  
  
 [in]*rect*  
 新しい編集ボックスの外接する四角形。  
  
 [in]*dwEditStyle*  
 新しい編集ボックスのスタイルを制御します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、新しい編集ボックスへのポインターそれ以外の場合、`NULL`です。  
  
### <a name="remarks"></a>Remarks  
 フレームワークは、コンボ ボックス ボタン用の新しい編集ボックスを作成するときに、このメソッドを呼び出します。 変更するには、このメソッドをオーバーライドする方法[CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md)を作成します。  
  
##  <a name="deleteitem"></a>  CMFCToolBarComboBoxButton::DeleteItem  
 リスト ボックスから、指定した項目を削除します。  
  
```  
BOOL DeleteItem(int iIndex);  
BOOL DeleteItem(DWORD_PTR dwData);  
  BOOL DeleteItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*iIndex*  
 削除する項目の 0 から始まるインデックス。  
  
 [in]*dwData*  
 削除するアイテムに関連付けられたデータ。  
  
 [in]*lpszText*  
 削除する項目のテキスト。 同じテキストで複数の項目がある場合は、最初の項目は削除されます。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、項目が見つかり、正常に削除されました。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="duplicatedata"></a>  CMFCToolBarComboBoxButton::DuplicateData  
 ユーザー定義データを重複します。  
  
```  
virtual void DuplicateData();
```  
  
### <a name="remarks"></a>Remarks  
 既定では、このメソッドは何も行いません。 すべてのユーザー定義データをコピーする場合は、派生クラスでは、このメソッドをオーバーライドします。  
  
##  <a name="enablewindow"></a>  CMFCToolBarComboBoxButton::EnableWindow  
 有効または編集し、コンボ ボックスを無効にします。  
  
```  
virtual void EnableWindow(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bEnable*  
 `TRUE` 編集し、コンボ ボックスを有効にするには`FALSE`を編集し、コンボ ボックスを無効にします。  
  
### <a name="remarks"></a>Remarks  
 無効にすると、コントロールがアクティブになることはできず、ユーザー入力を受け付けることはできません。  
  
##  <a name="exporttomenubutton"></a>  CMFCToolBarComboBoxButton::ExportToMenuButton  
 コピー id コンボ ボックス ボタンのコマンドを使用して指定されたメニューには、アプリケーションの文字列テーブルから文字列です。  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*メニュー ボタン*  
 メニュー ボタンへの参照。  
  
### <a name="return-value"></a>戻り値  
 常に `TRUE`。  
  
##  <a name="finditem"></a>  CMFCToolBarComboBoxButton::FindItem  
 指定した文字列を含む、リスト ボックスで、最初の項目のインデックスを返します。  
  
```  
int FindItem(LPCTSTR lpszText) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszText*  
 リスト ボックスに検索するテキストです。  
  
### <a name="return-value"></a>戻り値  
 項目のインデックスまたは`CB_ERR`場合は、項目は見つかっていません。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getbycmd"></a>  CMFCToolBarComboBoxButton::GetByCmd  
 指定されたコマンド ID を持つコンボ ボックス ボタンへのポインターを取得します。  
  
```  
static CMFCToolBarComboBoxButton* GetByCmd(
    UINT uiCmd,  
    BOOL bIsFocus=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiCmd*  
 コンボ ボックス ボタンのコマンド ID。  
  
 [in]*bIsFocus*  
 `TRUE` だけを検索する特定のボタンです。`FALSE`をすべてのボタンを検索します。  
  
### <a name="return-value"></a>戻り値  
 コンボ ボックス ボタン; へのポインターまたは`NULL`場合は、ボタンが見つかりません。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getcombobox"></a>  CMFCToolBarComboBoxButton::GetComboBox  
 コンボ ボックス ボタンに含まれるコンボ ボックスへのポインターを返します。  
  
```  
CComboBox* GetComboBox() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CComboBox クラス](../../mfc/reference/ccombobox-class.md)オブジェクトのメソッドが成功しなかった場合はかどうか`NULL`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getcontextmenuid"></a>  CMFCToolBarComboBoxButton::GetContextMenuID  
 コンボ ボックス ボタンのショートカット メニューのリソース ID を取得します。  
  
```  
UINT GetContextMenuID();
```  
  
### <a name="return-value"></a>戻り値  
 ショートカット メニューのリソース id です。  
  
##  <a name="getcount"></a>  CMFCToolBarComboBoxButton::GetCount  
 リスト ボックスで項目の数を返します。  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リスト ボックス内の項目の数。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getcountall"></a>  CMFCToolBarComboBoxButton::GetCountAll  
 指定されたコマンド ID を持つコンボ ボックス ボタンのリスト ボックス内の項目の数を取得します。  
  
```  
static int GetCountAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiCmd*  
 コンボ ボックス ボタンのコマンド ID。  
  
### <a name="return-value"></a>戻り値  
 リスト ボックス内の項目数それ以外の場合、`CB_ERR`コンボ ボックス ボタンが見つからない場合。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getcursel"></a>  CMFCToolBarComboBoxButton::GetCurSel  
 リスト ボックスで現在選択されている項目のインデックスを取得します。  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リスト ボックスで現在選択されている項目のインデックスまたは`CB_ERR`項目が選択されていない場合。  
  
### <a name="remarks"></a>Remarks  
 リスト ボックス インデックスは 0 です。  
  
##  <a name="getcurselall"></a>  CMFCToolBarComboBoxButton::GetCurSelAll  
 指定されたコマンド ID を持つボックス ボタン、コンボ ボックスで現在選択されている項目のインデックスを返します  
  
```  
static int GetCurSelAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiCmd*  
 コンボ ボックス ボタンのコマンド ID。  
  
### <a name="return-value"></a>戻り値  
 リスト ボックスで現在選択されている項目のインデックスそれ以外の場合、`CB_ERR`項目が選択されていないか、コンボ ボックス ボタンが見つからない場合。  
  
### <a name="remarks"></a>Remarks  
 リスト ボックス インデックスは 0 です。  
  
##  <a name="geteditctrl"></a>  CMFCToolBarComboBoxButton::GetEditCtrl  
 コンボ ボックス ボタンに含まれるエディット ボックスへのポインターを返します。  
  
```  
virtual CEdit* GetEditCtrl();
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、編集ボックスへのポインターそれ以外の場合、`NULL`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="gethwnd"></a>  CMFCToolBarComboBoxButton::GetHwnd  
 コンボ ボックスのウィンドウ ハンドルを返します。  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>戻り値  
 ウィンドウ ハンドルまたは`NULL`コンボ ボックスはウィンドウ オブジェクトに関連付けられていない場合。  
  
##  <a name="getitem"></a>  CMFCToolBarComboBoxButton::GetItem  
 リスト ボックスで指定したインデックス位置にある項目に関連付けられている文字列を返します。  
  
```  
LPCTSTR GetItem(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*iIndex*  
 リスト ボックス内の項目の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 アイテムに関連付けられている文字列へのポインターそれ以外の場合、`NULL`インデックス パラメーターが有効でない場合、またはインデックス パラメーターが-1 とコンボ ボックスで選択した項目がない場合。  
  
### <a name="remarks"></a>Remarks  
 -1 のインデックス パラメーターは、現在選択されている項目の文字列を返します。  
  
##  <a name="getitemall"></a>  CMFCToolBarComboBoxButton::GetItemAll  
 指定されたコマンド ID を持つコンボ ボックス ボタンのリスト ボックスで指定したインデックス位置にある項目に関連付けられている文字列を返します  
  
```  
static LPCTSTR GetItemAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiCmd*  
 コンボ ボックス ボタンのコマンド ID。  
  
 [in]*iIndex*  
 リスト ボックス内の項目の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、項目の文字列へのポインターそれ以外の場合、`NULL`コンボ ボックス ボタンがありませんが、インデックスが有効でない場合が見つかると、インデックス-1 は、コンボ ボックスで選択した項目がない場合またはします。  
  
### <a name="remarks"></a>Remarks  
 インデックス値の-1 は、現在選択されている項目の文字列を返します。  
  
##  <a name="getitemdata"></a>  CMFCToolBarComboBoxButton::GetItemData  
 リスト ボックスで指定したインデックス位置にある項目に関連付けられているデータを返します。  
  
```  
DWORD_PTR GetItemData(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*iIndex*  
 リスト ボックス内の項目の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 項目に関連付けられたデータまたは、項目が存在しない場合は 0 です。  
  
### <a name="remarks"></a>Remarks  
 -1 のインデックス パラメーターは、現在選択されている項目に関連付けられているデータを返します。  
  
##  <a name="getitemdataall"></a>  CMFCToolBarComboBoxButton::GetItemDataAll  
 特定のコマンド ID を持つコンボ ボックス ボタンのリスト ボックスで指定したインデックス位置にある項目に関連付けられているデータを返します  
  
```  
static DWORD_PTR GetItemDataAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiCmd*  
 コンボ ボックス ボタンのコマンド ID。  
  
 [in]*iIndex*  
 リスト ボックス内の項目の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、アイテムに関連付けられているデータそれ以外の場合、指定したインデックスが有効でない場合は 0 を返します、コンボ ボックス ボタンが見つかりません。  
  
### <a name="remarks"></a>Remarks  
 -1 のインデックス パラメーターは、現在選択されている項目に関連付けられているデータを返します。  
  
##  <a name="getitemdataptrall"></a>  CMFCToolBarComboBoxButton::GetItemDataPtrAll  
 特定のコマンド ID を持つコンボ ボックス ボタンのリスト ボックスで指定したインデックス位置にある項目に関連付けられているデータを返します このデータは、ポインターとして返されます。  
  
```  
static void* GetItemDataPtrAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiCmd*  
 コンボ ボックス ボタンのコマンド ID。  
  
 [in]*iIndex*  
 リスト ボックス内の項目の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合に、アイテムに関連付けられたポインターエラーが発生する場合は、それ以外の場合、-1 または`NULL`コンボ ボックス ボタンが見つからない場合。  
  
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
 指定されたコマンド ID を持つコンボ ボックス ボタンの編集ボックスにテキストを取得します。  
  
```  
static LPCTSTR GetTextAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiCmd*  
 特定のコンボ ボックス ボタンのコマンド ID。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、編集ボックス内のテキストそれ以外の場合、`NULL`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="hasfocus"></a>  CMFCToolBarComboBoxButton::HasFocus  
 コンボ ボックスで現在フォーカスがあるかどうかを示します。  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` コンボ ボックス現在フォーカスがある場合です。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドも返します`TRUE`コンボ ボックスの任意の子ウィンドウに現在フォーカスがある場合。  
  
##  <a name="iscentervert"></a>  CMFCToolBarComboBoxButton::IsCenterVert  
 アプリケーションでは、コンボ ボックス ボタンの縦方向の位置を返します。  
  
```  
static BOOL IsCenterVert();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ボタンは中央揃えです。`FALSE`ボタンが上部に固定されている場合。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="isflatmode"></a>  CMFCToolBarComboBoxButton::IsFlatMode  
 アプリケーションでは、コンボ ボックス ボタンのフラット スタイルの外観を返します。  
  
```  
static BOOL IsFlatMode();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ボタンにフラット スタイル; があります。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 コンボ ボックス ボタンの既定のフラット スタイルします。 `FALSE.`  
  
##  <a name="isownerof"></a>  CMFCToolBarComboBoxButton::IsOwnerOf  
 指定されたハンドルが、コンボ ボックス ボタン、またはその子のいずれかに関連付けられているかどうかを示します。  
  
```  
virtual BOOL IsOwnerOf(HWND hwnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*hwnd*  
 ウィンドウ ハンドル。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ハンドルが、コンボ ボックス ボタン、またはその子の 1 つに関連付けられている場合それ以外の場合、`FALSE`です。  
  
##  <a name="isribbonbutton"></a>  CMFCToolBarComboBoxButton::IsRibbonButton  
 コンボ ボックス ボタンがリボン パネルにあるかどうかを示します。  
  
```  
BOOL IsRibbonButton() const;  
```  
  
### <a name="return-value"></a>戻り値  
 常に `FALSE`。  
  
### <a name="remarks"></a>Remarks  
 既定では、このメソッドは常`FALSE`、リボン パネルには、コンボ ボックス ボタンは表示されません。  
  
##  <a name="iswindowvisible"></a>  CMFCToolBarComboBoxButton::IsWindowVisible  
 可視性の状態のコンボ ボックス ボタンを返します。  
  
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
 [in]*iNotifyCode*  
 コマンドに関連付けられている通知メッセージです。  
  
### <a name="return-value"></a>戻り値  
 かどうかコンボ ボックス ボタンは、メッセージを処理します。  
  
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
 [in]*pDC*  
 コンボ ボックス ボタンを表示しているデバイス コンテキスト。  
  
 [in]*sizeDefault*  
 コンボ ボックス ボタンの既定のサイズ。  
  
 [in]*bHorz*  
 親ツールバーのドッキング状態です。 `TRUE` ツールバーが水平にドッキングされているときと`FALSE`ツールバーが垂直方向にドッキングされているとき。  
  
### <a name="return-value"></a>戻り値  
 A`SIZE`コンボ ボックス ボタンのピクセル単位の大きさを格納する構造体。  
  
##  <a name="onchangeparentwnd"></a>  CMFCToolBarComboBoxButton::OnChangeParentWnd  
 新しいツールバーにコンボ ボックス ボタンを挿入したときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pWndParent*  
 新しい親ツールバーへのポインター。  
  
##  <a name="onclick"></a>  CMFCToolBarComboBoxButton::OnClick  
 ユーザーがコンボ ボックス ボタンをクリックしたときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pWnd*  
 コンボ ボックス ボタンの親ウィンドウへのポインター。  
  
 [in]*bDelay*  
 派生クラスで使用するために予約されています。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドがイベントを処理する場合それ以外の場合、`FALSE`です。  
  
##  <a name="onctlcolor"></a>  CMFCToolBarComboBoxButton::OnCtlColor  
 親ツールバーのコンボ ボックス ボタンの色を設定する色を変更したときに、フレームワークによって呼び出されます。  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 コンボ ボックス ボタンを表示しているデバイス コンテキスト。  
  
 [in]*のため*  
 使用されません。  
  
### <a name="return-value"></a>戻り値  
 フレームワークを使用して、コンボ ボックス ボタンの背景を描画するブラシへのハンドルします。  
  
### <a name="remarks"></a>Remarks  
 また、このメソッドは、コンボ ボックス ボタン テキストの色を設定します。  
  
##  <a name="ondraw"></a>  CMFCToolBarComboBoxButton::OnDraw  
 指定したスタイルとオプションを使用して、コンボ ボックス ボタンを描画するためにフレームワークによって呼び出されます。  
  
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
 [in]*Pdc*  
 ボタンを表示しているデバイス コンテキスト。  
  
 [in]*rect*  
 ボタンの外接する四角形。  
  
 [in]*pImages*  
 ボタンに関連付けられているイメージのコレクション。  
  
 [in]*bHorz*  
 親ツールバーのドッキング状態です。 `TRUE` ツールバーが水平にドッキングされているときと`FALSE`ツールバーが垂直方向にドッキングされているとき。  
  
 [in]*bCustomizeMode*  
 かどうか、アプリケーションは、カスタマイズ モードでです。  
  
 [in]*bHighlight*  
 強調表示されているコンボ ボックス ボタンを描画するかどうか。  
  
 [in]*bDrawBorder*  
 罫線のコンボ ボックス ボタンを描画するかどうか。  
  
 [in]*bGrayDisabledButtons*  
 `TRUE` 無効なボタン以外の影を描画するには`FALSE`無効化を使用するイメージのコレクション。  
  
##  <a name="ondrawoncustomizelist"></a>  CMFCToolBarComboBoxButton::OnDrawOnCustomizeList  
 コンボ ボックス ボタンを描画するためにフレームワークによって呼び出されます、**コマンド**のペイン、**カスタマイズ** ダイアログ ボックス。  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 コンボ ボックス ボタンを表示しているデバイス コンテキスト。  
  
 [in]*rect*  
 コンボ ボックス ボタンの外接する四角形。  
  
 [in]*bSelected*  
 `TRUE` コンボ ボックス ボタンが選択されます。それ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 コンボ ボックス ボタンのピクセル単位の幅。  
  
##  <a name="onglobalfontschanged"></a>  CMFCToolBarComboBoxButton::OnGlobalFontsChanged  
 アプリケーションのフォントが変更されたときに、コンボ ボックス ボタンのフォントを設定するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
##  <a name="onmove"></a>  CMFCToolBarComboBoxButton::OnMove  
 親ツールバーを動かしたときに、コンボ ボックス ボタンの場所を変更するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnMove();
```  
  
##  <a name="onshow"></a>  CMFCToolBarComboBoxButton::OnShow  
 コンボ ボックス ボタンを非表示にするか、または表示するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bShow*  
 コンボ ボックス ボタンを表示または非表示するかどうか。  
  
##  <a name="onsize"></a>  CMFCToolBarComboBoxButton::OnSize  
 親ツールバーのサイズが変更されたときに、コンボ ボックス ボタンのサイズを変更するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*iSize*  
 コンボ ボックス ボタンの幅。  
  
##  <a name="onupdatetooltip"></a>  CMFCToolBarComboBoxButton::OnUpdateToolTip  
 コンボ ボックス ボタンのツール ヒントを変更したときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,  
    int iButtonIndex,  
    CToolTipCtrl& wndToolTip,  
    CString& str);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pWndParent*  
 コンボ ボックス ボタンは、親ウィンドウへのポインター。  
  
 [in]*iButtonIndex*  
 コンボ ボックス ボタンの ID です。  
  
 [in]*wndToolTip*  
 コンボ ボックス ボタンに関連付けるツールヒント。  
  
 [in]*str*  
 ツール ヒントのテキスト。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドがイベントを処理する場合それ以外の場合、`FALSE`です。  
  
##  <a name="removeallitems"></a>  CMFCToolBarComboBoxButton::RemoveAllItems  
 一覧および編集ボックスからすべての項目を削除します。  
  
```  
void RemoveAllItems();
```  
  
### <a name="remarks"></a>Remarks  
 一覧からすべての項目 ボックス、コンボ ボックスのコントロールを編集を削除します。  
  
##  <a name="selectitem"></a>  CMFCToolBarComboBoxButton::SelectItem  
 リスト ボックスの項目を選択します。  
  
```  
BOOL SelectItem(
    int iIndex,  
    BOOL bNotify=TRUE);  
  
BOOL SelectItem(DWORD_PTR dwData);  
BOOL SelectItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*iIndex*  
 リスト ボックス内の項目の 0 から始まるインデックス。  
  
 [in]*bNotify*  
 `TRUE` 選択範囲のコンボ ボックス ボタンに通知するにはそれ以外の場合`FALSE`です。  
  
 [in]*dwData*  
 リスト ボックス内の項目に関連付けられたデータ。  
  
 [in]*lpszText*  
 リスト ボックス内の項目のテキストです。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功した場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="selectitemall"></a>  CMFCToolBarComboBoxButton::SelectItemAll  
 指定されたコマンド ID を持つコンボ ボックス ボタンのリスト ボックスで項目を選択します。  
  
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
 [in]*uiCmd*  
 リスト ボックスを含むコンボ ボックス ボタンのコマンド ID。  
  
 [in]*iIndex*  
 リスト ボックス内の項目の 0 から始まるインデックス。 値-1 は、リスト ボックス内の現在の選択項目を削除し、編集ボックスをクリアします。  
  
 [in]*dwData*  
 リスト ボックス内のアイテムのデータです。  
  
 [in]*lpszText*  
 リスト ボックス内の項目のテキストです。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功した場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="serialize"></a>  CMFCToolBarComboBoxButton::Serialize  
 アーカイブからこのオブジェクトを読み取りまたはアーカイブを書き込みます。  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力].*ar*  
 `CArchive`シリアル化するオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 設定、`CArchive`オブジェクトは、このメソッドが読み取りまたは書き込みをアーカイブするかどうかを判断します。  
  
##  <a name="setaccdata"></a>  CMFCToolBarComboBoxButton::SetACCData  
 指定した設定`CAccessibilityData`コンボ ボックス ボタンからのアクセシビリティ データを使用してオブジェクト。  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pParent*  
 コンボ ボックス ボタンの親ウィンドウです。  
  
 [out]*データ*  
 A`CAccessibilityData`コンボ ボックス ボタンからのアクセシビリティ データを受け取るオブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功した場合それ以外の場合`FALSE`です。  
  
##  <a name="setcentervert"></a>  CMFCToolBarComboBoxButton::SetCenterVert  
 アプリケーションでは、コンボ ボックス ボタンの縦方向の位置を設定します。  
  
```  
static void SetCenterVert(BOOL bCenterVert=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bCenterVert*  
 `TRUE` ツールバーのコンボ ボックス ボタンを中央に`FALSE`をコンボ ボックス ボタンをツールバーの上部を揃えます。  
  
### <a name="remarks"></a>Remarks  
 既定では、コンボ ボックス ボタンが上部に配置します。  
  
##  <a name="setcontextmenuid"></a>  CMFCToolBarComboBoxButton::SetContextMenuID  
 コンボ ボックス ボタンのショートカット メニューのリソース ID を設定します。  
  
```  
void SetContextMenuID(UINT uiResID);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiResID*  
 ショートカット メニューのリソース id です。  
  
##  <a name="setdropdownheight"></a>  CMFCToolBarComboBoxButton::SetDropDownHeight  
 にドロップしたときに、リスト ボックスの高さを設定します。  
  
```  
void SetDropDownHeight(int nHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*パラメーター nHeight*  
 (ピクセル単位)、リスト ボックスの高さ。  
  
### <a name="remarks"></a>Remarks  
 既定の高さは、150 ピクセルです。  
  
##  <a name="setflatmode"></a>  CMFCToolBarComboBoxButton::SetFlatMode  
 アプリケーションでは、コンボ ボックス ボタンのフラット スタイルの外観を設定します。  
  
```  
static void SetFlatMode(BOOL bFlat=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bFlat*  
 `TRUE` フラット スタイルの外観です。それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 コンボ ボックス ボタンの既定のフラット スタイル`FALSE`です。  
  
##  <a name="setstyle"></a>  CMFCToolBarComboBoxButton::SetStyle  
 コンボ ボックス ボタンに指定したスタイルを設定しては無効になっていない場合は、コントロールを再作成します。  
  
```  
virtual void SetStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nStyle*  
 ツール バー スタイルのビットごとの組み合わせ (OR)。  
  
### <a name="remarks"></a>Remarks  
 ツール バー ボタンのスタイルの一覧については、次を参照してください[ツール バー コントロールのスタイル。](../../mfc/reference/toolbar-control-styles.md)  
  
##  <a name="settext"></a>  CMFCToolBarComboBoxButton::SetText  
 ボックス ボタン、コンボ ボックスの編集ボックスにテキストを設定します。  
  
```  
void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszText*  
 エディット ボックスのテキストを含む文字列へのポインター。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CComboBox クラス](../../mfc/reference/ccombobox-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)



