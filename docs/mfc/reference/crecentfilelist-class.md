---
title: クラスを表示します。
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
ms.openlocfilehash: a2102c6a39c14c548828e57ad1c49de6a5bc03dd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370907"
---
# <a name="crecentfilelist-class"></a>クラスを表示します。

MRU ファイル リストのコントロールをサポートします。

## <a name="syntax"></a>構文

```
class CRecentFileList
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[リスト::コリストファイルリスト](#crecentfilelist)|`CRecentFileList` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ファイルリスト::追加](#add)|MRU ファイル リストにファイルを追加します。|
|[一覧::表示名を取得します。](#getdisplayname)|MRU ファイル名のメニュー表示の表示名を指定します。|
|[一覧::取得サイズ](#getsize)|MRU ファイル リスト内のファイル数を取得します。|
|[リストの一覧::リストの読み取り](#readlist)|レジストリまたは から MRU ファイルの一覧を読み取ります。INI ファイル。|
|[リスト::削除](#remove)|MRU ファイル リストからファイルを削除します。|
|[一覧:メニューの更新](#updatemenu)|MRU ファイルリストのメニュー表示を更新します。|
|[リスト::ライトリスト](#writelist)|レジストリまたは から MRU ファイルリストを書き込みます。INI ファイル。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[一覧::演算子\[\]](#operator_at)|指定した`CString`位置にあるオブジェクトを返します。|

## <a name="remarks"></a>解説

MRU ファイルリストにファイルを追加したり、MRU ファイルリストから削除したり、ファイルリストをレジストリまたは .INI ファイル、および MRU ファイルリストを表示するメニューを更新することができます。

## <a name="inheritance-hierarchy"></a>継承階層

`CRecentFileList`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxadv.h

## <a name="crecentfilelistadd"></a><a name="add"></a>ファイルリスト::追加

最近使用した (MRU) ファイルリストにファイルを追加します。

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

*パス名*<br/>
リストに追加するパス名を指定します。

*をクリックします。*<br/>
アプリケーションのアプリケーション ユーザー モデル ID を指定します。

*Pitem*<br/>
リストに追加するシェル項目へのポインターを指定します。

*Plink*<br/>
リストに追加するシェル リンクへのポインターを指定します。

*Pidl*<br/>
最近使ったドキュメント フォルダに追加するシェル項目の IDLIST を指定します。

### <a name="remarks"></a>解説

ファイル名は MRU リストの先頭に追加されます。 ファイル名が既に MRU リストに存在する場合は、先頭に移動します。

## <a name="crecentfilelistcrecentfilelist"></a><a name="crecentfilelist"></a>リスト::コリストファイルリスト

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

*n開始*<br/>
MRU (最近使用した) ファイル・リストのメニュー表示での番号付けのオフセット。

*セクション*<br/>
レジストリまたはアプリケーションのセクションの名前を指定します。MRU ファイル リストが読み取られるか書き込まれる INI ファイル。

*フォーマット*<br/>
レジストリまたはアプリケーションの に格納されているエントリの名前に使用する書式指定文字列へのポイント。INI ファイル。

*Nsize*<br/>
MRU ファイル リスト内の最大ファイル数。

*nマックスディスレン*<br/>
MRU ファイル リストのファイル名のメニュー表示に使用できる最大長 (文字数)。

### <a name="remarks"></a>解説

*lpszEntryFormat*によって指される書式指定文字列は、"%d" を含む必要があります。 たとえば、書式指定文字列の場合、`"file%d"`エントリは 、 など`file0``file1`という名前になります。

## <a name="crecentfilelistgetdisplayname"></a><a name="getdisplayname"></a>一覧::表示名を取得します。

MRU ファイル・リストのメニュー表示で使用する、MRU ファイル・リスト内のファイルの表示名を取得します。

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
MRU ファイルのメニューリストに表示される名前のファイルの完全パス。

*nIndex*<br/>
MRU ファイル リスト内のファイルの 0 から始まるインデックス。

*ル・シ・ラ*<br/>
現在のディレクトリを保持する文字列。

*nCurDir*<br/>
現在のディレクトリ文字列の長さ。

*名前*<br/>
0 以外の場合は、ファイルの基本名が最大表示長 *(nMaxDispLen*パラメーターとして`CRecentFileList`コンストラクターに渡された) を超えても返されることを示します。

### <a name="return-value"></a>戻り値

最後に使用された (MRU) ファイル・リスト内の指定されたインデックスにファイル名がない場合**は FALSE。**

### <a name="remarks"></a>解説

ファイルが現在のディレクトリにある場合、この関数はディレクトリを表示から外します。 ファイル名が長すぎる場合は、ディレクトリと拡張子が削除されます。 ファイル名がまだ長すぎる場合は *、bAtLeastName*が 0 以外の場合を除き、表示名は空の文字列に設定されます。

## <a name="crecentfilelistgetsize"></a><a name="getsize"></a>一覧::取得サイズ

MRU ファイル リスト内のファイル数を取得します。

```
int GetSize() const;
```

### <a name="return-value"></a>戻り値

現在使用されている (MRU) ファイル リスト内のファイルの数。

## <a name="crecentfilelistoperator--"></a><a name="operator_at"></a>一覧::演算子 [ ]

オーバーロードされた添字 (`[]`) 演算子は`CString`*、nIndex*の 0 から始まるインデックスで指定された単一の値を返します。

```
CString& operator[ ](int nindex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
s のセット内の`CString`a の`CString`0 から始まるインデックス。

## <a name="crecentfilelistreadlist"></a><a name="readlist"></a>リストの一覧::リストの読み取り

レジストリまたはアプリケーションのから、最近使用した (MRU) ファイルの一覧を読み取ります。INI ファイル。

```
virtual void ReadList();
```

## <a name="crecentfilelistremove"></a><a name="remove"></a>リスト::削除

MRU ファイル リストからファイルを削除します。

```
virtual void Remove(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
最後に使用した (MRU) ファイルリストから削除するファイルの 0 から始まるインデックス。

## <a name="crecentfilelistupdatemenu"></a><a name="updatemenu"></a>一覧:メニューの更新

MRU ファイルリストのメニュー表示を更新します。

```
virtual void UpdateMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
最近使用した (MRU) ファイル一覧メニューの[CCmdUI](../../mfc/reference/ccmdui-class.md)オブジェクトへのポインター。

## <a name="crecentfilelistwritelist"></a><a name="writelist"></a>リスト::ライトリスト

最後に使用した (MRU) ファイルの一覧をレジストリまたはアプリケーションの .INI ファイル。

```
virtual void WriteList();
```

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)
