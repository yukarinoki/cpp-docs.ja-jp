---
description: '詳細情報: CRecentFileList クラス'
title: CRecentFileList クラス
ms.date: 11/04/2016
f1_keywords:
- CRecentFileList
- AFXADV/CRecentFileList
- AFXADV/CRecentFileList::CRecentFileList
- AFXADV/CRecentFileList::Add
- AFXADV/CRecentFileList::GetDisplayName
- AFXADV/CRecentFileList::GetSize
- AFXADV/CRecentFileList::ReadList
- AFXADV/CRecentFileList::Remove
- AFXADV/CRecentFileList::UpdateMenu
- AFXADV/CRecentFileList::WriteList
helpviewer_keywords:
- CRecentFileList [MFC], CRecentFileList
- CRecentFileList [MFC], Add
- CRecentFileList [MFC], GetDisplayName
- CRecentFileList [MFC], GetSize
- CRecentFileList [MFC], ReadList
- CRecentFileList [MFC], Remove
- CRecentFileList [MFC], UpdateMenu
- CRecentFileList [MFC], WriteList
ms.assetid: a77f0524-7584-4582-849a-7e97b76d186e
ms.openlocfilehash: 9433e65336cba1018c7bff8cf3a90e239ae5e3eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301127"
---
# <a name="crecentfilelist-class"></a>CRecentFileList クラス

MRU ファイル リストのコントロールをサポートします。

## <a name="syntax"></a>構文

```
class CRecentFileList
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CRecentFileList::CRecentFileList](#crecentfilelist)|`CRecentFileList` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CRecentFileList:: Add](#add)|MRU ファイルリストにファイルを追加します。|
|[CRecentFileList:: GetDisplayName](#getdisplayname)|MRU ファイル名をメニューに表示するための表示名を提供します。|
|[CRecentFileList:: GetSize](#getsize)|MRU ファイルリスト内のファイルの数を取得します。|
|[CRecentFileList:: ReadList](#readlist)|MRU ファイルリストをレジストリまたはから読み取ります。INI ファイル。|
|[CRecentFileList:: Remove](#remove)|MRU ファイルリストからファイルを削除します。|
|[CRecentFileList:: UpdateMenu](#updatemenu)|MRU ファイルリストのメニュー表示を更新します。|
|[CRecentFileList:: WriteList](#writelist)|レジストリまたはから MRU ファイルリストを書き込みます。INI ファイル。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CRecentFileList:: operator \[\]](#operator_at)|`CString`指定された位置にあるオブジェクトを返します。|

## <a name="remarks"></a>解説

MRU ファイルリストに対してファイルの追加または削除を行うことができます。ファイルの一覧は、レジストリまたはに対して読み書きできます。INI ファイルを使用すると、MRU ファイルリストを表示するメニューを更新できます。

## <a name="inheritance-hierarchy"></a>継承階層

`CRecentFileList`

## <a name="requirements"></a>要件

**ヘッダー:** afxadv

## <a name="crecentfilelistadd"></a><a name="add"></a> CRecentFileList:: Add

最近使用した (MRU) ファイルの一覧にファイルを追加します。

```
virtual void Add(LPCTSTR lpszPathName);

virtual void Add(
    LPCTSTR lpszPathName,
    LPCTSTR lpszAppID);

void Add(
    IShellItem* pItem,
    LPCTSTR lpszAppID);

void Add(
    IShellLink* pLink,
    LPCTSTR lpszAppID);

void Add(
    PIDLIST_ABSOLUTE pidl,
    LPCTSTR lpszAppID);
```

### <a name="parameters"></a>パラメーター

*lpszPathName*<br/>
リストに追加するパス名を指定します。

*lpszAppID*<br/>
アプリケーションのアプリケーションユーザーモデル ID を指定します。

*pItem*<br/>
リストに追加するシェル項目へのポインターを指定します。

*pLink*<br/>
リストに追加するシェルリンクへのポインターを指定します。

*pidl*<br/>
最近使用した docs フォルダーに追加する必要があるシェル項目の IDLIST を指定します。

### <a name="remarks"></a>解説

ファイル名は MRU 一覧の先頭に追加されます。 MRU 一覧にファイル名が既に存在する場合は、一番上に移動します。

## <a name="crecentfilelistcrecentfilelist"></a><a name="crecentfilelist"></a> CRecentFileList::CRecentFileList

`CRecentFileList` オブジェクトを構築します。

```
CRecentFileList(
    UINT nStart,
    LPCTSTR lpszSection,
    LPCTSTR lpszEntryFormat,
    int nSize,
    int nMaxDispLen = AFX_ABBREV_FILENAME_LEN);
```

### <a name="parameters"></a>パラメーター

*nStart*<br/>
MRU (最近使用された) ファイルリストのメニュー表示での番号付けのオフセット。

*lpszSection*<br/>
レジストリまたはアプリケーションののセクション名を指します。MRU ファイルリストが読み取られ、書き込まれている INI ファイル。

*lpszEntryFormat*<br/>
レジストリまたはアプリケーションのに格納されているエントリの名前に使用される書式指定文字列を指します。INI ファイル。

*nSize*<br/>
MRU ファイルリスト内のファイルの最大数。

*nMaxDispLen*<br/>
MRU ファイルリスト内のファイル名のメニュー表示に使用できる最大文字数。

### <a name="remarks"></a>解説

*Lpszentryformat* が指す書式指定文字列には、"% d" が含まれている必要があります。これは、各 MRU 項目のインデックスを置き換えるために使用されます。 たとえば、書式文字列がの場合、エントリには、、などの `"file%d"` 名前が付けられ `file0` `file1` ます。

## <a name="crecentfilelistgetdisplayname"></a><a name="getdisplayname"></a> CRecentFileList:: GetDisplayName

Mru リストのメニュー表示に使用する、MRU ファイルリスト内のファイルの表示名を取得します。

```
virtual BOOL GetDisplayName(
    CString& strName,
    int nIndex,
    LPCTSTR lpszCurDir,
    int nCurDir,
    BOOL bAtLeastName = TRUE) const;
```

### <a name="parameters"></a>パラメーター

*strName*<br/>
MRU ファイルのメニューリストに表示される名前を持つファイルの完全パスです。

*nIndex*<br/>
MRU ファイルリスト内のファイルの0から始まるインデックス。

*lpszCurDir*<br/>
現在のディレクトリを保持している文字列。

*nCurDir*<br/>
現在のディレクトリ文字列の長さ。

*bAtLeastName*<br/>
0以外の場合は、ファイルの基本名が返されることを示します ( *nMaxDispLen* パラメーターとしてコンストラクターに渡される `CRecentFileList` )。

### <a name="return-value"></a>戻り値

最後に使用した (MRU) ファイルリストの指定されたインデックスにファイル名がない場合は **FALSE** 。

### <a name="remarks"></a>解説

ファイルが現在のディレクトリにある場合、この関数はディレクトリを表示から外に出ます。 ファイル名が長すぎる場合、ディレクトリと拡張子は削除されます。 ファイル名が長すぎる場合、 *bAtLeastName* が0以外の場合を除き、表示名は空の文字列に設定されます。

## <a name="crecentfilelistgetsize"></a><a name="getsize"></a> CRecentFileList:: GetSize

MRU ファイルリスト内のファイルの数を取得します。

```
int GetSize() const;
```

### <a name="return-value"></a>戻り値

現在使用されている (MRU) ファイルリスト内のファイルの数。

## <a name="crecentfilelistoperator--"></a><a name="operator_at"></a> CRecentFileList:: operator []

オーバーロードされた添字 ( `[]` ) 演算子は、型の `CString` 0 から始まるインデックスで指定された単一のを返します。

```
CString& operator[ ](int nindex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
のセット内のの0から始まるインデックス `CString` `CString` 。

## <a name="crecentfilelistreadlist"></a><a name="readlist"></a> CRecentFileList:: ReadList

最近使用した (MRU) ファイルの一覧をレジストリまたはアプリケーションのから読み取ります。INI ファイル。

```
virtual void ReadList();
```

## <a name="crecentfilelistremove"></a><a name="remove"></a> CRecentFileList:: Remove

MRU ファイルリストからファイルを削除します。

```
virtual void Remove(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
最近使用した (MRU) ファイルの一覧から削除するファイルの0から始まるインデックス。

## <a name="crecentfilelistupdatemenu"></a><a name="updatemenu"></a> CRecentFileList:: UpdateMenu

MRU ファイルリストのメニュー表示を更新します。

```
virtual void UpdateMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*pCmdUI*<br/>
最近使用した (MRU) ファイルリストメニューの [CCmdUI](../../mfc/reference/ccmdui-class.md) オブジェクトへのポインター。

## <a name="crecentfilelistwritelist"></a><a name="writelist"></a> CRecentFileList:: WriteList

最近使用した (MRU) ファイルの一覧をレジストリまたはアプリケーションのに書き込みます。INI ファイル。

```
virtual void WriteList();
```

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)
