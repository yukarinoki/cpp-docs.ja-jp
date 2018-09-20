---
title: CMFCShellListCtrl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2d7238fa9a75c173e1b02697359a72630a95a06
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433986"
---
# <a name="cmfcshelllistctrl-class"></a>CMFCShellListCtrl クラス

`CMFCShellListCtrl`クラスは、Windows リスト コントロールの機能を提供し、シェル項目の一覧を表示する機能を含めることによってを展開します。

## <a name="syntax"></a>構文

```
class CMFCShellListCtrl : public CMFCListCtrl
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCShellListCtrl::DisplayFolder](#displayfolder)|指定されたフォルダー内に含まれる項目の一覧を表示します。|
|[CMFCShellListCtrl::DisplayParentFolder](#displayparentfolder)|現在表示されているフォルダーの親であるフォルダー内に含まれる項目の一覧を表示します。|
|[CMFCShellListCtrl::EnableShellContextMenu](#enableshellcontextmenu)|有効または、ショートカット メニューを無効にします。|
|[CMFCShellListCtrl::GetCurrentFolder](#getcurrentfolder)|現在のフォルダーのパスを取得します。|
|[CMFCShellListCtrl::GetCurrentFolderName](#getcurrentfoldername)|現在のフォルダーの名前を取得します。|
|[CMFCShellListCtrl::GetCurrentItemIdList](#getcurrentitemidlist)|現在のリスト コントロール項目の PIDL を返します。|
|[CMFCShellListCtrl::GetCurrentShellFolder](#getcurrentshellfolder)|現在のシェル フォルダーへのポインターを返します。|
|[CMFCShellListCtrl::GetItemPath](#getitempath)|項目のテキストのパスを返します。|
|[CMFCShellListCtrl::GetItemTypes](#getitemtypes)|リスト コントロールによって表示されるシェル項目の種類を返します。|
|[CMFCShellListCtrl::IsDesktop](#isdesktop)|現在選択されているフォルダーのデスクトップのフォルダーを確認します。|
|[CMFCShellListCtrl::OnCompareItems](#oncompareitems)|フレームワークは、2 つの項目を比較する際に、このメソッドを呼び出します。 (上書き[CMFCListCtrl::OnCompareItems](../../mfc/reference/cmfclistctrl-class.md#oncompareitems))。|
|[CMFCShellListCtrl::OnFormatFileDate](#onformatfiledate)|フレームワーク リスト コントロールによって表示されるファイルの日付を取得するときに呼び出されます。|
|[CMFCShellListCtrl::OnFormatFileSize](#onformatfilesize)|フレームワークは、リスト コントロールのファイル サイズを変換するときに呼び出されます。|
|[CMFCShellListCtrl::OnGetItemIcon](#ongetitemicon)|フレームワーク リスト コントロール項目のアイコンを取得するときに呼び出されます。|
|[CMFCShellListCtrl::OnGetItemText](#ongetitemtext)|フレームワークは、リスト コントロール項目のテキストを変換するときに呼び出されます。|
|[CMFCShellListCtrl::OnSetColumns](#onsetcolumns)|列の名前を設定するときに、フレームワークによって呼び出されます。|
|[CMFCShellListCtrl::Refresh](#refresh)|更新して、リスト コントロールを再描画します。|
|[CMFCShellListCtrl::SetItemTypes](#setitemtypes)|リスト コントロールによって表示される項目の種類を設定します。|

## <a name="remarks"></a>Remarks

`CMFCShellListCtrl`クラスの機能を拡張する、 [CMFCListCtrl クラス](../../mfc/reference/cmfclistctrl-class.md)Windows シェル項目の一覧にプログラムを有効にするとします。 使用される表示形式は、エクスプ ローラー ウィンドウのリスト ビューのと同様です。

A [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)オブジェクトが関連付けられる、`CMFCShellListCtrl`完了エクスプ ローラー ウィンドウを作成するオブジェクト。 内の項目を選択し、`CMFCShellTreeCtrl`により、`CMFCShellListCtrl`選択した項目の内容を一覧表示するオブジェクト。

## <a name="example"></a>例

次の例のオブジェクトを作成する方法、`CMFCShellListCtrl`クラスと、現在表示されているフォルダーの親フォルダーを表示する方法。 このコード スニペットの一部、 [Explorer サンプル](../../visual-cpp-samples.md)します。

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

## <a name="requirements"></a>要件

**ヘッダー:** afxshelllistCtrl.h

##  <a name="displayfolder"></a>  CMFCShellListCtrl::DisplayFolder

指定されたフォルダー内に含まれる項目の一覧を表示します。

```
virtual HRESULT DisplayFolder(LPCTSTR lpszPath);
virtual HRESULT DisplayFolder(LPAFX_SHELLITEMINFO lpItemInfo);
```

### <a name="parameters"></a>パラメーター

*lpszPath*<br/>
[in]フォルダーのパスを含む文字列。

*lpItemInfo*<br/>
[in]ポインター、`LPAFX_SHELLITEMINFO`構造を表示するフォルダーについて説明します。

### <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。E_FAIL をそれ以外の場合。

##  <a name="displayparentfolder"></a>  CMFCShellListCtrl::DisplayParentFolder

更新プログラム、 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)現在表示されているフォルダーの親フォルダーを表示するオブジェクト。

```
virtual HRESULT DisplayParentFolder();
```

### <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。E_FAIL をそれ以外の場合。

##  <a name="enableshellcontextmenu"></a>  CMFCShellListCtrl::EnableShellContextMenu

ショートカット メニューを有効にします。

```
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
[in]ショートカット メニューをフレームワークが有効かどうかを指定するブール値。

##  <a name="getcurrentfolder"></a>  CMFCShellListCtrl::GetCurrentFolder

現在選択されているフォルダーのパスを取得、 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクト。

```
BOOL GetCurrentFolder(CString& strPath) const;
```

### <a name="parameters"></a>パラメーター

*strPath*<br/>
[out]メソッドを書き込むパス文字列のパラメーターへの参照。

### <a name="return-value"></a>戻り値

成功した場合、0 以外の場合それ以外の場合は 0 です。

### <a name="remarks"></a>Remarks

このメソッドは失敗で選択したフォルダーが存在しない場合、`CMFCShellListCtrl`します。

##  <a name="getcurrentfoldername"></a>  CMFCShellListCtrl::GetCurrentFolderName

現在選択されているフォルダーの名前を取得、 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクト。

```
BOOL GetCurrentFolderName(CString& strName) const;
```

### <a name="parameters"></a>パラメーター

*strName*<br/>
[out]メソッド名の書き込み先の文字列パラメーターへの参照。

### <a name="return-value"></a>戻り値

成功した場合、0 以外の場合それ以外の場合は 0 です。

### <a name="remarks"></a>Remarks

このメソッドは失敗で選択したフォルダーが存在しない場合、`CMFCShellListCtrl`します。

##  <a name="getcurrentitemidlist"></a>  CMFCShellListCtrl::GetCurrentItemIdList

現在選択されている項目の PIDL を返します。

```
LPITEMIDLIST GetCurrentItemIdList() const;
```

### <a name="return-value"></a>戻り値

現在の項目の PIDL します。

##  <a name="getcurrentshellfolder"></a>  CMFCShellListCtrl::GetCurrentShellFolder

現在選択されている項目にポインターを取得、 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクト。

```
const IShellFolder* GetCurrentShellFolder() const;
```

### <a name="return-value"></a>戻り値

ポインター、 [IShellFolder インターフェイス](https://msdn.microsoft.com/library/windows/desktop/bb775075)選択したオブジェクト。

### <a name="remarks"></a>Remarks

オブジェクトが現在選択されていない場合、このメソッドは NULL を返します。

##  <a name="getitempath"></a>  CMFCShellListCtrl::GetItemPath

項目のパスを取得します。

```
BOOL GetItemPath(
    CString& strPath,
    int iItem) const;
```

### <a name="parameters"></a>パラメーター

*strPath*<br/>
[out]パスを受け取る文字列への参照。

*iItem*<br/>
[in]リスト項目のインデックス。

### <a name="return-value"></a>戻り値

成功した場合は TRUE。FALSE それ以外の場合。

### <a name="remarks"></a>Remarks

によって指定されたインデックス*iItem*によって現在表示されている項目に基づいて、 [CMFCShellListCtrl クラス](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクト。

##  <a name="getitemtypes"></a>  CMFCShellListCtrl::GetItemTypes

によって表示される項目の型を返します、 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクト。

```
SHCONTF GetItemTypes() const;
```

### <a name="return-value"></a>戻り値

A [SHCONTF](/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_shcontf)に表示される項目の種類を含む値、`CMFCShellListCtrl`します。

### <a name="remarks"></a>Remarks

表示される項目の種類を設定する、 `CMFCShellListCtrl`、呼び出す[CMFCShellListCtrl::SetItemTypes](#setitemtypes)します。

##  <a name="isdesktop"></a>  CMFCShellListCtrl::IsDesktop

かどうかをフォルダーを表示、 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクトは、デスクトップのフォルダー。

```
BOOL IsDesktop() const;
```

### <a name="return-value"></a>戻り値

表示されるフォルダーはデスクトップ フォルダーは、TRUE を返します。FALSE それ以外の場合。

##  <a name="oncompareitems"></a>  CMFCShellListCtrl::OnCompareItems

詳細についてにあるソース コードを参照してください、 **VC\\atlmfc\\src\\mfc** Visual Studio のインストールのフォルダー。

```
virtual int OnCompareItems(
    LPARAM lParam1,
    LPARAM lParam2,
    int iColumn);
```

### <a name="parameters"></a>パラメーター

*lParam1*<br/>
[in][in]*lParam2* [in] *iColumn*

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="onformatfiledate"></a>  CMFCShellListCtrl::OnFormatFileDate

フレームワークは、文字列オブジェクトに関連付けられている日付を変換する必要がありますと、このメソッドを呼び出します。

```
virtual void OnFormatFileDate(
    const CTime& tmFile,
    CString& str);
```

### <a name="parameters"></a>パラメーター

*tmFile*<br/>
[in]ファイルに関連付けられている日付。

*str*<br/>
[out]書式設定されたファイルの日付を含む文字列。

### <a name="remarks"></a>Remarks

ときに、 [CMFCShellListCtrl クラス](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクトは、ファイルに関連付けられている日付を表示します。、、その日付を文字列形式に変換する必要があります。 `CMFCShellListCtrl`このメソッドを使用して、その変換を行います。 既定では、このメソッドは、現在のロケールを使用して日付の書式設定文字列にします。

##  <a name="onformatfilesize"></a>  CMFCShellListCtrl::OnFormatFileSize

フレームワークは、オブジェクトのサイズを文字列に変換するときに、このメソッドを呼び出します。

```
virtual void OnFormatFileSize(
    long lFileSize,
    CString& str);
```

### <a name="parameters"></a>パラメーター

*lFileSize*<br/>
[in]フレームワークは、表示されるファイルのサイズ。

*str*<br/>
[out]書式設定されたファイルのサイズを含む文字列。

### <a name="remarks"></a>Remarks

ときに、 [CMFCShellListCtrl クラス](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクトは、ファイルのサイズを表示する必要がある、ファイルのサイズを文字列形式に変換する必要があります。 `CMFCShellListCtrl`このメソッドを使用して、その変換を行います。 既定では、このメソッドは、バイトから、ファイルのサイズをキロバイト単位に変換し、サイズの書式設定文字列に現在のロケールを使用します。

##  <a name="ongetitemicon"></a>  CMFCShellListCtrl::OnGetItemIcon

フレームワークは、シェル リスト項目に関連付けられているアイコンを取得するには、このメソッドを呼び出します。

```
virtual int OnGetItemIcon(
    int iItem,
    LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>パラメーター

*iItem*<br/>
[in]項目のインデックス。

*pItem*<br/>
[in]項目を説明する LPAFX_SHELLITEMINFO パラメーター。

### <a name="return-value"></a>戻り値

成功した場合は、アイコン イメージのインデックス関数が失敗した場合は-1。

### <a name="remarks"></a>Remarks

アイコン イメージのインデックスは、システムのイメージ リストに基づきます。

この方法では、既定で、 *pItem*パラメーター。 値*iItem*既定の実装では使用されません。 使用することができます*iItem*カスタム動作を実装します。

##  <a name="ongetitemtext"></a>  CMFCShellListCtrl::OnGetItemText

フレームワークは、シェル項目のテキストを取得する必要がありますと、このメソッドを呼び出します。

```
virtual CString OnGetItemText(
    int iItem,
    int iColumn,
    LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>パラメーター

*iItem*<br/>
[in]項目のインデックス。

*iColumn*<br/>
[in]関心のある列です。

*pItem*<br/>
[in]項目を説明する LPAFX_SHELLITEMINFO パラメーター。

### <a name="return-value"></a>戻り値

A`CString`アイテムに関連付けられているテキストを格納しています。

### <a name="remarks"></a>Remarks

内の各項目、`CMFCShellListCtrl`オブジェクトでは、1 つまたは複数の列にテキストがあります。 フレームワークは、このメソッドを呼び出すときに、対象の列を指定します。 この関数を手動で呼び出す場合に関心がある列を指定する必要もあります。

この方法では、既定で、 *pItem*プロセスに項目を決定するパラメーター。 値*iItem*既定の実装では使用されません。

##  <a name="onsetcolumns"></a>  CMFCShellListCtrl::OnSetColumns

フレームワークは、列の名前を設定するときに、このメソッドを呼び出します。

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>Remarks

既定では、フレームワークが 4 つの列を作成、`CMFCShellListCtrl`オブジェクト。 これらの列の名前は**名前**、**サイズ**、**型**、および**Modified**します。 列およびその名前の数をカスタマイズするには、このメソッドをオーバーライドすることができます。

##  <a name="refresh"></a>  CMFCShellListCtrl::Refresh

更新して再描画、 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクト。

```
virtual HRESULT Refresh();
```

### <a name="return-value"></a>戻り値

`S_OK` 成功した場合それ以外の場合、エラー値。

### <a name="remarks"></a>Remarks

によって表示される項目の一覧を更新するには、このメソッドを呼び出して、`CMFCShellListCtrl`オブジェクト。

##  <a name="setitemtypes"></a>  CMFCShellListCtrl::SetItemTypes

記載されている項目の種類を設定、 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクト。

```
void SetItemTypes(SHCONTF nTypes);
```

### <a name="parameters"></a>パラメーター

*nTypes*<br/>
[in]リスト項目の種類、`CMFCShellListCtrl`サポートしています。

### <a name="remarks"></a>Remarks

項目の種類の一覧については、次を参照してください。 [SHCONTF](/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_shcontf)します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCListCtrl クラス](../../mfc/reference/cmfclistctrl-class.md)<br/>
[CMFCShellTreeCtrl クラス](../../mfc/reference/cmfcshelltreectrl-class.md)
