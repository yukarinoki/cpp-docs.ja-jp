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
ms.openlocfilehash: 1c2f9ac1658f50f0ec5bd9e2f53d270c09bfcb6a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750326"
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
|[次の手順を実行します。](#cshellmanager)|`CShellManager` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を見る](#browseforfolder)|ユーザーがシェル フォルダを選択するためのダイアログ ボックスを表示します。|
|[をクリックします。](#concatenateitem)|2 つの PidL を連結します。|
|[次の項目をコピーします。](#copyitem)|新しい PIDL を作成し、指定された PIDL をコピーします。|
|[次の項目を作成します。](#createitem)|指定したサイズの新しい PIDL を作成します。|
|[次の項目を使用します。](#freeitem)|指定された PIDL を削除します。|
|[を使用します。](#getitemcount)|指定された PIDL 内の項目数を返します。|
|[次の項目を使用します。](#getitemsize)|指定された PIDL のサイズを返します。|
|[次の項目を取得します。](#getnextitem)|PIDL から次の項目を返します。|
|[次の項目を取得します。](#getparentitem)|指定された項目の親項目を取得します。|
|[次のパスを使用します。](#itemfrompath)|指定されたパスで識別される項目の PIDL を取得します。|

## <a name="remarks"></a>解説

クラスの`CShellManager`メソッドはすべて、PIDL を扱います。 PIDL はシェルオブジェクトの一意の識別子です。

オブジェクトは手動で`CShellManager`作成しないでください。 アプリケーションのフレームワークによって自動的に作成されます。 ただし、アプリケーションの初期化プロセス中に[CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager)を呼び出す必要があります。 アプリケーションのシェル マネージャーへのポインターを取得するには[、CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager)を呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CShellManager](../../mfc/reference/cshellmanager-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxshellmanager.h

## <a name="cshellmanagerbrowseforfolder"></a><a name="browseforfolder"></a>を見る

ユーザーがシェル フォルダを選択するためのダイアログ ボックスを表示します。

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

*ストラウトフォルダ*<br/>
[アウト]選択したフォルダーのパスを格納するためにメソッドによって使用される文字列。

*親の子*<br/>
[in]親ウィンドウへのポインター。

*をクリックします。*<br/>
[in]ダイアログ ボックスが表示されるときに既定で選択されているフォルダーを含む文字列。

*lpszタイトル*<br/>
[in]ダイアログ ボックスのタイトル。

*ulFlags*<br/>
[in]ダイアログ ボックスのオプションを指定するフラグ。 詳細な説明については[、BROWSEINFO](/windows/win32/api/shlobj_core/ns-shlobj_core-browseinfow)を参照してください。

*イメージ*<br/>
[アウト]選択したフォルダーのイメージ インデックスを書き込む整数値へのポインター。

### <a name="return-value"></a>戻り値

ユーザーがダイアログ ボックスからフォルダを選択した場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドを呼び出すと、アプリケーションは、ユーザーがフォルダーを選択できるダイアログ ボックスを作成して表示します。 メソッドは、フォルダーのパスを*strOutFolder*パラメーターに書き込みます。

### <a name="example"></a>例

メソッドを使用してオブジェクトへの参照を取得する方法と`CShellManager`、メソッドを使用`CWinAppEx::GetShellManager`する方法を次の例`BrowseForFolder`に示します。 このコード スニペットは[、エクスプローラーのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_Explorer#6](../../mfc/reference/codesnippet/cpp/cshellmanager-class_1.cpp)]

## <a name="cshellmanagerconcatenateitem"></a><a name="concatenateitem"></a>をクリックします。

2 つの PIDL を含む新しいリストを作成します。

```
LPITEMIDLIST ConcatenateItem(
    LPCITEMIDLIST pidl1,
    LPCITEMIDLIST pidl2);
```

### <a name="parameters"></a>パラメーター

*ピドル1*<br/>
[in]最初の項目。

*ピドル2*<br/>
[in]2 番目の項目。

### <a name="return-value"></a>戻り値

関数が成功した場合は新しい項目リストへのポインター。

### <a name="remarks"></a>解説

このメソッドは *、pidl1*と*pidl2*の両方を含めるのに十分な大きさの新しい[ITEMIDLIST](/windows/win32/api/shtypes/ns-shtypes-itemidlist)を作成します。 次に *、pidl1*と*pidl2 を*新しいリストにコピーします。

## <a name="cshellmanagercopyitem"></a><a name="copyitem"></a>次の項目をコピーします。

項目リストをコピーします。

```
LPITEMIDLIST CopyItem(LPCITEMIDLIST pidlSource);
```

### <a name="parameters"></a>パラメーター

*ピドルソース*<br/>
[in]元の項目リスト。

### <a name="return-value"></a>戻り値

正常に終了した場合は、新しく作成された項目リストへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

新しく作成された項目リストのサイズは、ソース項目リストと同じです。

## <a name="cshellmanagercreateitem"></a><a name="createitem"></a>次の項目を作成します。

新しい PIDL を作成します。

```
LPITEMIDLIST CreateItem(UINT cbSize);
```

### <a name="parameters"></a>パラメーター

*Cbsize*<br/>
[in]項目リストのサイズ。

### <a name="return-value"></a>戻り値

正常終了した場合は、作成された項目リストへのポインター。それ以外の場合は NULL。

## <a name="cshellmanagercshellmanager"></a><a name="cshellmanager"></a>次の手順を実行します。

`CShellManager` オブジェクトを構築します。

```
CShellManager();
```

### <a name="remarks"></a>解説

ほとんどの場合、`CShellManager`直接作成する必要はありません。 既定では、フレームワークは自動的に作成されます。 へのポインターを取得するには`CShellManager`[、CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager)を呼び出します。 手動で作成する`CShellManager`場合は、CWinAppEx::InitShellManager メソッドを使用して初期化する必要があります。 [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager)

## <a name="cshellmanagerfreeitem"></a><a name="freeitem"></a>次の項目を使用します。

アイテム リストを削除します。

```cpp
void FreeItem(LPITEMIDLIST pidl);
```

### <a name="parameters"></a>パラメーター

*Pidl*<br/>
[in]削除する項目リスト。

## <a name="cshellmanagergetitemcount"></a><a name="getitemcount"></a>を使用します。

項目リスト内の項目数を返します。

```
UINT GetItemCount(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>パラメーター

*Pidl*<br/>
[in]項目リストへのポインター。

### <a name="return-value"></a>戻り値

項目リスト内の項目の数。

## <a name="cshellmanagergetitemsize"></a><a name="getitemsize"></a>次の項目を使用します。

項目リストのサイズを返します。

```
UINT GetItemSize(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>パラメーター

*Pidl*<br/>
[in]項目リストへのポインター。

### <a name="return-value"></a>戻り値

項目リストのサイズ。

## <a name="cshellmanagergetnextitem"></a><a name="getnextitem"></a>次の項目を取得します。

項目識別子リスト (PIDL) へのポインターから次の項目を取得します。

```
LPITEMIDLIST GetNextItem(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>パラメーター

*Pidl*<br/>
[in]反復処理する項目のリスト。

### <a name="return-value"></a>戻り値

リスト内の次の項目へのポインター。

### <a name="remarks"></a>解説

リストに項目がなくなった場合、このメソッドは NULL を返します。

## <a name="cshellmanagergetparentitem"></a><a name="getparentitem"></a>次の項目を取得します。

項目識別子リスト (PIDL) へのポインターの親を取得します。

```
int GetParentItem(
    LPCITEMIDLIST lpidl,
    LPITEMIDLIST& lpidlParent);
```

### <a name="parameters"></a>パラメーター

*ルピドル*<br/>
[in]親が取得される PIDL。

*ルピドル親*<br/>
[アウト]メソッドが結果を格納する PIDL への参照。

### <a name="return-value"></a>戻り値

親 PIDL のレベル。

### <a name="remarks"></a>解説

PIDL のレベルは、デスクトップに対して相対的です。 デスクトップ PIDL はレベル 0 と見なされます。

## <a name="cshellmanageritemfrompath"></a><a name="itemfrompath"></a>次のパスを使用します。

文字列パスで識別される項目から項目識別子リスト (PIDL) へのポインターを取得します。

```
HRESULT ItemFromPath(
    LPCTSTR lpszPath,
    LPITEMIDLIST& pidl);
```

### <a name="parameters"></a>パラメーター

*パス*<br/>
[in]項目のパスを指定する文字列。

*Pidl*<br/>
[アウト]PIDL への参照。 このメソッドは、この PIDL を使用して、戻り値へのポインターを格納します。

### <a name="return-value"></a>戻り値

成功した場合は NOERROR を返します。OLE 定義エラー値。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
