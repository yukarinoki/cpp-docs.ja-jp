---
title: CGopherFileFind クラス
ms.date: 11/04/2016
f1_keywords:
- CGopherFileFind
- AFXINET/CGopherFileFind
- AFXINET/CGopherFileFind::CGopherFileFind
- AFXINET/CGopherFileFind::FindFile
- AFXINET/CGopherFileFind::FindNextFile
- AFXINET/CGopherFileFind::GetCreationTime
- AFXINET/CGopherFileFind::GetLastAccessTime
- AFXINET/CGopherFileFind::GetLastWriteTime
- AFXINET/CGopherFileFind::GetLength
- AFXINET/CGopherFileFind::GetLocator
- AFXINET/CGopherFileFind::GetScreenName
- AFXINET/CGopherFileFind::IsDots
helpviewer_keywords:
- CGopherFileFind [MFC], CGopherFileFind
- CGopherFileFind [MFC], FindFile
- CGopherFileFind [MFC], FindNextFile
- CGopherFileFind [MFC], GetCreationTime
- CGopherFileFind [MFC], GetLastAccessTime
- CGopherFileFind [MFC], GetLastWriteTime
- CGopherFileFind [MFC], GetLength
- CGopherFileFind [MFC], GetLocator
- CGopherFileFind [MFC], GetScreenName
- CGopherFileFind [MFC], IsDots
ms.assetid: 8465a979-6323-496d-ab4b-e81383fb999d
ms.openlocfilehash: 7a42b99c919abd9098bff1897c4c5febf443314d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373679"
---
# <a name="cgopherfilefind-class"></a>CGopherFileFind クラス

gopher サーバーのインターネット ファイル検索を支援します。

> [!NOTE]
> クラス`CGopherConnection` `CGopherFile`、、`CGopherFileFind``CGopherLocator`およびメンバーは Windows XP プラットフォームでは動作しないため、非推奨になりましたが、以前のプラットフォームでは引き続き動作します。

## <a name="syntax"></a>構文

```
class CGopherFileFind : public CFileFind
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ファイル検索::CGopher ファイルの検索](#cgopherfilefind)|`CGopherFileFind` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ファイルの検索::ファイルの検索](#findfile)|gopher サーバー上のファイルを検索します。|
|[ファイル検索:次のファイルを検索します。](#findnextfile)|[FindFile](#findfile)への以前の呼び出しからファイル検索を続行します。|
|[ファイル検索::取得作成時間](#getcreationtime)|指定したファイルが作成された時刻を取得します。|
|[ファイル検索::取得ラストアクセスタイム](#getlastaccesstime)|指定したファイルが最後にアクセスされた時刻を取得します。|
|[ファイル検索::取得ラストライトタイム](#getlastwritetime)|指定したファイルが最後に書き込まれた時刻を取得します。|
|[ファイルを検索します。](#getlength)|見つかったファイルの長さ (バイト単位) を取得します。|
|[ファイル検索::ゲットロケーター](#getlocator)|オブジェクトを`CGopherLocator`取得します。|
|[ファイルを検索します。](#getscreenname)|gopher 画面の名前を取得します。|
|[ファイル検索::イズドット](#isdots)|ファイルを反復処理しながら、現在のディレクトリと親ディレクトリ マーカーをテストします。|

## <a name="remarks"></a>解説

`CGopherFileFind`には、検索を開始し、ファイルを検索して、ファイルの URL を返すメンバー関数が含まれます。

インターネットおよびローカル ファイル検索用に設計されたその他の MFC クラスには[、CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)と[CFileFind](../../mfc/reference/cfilefind-class.md)が含まれます。 これらのクラス`CGopherFileFind`を使用すると、サーバー プロトコル、ファイルの種類、または場所 (ローカル マシンまたはリモート サーバー) に関係なく、ユーザーが特定のファイルを検索するシームレスなメカニズムが提供されます。HTTP は検索に必要な直接ファイル操作をサポートしていないため、HTTP サーバー上で検索するための MFC クラスはありません。

> [!NOTE]
> `CGopherFileFind`は、その基本クラス[CFileFind](../../mfc/reference/cfilefind-class.md)の次のメンバー関数をサポートしていません。

- [GetRoot](../../mfc/reference/cfilefind-class.md#getroot)

- [GetFileName](../../mfc/reference/cfilefind-class.md#getfilename)

- [ファイルパスを取得します。](../../mfc/reference/cfilefind-class.md#getfilepath)

- [ファイルタイトルを取得します。](../../mfc/reference/cfilefind-class.md#getfiletitle)

- [ファイルの URL を取得します。](../../mfc/reference/cfilefind-class.md#getfileurl)

また、メンバー関数[IsDots](../../mfc/reference/cfilefind-class.md#isdots)と共に`CGopherFileFind``CFileFind`使用すると、常に FALSE になります。

その他の WinInet`CGopherFileFind`クラスの使用方法の詳細については[、「WinInet を使用したインターネット プログラミング](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFileFind](../../mfc/reference/cfilefind-class.md)

`CGopherFileFind`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

## <a name="cgopherfilefindcgopherfilefind"></a><a name="cgopherfilefind"></a>ファイル検索::CGopher ファイルの検索

このメンバー関数は、`CGopherFileFind`オブジェクトを構築するために呼び出されます。

```
explicit CGopherFileFind(
    CGopherConnection* pConnection,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>パラメーター

*pConnection*<br/>
[オブジェクト](../../mfc/reference/cgopherconnection-class.md)へのポインター。

*dw コンテキスト*<br/>
操作のコンテキスト識別子。 *dwContext*の詳細については **、「解説**」を参照してください。

### <a name="remarks"></a>解説

*dwContext*の既定値は、オブジェクトを作成した`CGopherFileFind` [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトからオブジェクトに MFC`CGopherFileFind`によって送信されます。 オブジェクトを`CGopherFileFind`作成する際、デフォルトをオーバーライドして、コンテキスト識別子を選択した値に設定できます。 コンテキスト識別子は、識別されるオブジェクトのステータスを提供するために[、CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)に返されます。 コンテキスト識別子の詳細については、「[インターネットの最初の手順: WinInet」](../../mfc/wininet-basics.md)を参照してください。

## <a name="cgopherfilefindfindfile"></a><a name="findfile"></a>ファイルの検索::ファイルの検索

gopher ファイルを検索するには、このメンバー関数を呼び出します。

```
virtual BOOL FindFile(
    CGopherLocator& refLocator,
    LPCTSTR pstrString,
    DWORD dwFlags = INTERNET_FLAG_RELOAD);

virtual BOOL FindFile(
    LPCTSTR pstrString,
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```

### <a name="parameters"></a>パラメーター

*リロケータ*<br/>
[CGopherLocator](../../mfc/reference/cgopherlocator-class.md)オブジェクトへの参照。

*文字列*<br/>
ファイル名を含む文字列へのポインター。

*dwFlags*<br/>
このセッションの処理方法を説明するフラグ。 有効なフラグは次のとおりです。

- INTERNET_FLAG_RELOAD ローカルにキャッシュされている場合でも、リモート サーバーからデータを取得します。

- INTERNET_FLAG_DONT_CACHE ローカルまたはゲートウェイにデータをキャッシュしません。

- INTERNET_FLAG_SECURE セキュア ソケット レイヤまたは PCT を使用して、ネットワーク上でセキュア なトランザクションを要求します。 このフラグは HTTP 要求にのみ適用されます。

- INTERNET_FLAG_USE_EXISTING 可能であれば、要求ごとに新しいセッションを作成するのではなく、`FindFile`サーバーへの既存の接続を再利用して新しい要求を行います。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 拡張エラー情報を取得するには、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)を呼び出します。

### <a name="remarks"></a>解説

最初の`FindFile`gopher オブジェクトを取得するために呼び出した後[、FindNextFile](#findnextfile)を呼び出して後続の gopher ファイルを取得できます。

## <a name="cgopherfilefindfindnextfile"></a><a name="findnextfile"></a>ファイル検索:次のファイルを検索します。

[CGopherFileFind::FindFile](#findfile)への呼び出しで開始されたファイル検索を続行するには、このメンバー関数を呼び出します。

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>戻り値

ファイルが多い場合は 0 以外。見つかったファイルがディレクトリ内の最後のファイルである場合、またはエラーが発生した場合は 0。 拡張エラー情報を取得するには、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)を呼び出します。 見つかったファイルがディレクトリ内の最後のファイルである場合、または一致するファイルが見つからない場合`GetLastError`、関数はERROR_NO_MORE_FILESを返します。

## <a name="cgopherfilefindgetcreationtime"></a><a name="getcreationtime"></a>ファイル検索::取得作成時間

現在のファイルの作成時刻を取得します。

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

成功した場合は 0 以外。失敗した場合は 0。 `GetCreationTime`この`CGopherFileFind`オブジェクトで[FindNextFile](#findnextfile)が呼び出されていない場合にのみ 0 を返します。

### <a name="remarks"></a>解説

を呼び出す前に、少なくとも`GetCreationTime`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

> [!NOTE]
> すべてのファイルシステムが同じセマンティクスを使用して、この関数によって返されるタイム・スタンプを実装するわけではありません。 この関数は、基礎となるファイルシステムまたはサーバが time 属性の保持をサポートしていない場合、他のタイム・スタンプ関数から戻される値と同じ値を返す場合があります。 時刻形式については[、WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw)の構造を参照してください。 一部のオペレーティング システムでは、返される時刻は、ファイルが配置されたコンピューターに対してローカルなタイム ゾーンにあります。 詳細については、Win32[ファイルタイムをローカルファイル時間](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime)API を参照してください。

## <a name="cgopherfilefindgetlastaccesstime"></a><a name="getlastaccesstime"></a>ファイル検索::取得ラストアクセスタイム

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

成功した場合は 0 以外。失敗した場合は 0。 `GetLastAccessTime`この`CGopherFileFind`オブジェクトで[FindNextFile](#findnextfile)が呼び出されていない場合にのみ 0 を返します。

### <a name="remarks"></a>解説

を呼び出す前に、少なくとも`GetLastAccessTime`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

> [!NOTE]
> すべてのファイルシステムが同じセマンティクスを使用して、この関数によって返されるタイム・スタンプを実装するわけではありません。 この関数は、基礎となるファイルシステムまたはサーバが time 属性の保持をサポートしていない場合、他のタイム・スタンプ関数から戻される値と同じ値を返す場合があります。 時刻形式については[、WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw)の構造を参照してください。 一部のオペレーティング システムでは、返される時刻は、ファイルが配置されたコンピューターに対してローカルなタイム ゾーンにあります。 詳細については、Win32[ファイルタイムをローカルファイル時間](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime)API を参照してください。

## <a name="cgopherfilefindgetlastwritetime"></a><a name="getlastwritetime"></a>ファイル検索::取得ラストライトタイム

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

成功した場合は 0 以外。失敗した場合は 0。 `GetLastWriteTime`この`CGopherFileFind`オブジェクトで[FindNextFile](#findnextfile)が呼び出されていない場合にのみ 0 を返します。

### <a name="remarks"></a>解説

を呼び出す前に、少なくとも`GetLastWriteTime`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

> [!NOTE]
> すべてのファイルシステムが同じセマンティクスを使用して、この関数によって返されるタイム・スタンプを実装するわけではありません。 この関数は、基礎となるファイルシステムまたはサーバが time 属性の保持をサポートしていない場合、他のタイム・スタンプ関数から戻される値と同じ値を返す場合があります。 時刻形式については[、WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw)の構造を参照してください。 一部のオペレーティング システムでは、返される時刻は、ファイルが配置されたコンピューターに対してローカルなタイム ゾーンにあります。 詳細については、Win32[ファイルタイムをローカルファイル時間](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime)API を参照してください。

## <a name="cgopherfilefindgetlength"></a><a name="getlength"></a>ファイルを検索します。

見つかったファイルの長さをバイト単位で取得します。

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>戻り値

見つかったファイルの長さ (バイト単位)。

### <a name="remarks"></a>解説

`GetLength`では、ファイル サイズの値をバイト単位で取得するために[、WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) Win32 構造体を使用します。

> [!NOTE]
> MFC 7.0 では`GetLength`、64 ビット整数型をサポートしています。 この新しいバージョンのライブラリで作成された既存のコードは、切り捨てに関する警告を表示する可能性があります。

### <a name="example"></a>例

  [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) (基本クラスの実装) の例を参照してください。

## <a name="cgopherfilefindgetlocator"></a><a name="getlocator"></a>ファイル検索::ゲットロケーター

このメンバー関数を呼び出して[、FindFile](#findfile)が gopher ファイルを検索するために使用する[CGopherLocator](../../mfc/reference/cgopherlocator-class.md)オブジェクトを取得します。

```
CGopherLocator GetLocator() const;
```

### <a name="return-value"></a>戻り値

`CGopherLocator` オブジェクト。

## <a name="cgopherfilefindgetscreenname"></a><a name="getscreenname"></a>ファイルを検索します。

gopher 画面の名前を取得します。

```
CString GetScreenName() const;
```

### <a name="return-value"></a>戻り値

ゴファースクリーンの名前。

## <a name="cgopherfilefindisdots"></a><a name="isdots"></a>ファイル検索::イズドット

ファイルを反復処理しながら、現在のディレクトリと親ディレクトリ マーカーをテストします。

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>戻り値

見つかったファイルの名前が "." または ".." の場合は 0 以外の値を指定します。 それ以外の場合は 0。

### <a name="remarks"></a>解説

を呼び出す前に、少なくとも`IsDots`1 回[は FindNextFile](#findnextfile)を呼び出す必要があります。

## <a name="see-also"></a>関連項目

[クラスを検索します。](../../mfc/reference/cfilefind-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CFtpFileFind クラス](../../mfc/reference/cftpfilefind-class.md)<br/>
[クラスを検索します。](../../mfc/reference/cfilefind-class.md)<br/>
[クラス](../../mfc/reference/cinternetfile-class.md)<br/>
[クラス](../../mfc/reference/cgopherfile-class.md)<br/>
[クラス](../../mfc/reference/chttpfile-class.md)
