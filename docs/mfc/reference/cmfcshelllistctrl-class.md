---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCShellListCtrl
- AFXSHELLLISTCTRL/CMFCShellListCtrl
- AFXSHELLLISTCTRL/CMFCShellListCtrl::DisplayFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::DisplayParentFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::EnableShellContextMenu
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentFolderName
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentItemIdList
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentShellFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetItemPath
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetItemTypes
- AFXSHELLLISTCTRL/CMFCShellListCtrl::IsDesktop
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnCompareItems
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnFormatFileDate
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnFormatFileSize
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnGetItemIcon
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnGetItemText
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnSetColumns
- AFXSHELLLISTCTRL/CMFCShellListCtrl::Refresh
- AFXSHELLLISTCTRL/CMFCShellListCtrl::SetItemTypes
helpviewer_keywords:
- CMFCShellListCtrl [MFC], DisplayFolder
- CMFCShellListCtrl [MFC], DisplayParentFolder
- CMFCShellListCtrl [MFC], EnableShellContextMenu
- CMFCShellListCtrl [MFC], GetCurrentFolder
- CMFCShellListCtrl [MFC], GetCurrentFolderName
- CMFCShellListCtrl [MFC], GetCurrentItemIdList
- CMFCShellListCtrl [MFC], GetCurrentShellFolder
- CMFCShellListCtrl [MFC], GetItemPath
- CMFCShellListCtrl [MFC], GetItemTypes
- CMFCShellListCtrl [MFC], IsDesktop
- CMFCShellListCtrl [MFC], OnCompareItems
- CMFCShellListCtrl [MFC], OnFormatFileDate
- CMFCShellListCtrl [MFC], OnFormatFileSize
- CMFCShellListCtrl [MFC], OnGetItemIcon
- CMFCShellListCtrl [MFC], OnGetItemText
- CMFCShellListCtrl [MFC], OnSetColumns
- CMFCShellListCtrl [MFC], Refresh
- CMFCShellListCtrl [MFC], SetItemTypes
ms.assetid: ad472958-5586-4c50-aadf-1844c30bf6e7
ms.openlocfilehash: 445556535217b0887a02227a0773c287911922a2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753479"
---
# <a name="cmfcshelllistctrl-class"></a>クラス

この`CMFCShellListCtrl`クラスは、Windows リスト コントロール機能を提供し、シェル項目の一覧を表示する機能を含めることによって、それを拡張します。

## <a name="syntax"></a>構文

```
class CMFCShellListCtrl : public CMFCListCtrl
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[:D再生フォルダー](#displayfolder)|指定されたフォルダーに含まれる項目の一覧を表示します。|
|[親フォルダー:D](#displayparentfolder)|現在表示されているフォルダの親であるフォルダに含まれるアイテムの一覧を表示します。|
|[次のコマンドを実行します。](#enableshellcontextmenu)|ショートカット メニューを有効または無効にします。|
|[次の項目を取得します。](#getcurrentfolder)|現在のフォルダーのパスを取得します。|
|[次の項目を取得します。](#getcurrentfoldername)|現在のフォルダーの名前を取得します。|
|[一覧を取得します。](#getcurrentitemidlist)|現在のリスト コントロール項目の PIDL を返します。|
|[次の項目を取得します。](#getcurrentshellfolder)|現在のシェル フォルダーへのポインターを返します。|
|[次の項目を取得します。](#getitempath)|項目のテキスト パスを返します。|
|[次の値を取得します。](#getitemtypes)|リスト コントロールによって表示されるシェル項目の種類を返します。|
|[次の処理を行います。](#isdesktop)|現在選択されているフォルダがデスクトップ フォルダかどうかを確認します。|
|[アイテムを比較します。](#oncompareitems)|フレームワークは、2 つの項目を比較するときにこのメソッドを呼び出します。 (オーバーライドします[。](../../mfc/reference/cmfclistctrl-class.md#oncompareitems)|
|[ファイル日付を指定します。](#onformatfiledate)|フレームワークがリスト コントロールによって表示されるファイルの日付を取得するときに呼び出されます。|
|[ファイルサイズを変更します。](#onformatfilesize)|フレームワークがリスト コントロールのファイル サイズを変換するときに呼び出されます。|
|[をクリックします。](#ongetitemicon)|フレームワークがリスト コントロール項目のアイコンを取得するときに呼び出されます。|
|[テキストを取得します。](#ongetitemtext)|フレームワークがリスト コントロール項目のテキストを変換するときに呼び出されます。|
|[列の設定](#onsetcolumns)|列の名前を設定するときに、フレームワークによって呼び出されます。|
|[をクリックします。](#refresh)|リスト コントロールを更新して再描画します。|
|[次の項目を選択します。](#setitemtypes)|リスト コントロールによって表示される項目の種類を設定します。|

## <a name="remarks"></a>解説

この`CMFCShellListCtrl`クラスは、プログラムが Windows シェル項目を一覧表示できるようにすることで[、CMFCListCtrl クラス](../../mfc/reference/cmfclistctrl-class.md)の機能を拡張します。 使用される表示形式は、エクスプローラー ウィンドウのリスト ビューと同じです。

[オブジェクト](../../mfc/reference/cmfcshelltreectrl-class.md)をオブジェクトに関連付けて、完全な`CMFCShellListCtrl`エクスプローラー ウィンドウを作成できます。 次に、 で項目を`CMFCShellTreeCtrl`選択すると、`CMFCShellListCtrl`オブジェクトは選択した項目の内容をリストします。

## <a name="example"></a>例

次の例は、`CMFCShellListCtrl`クラスのオブジェクトを作成する方法と、現在表示されているフォルダーの親フォルダーを表示する方法を示しています。 このコード スニペットは[、エクスプローラーのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_Explorer#1](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_1.h)]
[!code-cpp[NVC_MFC_Explorer#2](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_2.cpp)]
[!code-cpp[NVC_MFC_Explorer#3](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_3.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListCtrl](../../mfc/reference/clistctrl-class.md)

[CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)

`CMFCShellListCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx シェルリストCtrl.h

## <a name="cmfcshelllistctrldisplayfolder"></a><a name="displayfolder"></a>:D再生フォルダー

指定されたフォルダーに含まれる項目の一覧を表示します。

```
virtual HRESULT DisplayFolder(LPCTSTR lpszPath);
virtual HRESULT DisplayFolder(LPAFX_SHELLITEMINFO lpItemInfo);
```

### <a name="parameters"></a>パラメーター

*パス*<br/>
[in]フォルダーのパスを含む文字列。

*をクリックします。*<br/>
[in]表示するフォルダーを`LPAFX_SHELLITEMINFO`記述する構造体へのポインター。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合はE_FAILします。

## <a name="cmfcshelllistctrldisplayparentfolder"></a><a name="displayparentfolder"></a>親フォルダー:D

現在表示されているフォルダーの親フォルダーを表示するように[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクトを更新します。

```
virtual HRESULT DisplayParentFolder();
```

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合はE_FAILします。

## <a name="cmfcshelllistctrlenableshellcontextmenu"></a><a name="enableshellcontextmenu"></a>次のコマンドを実行します。

ショートカット メニューを有効にします。

```cpp
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]フレームワークがショートカット メニューを有効にするかどうかを指定するブール値。

## <a name="cmfcshelllistctrlgetcurrentfolder"></a><a name="getcurrentfolder"></a>次の項目を取得します。

[オブジェクト内](../../mfc/reference/cmfcshelllistctrl-class.md)で現在選択されているフォルダーのパスを取得します。

```
BOOL GetCurrentFolder(CString& strPath) const;
```

### <a name="parameters"></a>パラメーター

*ストレパス*<br/>
[アウト]メソッドがパスを書き込む文字列パラメーターへの参照。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは、 でフォルダが選択されていない場合`CMFCShellListCtrl`に失敗します。

## <a name="cmfcshelllistctrlgetcurrentfoldername"></a><a name="getcurrentfoldername"></a>次の項目を取得します。

[オブジェクト内](../../mfc/reference/cmfcshelllistctrl-class.md)で現在選択されているフォルダーの名前を取得します。

```
BOOL GetCurrentFolderName(CString& strName) const;
```

### <a name="parameters"></a>パラメーター

*strName*<br/>
[アウト]メソッドが名前を書き込む文字列パラメーターへの参照。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは、 でフォルダが選択されていない場合`CMFCShellListCtrl`に失敗します。

## <a name="cmfcshelllistctrlgetcurrentitemidlist"></a><a name="getcurrentitemidlist"></a>一覧を取得します。

現在選択されている項目の PIDL を返します。

```
LPITEMIDLIST GetCurrentItemIdList() const;
```

### <a name="return-value"></a>戻り値

現在の項目の PIDL。

## <a name="cmfcshelllistctrlgetcurrentshellfolder"></a><a name="getcurrentshellfolder"></a>次の項目を取得します。

[オブジェクト内](../../mfc/reference/cmfcshelllistctrl-class.md)で現在選択されている項目へのポインターを取得します。

```
const IShellFolder* GetCurrentShellFolder() const;
```

### <a name="return-value"></a>戻り値

選択したオブジェクトの[IShellFolder インターフェイス](/windows/win32/api/shobjidl_core/nn-shobjidl_core-ishellfolder)へのポインター。

### <a name="remarks"></a>解説

オブジェクトが現在選択されていない場合、このメソッドは NULL を返します。

## <a name="cmfcshelllistctrlgetitempath"></a><a name="getitempath"></a>次の項目を取得します。

項目のパスを取得します。

```
BOOL GetItemPath(
    CString& strPath,
    int iItem) const;
```

### <a name="parameters"></a>パラメーター

*ストレパス*<br/>
[アウト]パスを受け取る文字列への参照。

*iItem*<br/>
[in]リスト アイテムのインデックス。

### <a name="return-value"></a>戻り値

成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

*iItem*によって提供されるインデックスは、[現在 CMFCShellListCtrl クラス](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクトによって表示されている項目に基づいています。

## <a name="cmfcshelllistctrlgetitemtypes"></a><a name="getitemtypes"></a>次の値を取得します。

オブジェクトによって表示される項目の種類[を](../../mfc/reference/cmfcshelllistctrl-class.md)返します。

```
SHCONTF GetItemTypes() const;
```

### <a name="return-value"></a>戻り値

に一覧表示される項目の種類を含む[SHCONTF](/windows/win32/api/shobjidl_core/ne-shobjidl_core-_shcontf)値。 `CMFCShellListCtrl`

### <a name="remarks"></a>解説

にリストされている項目の種類を設定するには`CMFCShellListCtrl`[、CMFCShellListCtrl::SetItemTypes を](#setitemtypes)呼び出します。

## <a name="cmfcshelllistctrlisdesktop"></a><a name="isdesktop"></a>次の処理を行います。

[オブジェクトに](../../mfc/reference/cmfcshelllistctrl-class.md)表示されるフォルダーがデスクトップ フォルダーかどうかを判断します。

```
BOOL IsDesktop() const;
```

### <a name="return-value"></a>戻り値

表示されるフォルダがデスクトップ フォルダの場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcshelllistctrloncompareitems"></a><a name="oncompareitems"></a>アイテムを比較します。

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
virtual int OnCompareItems(
    LPARAM lParam1,
    LPARAM lParam2,
    int iColumn);
```

### <a name="parameters"></a>パラメーター

[in]*lパラム1*<br/>
[in]*lパラム2*<br/>
[in]*i列*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcshelllistctrlonformatfiledate"></a><a name="onformatfiledate"></a>ファイル日付を指定します。

フレームワークは、オブジェクトに関連付けられた日付を文字列に変換する必要があるときに、このメソッドを呼び出します。

```
virtual void OnFormatFileDate(
    const CTime& tmFile,
    CString& str);
```

### <a name="parameters"></a>パラメーター

*tmファイル*<br/>
[in]ファイルに関連付けられている日付。

*Str*<br/>
[アウト]書式設定されたファイルの日付を含む文字列。

### <a name="remarks"></a>解説

[CMFCShellListCtrl クラス](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクトは、ファイルに関連付けられている日付を表示する場合、その日付を文字列形式に変換する必要があります。 は`CMFCShellListCtrl`、このメソッドを使用して変換を行います。 既定では、このメソッドは現在のロケールを使用して日付を文字列に書式設定します。

## <a name="cmfcshelllistctrlonformatfilesize"></a><a name="onformatfilesize"></a>ファイルサイズを変更します。

フレームワークは、オブジェクトのサイズを文字列に変換するときに、このメソッドを呼び出します。

```
virtual void OnFormatFileSize(
    long lFileSize,
    CString& str);
```

### <a name="parameters"></a>パラメーター

*ファイルサイズ*<br/>
[in]フレームワークが表示するファイルのサイズ。

*Str*<br/>
[アウト]書式設定されたファイル サイズを含む文字列。

### <a name="remarks"></a>解説

[CMFCShellListCtrl クラス](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクトは、ファイルのサイズを表示する必要がある場合は、文字列形式にファイルサイズを変換する必要があります。 は`CMFCShellListCtrl`、このメソッドを使用して変換を行います。 既定では、このメソッドはファイル サイズをバイトからキロバイトに変換し、現在のロケールを使用してサイズを文字列にフォーマットします。

## <a name="cmfcshelllistctrlongetitemicon"></a><a name="ongetitemicon"></a>をクリックします。

フレームワークは、このメソッドを呼び出して、シェル リスト項目に関連付けられたアイコンを取得します。

```
virtual int OnGetItemIcon(
    int iItem,
    LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>パラメーター

*iItem*<br/>
[in]項目のインデックス。

*Pitem*<br/>
[in]項目を説明するLPAFX_SHELLITEMINFOパラメーター。

### <a name="return-value"></a>戻り値

成功した場合はアイコン イメージのインデックス。関数が失敗した場合は -1。

### <a name="remarks"></a>解説

アイコン イメージ インデックスは、システム イメージ リストに基づいています。

既定では、このメソッドは*pItem*パラメーターに依存します。 *iItem*の値は、既定の実装では使用されません。 *iItem*を使用してカスタム動作を実装できます。

## <a name="cmfcshelllistctrlongetitemtext"></a><a name="ongetitemtext"></a>テキストを取得します。

フレームワークは、シェル項目のテキストを取得する必要がある場合に、このメソッドを呼び出します。

```
virtual CString OnGetItemText(
    int iItem,
    int iColumn,
    LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>パラメーター

*iItem*<br/>
[in]項目のインデックス。

*i列*<br/>
[in]対象の列。

*Pitem*<br/>
[in]項目を説明するLPAFX_SHELLITEMINFOパラメーター。

### <a name="return-value"></a>戻り値

アイテム`CString`に関連付けられているテキストを含む A。

### <a name="remarks"></a>解説

オブジェクトの各項目`CMFCShellListCtrl`には、1 つ以上の列にテキストを含むことができます。 フレームワークがこのメソッドを呼び出すときに、目的の列を指定します。 この関数を手動で呼び出す場合は、対象となる列も指定する必要があります。

既定では、このメソッドは*pItem*パラメーターを使用して、処理する項目を決定します。 *iItem*の値は、既定の実装では使用されません。

## <a name="cmfcshelllistctrlonsetcolumns"></a><a name="onsetcolumns"></a>列の設定

フレームワークは、列の名前を設定するときにこのメソッドを呼び出します。

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>解説

既定では、フレームワークはオブジェクトに 4`CMFCShellListCtrl`つの列を作成します。 これらの列の名前は、**名前**、**サイズ**、**種類**、および**変更日時**です。 このメソッドをオーバーライドして、列の数と名前をカスタマイズできます。

## <a name="cmfcshelllistctrlrefresh"></a><a name="refresh"></a>をクリックします。

[オブジェクトを](../../mfc/reference/cmfcshelllistctrl-class.md)更新して再描画します。

```
virtual HRESULT Refresh();
```

### <a name="return-value"></a>戻り値

`S_OK`成功した場合。それ以外の場合はエラー値。

### <a name="remarks"></a>解説

`CMFCShellListCtrl`オブジェクトによって表示される項目の一覧を更新します。

## <a name="cmfcshelllistctrlsetitemtypes"></a><a name="setitemtypes"></a>次の項目を選択します。

[オブジェクトに](../../mfc/reference/cmfcshelllistctrl-class.md)一覧表示される項目の種類を設定します。

```cpp
void SetItemTypes(SHCONTF nTypes);
```

### <a name="parameters"></a>パラメーター

*nタイプ*<br/>
[in]オブジェクトがサポートする項目の種類`CMFCShellListCtrl`の一覧。

### <a name="remarks"></a>解説

項目タイプのリストの詳細については[、SHCONTF](/windows/win32/api/shobjidl_core/ne-shobjidl_core-_shcontf)を参照してください。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfclistctrl-class.md)<br/>
[クラス](../../mfc/reference/cmfcshelltreectrl-class.md)
