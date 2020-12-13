---
description: '詳細情報: CMFCShellTreeCtrl クラス'
title: CMFCShellTreeCtrl クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCShellTreeCtrl
- AFXSHELLTREECTRL/CMFCShellTreeCtrl
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::EnableShellContextMenu
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetFlags
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetItemPath
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetRelatedList
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnChildNotify
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnGetItemIcon
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnGetItemText
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::Refresh
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SelectPath
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SetFlags
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SetRelatedList
helpviewer_keywords:
- CMFCShellTreeCtrl [MFC], EnableShellContextMenu
- CMFCShellTreeCtrl [MFC], GetFlags
- CMFCShellTreeCtrl [MFC], GetItemPath
- CMFCShellTreeCtrl [MFC], GetRelatedList
- CMFCShellTreeCtrl [MFC], OnChildNotify
- CMFCShellTreeCtrl [MFC], OnGetItemIcon
- CMFCShellTreeCtrl [MFC], OnGetItemText
- CMFCShellTreeCtrl [MFC], Refresh
- CMFCShellTreeCtrl [MFC], SelectPath
- CMFCShellTreeCtrl [MFC], SetFlags
- CMFCShellTreeCtrl [MFC], SetRelatedList
ms.assetid: 3d1da715-9554-4ed7-968c-055c48146267
ms.openlocfilehash: 86b18d1cb919eaa36c3aed0d6e1623bab530a0aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339671"
---
# <a name="cmfcshelltreectrl-class"></a>CMFCShellTreeCtrl クラス

クラスは、 `CMFCShellTreeCtrl` シェル項目の階層を表示することによって、 [CTreeCtrl クラス](../../mfc/reference/ctreectrl-class.md) の機能を拡張します。

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

## <a name="syntax"></a>構文

```
class CMFCShellTreeCtrl : public CTreeCtrl
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCShellTreeCtrl:: EnableShellContextMenu](#enableshellcontextmenu)|ショートカットメニューを有効または無効にします。|
|[CMFCShellTreeCtrl:: GetFlags](#getflags)|[Ishellfolder:: EnumObjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects)に渡されるフラグの組み合わせを返します。|
|[CMFCShellTreeCtrl:: GetItemPath](#getitempath)|項目へのパスを取得します。|
|[CMFCShellTreeCtrl:: Get List](#getrelatedlist)|このオブジェクトと共に使用して、エクスプローラーのようなウィンドウを作成するために使用される [Cmfcshelllistctrl クラス](../../mfc/reference/cmfcshelllistctrl-class.md) オブジェクトへのポインターを返し `CMFCShellTreeCtrl` ます。|
|[CMFCShellTreeCtrl:: OnChildNotify](#onchildnotify)|このメンバー関数は、このウィンドウに適用される通知メッセージを受信すると、このウィンドウの親ウィンドウによって呼び出されます。 ( [CWnd:: OnChildNotify](../../mfc/reference/cwnd-class.md#onchildnotify)をオーバーライドします)。|
|[CMFCShellTreeCtrl:: OnGetItemIcon](#ongetitemicon)||
|[CMFCShellTreeCtrl:: OnGetItemText](#ongetitemtext)||
|[CMFCShellTreeCtrl:: Refresh](#refresh)|現在のオブジェクトを更新し、再描画し `CMFCShellTreeCtrl` ます。|
|[CMFCShellTreeCtrl:: SelectPath](#selectpath)|指定された PIDL または文字列パスに基づいて、適切なツリーコントロール項目を選択します。|
|[CMFCShellTreeCtrl:: SetFlags](#setflags)|ツリーコンテキストをフィルター処理するためのフラグを設定します (で使用されるフラグに似て `IShellFolder::EnumObjects` います)。|
|[CMFCShellTreeCtrl:: Set List](#setrelatedlist)|現在のオブジェクトとオブジェクトの間のリレーションシップを設定し `CMFCShellTreeCtrl` `CMFCShellListCtrl` ます。|

## <a name="remarks"></a>解説

このクラスは、 `CTreeCtrl` プログラムがツリーに Windows シェル項目を含めることができるようにすることでクラスを拡張します。 このクラスは、 `CMFCShellListCtrl` すべてのエクスプローラーウィンドウを作成するために、オブジェクトに関連付けることができます。 次に、ツリー内の項目を選択すると、関連付けられている一覧に Windows シェル項目の一覧が表示されます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CTreeCtrl](../../mfc/reference/ctreectrl-class.md)

`CMFCShellTreeCtrl`

## <a name="requirements"></a>要件

**ヘッダー:** afxshelltreeCtrl

## <a name="example"></a>例

次の例では、`CMFCShellTreeCtrl` クラスのオブジェクトを作成する方法を示します。 このコードスニペットは、エクスプローラーの [サンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_Explorer#4](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_1.h)]
[!code-cpp[NVC_MFC_Explorer#5](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_2.cpp)]

## <a name="cmfcshelltreectrlenableshellcontextmenu"></a><a name="enableshellcontextmenu"></a> CMFCShellTreeCtrl:: EnableShellContextMenu

ショートカットメニューを有効にします。

```cpp
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
からショートカットメニューを有効にするかどうかを指定するブール値。

## <a name="cmfcshelltreectrlgetflags"></a><a name="getflags"></a> CMFCShellTreeCtrl:: GetFlags

[CMFCShellTreeCtrl クラス](../../mfc/reference/cmfcshelltreectrl-class.md)オブジェクトに設定されたフラグを返します。

```
DWORD GetFlags() const;
```

### <a name="return-value"></a>戻り値

現在設定されているフラグの組み合わせを指定する DWORD 値。

### <a name="remarks"></a>解説

で設定されたフラグは、 `CMFCShellTreeCtrl` オブジェクトが更新されるたびに [Ishellfolder:: EnumObjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects) メソッドに送信されます。 フラグは、 [CMFCShellTreeCtrl:: SetFlags](#setflags) メソッドを使用して変更できます。

## <a name="cmfcshelltreectrlgetitempath"></a><a name="getitempath"></a> CMFCShellTreeCtrl:: GetItemPath

[CMFCShellTreeCtrl Class](../../mfc/reference/cmfcshelltreectrl-class.md)オブジェクト内の項目のパスを取得します。

```
BOOL GetItemPath(
    CString& strPath,
    HTREEITEM htreeItem = NULL) const;
```

### <a name="parameters"></a>パラメーター

*strPath*<br/>
入出力文字列パラメーターへの参照。 メソッドは、このパラメーターに項目のパスを書き込みます。

*htreeItem*<br/>
からメソッドは、このツリーコントロール項目のパスを取得します。

### <a name="return-value"></a>戻り値

成功した場合は0以外の。それ以外の場合は0。

### <a name="remarks"></a>解説

このメソッドが失敗した場合、 *strPath* には空の文字列が含まれます。

*HTreeItem* を指定しない場合、このメソッドは現在選択されている項目の文字列を取得しようとします。 項目が選択されておらず、 *hTreeItem* が NULL の場合、このメソッドは失敗します。

## <a name="cmfcshelltreectrlgetrelatedlist"></a><a name="getrelatedlist"></a> CMFCShellTreeCtrl:: Get List

この[CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)オブジェクトに関連付けられている[Cmfcshelllistctrl クラス](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクトへのポインターを返します。

```
CMFCShellListCtrl* GetRelatedList() const;
```

### <a name="return-value"></a>戻り値

`CMFCShellListCtrl`このツリーコントロールオブジェクトに関連付けられているオブジェクトへのポインター。

### <a name="remarks"></a>解説

オブジェクトを `CMFCShellListCtrl` オブジェクトと共に使用 `CMFCShellTreeCtrl` すると、エクスプローラーのようなウィンドウを作成できます。 2つのクラスを関連付けるには、 [CMFCShellTreeCtrl:: Set関連付けリスト](#setrelatedlist) メソッドを使用します。 これらが関連付けられると、の選択範囲が変更されると、フレームワークによってが自動的に更新され `CMFCShellListCtrl` `CMFCShellTreeCtrl` ます。

## <a name="cmfcshelltreectrlonchildnotify"></a><a name="onchildnotify"></a> CMFCShellTreeCtrl:: OnChildNotify

```
virtual BOOL OnChildNotify(
    UINT message,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* pLResult);
```

### <a name="parameters"></a>パラメーター

から *メッセージ*<br/>
から *wParam*<br/>
から *lParam*<br/>
から *Plresult*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcshelltreectrlongetitemicon"></a><a name="ongetitemicon"></a> CMFCShellTreeCtrl:: OnGetItemIcon

```
virtual int OnGetItemIcon(
    LPAFX_SHELLITEMINFO pItem,
    BOOL bSelected);
```

### <a name="parameters"></a>パラメーター

から *pItem*<br/>
から *選択された bselected*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcshelltreectrlongetitemtext"></a><a name="ongetitemtext"></a> CMFCShellTreeCtrl:: OnGetItemText

```
virtual CString OnGetItemText(LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>パラメーター

から *pItem*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcshelltreectrlrefresh"></a><a name="refresh"></a> CMFCShellTreeCtrl:: Refresh

[CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)を更新し、再描画します。

```cpp
void Refresh();
```

### <a name="remarks"></a>解説

に表示される項目の階層を更新するには、このメソッドを呼び出し `CMFCShellTreeCtrl` ます。

## <a name="cmfcshelltreectrlselectpath"></a><a name="selectpath"></a> CMFCShellTreeCtrl:: SelectPath

指定されたパスに基づいて、 [CMFCShellTreeCtrl クラス](../../mfc/reference/cmfcshelltreectrl-class.md) の項目を選択します。

```
BOOL SelectPath(LPCTSTR lpszPath);
BOOL SelectPath(LPCITEMIDLIST lpidl);
```

### <a name="parameters"></a>パラメーター

*lpszPath*<br/>
から項目のパスを指定する文字列。

*lpidl*<br/>
から項目を指定する PIDL

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は E_FAIL。

## <a name="cmfcshelltreectrlsetflags"></a><a name="setflags"></a> CMFCShellTreeCtrl:: SetFlags

ツリーコンテキストをフィルター処理するためのフラグを設定します。

```cpp
void SetFlags(
    DWORD dwFlags,
    BOOL bRefresh = TRUE);
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
から設定するフラグ。

*bRefresh*<br/>
からをすぐに更新するかどうかを指定するブール値 `CMFCShellTreeCtrl`  。

### <a name="remarks"></a>解説

は、 `CMFCShellTreeCtrl` すべての set フラグを [Ishellfolder:: EnumObjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects)に渡します。 異なるフラグの値の詳細については、「 [Ishellfolder:: EnumObjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects)」を参照してください。

## <a name="cmfcshelltreectrlsetrelatedlist"></a><a name="setrelatedlist"></a> CMFCShellTreeCtrl:: Set List

[Cmfcshelllistctrl](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクトを[CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)オブジェクトに関連付けます。

```cpp
void SetRelatedList(CMFCShellListCtrl* pShellList);
```

### <a name="parameters"></a>パラメーター

*pShellList*<br/>
からオブジェクトへのポインター `CMFCShellListCtrl` 。

### <a name="remarks"></a>解説

このメソッドは、をに関連付け `CMFCShellListCtrl` `CMFCShellTreeCtrl` ます。 これらのオブジェクトは、エクスプローラーのようなウィンドウとして表示される場合があります。ユーザーがでオブジェクトを選択すると、 `CMFCShellTreeCtrl` 内の関連する項目が `CMFCShellListCtrl` 自動的に更新されます。

メソッド [CMFCShellTreeCtrl:: Get関連付けリスト](#getrelatedlist) を使用して、 `CMFCShellListCtrl` に関連付けられているを取得 `CMFCShellTreeCtrl` します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CTreeCtrl クラス](../../mfc/reference/ctreectrl-class.md)<br/>
[CMFCShellListCtrl クラス](../../mfc/reference/cmfcshelllistctrl-class.md)
