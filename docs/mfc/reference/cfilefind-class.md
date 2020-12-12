---
description: '詳細情報: CFileFind クラス'
title: CFileFind クラス
ms.date: 11/04/2016
f1_keywords:
- CFileFind
- AFX/CFileFind
- AFX/CFileFind::CFileFind
- AFX/CFileFind::Close
- AFX/CFileFind::FindFile
- AFX/CFileFind::FindNextFile
- AFX/CFileFind::GetCreationTime
- AFX/CFileFind::GetFileName
- AFX/CFileFind::GetFilePath
- AFX/CFileFind::GetFileTitle
- AFX/CFileFind::GetFileURL
- AFX/CFileFind::GetLastAccessTime
- AFX/CFileFind::GetLastWriteTime
- AFX/CFileFind::GetLength
- AFX/CFileFind::GetRoot
- AFX/CFileFind::IsArchived
- AFX/CFileFind::IsCompressed
- AFX/CFileFind::IsDirectory
- AFX/CFileFind::IsDots
- AFX/CFileFind::IsHidden
- AFX/CFileFind::IsNormal
- AFX/CFileFind::IsReadOnly
- AFX/CFileFind::IsSystem
- AFX/CFileFind::IsTemporary
- AFX/CFileFind::MatchesMask
- AFX/CFileFind::CloseContext
- AFX/CFileFind::m_pTM
helpviewer_keywords:
- CFileFind [MFC], CFileFind
- CFileFind [MFC], Close
- CFileFind [MFC], FindFile
- CFileFind [MFC], FindNextFile
- CFileFind [MFC], GetCreationTime
- CFileFind [MFC], GetFileName
- CFileFind [MFC], GetFilePath
- CFileFind [MFC], GetFileTitle
- CFileFind [MFC], GetFileURL
- CFileFind [MFC], GetLastAccessTime
- CFileFind [MFC], GetLastWriteTime
- CFileFind [MFC], GetLength
- CFileFind [MFC], GetRoot
- CFileFind [MFC], IsArchived
- CFileFind [MFC], IsCompressed
- CFileFind [MFC], IsDirectory
- CFileFind [MFC], IsDots
- CFileFind [MFC], IsHidden
- CFileFind [MFC], IsNormal
- CFileFind [MFC], IsReadOnly
- CFileFind [MFC], IsSystem
- CFileFind [MFC], IsTemporary
- CFileFind [MFC], MatchesMask
- CFileFind [MFC], CloseContext
- CFileFind [MFC], m_pTM
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
ms.openlocfilehash: d47c45ac86386a6748ca212c569aeef568ca2a8a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184505"
---
# <a name="cfilefind-class"></a>CFileFind クラス

ローカルファイル検索を実行します。これは、インターネットファイル検索を実行する [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) と [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)の基本クラスです。

## <a name="syntax"></a>構文

```
class CFileFind : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CFileFind::CFileFind](#cfilefind)|`CFileFind` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CFileFind:: Close](#close)|検索要求を閉じます。|
|[CFileFind:: FindFile](#findfile)|指定されたファイル名をディレクトリで検索します。|
|[CFileFind::FindNextFile](#findnextfile)|以前の [FindFile](#findfile)の呼び出しからファイル検索を続行します。|
|[CFileFind:: Get Time](#getcreationtime)|ファイルが作成された時刻を取得します。|
|[CFileFind:: GetFileName](#getfilename)|検出されたファイルの名前 (拡張子を含む) を取得します。|
|[CFileFind:: GetFilePath](#getfilepath)|検出されたファイルの完全なパスを取得します。|
|[CFileFind::GetFileTitle](#getfiletitle)|検出されたファイルのタイトルを取得します。 タイトルには、拡張子は含まれません。|
|[CFileFind::GetFileURL](#getfileurl)|検出されたファイルの URL (ファイルパスを含む) を取得します。|
|[CFileFind:: GetLastAccessTime](#getlastaccesstime)|ファイルが最後にアクセスされた時刻を取得します。|
|[CFileFind:: GetLastWriteTime](#getlastwritetime)|ファイルが最後に変更されて保存された時刻を取得します。|
|[CFileFind:: GetLength](#getlength)|検出されたファイルの長さをバイト単位で取得します。|
|[CFileFind:: GetRoot](#getroot)|検出されたファイルのルートディレクトリを取得します。|
|[CFileFind:: IsArchived 済み](#isarchived)|検出されたファイルがアーカイブされているかどうかを判断します。|
|[CFileFind:: IsCompressed](#iscompressed)|検出されたファイルが圧縮されているかどうかを判断します。|
|[CFileFind:: IsDirectory](#isdirectory)|見つかったファイルがディレクトリであるかどうかを判断します。|
|[CFileFind:: IsDots](#isdots)|見つかったファイルの名前の名前が "." または ".." であるかどうかを判断します。これは、が実際にはディレクトリであることを示します。|
|[CFileFind:: IsHidden](#ishidden)|検出されたファイルが非表示かどうかを判断します。|
|[CFileFind:: IsNormal](#isnormal)|検出されたファイルが正常であるかどうかを判断します (つまり、に他の属性はありません)。|
|[CFileFind:: IsReadOnly](#isreadonly)|検出されたファイルが読み取り専用かどうかを判断します。|
|[CFileFind:: Issystem で](#issystem)|検出されたファイルがシステムファイルであるかどうかを判断します。|
|[CFileFind:: IsTemporary](#istemporary)|見つかったファイルが一時的なものかどうかを判断します。|
|[CFileFind::MatchesMask](#matchesmask)|検索するファイルの必要なファイル属性を示します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CFileFind:: Cloのテキスト](#closecontext)|現在の検索ハンドルによって指定されたファイルを閉じます。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CFileFind:: m_pTM](#m_ptm)|オブジェクトへのポインター `CAtlTransactionManager` 。|

## <a name="remarks"></a>解説

`CFileFind` には、検索を開始し、ファイルを検索し、ファイルのタイトル、名前、またはパスを返すメンバー関数が含まれています。 インターネット検索の場合、メンバー関数 [GetFileURL](#getfileurl) はファイルの URL を返します。

`CFileFind` は、特定のサーバーの種類を検索するように設計された、他の2つの MFC クラスの基本クラスです。これは `CGopherFileFind` 、特に gopher サーバーで機能し、 `CFtpFileFind` FTP サーバーで特に機能します。 これら3つのクラスは、サーバープロトコル、ファイルの種類、場所など、ローカルコンピューターまたはリモートサーバー上のファイルを検索するためのシームレスなメカニズムを提供します。

次のコードでは、現在のディレクトリにあるすべてのファイルを列挙し、各ファイルの名前を出力します。

[!code-cpp[NVC_MFCFiles#31](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]

例を単純にするために、このコードでは C++ 標準ライブラリクラスを使用して `cout` います。 この `cout` 行は `CListBox::AddString` 、グラフィカルユーザーインターフェイスを備えたプログラムで、などの呼び出しに置き換えることができます。

とその他の WinInet クラスの使用方法の詳細については、 `CFileFind` 「 [wininet を使用したインターネットプログラミング](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CFileFind`

## <a name="requirements"></a>要件

**ヘッダー:** afx

## <a name="cfilefindcfilefind"></a><a name="cfilefind"></a> CFileFind::CFileFind

このメンバー関数は、オブジェクトが構築されるときに呼び出され `CFileFind` ます。

```
CFileFind();
CFileFind(CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>パラメーター

*pTM*<br/>
CAtlTransactionManager オブジェクトへのポインター。

### <a name="example"></a>例

  [CFileFind:: GetFileName](#getfilename)の例を参照してください。

## <a name="cfilefindclose"></a><a name="close"></a> CFileFind:: Close

検索を終了し、コンテキストをリセットし、すべてのリソースを解放するには、このメンバー関数を呼び出します。

```cpp
void Close();
```

### <a name="remarks"></a>解説

を呼び出した後 `Close` 、 `CFileFind` [FindFile](#findfile) を呼び出して新しい検索を開始する前に、新しいインスタンスを作成する必要はありません。

### <a name="example"></a>例

  [CFileFind:: GetFileName](#getfilename)の例を参照してください。

## <a name="cfilefindclosecontext"></a><a name="closecontext"></a> CFileFind:: Cloのテキスト

現在の検索ハンドルによって指定されたファイルを閉じます。

```
virtual void CloseContext();
```

### <a name="remarks"></a>解説

検索ハンドルの現在の値によって指定されたファイルを閉じます。 既定の動作を変更するには、この関数をオーバーライドします。

有効な検索ハンドルを取得するには、少なくとも1回は [FindFile](#findfile) 関数または [FindNextFile](#findnextfile) 関数を呼び出す必要があります。 `FindFile`関数と関数は、検索ハンドルを使用して、 `FindNextFile` 指定された名前に一致する名前を持つファイルを検索します。

## <a name="cfilefindfindfile"></a><a name="findfile"></a> CFileFind:: FindFile

ファイル検索を開くには、このメンバー関数を呼び出します。

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwUnused = 0);
```

### <a name="parameters"></a>パラメーター

*pstrName*<br/>
検索するファイルの名前を格納している文字列へのポインター。 *Pstrname* に NULL を渡すと、 `FindFile` はワイルドカード (*. \* ) 検索を行います。

*dwUnused*<br/>
派生クラスでポリモーフィックにするために予約さ `FindFile` れています。 0 を指定する必要があります。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 拡張されたエラー情報を取得するには、Win32 関数 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)を呼び出します。

### <a name="remarks"></a>解説

を呼び出し `FindFile` てファイル検索を開始した後、 [FindNextFile](#findnextfile) を呼び出して後続のファイルを取得します。 `FindNextFile`次の属性メンバー関数のいずれかを呼び出す前に、を少なくとも1回呼び出す必要があります。

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [GetFileTitle](#getfiletitle)

- [GetFilePath](#getfilepath)

- [GetFileURL](#getfileurl)

- [GetLastAccessTime](#getlastaccesstime)

- [GetLastWriteTime](#getlastwritetime)

- [GetLength](#getlength)

- [GetRoot](#getroot)

- [IsArchived 済み](#isarchived)

- [IsCompressed](#iscompressed)

- [IsDirectory](#isdirectory)

- [IsDots](#isdots)

- [IsHidden](#ishidden)

- [IsNormal](#isnormal)

- [IsReadOnly](#isreadonly)

- [IsSystem](#issystem)

- [IsTemporary](#istemporary)

- [MatchesMask](#matchesmask)

### <a name="example"></a>例

  [CFileFind:: IsDirectory](#isdirectory)の例を参照してください。

## <a name="cfilefindfindnextfile"></a><a name="findnextfile"></a> CFileFind::FindNextFile

以前の [FindFile](#findfile)の呼び出しからファイル検索を続行するには、このメンバー関数を呼び出します。

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>戻り値

他のファイルがある場合は0以外。見つかったファイルがディレクトリ内の最後のファイルであるか、エラーが発生した場合は0。 拡張されたエラー情報を取得するには、Win32 関数 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)を呼び出します。 見つかったファイルがディレクトリ内の最後のファイルである場合、または一致するファイルが見つからない場合、 `GetLastError` 関数は ERROR_NO_MORE_FILES を返します。

### <a name="remarks"></a>解説

`FindNextFile`次の属性メンバー関数のいずれかを呼び出す前に、を少なくとも1回呼び出す必要があります。

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [GetFileTitle](#getfiletitle)

- [GetFilePath](#getfilepath)

- [GetFileURL](#getfileurl)

- [GetLastAccessTime](#getlastaccesstime)

- [GetLastWriteTime](#getlastwritetime)

- [GetLength](#getlength)

- [GetRoot](#getroot)

- [IsArchived 済み](#isarchived)

- [IsCompressed](#iscompressed)

- [IsDirectory](#isdirectory)

- [IsDots](#isdots)

- [IsHidden](#ishidden)

- [IsNormal](#isnormal)

- [IsReadOnly](#isreadonly)

- [IsSystem](#issystem)

- [IsTemporary](#istemporary)

- [MatchesMask](#matchesmask)

`FindNextFile` Win32 関数 [FindNextFile](/windows/win32/api/fileapi/nf-fileapi-findnextfilew)をラップします。

### <a name="example"></a>例

  [CFileFind:: IsDirectory](#isdirectory)の例を参照してください。

## <a name="cfilefindgetcreationtime"></a><a name="getcreationtime"></a> CFileFind:: Get Time

このメンバー関数を呼び出して、指定したファイルが作成された時刻を取得します。

```
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;
virtual BOOL GetCreationTime(CTime& refTime) const;
```

### <a name="parameters"></a>パラメーター

*pTimeStamp*<br/>
ファイルが作成された時刻を格納している [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) 構造体へのポインター。

*refTime*<br/>
[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトへの参照。

### <a name="return-value"></a>戻り値

成功した場合は0以外の。失敗した場合は0。 `GetCreationTime` このオブジェクトで [FindNextFile](#findnextfile) が呼び出されたことがない場合にのみ、0を返し `CFileFind` ます。

### <a name="remarks"></a>解説

を呼び出す前に、 [FindNextFile](#findnextfile) を少なくとも1回呼び出す必要があり `GetCreationTime` ます。

> [!NOTE]
> すべてのファイルシステムで同じセマンティクスを使用して、この関数によって返されるタイムスタンプが実装されるわけではありません。 基になるファイルシステムまたはサーバーが time 属性の保持をサポートしていない場合、この関数は、他のタイムスタンプ関数から返される値と同じ値を返すことがあります。 時刻形式の詳細については、 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 構造体を参照してください。 一部のオペレーティングシステムでは、返された時間は、コンピューターのローカルのタイムゾーンのファイルの場所にあります。 詳細については、Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API に関する説明を参照してください。

### <a name="example"></a>例

  [CFileFind:: GetLength](#getlength)の例を参照してください。

## <a name="cfilefindgetfilename"></a><a name="getfilename"></a> CFileFind:: GetFileName

検出されたファイルの名前を取得するには、このメンバー関数を呼び出します。

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>戻り値

最近検出されたファイルの名前。

### <a name="remarks"></a>解説

GetFileName を呼び出す前に、 [FindNextFile](#findnextfile) を少なくとも1回呼び出す必要があります。

`GetFileName` は `CFileFind` 、何らかの形式のファイル名を返す3つのメンバー関数のうちの1つです。 次の一覧では、3つの方法とそれらの違いについて説明します。

- `GetFileName` 拡張子を含むファイル名を返します。 たとえば、を呼び出し `GetFileName` て、ファイル *c:\myhtml\myfile.txt* に関するユーザーメッセージを生成すると、 *myfile.txt* ファイル名が返されます。

- [Getfilepath](#getfilepath) は、ファイルのパス全体を返します。 たとえば、を呼び出すと、ファイル `GetFilePath` *c:\myhtml\myfile.txt* に関するユーザーメッセージが生成され、 *c:\myhtml\myfile.txt* ファイルパスが返されます。

- [GetFileTitle](#getfiletitle) はファイル名を返します (ファイル拡張子は除く)。 たとえば、を呼び出すと、ファイル `GetFileTitle` の *c:\myhtml\myfile.txt* に関するユーザーメッセージが生成さ *れ* ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#32](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]

## <a name="cfilefindgetfilepath"></a><a name="getfilepath"></a> CFileFind:: GetFilePath

このメンバー関数を呼び出して、指定したファイルの完全なパスを取得します。

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>戻り値

指定したファイルのパス。

### <a name="remarks"></a>解説

を呼び出す前に、 [FindNextFile](#findnextfile) を少なくとも1回呼び出す必要があり `GetFilePath` ます。

`GetFilePath` は `CFileFind` 、何らかの形式のファイル名を返す3つのメンバー関数のうちの1つです。 次の一覧では、3つの方法とそれらの違いについて説明します。

- [Getfilename](#getfilename) は、拡張子を含むファイル名を返します。 たとえば、を呼び出し `GetFileName` て、ファイル *c:\myhtml\myfile.txt* に関するユーザーメッセージを生成すると、 *myfile.txt* ファイル名が返されます。

- `GetFilePath` ファイルのパス全体を返します。 たとえば、ファイルに `GetFilePath` 関するユーザーメッセージを生成するためにを呼び出すと、 `c:\myhtml\myfile.txt` ファイルパスが返され `c:\myhtml\myfile.txt` ます。

- [GetFileTitle](#getfiletitle) はファイル名を返します (ファイル拡張子は除く)。 たとえば、を呼び出すと、ファイル `GetFileTitle` の *c:\myhtml\myfile.txt* に関するユーザーメッセージが生成さ *れ* ます。

### <a name="example"></a>例

  [CFileFind:: GetFileName](#getfilename)の例を参照してください。

## <a name="cfilefindgetfiletitle"></a><a name="getfiletitle"></a> CFileFind::GetFileTitle

検出されたファイルのタイトルを取得するには、このメンバー関数を呼び出します。

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>戻り値

ファイルのタイトル。

### <a name="remarks"></a>解説

を呼び出す前に、 [FindNextFile](#findnextfile) を少なくとも1回呼び出す必要があり `GetFileTitle` ます。

`GetFileTitle` は `CFileFind` 、何らかの形式のファイル名を返す3つのメンバー関数のうちの1つです。 次の一覧では、3つの方法とそれらの違いについて説明します。

- [Getfilename](#getfilename) は、拡張子を含むファイル名を返します。 たとえば、を呼び出し `GetFileName` て、ファイル *c:\myhtml\myfile.txt* に関するユーザーメッセージを生成すると、 *myfile.txt* ファイル名が返されます。

- [Getfilepath](#getfilepath) は、ファイルのパス全体を返します。 たとえば、を呼び出すと、ファイル `GetFilePath` *c:\myhtml\myfile.txt* に関するユーザーメッセージが生成され、 *c:\myhtml\myfile.txt* ファイルパスが返されます。

- `GetFileTitle` ファイル名を返します (ファイル拡張子は除く)。 たとえば、を呼び出すと、ファイル `GetFileTitle` の *c:\myhtml\myfile.txt* に関するユーザーメッセージが生成さ *れ* ます。

### <a name="example"></a>例

  [CFileFind:: GetFileName](#getfilename)の例を参照してください。

## <a name="cfilefindgetfileurl"></a><a name="getfileurl"></a> CFileFind::GetFileURL

指定した URL を取得するには、このメンバー関数を呼び出します。

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>戻り値

完全な URL。

### <a name="remarks"></a>解説

を呼び出す前に、 [FindNextFile](#findnextfile) を少なくとも1回呼び出す必要があり `GetFileURL` ます。

`GetFileURL` は、という形式の URL を返す点を除けば、メンバー関数 [Getfilepath](#getfilepath)に似てい `file://path` ます。 たとえば、を呼び出して `GetFileURL` *myfile.txt* の完全な url を取得すると、url が返され `file://c:\myhtml\myfile.txt` ます。

### <a name="example"></a>例

  [CFileFind:: GetFileName](#getfilename)の例を参照してください。

## <a name="cfilefindgetlastaccesstime"></a><a name="getlastaccesstime"></a> CFileFind:: GetLastAccessTime

このメンバー関数を呼び出して、指定したファイルに最後にアクセスした時刻を取得します。

```
virtual BOOL GetLastAccessTime(CTime& refTime) const;
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;
```

### <a name="parameters"></a>パラメーター

*refTime*<br/>
[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトへの参照。

*pTimeStamp*<br/>
ファイルが最後にアクセスされた時刻を格納している [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) 構造体へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は0以外の。失敗した場合は0。 `GetLastAccessTime` このオブジェクトで [FindNextFile](#findnextfile) が呼び出されたことがない場合にのみ、0を返し `CFileFind` ます。

### <a name="remarks"></a>解説

を呼び出す前に、 [FindNextFile](#findnextfile) を少なくとも1回呼び出す必要があり `GetLastAccessTime` ます。

> [!NOTE]
> すべてのファイルシステムで同じセマンティクスを使用して、この関数によって返されるタイムスタンプが実装されるわけではありません。 基になるファイルシステムまたはサーバーが time 属性の保持をサポートしていない場合、この関数は、他のタイムスタンプ関数から返される値と同じ値を返すことがあります。 時刻形式の詳細については、 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 構造体を参照してください。 一部のオペレーティングシステムでは、返された時間は、コンピューターのローカルのタイムゾーンのファイルの場所にあります。 詳細については、Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API に関する説明を参照してください。

### <a name="example"></a>例

  [CFileFind:: GetLength](#getlength)の例を参照してください。

## <a name="cfilefindgetlastwritetime"></a><a name="getlastwritetime"></a> CFileFind:: GetLastWriteTime

ファイルが最後に変更された時刻を取得するには、このメンバー関数を呼び出します。

```
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;
virtual BOOL GetLastWriteTime(CTime& refTime) const;
```

### <a name="parameters"></a>パラメーター

*pTimeStamp*<br/>
ファイルが最後に書き込まれた時刻を格納している [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) 構造体へのポインター。

*refTime*<br/>
[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトへの参照。

### <a name="return-value"></a>戻り値

成功した場合は0以外の。失敗した場合は0。 `GetLastWriteTime` このオブジェクトで [FindNextFile](#findnextfile) が呼び出されたことがない場合にのみ、0を返し `CFileFind` ます。

### <a name="remarks"></a>解説

を呼び出す前に、 [FindNextFile](#findnextfile) を少なくとも1回呼び出す必要があり `GetLastWriteTime` ます。

> [!NOTE]
> すべてのファイルシステムで同じセマンティクスを使用して、この関数によって返されるタイムスタンプが実装されるわけではありません。 基になるファイルシステムまたはサーバーが time 属性の保持をサポートしていない場合、この関数は、他のタイムスタンプ関数から返される値と同じ値を返すことがあります。 時刻形式の詳細については、 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 構造体を参照してください。 一部のオペレーティングシステムでは、返された時間は、コンピューターのローカルのタイムゾーンのファイルの場所にあります。 詳細については、Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API に関する説明を参照してください。

### <a name="example"></a>例

  [CFileFind:: GetLength](#getlength)の例を参照してください。

## <a name="cfilefindgetlength"></a><a name="getlength"></a> CFileFind:: GetLength

このメンバー関数を呼び出して、検出されたファイルの長さをバイト単位で取得します。

```
ULONGLONG GetLength() const;
```

### <a name="return-value"></a>戻り値

検出されたファイルの長さ (バイト単位)。

### <a name="remarks"></a>解説

を呼び出す前に、 [FindNextFile](#findnextfile) を少なくとも1回呼び出す必要があり `GetLength` ます。

`GetLength` Win32 構造体 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) を使用して、ファイルサイズの値を取得して返します (バイト単位)。

> [!NOTE]
> MFC 7.0 の As では、は `GetLength` 64 ビットの整数型をサポートしています。 この新しいバージョンのライブラリでビルドされた既存のコードでは、切り捨ての警告が発生する可能性があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#33](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]

## <a name="cfilefindgetroot"></a><a name="getroot"></a> CFileFind:: GetRoot

検出されたファイルのルートを取得するには、このメンバー関数を呼び出します。

```
virtual CString GetRoot() const;
```

### <a name="return-value"></a>戻り値

アクティブな検索のルート。

### <a name="remarks"></a>解説

を呼び出す前に、 [FindNextFile](#findnextfile) を少なくとも1回呼び出す必要があり `GetRoot` ます。

このメンバー関数は、検索を開始するために使用されるドライブ指定子とパス名を返します。 たとえば、を指定して [FindFile](#findfile) を呼び出すと、によって `*.dat` `GetRoot` 空の文字列が返されます。 などのパスを `c:\windows\system\*.dll` 結果に渡す `FindFile` `GetRoot` `c:\windows\system\` 。

### <a name="example"></a>例

  [CFileFind:: GetFileName](#getfilename)の例を参照してください。

## <a name="cfilefindisarchived"></a><a name="isarchived"></a> CFileFind:: IsArchived 済み

見つかったファイルがアーカイブされているかどうかを判断するには、このメンバー関数を呼び出します。

```
BOOL IsArchived() const;
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

アプリケーションは、バックアップまたは削除されるアーカイブファイルを、 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 構造体で指定されたファイル属性 FILE_ATTRIBUTE_ARCHIVE でマークします。

を呼び出す前に、 [FindNextFile](#findnextfile) を少なくとも1回呼び出す必要があり `IsArchived` ます。

ファイル属性の完全な一覧については、「メンバー関数 [MatchesMask](#matchesmask) 」を参照してください。

### <a name="example"></a>例

  [CFileFind:: GetLength](#getlength)の例を参照してください。

## <a name="cfilefindiscompressed"></a><a name="iscompressed"></a> CFileFind:: IsCompressed

見つかったファイルが圧縮されているかどうかを判断するには、このメンバー関数を呼び出します。

```
BOOL IsCompressed() const;
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

圧縮ファイルは、 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 構造で識別されたファイル属性である FILE_ATTRIBUTE_COMPRESSED でマークされます。 ファイルの場合、この属性はファイル内のすべてのデータが圧縮されていることを示します。 ディレクトリの場合、この属性は、新しく作成されたファイルおよびサブディレクトリの圧縮が既定値であることを示します。

を呼び出す前に、 [FindNextFile](#findnextfile) を少なくとも1回呼び出す必要があり `IsCompressed` ます。

ファイル属性の完全な一覧については、「メンバー関数 [MatchesMask](#matchesmask) 」を参照してください。

### <a name="example"></a>例

  [CFileFind:: GetLength](#getlength)の例を参照してください。

## <a name="cfilefindisdirectory"></a><a name="isdirectory"></a> CFileFind:: IsDirectory

見つかったファイルがディレクトリであるかどうかを判断するには、このメンバー関数を呼び出します。

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ディレクトリであるファイルは、 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 構造で識別されたファイル属性 FILE_ATTRIBUTE_DIRECTORY でマークされます。

を呼び出す前に、 [FindNextFile](#findnextfile) を少なくとも1回呼び出す必要があり `IsDirectory` ます。

ファイル属性の完全な一覧については、「メンバー関数 [MatchesMask](#matchesmask) 」を参照してください。

### <a name="example"></a>例

この小さなプログラムは、C:\ 上のすべてのディレクトリを繰り返しします。ディレクトリの名前をドライブに出力します。

[!code-cpp[NVC_MFCFiles#34](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]

## <a name="cfilefindisdots"></a><a name="isdots"></a> CFileFind:: IsDots

ファイルの反復処理中に現在のディレクトリマーカーと親ディレクトリマーカーをテストするには、このメンバー関数を呼び出します。

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>戻り値

見つかったファイルの名前が "." または ".." である場合は0以外の値。見つかったファイルが実際にはディレクトリであることを示します。 それ以外の場合は0です。

### <a name="remarks"></a>解説

を呼び出す前に、 [FindNextFile](#findnextfile) を少なくとも1回呼び出す必要があり `IsDots` ます。

### <a name="example"></a>例

  [CFileFind:: IsDirectory](#isdirectory)の例を参照してください。

## <a name="cfilefindishidden"></a><a name="ishidden"></a> CFileFind:: IsHidden

検出されたファイルが非表示かどうかを判断するには、このメンバー関数を呼び出します。

```
BOOL IsHidden() const;
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

FILE_ATTRIBUTE_HIDDEN でマークされている隠しファイルは、 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 構造で識別されたファイル属性です。 隠しファイルは、通常のディレクトリの一覧には含まれません。

を呼び出す前に、 [FindNextFile](#findnextfile) を少なくとも1回呼び出す必要があり `IsHidden` ます。

ファイル属性の完全な一覧については、「メンバー関数 [MatchesMask](#matchesmask) 」を参照してください。

### <a name="example"></a>例

  [CFileFind:: GetLength](#getlength)の例を参照してください。

## <a name="cfilefindisnormal"></a><a name="isnormal"></a> CFileFind:: IsNormal

見つかったファイルが通常のファイルであるかどうかを判断するには、このメンバー関数を呼び出します。

```
BOOL IsNormal() const;
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

FILE_ATTRIBUTE_NORMAL でマークされたファイル。 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 構造体で識別されるファイル属性です。 通常のファイルには、他の属性は設定されていません。 他のすべてのファイル属性は、この属性をオーバーライドします。

を呼び出す前に、 [FindNextFile](#findnextfile) を少なくとも1回呼び出す必要があり `IsNormal` ます。

ファイル属性の完全な一覧については、「メンバー関数 [MatchesMask](#matchesmask) 」を参照してください。

### <a name="example"></a>例

  [CFileFind:: GetLength](#getlength)の例を参照してください。

## <a name="cfilefindisreadonly"></a><a name="isreadonly"></a> CFileFind:: IsReadOnly

検出されたファイルが読み取り専用かどうかを判断するには、このメンバー関数を呼び出します。

```
BOOL IsReadOnly() const;
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

読み取り専用ファイルは、 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 構造で識別されたファイル属性 FILE_ATTRIBUTE_READONLY でマークされます。 アプリケーションはこのようなファイルを読み取ることができますが、書き込みや削除を行うことはできません。

を呼び出す前に、 [FindNextFile](#findnextfile) を少なくとも1回呼び出す必要があり `IsReadOnly` ます。

ファイル属性の完全な一覧については、「メンバー関数 [MatchesMask](#matchesmask) 」を参照してください。

### <a name="example"></a>例

  [CFileFind:: GetLength](#getlength)の例を参照してください。

## <a name="cfilefindissystem"></a><a name="issystem"></a> CFileFind:: Issystem で

検出されたファイルがシステムファイルであるかどうかを判断するには、このメンバー関数を呼び出します。

```
BOOL IsSystem() const;
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

システムファイルは FILE_ATTRIBUTE_SYSTEM でマークされます。これは、 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 構造体で識別されるファイル属性です。 システムファイルは、オペレーティングシステムの一部であるか、オペレーティングシステムによって排他的に使用されます。

を呼び出す前に、 [FindNextFile](#findnextfile) を少なくとも1回呼び出す必要があり `IsSystem` ます。

ファイル属性の完全な一覧については、「メンバー関数 [MatchesMask](#matchesmask) 」を参照してください。

### <a name="example"></a>例

  [CFileFind:: GetLength](#getlength)の例を参照してください。

## <a name="cfilefindistemporary"></a><a name="istemporary"></a> CFileFind:: IsTemporary

このメンバー関数を呼び出して、見つかったファイルが一時ファイルであるかどうかを確認します。

```
BOOL IsTemporary() const;
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

一時ファイルは、 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 構造で識別されたファイル属性である FILE_ATTRIBUTE_TEMPORARY でマークされます。 一時ストレージには一時ファイルが使用されます。 アプリケーションは、絶対に必要な場合にのみファイルに書き込む必要があります。 ファイルはすぐに削除されるため、ファイルのデータのほとんどは、メディアにフラッシュされることなくメモリに残ります。

を呼び出す前に、 [FindNextFile](#findnextfile) を少なくとも1回呼び出す必要があり `IsTemporary` ます。

ファイル属性の完全な一覧については、「メンバー関数 [MatchesMask](#matchesmask) 」を参照してください。

### <a name="example"></a>例

  [CFileFind:: GetLength](#getlength)の例を参照してください。

## <a name="cfilefindm_ptm"></a><a name="m_ptm"></a> CFileFind:: m_pTM

オブジェクトへのポインター `CAtlTransactionManager` 。

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>解説

## <a name="cfilefindmatchesmask"></a><a name="matchesmask"></a> CFileFind::MatchesMask

検出されたファイルのファイル属性をテストするには、このメンバー関数を呼び出します。

```
virtual BOOL MatchesMask(DWORD dwMask) const;
```

### <a name="parameters"></a>パラメーター

*dwMask*<br/>
検出されたファイルの [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 構造体で識別される1つ以上のファイル属性を指定します。 複数の属性を検索するには、ビットごとの OR (&#124;) 演算子を使用します。 次の属性の任意の組み合わせを使用できます。

- ファイルがアーカイブファイルで FILE_ATTRIBUTE_ARCHIVE。 アプリケーションでは、この属性を使用して、バックアップまたは削除するファイルをマークします。

- FILE_ATTRIBUTE_COMPRESSED ファイルまたはディレクトリが圧縮されていることを示します。 ファイルの場合、これはファイル内のすべてのデータが圧縮されることを意味します。 ディレクトリの場合、これは、新しく作成されたファイルおよびサブディレクトリの既定の圧縮であることを意味します。

- FILE_ATTRIBUTE_DIRECTORY ファイルがディレクトリであることを示します。

- ファイルに他の属性が設定されていない FILE_ATTRIBUTE_NORMAL。 この属性は、単独で使用した場合にのみ有効です。 他のすべてのファイル属性は、この属性をオーバーライドします。

- FILE_ATTRIBUTE_HIDDEN ファイルが非表示になっています。 通常のディレクトリの一覧に含めることはできません。

- FILE_ATTRIBUTE_READONLY ファイルは読み取り専用です。 アプリケーションはファイルを読み取ることができますが、書き込むことや削除することはできません。

- ファイルがの一部であるか、オペレーティングシステムによって排他的に使用されて FILE_ATTRIBUTE_SYSTEM。

- 一時ストレージにファイルが使用されて FILE_ATTRIBUTE_TEMPORARY。 アプリケーションは、絶対に必要な場合にのみファイルに書き込む必要があります。 ファイルはすぐに削除されるため、ファイルのデータのほとんどは、メディアにフラッシュされることなくメモリに残ります。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 拡張されたエラー情報を取得するには、Win32 関数 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)を呼び出します。

### <a name="remarks"></a>解説

を呼び出す前に、 [FindNextFile](#findnextfile) を少なくとも1回呼び出す必要があり `MatchesMask` ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#35](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CFtpFileFind クラス](../../mfc/reference/cftpfilefind-class.md)<br/>
[CGopherFileFind クラス](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile クラス](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpFile クラス](../../mfc/reference/chttpfile-class.md)
