---
title: クラスを検索します。
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
ms.openlocfilehash: f01aa84593afed5a4f2f102da7d161ad42917080
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373873"
---
# <a name="cfilefind-class"></a>クラスを検索します。

ローカル ファイル検索を実行し、インターネット ファイル検索を実行する[CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)および[CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)の基本クラスです。

## <a name="syntax"></a>構文

```
class CFileFind : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ファイル検索::Cファイル検索](#cfilefind)|`CFileFind` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ファイル検索::閉じる](#close)|検索要求を閉じます。|
|[ファイル検索::ファイルを検索します。](#findfile)|指定したファイル名をディレクトリで検索します。|
|[ファイル検索:次のファイルを検索します。](#findnextfile)|[FindFile](#findfile)への以前の呼び出しからファイル検索を続行します。|
|[ファイル検索::取得作成時間](#getcreationtime)|ファイルが作成された時刻を取得します。|
|[ファイル検索::ファイル名を取得します。](#getfilename)|見つかったファイルの名前 (拡張子を含む) を取得します。|
|[ファイル検索::ファイルパスを取得します。](#getfilepath)|見つかったファイルのパス全体を取得します。|
|[ファイル検索::ファイルタイトルを取得します。](#getfiletitle)|見つかったファイルのタイトルを取得します。 タイトルには拡張子は含まれません。|
|[ファイル検索::ファイルのURLを取得します。](#getfileurl)|見つかったファイルの URL (ファイル パスを含む) を取得します。|
|[ファイル検索::取得ラストアクセスタイム](#getlastaccesstime)|ファイルが最後にアクセスされた時刻を取得します。|
|[ファイル検索::取得ラストライトタイム](#getlastwritetime)|ファイルが最後に変更され、保存された時刻を取得します。|
|[ファイル検索::取得長](#getlength)|見つかったファイルの長さ (バイト単位) を取得します。|
|[ファイル検索::ゲットルート](#getroot)|見つかったファイルのルート ディレクトリを取得します。|
|[ファイル検索::アーカイブ](#isarchived)|見つかったファイルをアーカイブするかどうかを決定します。|
|[ファイル検索::IsCompress](#iscompressed)|見つかったファイルを圧縮するかどうかを指定します。|
|[ファイル検索::IsDirectory](#isdirectory)|見つかったファイルがディレクトリかどうかを判断します。|
|[ファイル検索::イズドット](#isdots)|見つかったファイルの名前が、実際にディレクトリであることを示す "." または "." の名前かどうかを判断します。|
|[ファイル検索::IsHidden](#ishidden)|見つかったファイルが非表示かどうかを判断します。|
|[ファイル検索::IsNormal](#isnormal)|見つかったファイルが通常のファイルであるかどうかを判断します (つまり、他の属性はありません)。|
|[ファイル検索::読み取り専用](#isreadonly)|見つかったファイルが読み取り専用かどうかを判断します。|
|[ファイル検索::システム](#issystem)|見つかったファイルがシステム ファイルかどうかを判断します。|
|[ファイル検索::一時的](#istemporary)|見つかったファイルが一時的なものかどうかを判断します。|
|[ファイル検索::マッチマスク](#matchesmask)|検出するファイルの必要なファイル属性を示します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[ファイル検索::クローズコンテキスト](#closecontext)|現在の検索ハンドルで指定されたファイルを閉じます。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[ファイル検索::m_pTM](#m_ptm)|`CAtlTransactionManager`オブジェクトへのポインター。|

## <a name="remarks"></a>解説

`CFileFind`には、検索を開始し、ファイルを検索し、ファイルのタイトル、名前、またはパスを返すメンバー関数が含まれます。 インターネット検索の場合、メンバー関数[GetFileURL は](#getfileurl)ファイルの URL を返します。

`CFileFind`は、特定のサーバーの種類を検索するために設計された他の 2`CGopherFileFind`つの MFC クラスの基本クラス`CFtpFileFind`です。 これらの 3 つのクラスを組み合わせることで、サーバー プロトコル、ファイルの種類、または場所に関係なく、ローカル マシンまたはリモート サーバー上で、クライアントがシームレスにファイルを検索できます。

次のコードは、現在のディレクトリにあるすべてのファイルを列挙し、各ファイルの名前を出力します。

[!code-cpp[NVC_MFCFiles#31](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]

このコードでは、この例を単純にするために、C++ 標準`cout`ライブラリ クラスを使用します。 この`cout`行は、 グラフィカル ユーザー`CListBox::AddString`インターフェイスを持つプログラムなどでの 呼び出しに置き換えることができます。

その他の WinInet`CFileFind`クラスの使用方法の詳細については[、「WinInet を使用したインターネット プログラミング](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CFileFind`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="cfilefindcfilefind"></a><a name="cfilefind"></a>ファイル検索::Cファイル検索

このメンバー関数は、オブジェクトが`CFileFind`構築されるときに呼び出されます。

```
CFileFind();
CFileFind(CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>パラメーター

*Ptm*<br/>
CAtlTransactionManager オブジェクトへのポインター。

### <a name="example"></a>例

  [ファイル検索::GetFileName](#getfilename)の例を参照してください。

## <a name="cfilefindclose"></a><a name="close"></a>ファイル検索::閉じる

検索を終了し、コンテキストをリセットし、すべてのリソースを解放するには、このメンバー関数を呼び出します。

```
void Close();
```

### <a name="remarks"></a>解説

を呼`Close`び出した後は[、FindFile](#findfile) `CFileFind`を呼び出す前に新しいインスタンスを作成する必要はありません。

### <a name="example"></a>例

  [ファイル検索::GetFileName](#getfilename)の例を参照してください。

## <a name="cfilefindclosecontext"></a><a name="closecontext"></a>ファイル検索::クローズコンテキスト

現在の検索ハンドルで指定されたファイルを閉じます。

```
virtual void CloseContext();
```

### <a name="remarks"></a>解説

検索ハンドルの現在の値で指定されたファイルを閉じます。 既定の動作を変更するには、この関数をオーバーライドします。

有効な検索ハンドルを取得するには、少なくとも 1 回は[FindFile](#findfile)関数または[FindNextFile](#findnextfile)関数を呼び出す必要があります。 および`FindFile``FindNextFile`関数は、検索ハンドルを使用して、指定された名前と一致する名前のファイルを検索します。

## <a name="cfilefindfindfile"></a><a name="findfile"></a>ファイル検索::ファイルを検索します。

ファイル検索を開くには、このメンバー関数を呼び出します。

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwUnused = 0);
```

### <a name="parameters"></a>パラメーター

*名前*<br/>
検索するファイルの名前を含む文字列へのポインター。 *に*NULL を`FindFile`渡すと、ワイルドカード (*.\*) 検索が行われます。

*dw未使用*<br/>
派生クラスで`FindFile`ポリモーフィックにするために予約されています。 0 を指定する必要があります。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 拡張エラー情報を取得するには、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)を呼び出します。

### <a name="remarks"></a>解説

ファイル検索`FindFile`を開始するために呼び出した後[、FindNextFile](#findnextfile)を呼び出して後続のファイルを取得します。 次のいずれかの属性`FindNextFile`メンバー関数を呼び出す前に、少なくとも 1 回は呼び出す必要があります。

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [ファイルタイトルを取得します。](#getfiletitle)

- [ファイルパスを取得します。](#getfilepath)

- [ファイルの URL を取得します。](#getfileurl)

- [ラストアクセスタイム](#getlastaccesstime)

- [書き込み時間](#getlastwritetime)

- [長さを取得します。](#getlength)

- [GetRoot](#getroot)

- [アーカイブ済み](#isarchived)

- [IsCompressed](#iscompressed)

- [ディレクトリ](#isdirectory)

- [イスドット](#isdots)

- [IsHidden](#ishidden)

- [正常](#isnormal)

- [IsReadOnly](#isreadonly)

- [IsSystem](#issystem)

- [一時的な](#istemporary)

- [マッチマスク](#matchesmask)

### <a name="example"></a>例

  [CFileFind::IsDirectory](#isdirectory)の例を参照してください。

## <a name="cfilefindfindnextfile"></a><a name="findnextfile"></a>ファイル検索:次のファイルを検索します。

FindFile への前回の呼び出しからファイル検索を[FindFile](#findfile)続行するには、このメンバー関数を呼び出します。

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>戻り値

ファイルが多い場合は 0 以外。見つかったファイルがディレクトリ内の最後のファイルである場合、またはエラーが発生した場合は 0。 拡張エラー情報を取得するには、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)を呼び出します。 見つかったファイルがディレクトリ内の最後のファイルである場合、または一致するファイルが見つからない場合`GetLastError`、関数はERROR_NO_MORE_FILESを返します。

### <a name="remarks"></a>解説

次のいずれかの属性`FindNextFile`メンバー関数を呼び出す前に、少なくとも 1 回は呼び出す必要があります。

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [ファイルタイトルを取得します。](#getfiletitle)

- [ファイルパスを取得します。](#getfilepath)

- [ファイルの URL を取得します。](#getfileurl)

- [ラストアクセスタイム](#getlastaccesstime)

- [書き込み時間](#getlastwritetime)

- [長さを取得します。](#getlength)

- [GetRoot](#getroot)

- [アーカイブ済み](#isarchived)

- [IsCompressed](#iscompressed)

- [ディレクトリ](#isdirectory)

- [イスドット](#isdots)

- [IsHidden](#ishidden)

- [正常](#isnormal)

- [IsReadOnly](#isreadonly)

- [IsSystem](#issystem)

- [一時的な](#istemporary)

- [マッチマスク](#matchesmask)

`FindNextFile`関数をラップ[します。](/windows/win32/api/fileapi/nf-fileapi-findnextfilew)

### <a name="example"></a>例

  [CFileFind::IsDirectory](#isdirectory)の例を参照してください。

## <a name="cfilefindgetcreationtime"></a><a name="getcreationtime"></a>ファイル検索::取得作成時間

指定したファイルが作成された時刻を取得します。

```
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;
virtual BOOL GetCreationTime(CTime& refTime) const;
```

### <a name="parameters"></a>パラメーター

*スタンプ*<br/>
ファイルが作成された時刻を含む[FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime)構造体へのポインター。

*時間*<br/>
[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトへの参照。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外。失敗した場合は 0。 `GetCreationTime`この`CFileFind`オブジェクトで[FindNextFile](#findnextfile)が呼び出されていない場合にのみ 0 を返します。

### <a name="remarks"></a>解説

を呼び出す前に、少なくとも`GetCreationTime`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

> [!NOTE]
> すべてのファイルシステムが同じセマンティクスを使用して、この関数によって返されるタイム・スタンプを実装するわけではありません。 この関数は、基礎となるファイルシステムまたはサーバが time 属性の保持をサポートしていない場合、他のタイム・スタンプ関数から戻される値と同じ値を返す場合があります。 時刻形式については[、WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw)の構造を参照してください。 一部のオペレーティング・システムでは、戻り時刻は、ファイルが置かれたマシンに対してローカルな時間帯にあります。 詳細については、Win32[ファイルタイムをローカルファイル時間](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime)API を参照してください。

### <a name="example"></a>例

  [CFileFind::GetLength](#getlength)の例を参照してください。

## <a name="cfilefindgetfilename"></a><a name="getfilename"></a>ファイル検索::ファイル名を取得します。

見つかったファイルの名前を取得します。

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>戻り値

最近見つかったファイルの名前。

### <a name="remarks"></a>解説

GetFileName を呼び出す前に、少なくとも 1 回は[FindNextFile](#findnextfile)を呼び出す必要があります。

`GetFileName`は、ファイル名`CFileFind`の形式を返す 3 つのメンバー関数のうちの 1 つです。 次のリストでは、3 つの内容とその違いについて説明します。

- `GetFileName`は、拡張子を含むファイル名を返します。 たとえば`GetFileName`*、c:\myhtml\myfile.txt*ファイルに関するユーザー メッセージを生成する呼び出しは、ファイル名*myfile.txt*を返します。

- [ファイルの](#getfilepath)パス全体を返します。 たとえば`GetFilePath`*、c:\myhtml\myfile.txt*ファイルに関するユーザー メッセージを生成するために呼び出すと、ファイル パス*c:\myhtml\myfile.txt*が返されます。

- [ファイル](#getfiletitle)名を返します。 たとえば`GetFileTitle`*、c:\myhtml\myfile.txt*ファイルに関するユーザー メッセージを生成する呼び出しは、ファイル タイトル*myfile*を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#32](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]

## <a name="cfilefindgetfilepath"></a><a name="getfilepath"></a>ファイル検索::ファイルパスを取得します。

指定したファイルの完全パスを取得します。

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>戻り値

指定したファイルのパス。

### <a name="remarks"></a>解説

を呼び出す前に、少なくとも`GetFilePath`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

`GetFilePath`は、ファイル名`CFileFind`の形式を返す 3 つのメンバー関数のうちの 1 つです。 次のリストでは、3 つの内容とその違いについて説明します。

- [ファイル名を](#getfilename)返します。 たとえば`GetFileName`*、c:\myhtml\myfile.txt*ファイルに関するユーザー メッセージを生成する呼び出しは、ファイル名*myfile.txt*を返します。

- `GetFilePath`は、ファイルのパス全体を返します。 たとえば、ファイルに`GetFilePath`関するユーザー メッセージを生成する`c:\myhtml\myfile.txt`呼び出し`c:\myhtml\myfile.txt`は、ファイル パスを返します。

- [ファイル](#getfiletitle)名を返します。 たとえば`GetFileTitle`*、c:\myhtml\myfile.txt*ファイルに関するユーザー メッセージを生成する呼び出しは、ファイル タイトル*myfile*を返します。

### <a name="example"></a>例

  [ファイル検索::GetFileName](#getfilename)の例を参照してください。

## <a name="cfilefindgetfiletitle"></a><a name="getfiletitle"></a>ファイル検索::ファイルタイトルを取得します。

見つかったファイルのタイトルを取得します。

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>戻り値

ファイルのタイトル。

### <a name="remarks"></a>解説

を呼び出す前に、少なくとも`GetFileTitle`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

`GetFileTitle`は、ファイル名`CFileFind`の形式を返す 3 つのメンバー関数のうちの 1 つです。 次のリストでは、3 つの内容とその違いについて説明します。

- [ファイル名を](#getfilename)返します。 たとえば`GetFileName`*、c:\myhtml\myfile.txt*ファイルに関するユーザー メッセージを生成する呼び出しは、ファイル名*myfile.txt*を返します。

- [ファイルの](#getfilepath)パス全体を返します。 たとえば`GetFilePath`*、c:\myhtml\myfile.txt*ファイルに関するユーザー メッセージを生成するために呼び出すと、ファイル パス*c:\myhtml\myfile.txt*が返されます。

- `GetFileTitle`は、ファイル拡張子を除くファイル名を返します。 たとえば`GetFileTitle`*、c:\myhtml\myfile.txt*ファイルに関するユーザー メッセージを生成する呼び出しは、ファイル タイトル*myfile*を返します。

### <a name="example"></a>例

  [ファイル検索::GetFileName](#getfilename)の例を参照してください。

## <a name="cfilefindgetfileurl"></a><a name="getfileurl"></a>ファイル検索::ファイルのURLを取得します。

指定した URL を取得するには、このメンバー関数を呼び出します。

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>戻り値

完全な URL。

### <a name="remarks"></a>解説

を呼び出す前に、少なくとも`GetFileURL`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

`GetFileURL`はメンバー関数[GetFilePath](#getfilepath)に似ていますが、URL がフォームで返`file://path`される点が異なっています。 たとえば *、myfile.txt*の完全な URL を取得するために呼`file://c:\myhtml\myfile.txt`び出すと`GetFileURL`、URL が返されます。

### <a name="example"></a>例

  [ファイル検索::GetFileName](#getfilename)の例を参照してください。

## <a name="cfilefindgetlastaccesstime"></a><a name="getlastaccesstime"></a>ファイル検索::取得ラストアクセスタイム

指定したファイルが最後にアクセスされた時刻を取得します。

```
virtual BOOL GetLastAccessTime(CTime& refTime) const;
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;
```

### <a name="parameters"></a>パラメーター

*時間*<br/>
[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトへの参照。

*スタンプ*<br/>
ファイルが最後にアクセスされた時刻を含む[FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime)構造体へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外。失敗した場合は 0。 `GetLastAccessTime`この`CFileFind`オブジェクトで[FindNextFile](#findnextfile)が呼び出されていない場合にのみ 0 を返します。

### <a name="remarks"></a>解説

を呼び出す前に、少なくとも`GetLastAccessTime`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

> [!NOTE]
> すべてのファイルシステムが同じセマンティクスを使用して、この関数によって返されるタイム・スタンプを実装するわけではありません。 この関数は、基礎となるファイルシステムまたはサーバが time 属性の保持をサポートしていない場合、他のタイム・スタンプ関数から戻される値と同じ値を返す場合があります。 時刻形式については[、WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw)の構造を参照してください。 一部のオペレーティング・システムでは、戻り時刻は、ファイルが置かれたマシンに対してローカルな時間帯にあります。 詳細については、Win32[ファイルタイムをローカルファイル時間](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime)API を参照してください。

### <a name="example"></a>例

  [CFileFind::GetLength](#getlength)の例を参照してください。

## <a name="cfilefindgetlastwritetime"></a><a name="getlastwritetime"></a>ファイル検索::取得ラストライトタイム

ファイルが最後に変更された時刻を取得します。

```
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;
virtual BOOL GetLastWriteTime(CTime& refTime) const;
```

### <a name="parameters"></a>パラメーター

*スタンプ*<br/>
ファイルが最後に書き込まれた時刻を含む[FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime)構造体へのポインター。

*時間*<br/>
[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトへの参照。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外。失敗した場合は 0。 `GetLastWriteTime`この`CFileFind`オブジェクトで[FindNextFile](#findnextfile)が呼び出されていない場合にのみ 0 を返します。

### <a name="remarks"></a>解説

を呼び出す前に、少なくとも`GetLastWriteTime`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

> [!NOTE]
> すべてのファイルシステムが同じセマンティクスを使用して、この関数によって返されるタイム・スタンプを実装するわけではありません。 この関数は、基礎となるファイルシステムまたはサーバが time 属性の保持をサポートしていない場合、他のタイム・スタンプ関数から戻される値と同じ値を返す場合があります。 時刻形式については[、WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw)の構造を参照してください。 一部のオペレーティング・システムでは、戻り時刻は、ファイルが置かれたマシンに対してローカルな時間帯にあります。 詳細については、Win32[ファイルタイムをローカルファイル時間](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime)API を参照してください。

### <a name="example"></a>例

  [CFileFind::GetLength](#getlength)の例を参照してください。

## <a name="cfilefindgetlength"></a><a name="getlength"></a>ファイル検索::取得長

見つかったファイルの長さをバイト単位で取得します。

```
ULONGLONG GetLength() const;
```

### <a name="return-value"></a>戻り値

見つかったファイルの長さ (バイト単位)。

### <a name="remarks"></a>解説

を呼び出す前に、少なくとも`GetLength`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

`GetLength`Win32 構造体[WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw)を使用して、ファイル サイズの値をバイト単位で取得および返します。

> [!NOTE]
> MFC 7.0 では`GetLength`、64 ビット整数型をサポートしています。 以前にこの新しいバージョンのライブラリでビルドされた既存のコードは、切り捨ての警告を発生する可能性があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#33](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]

## <a name="cfilefindgetroot"></a><a name="getroot"></a>ファイル検索::ゲットルート

見つかったファイルのルートを取得します。

```
virtual CString GetRoot() const;
```

### <a name="return-value"></a>戻り値

アクティブな検索のルート。

### <a name="remarks"></a>解説

を呼び出す前に、少なくとも`GetRoot`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

このメンバー関数は、検索を開始するために使用されるドライブ指定子とパス名を返します。 たとえば[、FindFile](#findfile)を呼`*.dat`び出`GetRoot`すと、空の文字列が返されます。 などの`c:\windows\system\*.dll`パスを返す結果`FindFile``GetRoot`に渡す。 `c:\windows\system\`

### <a name="example"></a>例

  [ファイル検索::GetFileName](#getfilename)の例を参照してください。

## <a name="cfilefindisarchived"></a><a name="isarchived"></a>ファイル検索::アーカイブ

見つかったファイルがアーカイブされているかどうかを確認します。

```
BOOL IsArchived() const;
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

アプリケーションは、アーカイブ・ファイル (バックアップまたは削除) を[、WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw)構造で識別されるファイル属性でFILE_ATTRIBUTE_ARCHIVEにマークします。

を呼び出す前に、少なくとも`IsArchived`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

ファイル属性の完全なリストについては、メンバー関数[MatchesMask](#matchesmask)を参照してください。

### <a name="example"></a>例

  [CFileFind::GetLength](#getlength)の例を参照してください。

## <a name="cfilefindiscompressed"></a><a name="iscompressed"></a>ファイル検索::IsCompress

見つかったファイルが圧縮されているかどうかを調べます。

```
BOOL IsCompressed() const;
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

圧縮ファイルは[、WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw)構造で識別されるファイル属性であるFILE_ATTRIBUTE_COMPRESSEDでマークされます。 ファイルの場合、この属性は、ファイル内のすべてのデータが圧縮されていることを示します。 ディレクトリの場合、この属性は、圧縮が新しく作成されたファイルおよびサブディレクトリのデフォルトであることを示します。

を呼び出す前に、少なくとも`IsCompressed`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

ファイル属性の完全なリストについては、メンバー関数[MatchesMask](#matchesmask)を参照してください。

### <a name="example"></a>例

  [CFileFind::GetLength](#getlength)の例を参照してください。

## <a name="cfilefindisdirectory"></a><a name="isdirectory"></a>ファイル検索::IsDirectory

見つかったファイルがディレクトリかどうかを調べます。

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ディレクトリーであるファイルには[、WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw)構造で指定されたファイル属性FILE_ATTRIBUTE_DIRECTORYマークが付けられます。

を呼び出す前に、少なくとも`IsDirectory`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

ファイル属性の完全なリストについては、メンバー関数[MatchesMask](#matchesmask)を参照してください。

### <a name="example"></a>例

この小さなプログラムは、C:\ のすべてのディレクトリを再帰的に行います。ドライブを作成し、ディレクトリの名前を出力します。

[!code-cpp[NVC_MFCFiles#34](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]

## <a name="cfilefindisdots"></a><a name="isdots"></a>ファイル検索::イズドット

ファイルを反復処理しながら、現在のディレクトリと親ディレクトリ マーカーをテストします。

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>戻り値

見つかったファイルの名前が "." または ".." の場合は 0 以外の値を指定します。 それ以外の場合は 0。

### <a name="remarks"></a>解説

を呼び出す前に、少なくとも`IsDots`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

### <a name="example"></a>例

  [CFileFind::IsDirectory](#isdirectory)の例を参照してください。

## <a name="cfilefindishidden"></a><a name="ishidden"></a>ファイル検索::IsHidden

見つかったファイルが隠ぺいされているかどうかを調べます。

```
BOOL IsHidden() const;
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

隠しファイルは、FILE_ATTRIBUTE_HIDDENでマークされ[、WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw)構造で識別されるファイル属性です。 隠しファイルは、通常のディレクトリ一覧には含まれません。

を呼び出す前に、少なくとも`IsHidden`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

ファイル属性の完全なリストについては、メンバー関数[MatchesMask](#matchesmask)を参照してください。

### <a name="example"></a>例

  [CFileFind::GetLength](#getlength)の例を参照してください。

## <a name="cfilefindisnormal"></a><a name="isnormal"></a>ファイル検索::IsNormal

見つかったファイルが通常のファイルかどうかを確認します。

```
BOOL IsNormal() const;
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

FILE_ATTRIBUTE_NORMALでマークされたファイル[、WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw)構造で識別されるファイル属性。 通常のファイルには、他の属性は設定されません。 その他のファイル属性はすべて、この属性をオーバーライドします。

を呼び出す前に、少なくとも`IsNormal`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

ファイル属性の完全なリストについては、メンバー関数[MatchesMask](#matchesmask)を参照してください。

### <a name="example"></a>例

  [CFileFind::GetLength](#getlength)の例を参照してください。

## <a name="cfilefindisreadonly"></a><a name="isreadonly"></a>ファイル検索::読み取り専用

見つかったファイルが読み取り専用かどうかを調べます。

```
BOOL IsReadOnly() const;
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

読み取り専用ファイルは[、WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw)構造で指定されたファイル属性であるFILE_ATTRIBUTE_READONLYでマークされます。 アプリケーションはこのようなファイルを読み取ることができますが、書き込みや削除はできません。

を呼び出す前に、少なくとも`IsReadOnly`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

ファイル属性の完全なリストについては、メンバー関数[MatchesMask](#matchesmask)を参照してください。

### <a name="example"></a>例

  [CFileFind::GetLength](#getlength)の例を参照してください。

## <a name="cfilefindissystem"></a><a name="issystem"></a>ファイル検索::システム

見つかったファイルがシステム ファイルかどうかを調べます。

```
BOOL IsSystem() const;
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

システム ファイルは[、WIN32_FIND_DATA FILE_ATTRIBUTE_SYSTEM](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw)でマークされます。 システム ファイルは、オペレーティング システムの一部であるか、またはオペレーティング システムによって排他的に使用されます。

を呼び出す前に、少なくとも`IsSystem`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

ファイル属性の完全なリストについては、メンバー関数[MatchesMask](#matchesmask)を参照してください。

### <a name="example"></a>例

  [CFileFind::GetLength](#getlength)の例を参照してください。

## <a name="cfilefindistemporary"></a><a name="istemporary"></a>ファイル検索::一時的

見つかったファイルが一時ファイルかどうかを調べます。

```
BOOL IsTemporary() const;
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

一時ファイルは、FILE_ATTRIBUTE_TEMPORARYでマークされ[、WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw)構造で指定されたファイル属性です。 一時ファイルは、一時記憶域に使用されます。 アプリケーションは、絶対に必要な場合にのみファイルに書き込む必要があります。 ファイルのデータのほとんどは、メディアにフラッシュされずにメモリに残ります。

を呼び出す前に、少なくとも`IsTemporary`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

ファイル属性の完全なリストについては、メンバー関数[MatchesMask](#matchesmask)を参照してください。

### <a name="example"></a>例

  [CFileFind::GetLength](#getlength)の例を参照してください。

## <a name="cfilefindm_ptm"></a><a name="m_ptm"></a>ファイル検索::m_pTM

`CAtlTransactionManager`オブジェクトへのポインター。

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>解説

## <a name="cfilefindmatchesmask"></a><a name="matchesmask"></a>ファイル検索::マッチマスク

見つかったファイルのファイル属性をテストします。

```
virtual BOOL MatchesMask(DWORD dwMask) const;
```

### <a name="parameters"></a>パラメーター

*Dwmask*<br/>
見つかったファイルの[WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw)構造で識別される 1 つ以上のファイル属性を指定します。 複数の属性を検索するには、ビットごとの OR (&#124;) 演算子を使用します。 以下の属性の任意の組み合わせが可能です。

- FILE_ATTRIBUTE_ARCHIVE ファイルがアーカイブ ファイルです。 アプリケーションは、この属性を使用して、バックアップまたは削除用のファイルをマークします。

- FILE_ATTRIBUTE_COMPRESSED ファイルまたはディレクトリが圧縮されます。 ファイルの場合、ファイル内のすべてのデータが圧縮されます。 ディレクトリの場合、新しく作成されたファイルとサブディレクトリの圧縮がデフォルトになります。

- FILE_ATTRIBUTE_DIRECTORY ファイルはディレクトリです。

- FILE_ATTRIBUTE_NORMAL ファイルに他の属性が設定されていない。 この属性は、単独で使用する場合にのみ有効です。 その他のファイル属性はすべて、この属性をオーバーライドします。

- FILE_ATTRIBUTE_HIDDEN ファイルが非表示になっています。 通常のディレクトリリストには含まれません。

- FILE_ATTRIBUTE_READONLY ファイルは読み取り専用です。 アプリケーションはファイルを読み取ることができますが、書き込みや削除はできません。

- FILE_ATTRIBUTE_SYSTEM ファイルはオペレーティング システムの一部であるか、オペレーティング システムによって排他的に使用されます。

- FILE_ATTRIBUTE_TEMPORARY ファイルは一時記憶域に使用されています。 アプリケーションは、絶対に必要な場合にのみファイルに書き込む必要があります。 ファイルのデータのほとんどは、メディアにフラッシュされずにメモリに残ります。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 拡張エラー情報を取得するには、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)を呼び出します。

### <a name="remarks"></a>解説

を呼び出す前に、少なくとも`MatchesMask`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#35](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CFtpFileFind クラス](../../mfc/reference/cftpfilefind-class.md)<br/>
[CGopherFileFind クラス](../../mfc/reference/cgopherfilefind-class.md)<br/>
[クラス](../../mfc/reference/cinternetfile-class.md)<br/>
[クラス](../../mfc/reference/cgopherfile-class.md)<br/>
[クラス](../../mfc/reference/chttpfile-class.md)
