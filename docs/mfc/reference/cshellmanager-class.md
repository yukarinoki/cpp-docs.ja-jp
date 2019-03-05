---
title: CShellManager クラス
ms.date: 11/04/2016
f1_keywords:
- CShellManager
- AFXSHELLMANAGER/CShellManager
- AFXSHELLMANAGER/CShellManager::CShellManager
- AFXSHELLMANAGER/CShellManager::BrowseForFolder
- AFXSHELLMANAGER/CShellManager::ConcatenateItem
- AFXSHELLMANAGER/CShellManager::CopyItem
- AFXSHELLMANAGER/CShellManager::CreateItem
- AFXSHELLMANAGER/CShellManager::FreeItem
- AFXSHELLMANAGER/CShellManager::GetItemCount
- AFXSHELLMANAGER/CShellManager::GetItemSize
- AFXSHELLMANAGER/CShellManager::GetNextItem
- AFXSHELLMANAGER/CShellManager::GetParentItem
- AFXSHELLMANAGER/CShellManager::ItemFromPath
helpviewer_keywords:
- CShellManager [MFC], CShellManager
- CShellManager [MFC], BrowseForFolder
- CShellManager [MFC], ConcatenateItem
- CShellManager [MFC], CopyItem
- CShellManager [MFC], CreateItem
- CShellManager [MFC], FreeItem
- CShellManager [MFC], GetItemCount
- CShellManager [MFC], GetItemSize
- CShellManager [MFC], GetNextItem
- CShellManager [MFC], GetParentItem
- CShellManager [MFC], ItemFromPath
ms.assetid: f15c4c1a-6fae-487d-9913-9b7369b33da0
ms.openlocfilehash: 3f58492c6adbb6c183d6498e4a58f3ce639d7d18
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57269384"
---
# <a name="cshellmanager-class"></a>CShellManager クラス

ID リストへのポインター (PIDL) を操作するためのさまざまなメソッドを実装します。

## <a name="syntax"></a>構文

```
class CShellManager : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CShellManager::CShellManager](#cshellmanager)|`CShellManager` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CShellManager::BrowseForFolder](#browseforfolder)|ユーザーがシェル フォルダーを選択できるダイアログ ボックスが表示されます。|
|[CShellManager::ConcatenateItem](#concatenateitem)|2 つの Pidl を連結します。|
|[CShellManager::CopyItem](#copyitem)|新しい PIDL を作成し、指定した PIDL をコピーします。|
|[CShellManager::CreateItem](#createitem)|指定したサイズの新しい PIDL を作成します。|
|[CShellManager::FreeItem](#freeitem)|指定した PIDL を削除します。|
|[CShellManager::GetItemCount](#getitemcount)|指定した PIDL で項目の数を返します。|
|[CShellManager::GetItemSize](#getitemsize)|指定した PIDL のサイズを返します。|
|[CShellManager::GetNextItem](#getnextitem)|PIDL から次の項目を返します。|
|[CShellManager::GetParentItem](#getparentitem)|指定された項目の親項目を取得します。|
|[CShellManager::ItemFromPath](#itemfrompath)|指定されたパスで識別される項目の PIDL を取得します。|

## <a name="remarks"></a>Remarks

メソッド、`CShellManager`クラス Pidl をすべて処理します。 PIDL は、shell オブジェクトの一意の識別子です。

作成しないようにする、`CShellManager`手動でのオブジェクトします。 アプリケーションのフレームワークによって自動的に作成されます。 ただし、呼び出す必要があります[CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager)アプリケーションの初期化プロセス中にします。 アプリケーションのシェル マネージャーへのポインターを取得する[CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CShellManager](../../mfc/reference/cshellmanager-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxshellmanager.h

##  <a name="browseforfolder"></a>  CShellManager::BrowseForFolder

ユーザーがシェル フォルダーを選択できるダイアログ ボックスが表示されます。

```
BOOL BrowseForFolder(
    CString& strOutFolder,
    CWnd* pWndParent = NULL,
    LPCTSTR lplszInitialFolder = NULL,
    LPCTSTR lpszTitle = NULL,
    UINT ulFlags = BIF_RETURNONLYFSDIRS,
    LPINT piFolderImage = NULL);
```

### <a name="parameters"></a>パラメーター

*strOutFolder*<br/>
[out]選択したフォルダーのパスを格納するメソッドによって使用される文字列。

*pWndParent*<br/>
[in]親ウィンドウへのポインター。

*lplszInitialFolder*<br/>
[in]ダイアログ ボックスが表示されるときに、既定で選択されているフォルダーを含む文字列。

*lpszTitle*<br/>
[in]ダイアログ ボックスのタイトル。

*ulFlags*<br/>
[in]ダイアログ ボックスのオプションを指定するフラグ。 参照してください[BROWSEINFO](/windows/desktop/api/shlobj_core/ns-shlobj_core-_browseinfoa)詳細説明します。

*piFolderImage*<br/>
[out]メソッドが選択したフォルダーのイメージのインデックスを書き込む整数値へのポインター。

### <a name="return-value"></a>戻り値

ユーザーがダイアログ ボックスからフォルダーを選択した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

このメソッドを呼び出すときに、アプリケーションは作成し、ユーザーがフォルダーを選択できるダイアログ ボックスが表示されます。 メソッドは、フォルダーのパスを記述、 *strOutFolder*パラメーター。

### <a name="example"></a>例

次の例への参照を取得する方法を示します、`CShellManager`オブジェクトを使用して、`CWinAppEx::GetShellManager`メソッドを使用する方法、`BrowseForFolder`メソッド。 このコード スニペットの一部、 [Explorer サンプル](../../visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_Explorer#6](../../mfc/reference/codesnippet/cpp/cshellmanager-class_1.cpp)]

##  <a name="concatenateitem"></a>  CShellManager::ConcatenateItem

2 つの Pidl を含む新しいリストを作成します。

```
LPITEMIDLIST ConcatenateItem(
    LPCITEMIDLIST pidl1,
    LPCITEMIDLIST pidl2);
```

### <a name="parameters"></a>パラメーター

*pidl1*<br/>
[in]最初の項目。

*pidl2*<br/>
[in]2 番目の項目。

### <a name="return-value"></a>戻り値

それ以外の場合、関数が成功した場合は、新しい項目リストへのポインターが NULL です。

### <a name="remarks"></a>Remarks

このメソッドは、新しい作成[ITEMIDLIST](/windows/desktop/api/shtypes/ns-shtypes-_itemidlist)両方を格納するのに十分な大きさ*pidl1*と*pidl2*します。 コピーし、 *pidl1*と*pidl2*新しいリストにします。

##  <a name="copyitem"></a>  CShellManager::CopyItem

項目のリストをコピーします。

```
LPITEMIDLIST CopyItem(LPCITEMIDLIST pidlSource);
```

### <a name="parameters"></a>パラメーター

*pidlSource*<br/>
[in]元の項目のリスト。

### <a name="return-value"></a>戻り値

成功した場合は、新しく作成された項目リストへのポインターそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

新しく作成された項目の一覧が、元の項目リストと同じサイズです。

##  <a name="createitem"></a>  CShellManager::CreateItem

新しい PIDL を作成します。

```
LPITEMIDLIST CreateItem(UINT cbSize);
```

### <a name="parameters"></a>パラメーター

*cbSize*<br/>
[in]項目リストのサイズ。

### <a name="return-value"></a>戻り値

成功した場合は、作成された項目リストへのポインターそれ以外の場合は NULL です。

##  <a name="cshellmanager"></a>  CShellManager::CShellManager

`CShellManager` オブジェクトを構築します。

```
CShellManager();
```

### <a name="remarks"></a>Remarks

ほとんどの場合は作成する必要はありません、`CShellManager`直接します。 既定では、フレームワークの 1 つを作成します。 ポインターを取得する、 `CShellManager`、呼び出す[CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager)します。 作成する場合は、 `CShellManager` 、手動でメソッドを使用して初期化する必要があります[CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager)します。

##  <a name="freeitem"></a>  CShellManager::FreeItem

項目のリストを削除します。

```
void FreeItem(LPITEMIDLIST pidl);
```

### <a name="parameters"></a>パラメーター

*pidl*<br/>
[in]削除する項目のリスト。

##  <a name="getitemcount"></a>  CShellManager::GetItemCount

項目のリストで項目の数を返します。

```
UINT GetItemCount(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>パラメーター

*pidl*<br/>
[in]項目のリストへのポインター。

### <a name="return-value"></a>戻り値

項目リスト内の項目の数。

##  <a name="getitemsize"></a>  CShellManager::GetItemSize

項目一覧のサイズを返します。

```
UINT GetItemSize(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>パラメーター

*pidl*<br/>
[in]項目のリストへのポインター。

### <a name="return-value"></a>戻り値

項目リストのサイズ。

##  <a name="getnextitem"></a>  CShellManager::GetNextItem

項目識別子一覧 (PIDL) へのポインターから次の項目を取得します。

```
LPITEMIDLIST GetNextItem(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>パラメーター

*pidl*<br/>
[in]反復処理する項目の一覧。

### <a name="return-value"></a>戻り値

一覧の次の項目へのポインター。

### <a name="remarks"></a>Remarks

一覧にこれ以上項目がある場合、このメソッドは NULL を返します。

##  <a name="getparentitem"></a>  CShellManager::GetParentItem

項目識別子の一覧 (PIDL) へのポインターの親を取得します。

```
int GetParentItem(
    LPCITEMIDLIST lpidl,
    LPITEMIDLIST& lpidlParent);
```

### <a name="parameters"></a>パラメーター

*lpidl*<br/>
[in]親を取得する PIDL します。

*lpidlParent*<br/>
[out]PIDL メソッドが結果を格納する場所への参照。

### <a name="return-value"></a>戻り値

PIDL 親のレベルです。

### <a name="remarks"></a>Remarks

デスクトップに対する相対パス PIDL のレベルです。 デスクトップ PIDL レベル 0 と見なされます。

##  <a name="itemfrompath"></a>  CShellManager::ItemFromPath

文字列のパスで識別される項目から項目識別子リスト (PIDL) にポインターを取得します。

```
HRESULT ItemFromPath(
    LPCTSTR lpszPath,
    LPITEMIDLIST& pidl);
```

### <a name="parameters"></a>パラメーター

*lpszPath*<br/>
[in]項目のパスを指定する文字列。

*pidl*<br/>
[out]PIDL への参照。 メソッドは、その戻り値へのポインターを格納するのにこの PIDL を使用します。

### <a name="return-value"></a>戻り値

成功した場合は NOERROR を返します。エラーの OLE 定義されている値。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
