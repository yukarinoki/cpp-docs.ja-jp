---
title: クラス
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
ms.openlocfilehash: 41d9a14e379c566f001eda8b10b2669b95beb171
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376135"
---
# <a name="cmfcshelltreectrl-class"></a>クラス

この`CMFCShellTreeCtrl`クラスは、シェル項目の階層を表示することによって[CTreeCtrl クラス](../../mfc/reference/ctreectrl-class.md)の機能を拡張します。

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

## <a name="syntax"></a>構文

```
class CMFCShellTreeCtrl : public CTreeCtrl
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[次のコマンドを実行します。](#enableshellcontextmenu)|ショートカット メニューを有効または無効にします。|
|[をクリックします。](#getflags)|に渡されるフラグの組み合わせを返[します](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects)。|
|[をクリックします。](#getitempath)|項目へのパスを取得します。|
|[一覧を参照してください。](#getrelatedlist)|エクスプローラーのようなウィンドウを作成するためにこの`CMFCShellTreeCtrl`オブジェクトと共に使用される[CMFCShellListCtrl クラス](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクトへのポインターを返します。|
|[をクリックします。](#onchildnotify)|このメンバー関数は、このウィンドウに適用される通知メッセージを受け取ると、このウィンドウの親ウィンドウによって呼び出されます。 [(CWnd をオーバーライドします。)](../../mfc/reference/cwnd-class.md#onchildnotify)|
|[をクリックします。](#ongetitemicon)||
|[テキストを取得します。](#ongetitemtext)||
|[をクリックします。](#refresh)|現在`CMFCShellTreeCtrl`のオブジェクトを更新し、再描画します。|
|[を選択します。](#selectpath)|指定された PIDL または文字列パスに基づいて、適切なツリー コントロール項目を選択します。|
|[をクリックします。](#setflags)|ツリー コンテキストをフィルター処理するフラグを設定します (`IShellFolder::EnumObjects`で使用されるフラグに似ています)。|
|[一覧の設定](#setrelatedlist)|現在`CMFCShellTreeCtrl`のオブジェクトとオブジェクトの間の関係`CMFCShellListCtrl`を設定します。|

## <a name="remarks"></a>解説

このクラスは、`CTreeCtrl`プログラムが Windows Shell の項目をツリーに含めることによってクラスを拡張します。 このクラスは、完全なエクスプローラー`CMFCShellListCtrl`ウィンドウを作成するオブジェクトに関連付けることができます。 次に、ツリー内の項目を選択すると、関連付けられたリストに Windows Shell 項目のリストが表示されます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CTreeCtrl](../../mfc/reference/ctreectrl-class.md)

`CMFCShellTreeCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx シェルツリーCtrl.h

## <a name="example"></a>例

次の例では、`CMFCShellTreeCtrl` クラスのオブジェクトを作成する方法を示します。 このコード スニペットは[、エクスプローラーのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_Explorer#4](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_1.h)]
[!code-cpp[NVC_MFC_Explorer#5](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_2.cpp)]

## <a name="cmfcshelltreectrlenableshellcontextmenu"></a><a name="enableshellcontextmenu"></a>次のコマンドを実行します。

ショートカット メニューを有効にします。

```
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]ショートカット メニューを有効にするかどうかを指定するブール値。

## <a name="cmfcshelltreectrlgetflags"></a><a name="getflags"></a>をクリックします。

[クラス](../../mfc/reference/cmfcshelltreectrl-class.md)オブジェクトに設定されているフラグを返します。

```
DWORD GetFlags() const;
```

### <a name="return-value"></a>戻り値

現在設定されているフラグの組み合わせを指定する DWORD 値。

### <a name="remarks"></a>解説

で設定`CMFCShellTreeCtrl`されたフラグは、オブジェクトが更新されるたびにメソッド[IShellFolder::EnumObjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects)に送信されます。 [メソッドを](#setflags)使用してフラグを変更できます。

## <a name="cmfcshelltreectrlgetitempath"></a><a name="getitempath"></a>をクリックします。

[クラス](../../mfc/reference/cmfcshelltreectrl-class.md)オブジェクト内の項目のパスを取得します。

```
BOOL GetItemPath(
    CString& strPath,
    HTREEITEM htreeItem = NULL) const;
```

### <a name="parameters"></a>パラメーター

*ストレパス*<br/>
[アウト]文字列パラメーターへの参照。 このメソッドは、このパラメーターに項目のパスを書き込みます。

*htreeItem*<br/>
[in]このメソッドは、このツリー コントロール項目のパスを取得します。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドが失敗した場合 *、strPath*には空の文字列が含まれます。

*hTreeItem*を指定しない場合、このメソッドは現在選択されている項目の文字列を取得しようとします。 項目が選択されていない場合 *、hTreeItem*が NULL の場合、このメソッドは失敗します。

## <a name="cmfcshelltreectrlgetrelatedlist"></a><a name="getrelatedlist"></a>一覧を参照してください。

このオブジェクトに関連付けられている[クラス](../../mfc/reference/cmfcshelllistctrl-class.md)を指すポインター[を](../../mfc/reference/cmfcshelltreectrl-class.md)返します。

```
CMFCShellListCtrl* GetRelatedList() const;
```

### <a name="return-value"></a>戻り値

このツリー コントロール`CMFCShellListCtrl`オブジェクトに関連付けられているオブジェクトへのポインター。

### <a name="remarks"></a>解説

オブジェクトと共`CMFCShellListCtrl`にオブジェクトを`CMFCShellTreeCtrl`使用すると、エクスプローラのようなウィンドウを作成できます。 2 つのクラスを関連付けるには、メソッド[CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist)を使用します。 これらのオプションが関連付けられた後、フレームワークは`CMFCShellListCtrl`、選択した項目が`CMFCShellTreeCtrl`変更された場合に自動的に更新されます。

## <a name="cmfcshelltreectrlonchildnotify"></a><a name="onchildnotify"></a>をクリックします。

```
virtual BOOL OnChildNotify(
    UINT message,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* pLResult);
```

### <a name="parameters"></a>パラメーター

[in]*メッセージ*<br/>
[in]*wパラム*<br/>
[in]*lパラム*<br/>
[in]*結果*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcshelltreectrlongetitemicon"></a><a name="ongetitemicon"></a>をクリックします。

```
virtual int OnGetItemIcon(
    LPAFX_SHELLITEMINFO pItem,
    BOOL bSelected);
```

### <a name="parameters"></a>パラメーター

[in]*をクリックします。*<br/>
[in]*b選択済み*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcshelltreectrlongetitemtext"></a><a name="ongetitemtext"></a>テキストを取得します。

```
virtual CString OnGetItemText(LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>パラメーター

[in]*をクリックします。*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcshelltreectrlrefresh"></a><a name="refresh"></a>をクリックします。

を更新し、[再描画します](../../mfc/reference/cmfcshelltreectrl-class.md)。

```
void Refresh();
```

### <a name="remarks"></a>解説

に表示される項目の階層を更新`CMFCShellTreeCtrl`します。

## <a name="cmfcshelltreectrlselectpath"></a><a name="selectpath"></a>を選択します。

指定されたパスに基づいて[、CMFCShellTreeCtrl クラス](../../mfc/reference/cmfcshelltreectrl-class.md)内の項目を選択します。

```
BOOL SelectPath(LPCTSTR lpszPath);
BOOL SelectPath(LPCITEMIDLIST lpidl);
```

### <a name="parameters"></a>パラメーター

*パス*<br/>
[in]項目のパスを指定する文字列。

*ルピドル*<br/>
[in]項目を指定する PIDL

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合はE_FAILします。

## <a name="cmfcshelltreectrlsetflags"></a><a name="setflags"></a>をクリックします。

ツリー コンテキストをフィルター処理するフラグを設定します。

```
void SetFlags(
    DWORD dwFlags,
    BOOL bRefresh = TRUE);
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
[in]設定するフラグ。

*bリフレッシュ*<br/>
[in]をすぐに更新するかどうかを指定する`CMFCShellTreeCtrl`ブール値。

### <a name="remarks"></a>解説

すべての`CMFCShellTreeCtrl`設定されたフラグを[IShellFolder::列挙オブジェクトに渡します](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects)。 さまざまなフラグの値の詳細については[、「IShellFolder::列挙オブジェクト](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects)」を参照してください。

## <a name="cmfcshelltreectrlsetrelatedlist"></a><a name="setrelatedlist"></a>一覧の設定

オブジェクトを[オブジェクト](../../mfc/reference/cmfcshelllistctrl-class.md)[に関連](../../mfc/reference/cmfcshelltreectrl-class.md)付けます。

```
void SetRelatedList(CMFCShellListCtrl* pShellList);
```

### <a name="parameters"></a>パラメーター

*一覧*<br/>
[in]`CMFCShellListCtrl`オブジェクトへのポインター。

### <a name="remarks"></a>解説

このメソッドは、`CMFCShellListCtrl`を`CMFCShellTreeCtrl`に関連付けます。 これらのオブジェクトは、Explorer のようなウィンドウとして表示される場合があります。 `CMFCShellTreeCtrl` `CMFCShellListCtrl`

メソッドを使用して[、に](#getrelatedlist)関連付けられているを`CMFCShellListCtrl`取得します。 `CMFCShellTreeCtrl`

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CTreeCtrl クラス](../../mfc/reference/ctreectrl-class.md)<br/>
[クラス](../../mfc/reference/cmfcshelllistctrl-class.md)
