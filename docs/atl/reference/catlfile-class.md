---
title: CAtlFile クラス
ms.date: 11/04/2016
f1_keywords:
- CAtlFile
- ATLFILE/ATL::CAtlFile
- ATLFILE/ATL::CAtlFile::CAtlFile
- ATLFILE/ATL::CAtlFile::Create
- ATLFILE/ATL::CAtlFile::Flush
- ATLFILE/ATL::CAtlFile::GetOverlappedResult
- ATLFILE/ATL::CAtlFile::GetPosition
- ATLFILE/ATL::CAtlFile::GetSize
- ATLFILE/ATL::CAtlFile::LockRange
- ATLFILE/ATL::CAtlFile::Read
- ATLFILE/ATL::CAtlFile::Seek
- ATLFILE/ATL::CAtlFile::SetSize
- ATLFILE/ATL::CAtlFile::UnlockRange
- ATLFILE/ATL::CAtlFile::Write
- ATLFILE/ATL::CAtlFile::m_pTM
helpviewer_keywords:
- CAtlFile class
ms.assetid: 93ed160b-af2a-448c-9cbe-e5fa46c199bb
ms.openlocfilehash: 0faae50afcd26948bdcb4d4333efb25d5cca33ea
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58772970"
---
# <a name="catlfile-class"></a>CAtlFile クラス

このクラスは、ファイル処理 API、Windows の thin ラッパーを提供します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CAtlFile : public CHandle
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAtlFile::CAtlFile](#catlfile)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAtlFile::Create](#create)|作成またはファイルを開くには、このメソッドを呼び出します。|
|[CAtlFile::Flush](#flush)|ファイルのバッファーをクリアして、ファイルに書き込まれるバッファー内のすべてのデータには、このメソッドを呼び出します。|
|[CAtlFile::GetOverlappedResult](#getoverlappedresult)|ファイルの重複した操作の結果を取得するには、このメソッドを呼び出します。|
|[CAtlFile::GetPosition](#getposition)|ファイルから現在のファイル ポインターの位置を取得するには、このメソッドを呼び出します。|
|[CAtlFile::GetSize](#getsize)|ファイルのバイト単位のサイズを取得するには、このメソッドを呼び出します。|
|[CAtlFile::LockRange](#lockrange)|他のプロセスがそれにアクセスすることを防ぐために、ファイル内の領域をロックするには、このメソッドを呼び出します。|
|[CAtlFile::Read](#read)|ファイル ポインターによって示される位置以降にあるファイルからデータを読み取るには、このメソッドを呼び出します。|
|[CAtlFile::Seek](#seek)|ファイルのファイル ポインターを移動するには、このメソッドを呼び出します。|
|[CAtlFile::SetSize](#setsize)|ファイルのサイズを設定するには、このメソッドを呼び出します。|
|[CAtlFile::UnlockRange](#unlockrange)|ファイルの領域のロックを解除するには、このメソッドを呼び出します。|
|[CAtlFile::Write](#write)|ファイル ポインターによって示される位置からファイルにデータを書き込むには、このメソッドを呼び出します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CAtlFile::m_pTM](#m_ptm)|ポインター`CAtlTransactionManager`オブジェクト|

## <a name="remarks"></a>Remarks

ファイル処理ニーズが比較的単純な Windows API が提供する以上の複数の抽象化は、MFC の依存関係を含めなくても、必要な場合は、このクラスを使用します。

## <a name="inheritance-hierarchy"></a>継承階層

[CHandle](../../atl/reference/chandle-class.md)

`CAtlFile`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlfile.h

##  <a name="catlfile"></a>  CAtlFile::CAtlFile

コンストラクターです。

```
CAtlFile() throw();
CAtlFile(CAtlTransactionManager* pTM = NULL) throw();
CAtlFile(CAtlFile& file) throw();
explicit CAtlFile(HANDLE hFile) throw();
```

### <a name="parameters"></a>パラメーター

*file*<br/>
ファイル オブジェクト。

*hFile*<br/>
ファイル ハンドル。

*pTM*<br/>
CAtlTransactionManager オブジェクトへのポインター。

### <a name="remarks"></a>Remarks

コピー コンス トラクターは、元のファイル ハンドルの所有権を転送`CAtlFile`オブジェクトを新しく構築されたオブジェクト。

##  <a name="create"></a>  CAtlFile::Create

作成またはファイルを開くには、このメソッドを呼び出します。

```
HRESULT Create(
    LPCTSTR szFilename,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes = FILE_ATTRIBUTE_NORMAL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    HANDLE hTemplateFile = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*szFilename*<br/>
ファイル名。

*dwDesiredAccess*<br/>
必要なアクセス。 参照してください*dwDesiredAccess*で[CreateFile](/windows/desktop/api/fileapi/nf-fileapi-createfilea) Windows SDK に含まれています。

*dwShareMode*<br/>
共有モード。 参照してください*dwShareMode*で`CreateFile`します。

*dwCreationDisposition*<br/>
作成処理します。 参照してください*dwCreationDisposition*で`CreateFile`します。

*dwFlagsAndAttributes*<br/>
フラグと属性。 参照してください*dwFlagsAndAttributes*で`CreateFile`します。

*lpsa*<br/>
セキュリティ属性。 参照してください*lpSecurityAttributes*で`CreateFile`します。

*hTemplateFile*<br/>
テンプレート ファイル。 参照してください*hTemplateFile*で`CreateFile`します。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

呼び出し[CreateFile](/windows/desktop/api/fileapi/nf-fileapi-createfilea)を作成したり、ファイルを開きます。

##  <a name="flush"></a>  CAtlFile::Flush

ファイルのバッファーをクリアして、ファイルに書き込まれるバッファー内のすべてのデータには、このメソッドを呼び出します。

```
HRESULT Flush() throw();
```

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

呼び出し[FlushFileBuffers](/windows/desktop/api/fileapi/nf-fileapi-flushfilebuffers)バッファー内のデータをファイルにフラッシュします。

##  <a name="getoverlappedresult"></a>  CAtlFile::GetOverlappedResult

ファイルの重複した操作の結果を取得するには、このメソッドを呼び出します。

```
HRESULT GetOverlappedResult(
    LPOVERLAPPED pOverlapped,
    DWORD& dwBytesTransferred,
    BOOL bWait) throw();
```

### <a name="parameters"></a>パラメーター

*pOverlapped*<br/>
オーバー ラップ構造体。 参照してください*lpOverlapped*で[GetOverlappedResult](/windows/desktop/api/ioapiset/nf-ioapiset-getoverlappedresult) Windows SDK に含まれています。

*dwBytesTransferred*<br/>
バイトが転送されます。 参照してください*lpNumberOfBytesTransferred*で`GetOverlappedResult`します。

*して*<br/>
待機オプション。 参照してください*して*で`GetOverlappedResult`します。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

呼び出し[GetOverlappedResult](/windows/desktop/api/ioapiset/nf-ioapiset-getoverlappedresult)ファイルの重複した操作の結果を取得します。

##  <a name="getposition"></a>  CAtlFile::GetPosition

現在のファイル ポインターの位置を取得するには、このメソッドを呼び出します。

```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```

### <a name="parameters"></a>パラメーター

*nPos*<br/>
位置 (バイト単位)。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

呼び出し[SetFilePointer](/windows/desktop/api/fileapi/nf-fileapi-setfilepointer)を現在のファイル ポインターの位置を取得します。

##  <a name="getsize"></a>  CAtlFile::GetSize

ファイルのバイト単位のサイズを取得するには、このメソッドを呼び出します。

```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>パラメーター

*nLen*<br/>
ファイル内のバイト数。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

呼び出し[GetFileSize](/windows/desktop/api/fileapi/nf-fileapi-getfilesize)ファイルのバイト単位でサイズを取得します。

##  <a name="lockrange"></a>  CAtlFile::LockRange

他のプロセスがそれにアクセスすることを防ぐために、ファイル内の領域をロックするには、このメソッドを呼び出します。

```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>パラメーター

*nPos*<br/>
ロックの開始位置、ファイル内の位置。

*nCount*<br/>
ロックするバイト範囲の長さ。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

呼び出し[ロック ファイル](/windows/desktop/api/fileapi/nf-fileapi-lockfile)ファイルに領域をロックします。 ファイル内のバイトをロックすると、他のプロセスがそれらのバイトにアクセスできなくなります。 ファイルの 1 つ以上の領域をロックすることができますが、重なり合う領域は許可されません。 使用して、リージョンのロックを解除するときに[CAtlFile::UnlockRange](#unlockrange)、バイト範囲は、以前にロックされた領域に正確に対応する必要があります。 `LockRange` 隣接する領域をマージできません。ロックされている 2 つの領域が隣接している場合とは別に解除各する必要があります。

##  <a name="m_ptm"></a>  CAtlFile::m_pTM

ポインターを`CAtlTransactionManager`オブジェクト。

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Remarks

##  <a name="read"></a>  CAtlFile::Read

ファイル ポインターによって示される位置以降にあるファイルからデータを読み取るには、このメソッドを呼び出します。

```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped,
    LPOVERLAPPED_COMPLETION_ROUTINE pfnCompletionRoutine) throw();
```

### <a name="parameters"></a>パラメーター

*pBuffer*<br/>
ファイルから読み取られるデータを受け取るバッファーへのポインター。

*nBufSize*<br/>
バイト単位のバッファー サイズ。

*nBytesRead*<br/>
読み取られたバイト数。

*pOverlapped*<br/>
オーバー ラップ構造体。 参照してください*lpOverlapped*で[ReadFile](/windows/desktop/api/fileapi/nf-fileapi-readfile) Windows SDK に含まれています。

*pfnCompletionRoutine*<br/>
メモリを割り当てます。 参照してください*lpCompletionRoutine*で[ReadFileEx](/windows/desktop/api/fileapi/nf-fileapi-readfileex) Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

最初の 3 つのフォームを呼び出す[ReadFile](/windows/desktop/api/fileapi/nf-fileapi-readfile)、最後の[ReadFileEx](/windows/desktop/api/fileapi/nf-fileapi-readfileex)ファイルからデータを読み取る。 使用[CAtlFile::Seek](#seek)ファイル ポインターを移動します。

##  <a name="seek"></a>  CAtlFile::Seek

ファイルのファイル ポインターを移動するには、このメソッドを呼び出します。

```
HRESULT Seek(
    LONGLONG nOffset,
    DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>パラメーター

*nOffset*<br/>
指定された開始点からのオフセット*dwFrom*します。

*dwFrom*<br/>
(FILE_BEGIN、FILE_CURRENT、または FILE_END) の開始点。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

呼び出し[SetFilePointer](/windows/desktop/api/fileapi/nf-fileapi-setfilepointer)ファイル ポインターを移動します。

##  <a name="setsize"></a>  CAtlFile::SetSize

ファイルのサイズを設定するには、このメソッドを呼び出します。

```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>パラメーター

*nNewLen*<br/>
ファイルのバイトの新しい長さ。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

呼び出し[SetFilePointer](/windows/desktop/api/fileapi/nf-fileapi-setfilepointer)と[SetEndOfFile](/windows/desktop/api/fileapi/nf-fileapi-setendoffile)ファイルのサイズを設定します。 返された場合は、ファイル ポインターは、ファイルの末尾に配置されます。

##  <a name="unlockrange"></a>  CAtlFile::UnlockRange

ファイルの領域のロックを解除するには、このメソッドを呼び出します。

```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>パラメーター

*nPos*<br/>
ロックの解除の開始位置、ファイル内の位置。

*nCount*<br/>
ロックするバイト範囲の長さ。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

呼び出し[UnlockFile](/windows/desktop/api/fileapi/nf-fileapi-unlockfile)ファイルの領域のロックを解除します。

##  <a name="write"></a>  CAtlFile::Write

ファイル ポインターによって示される位置からファイルにデータを書き込むには、このメソッドを呼び出します。

```
HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped,
    LPOVERLAPPED_COMPLETION_ROUTINE pfnCompletionRoutine) throw();

HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();

HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped) throw();
```

### <a name="parameters"></a>パラメーター

*pBuffer*<br/>
ファイルに書き込まれるデータを保持するバッファー。

*nBufSize*<br/>
バッファーから転送されるバイト数。

*pOverlapped*<br/>
オーバー ラップ構造体。 参照してください*lpOverlapped*で[WriteFile](/windows/desktop/api/fileapi/nf-fileapi-writefile) Windows SDK に含まれています。

*pfnCompletionRoutine*<br/>
メモリを割り当てます。 参照してください*lpCompletionRoutine*で[WriteFileEx](/windows/desktop/api/fileapi/nf-fileapi-writefileex) Windows SDK に含まれています。

*pnBytesWritten*<br/>
書き込みバイト数。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

最初の 3 つのフォームを呼び出す[WriteFile](/windows/desktop/api/fileapi/nf-fileapi-writefile)、最後の呼び出し[WriteFileEx](/windows/desktop/api/fileapi/nf-fileapi-writefileex)データ ファイルに書き込めません。 使用[CAtlFile::Seek](#seek)ファイル ポインターを移動します。

## <a name="see-also"></a>関連項目

[マーキーのサンプル](../../overview/visual-cpp-samples.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[CHandle クラス](../../atl/reference/chandle-class.md)
