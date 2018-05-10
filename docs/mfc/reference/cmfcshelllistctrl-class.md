---
title: CMFCShellListCtrl クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 9073c3443b1c74a27c9de9be142c67fab7f40ba8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcshelllistctrl-class"></a>CMFCShellListCtrl クラス
`CMFCShellListCtrl`クラスは、Windows のリスト コントロールの機能を提供し、シェル項目の一覧を表示する機能などを展開します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCShellListCtrl : public CMFCListCtrl  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCShellListCtrl::DisplayFolder](#displayfolder)|指定されたフォルダーに含まれているアイテムの一覧を表示します。|  
|[CMFCShellListCtrl::DisplayParentFolder](#displayparentfolder)|現在表示されているフォルダーの親であるフォルダーに含まれているアイテムの一覧を表示します。|  
|[CMFCShellListCtrl::EnableShellContextMenu](#enableshellcontextmenu)|有効またはショートカット メニューを無効にします。|  
|[CMFCShellListCtrl::GetCurrentFolder](#getcurrentfolder)|現在のフォルダーのパスを取得します。|  
|[CMFCShellListCtrl::GetCurrentFolderName](#getcurrentfoldername)|現在のフォルダーの名前を取得します。|  
|[CMFCShellListCtrl::GetCurrentItemIdList](#getcurrentitemidlist)|現在のリスト コントロール項目の PIDL を返します。|  
|[CMFCShellListCtrl::GetCurrentShellFolder](#getcurrentshellfolder)|現在のシェル フォルダーへのポインターを返します。|  
|[CMFCShellListCtrl::GetItemPath](#getitempath)|アイテムのパスのテキスト表現を返します。|  
|[CMFCShellListCtrl::GetItemTypes](#getitemtypes)|リスト コントロールによって表示される、シェル項目の種類を返します。|  
|[CMFCShellListCtrl::IsDesktop](#isdesktop)|現在選択されているフォルダーのデスクトップのフォルダーを確認します。|  
|[CMFCShellListCtrl::OnCompareItems](#oncompareitems)|フレームワークは、2 つの項目を比較するときに、このメソッドを呼び出します。 (上書き[CMFCListCtrl::OnCompareItems](../../mfc/reference/cmfclistctrl-class.md#oncompareitems))。|  
|[CMFCShellListCtrl::OnFormatFileDate](#onformatfiledate)|フレームワークは、リスト コントロールによって表示されるファイルの日付を取得するときに呼び出されます。|  
|[CMFCShellListCtrl::OnFormatFileSize](#onformatfilesize)|フレームワーク リスト コントロールのファイル サイズを変換するときに呼び出されます。|  
|[CMFCShellListCtrl::OnGetItemIcon](#ongetitemicon)|フレームワーク リスト コントロール項目のアイコンを取得するときに呼び出されます。|  
|[CMFCShellListCtrl::OnGetItemText](#ongetitemtext)|フレームワーク リスト コントロール項目のテキストを変換するときに呼び出されます。|  
|[CMFCShellListCtrl::OnSetColumns](#onsetcolumns)|列の名前を設定するときに、フレームワークによって呼び出されます。|  
|[CMFCShellListCtrl::Refresh](#refresh)|更新して、リスト コントロールを再描画します。|  
|[CMFCShellListCtrl::SetItemTypes](#setitemtypes)|リスト コントロールによって表示される項目の種類を設定します。|  
  
## <a name="remarks"></a>コメント  
 `CMFCShellListCtrl`クラスの機能を拡張する、 [CMFCListCtrl クラス](../../mfc/reference/cmfclistctrl-class.md)Windows シェル項目の一覧にプログラムを有効にするとします。 使用される表示形式は、エクスプ ローラー ウィンドウのリスト ビューに似ています。  
  
 A [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)オブジェクトが関連付けられることができます、`CMFCShellListCtrl`完了エクスプ ローラー ウィンドウを作成するオブジェクト。 内の項目を選択し、`CMFCShellTreeCtrl`により、`CMFCShellListCtrl`オブジェクトを選択した項目の内容を一覧表示します。  
  
## <a name="example"></a>例  
 次の例でのオブジェクトを作成する方法、`CMFCShellListCtrl`クラスと、現在表示されているフォルダーの親フォルダーを表示する方法です。 このコード スニペットの一部である、[エクスプ ローラー サンプル](../../visual-cpp-samples.md)です。  
  
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
 指定されたフォルダーに含まれているアイテムの一覧を表示します。  
  
```  
virtual HRESULT DisplayFolder(LPCTSTR lpszPath);
virtual HRESULT DisplayFolder(LPAFX_SHELLITEMINFO lpItemInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszPath`  
 フォルダーのパスを含む文字列です。  
  
 [入力] `lpItemInfo`  
 ポインター、`LPAFX_SHELLITEMINFO`を表示するフォルダーを記述する構造体。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` 成功した場合`E_FAIL`それ以外の場合。  
  
##  <a name="displayparentfolder"></a>  CMFCShellListCtrl::DisplayParentFolder  
 更新プログラム、 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)現在表示されているフォルダーの親フォルダーを表示するオブジェクト。  
  
```  
virtual HRESULT DisplayParentFolder();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` 成功した場合`E_FAIL`それ以外の場合。  
  
##  <a name="enableshellcontextmenu"></a>  CMFCShellListCtrl::EnableShellContextMenu  
 ショートカット メニューを有効にします。  
  
```  
void EnableShellContextMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 ショートカット メニューをフレームワークが有効かどうかを指定するブール値。  
  
##  <a name="getcurrentfolder"></a>  CMFCShellListCtrl::GetCurrentFolder  
 現在選択されているフォルダーのパスを取得、 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクト。  
  
```  
BOOL GetCurrentFolder(CString& strPath) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `strPath`  
 メソッドが、パスを書き込む文字列パラメーターへの参照。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは失敗で選択したフォルダーが存在しない場合、`CMFCShellListCtrl`です。  
  
##  <a name="getcurrentfoldername"></a>  CMFCShellListCtrl::GetCurrentFolderName  
 現在選択されているフォルダーの名前を取得、 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクト。  
  
```  
BOOL GetCurrentFolderName(CString& strName) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `strName`  
 メソッド名の書き込み先の文字列パラメーターへの参照。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは失敗で選択したフォルダーが存在しない場合、`CMFCShellListCtrl`です。  
  
##  <a name="getcurrentitemidlist"></a>  CMFCShellListCtrl::GetCurrentItemIdList  
 現在選択されている項目の PIDL を返します。  
  
```  
LPITEMIDLIST GetCurrentItemIdList() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のアイテムの PIDL です。  
  
##  <a name="getcurrentshellfolder"></a>  CMFCShellListCtrl::GetCurrentShellFolder  
 現在選択されている項目へのポインターを取得、 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクト。  
  
```  
const IShellFolder* GetCurrentShellFolder() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [IShellFolder インターフェイス](http://msdn.microsoft.com/library/windows/desktop/bb775075)選択したオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメソッドが戻る`NULL`オブジェクトが現在選択されていない場合。  
  
##  <a name="getitempath"></a>  CMFCShellListCtrl::GetItemPath  
 項目のパスを取得します。  
  
```  
BOOL GetItemPath(
    CString& strPath,  
    int iItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `strPath`  
 パスを受け取る文字列への参照。  
  
 [入力] `iItem`  
 リスト項目のインデックス。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 成功した場合`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 指定したインデックス`iItem`で現在表示されている項目に基づくが、 [CMFCShellListCtrl クラス](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクト。  
  
##  <a name="getitemtypes"></a>  CMFCShellListCtrl::GetItemTypes  
 によって表示される項目の種類を返します、 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクト。  
  
```  
SHCONTF GetItemTypes() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [SHCONTF](http://msdn.microsoft.com/library/windows/desktop/bb762539)に表示される項目の種類を表す値、`CMFCShellListCtrl`です。  
  
### <a name="remarks"></a>コメント  
 表示される項目の種類を設定する、 `CMFCShellListCtrl`、呼び出す[CMFCShellListCtrl::SetItemTypes](#setitemtypes)です。  
  
##  <a name="isdesktop"></a>  CMFCShellListCtrl::IsDesktop  
 かどうかをフォルダーをで表示される、 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクトは、デスクトップ フォルダーです。  
  
```  
BOOL IsDesktop() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、表示されているフォルダーは、デスクトップ フォルダーです。`FALSE`それ以外の場合。  
  
##  <a name="oncompareitems"></a>  CMFCShellListCtrl::OnCompareItems  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int OnCompareItems(
    LPARAM lParam1,  
    LPARAM lParam2,  
    int iColumn);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lParam1`  
 [入力] `lParam2`  
 [入力] `iColumn`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onformatfiledate"></a>  CMFCShellListCtrl::OnFormatFileDate  
 フレームワークは、文字列オブジェクトに関連付けられている日付を変換する必要がありますと、このメソッドを呼び出します。  
  
```  
virtual void OnFormatFileDate(
    const CTime& tmFile,  
    CString& str);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `tmFile`  
 ファイルに関連付けられた日付。  
  
 [出力] `str`  
 書式設定されたファイルの日付を表す文字列。  
  
### <a name="remarks"></a>コメント  
 ときに、 [CMFCShellListCtrl クラス](../../mfc/reference/cmfcshelllistctrl-class.md)その日付を文字列形式を変換する必要があります、オブジェクトには、ファイルに関連付けられた日付が表示されます。 `CMFCShellListCtrl`このメソッドを使用してその変換を行います。 既定では、このメソッドを文字列に日付の形式を現在のロケールを使用します。  
  
##  <a name="onformatfilesize"></a>  CMFCShellListCtrl::OnFormatFileSize  
 フレームワークは、オブジェクトのサイズを文字列に変換するときに、このメソッドを呼び出します。  
  
```  
virtual void OnFormatFileSize(
    long lFileSize,  
    CString& str);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lFileSize`  
 フレームワークは、表示されるファイルのサイズ。  
  
 [出力] `str`  
 書式設定されたファイルのサイズを表す文字列。  
  
### <a name="remarks"></a>コメント  
 ときに、 [CMFCShellListCtrl クラス](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクトは、ファイルのサイズを表示する必要がある、ファイルのサイズを文字列の形式に変換する必要があります。 `CMFCShellListCtrl`このメソッドを使用してその変換を行います。 既定では、このメソッドはバイトからファイルのサイズをキロバイト単位に変換し、サイズを文字列に書式設定を現在のロケールを使用しています。  
  
##  <a name="ongetitemicon"></a>  CMFCShellListCtrl::OnGetItemIcon  
 フレームワークは、シェル リスト項目に関連付けられたアイコンを取得するには、このメソッドを呼び出します。  
  
```  
virtual int OnGetItemIcon(
    int iItem,  
    LPAFX_SHELLITEMINFO pItem);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iItem`  
 項目のインデックス。  
  
 [入力] `pItem`  
 A`LPAFX_SHELLITEMINFO`アイテムを説明するパラメーターです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、アイコン イメージのインデックス関数が失敗した場合は-1。  
  
### <a name="remarks"></a>コメント  
 アイコン イメージのインデックスは、システムのイメージ リストに基づきます。  
  
 既定では、このメソッドは、`pItem`パラメーター。 値`iItem`既定の実装では使用されません。 使用することができます`iItem`カスタム動作を実装します。  
  
##  <a name="ongetitemtext"></a>  CMFCShellListCtrl::OnGetItemText  
 フレームワークは、シェル項目のテキストを取得する必要があるときに、このメソッドを呼び出します。  
  
```  
virtual CString OnGetItemText(
    int iItem,  
    int iColumn,  
    LPAFX_SHELLITEMINFO pItem);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iItem`  
 項目のインデックス。  
  
 [入力] `iColumn`  
 関心のある列です。  
  
 [入力] `pItem`  
 A`LPAFX_SHELLITEMINFO`アイテムを説明するパラメーターです。  
  
### <a name="return-value"></a>戻り値  
 A`CString`アイテムに関連付けられているテキストを格納しています。  
  
### <a name="remarks"></a>コメント  
 内の各項目、`CMFCShellListCtrl`オブジェクトでは、1 つまたは複数の列にテキストがあります。 フレームワークは、このメソッドを呼び出すときに、対象の列を指定します。 この関数を手動で呼び出す場合も、興味のある列を指定する必要があります。  
  
 既定では、このメソッドは、`pItem`パラメーターをプロセスに項目を決定します。 値`iItem`既定の実装では使用されません。  
  
##  <a name="onsetcolumns"></a>  CMFCShellListCtrl::OnSetColumns  
 フレームワークは、列の名前を設定するときに、このメソッドを呼び出します。  
  
```  
virtual void OnSetColumns();
```  
  
### <a name="remarks"></a>コメント  
 既定では、フレームワークがで 4 つの列を作成、`CMFCShellListCtrl`オブジェクト。 これらの列の名前は`Name`、 `Size`、 `Type`、および`Modified`です。 列とその名前の数をカスタマイズするには、このメソッドをオーバーライドすることができます。  
  
##  <a name="refresh"></a>  CMFCShellListCtrl::Refresh  
 更新して再描画、 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクト。  
  
```  
virtual HRESULT Refresh();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` 成功した場合それ以外の場合、エラー値。  
  
### <a name="remarks"></a>コメント  
 によって表示される項目の一覧を更新するには、このメソッドを呼び出して、`CMFCShellListCtrl`オブジェクト。  
  
##  <a name="setitemtypes"></a>  CMFCShellListCtrl::SetItemTypes  
 示されている項目の種類を設定、 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクト。  
  
```  
void SetItemTypes(SHCONTF nTypes);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nTypes`  
 項目のリストの種類を`CMFCShellListCtrl`サポートしています。  
  
### <a name="remarks"></a>コメント  
 項目の種類の一覧に関する詳細については、次を参照してください。 [SHCONTF](http://msdn.microsoft.com/library/windows/desktop/bb762539)です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCListCtrl クラス](../../mfc/reference/cmfclistctrl-class.md)   
 [CMFCShellTreeCtrl クラス](../../mfc/reference/cmfcshelltreectrl-class.md)
