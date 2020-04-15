---
title: クラス
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
ms.openlocfilehash: 39f323874ccde5178722235b9beb34c2572407a1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318974"
---
# <a name="catlfile-class"></a>クラス

このクラスは、Windows ファイル処理 API をラップするシン ラッパーを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CAtlFile : public CHandle
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[カトルファイル::カトルファイル](#catlfile)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[カトルファイル::作成](#create)|ファイルを作成または開きます。|
|[カトルファイル::フラッシュ](#flush)|ファイルのバッファをクリアし、バッファリングされたデータをすべてファイルに書き込みます。|
|[ファイル::オーバーラップ結果を取得します。](#getoverlappedresult)|ファイルに対する重複した操作の結果を取得します。|
|[カトルファイル::ゲットポジション](#getposition)|ファイルから現在のファイル ポインターの位置を取得します。|
|[カトルファイル::ゲットサイズ](#getsize)|ファイルのサイズ (バイト単位) を取得します。|
|[カトルファイル::ロックレンジ](#lockrange)|他のプロセスがアクセスできないように、ファイル内の領域をロックします。|
|[カトルファイル::読み取り](#read)|ファイル ポインターで指定された位置から開始するファイルからデータを読み取ります。|
|[カトルファイル::シーク](#seek)|ファイルのファイル ポインタを移動します。|
|[カトルファイル::セットサイズ](#setsize)|ファイルのサイズを設定します。|
|[カトルファイル::ロック解除範囲](#unlockrange)|ファイルの領域をロック解除します。|
|[カトルファイル::書き込み](#write)|ファイル ポインターで指定された位置からファイルにデータを書き込みます。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[カトルファイル::m_pTM](#m_ptm)|オブジェクトへの`CAtlTransactionManager`ポインタ|

## <a name="remarks"></a>解説

ファイル処理のニーズが比較的単純であるが、MFC の依存関係を含めずに Windows API が提供する抽象化よりも多くの抽象化が必要な場合は、このクラスを使用します。

## <a name="inheritance-hierarchy"></a>継承階層

[ハンドル](../../atl/reference/chandle-class.md)

`CAtlFile`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlfile.h

## <a name="catlfilecatlfile"></a><a name="catlfile"></a>カトルファイル::カトルファイル

コンストラクターです。

```
CAtlFile() throw();
CAtlFile(CAtlTransactionManager* pTM = NULL) throw();
CAtlFile(CAtlFile& file) throw();
explicit CAtlFile(HANDLE hFile) throw();
```

### <a name="parameters"></a>パラメーター

*ファイル*<br/>
ファイル オブジェクト。

*hファイル*<br/>
ファイル ハンドル。

*Ptm*<br/>
CAtlTransactionManager オブジェクトへのポインター。

### <a name="remarks"></a>解説

コピー コンストラクターは、元`CAtlFile`のオブジェクトから新しく構築されたオブジェクトにファイル ハンドルの所有権を転送します。

## <a name="catlfilecreate"></a><a name="create"></a>カトルファイル::作成

ファイルを作成または開きます。

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

*ファイル名*<br/>
ファイル名。

*アクセスを許可*<br/>
目的のアクセス。 Windows SDK の[「ファイルの作成](/windows/win32/api/fileapi/nf-fileapi-createfilew)」の*dwDesiredAccess*を参照してください。

*を使用します。*<br/>
共有モード。 の*dwShare* `CreateFile`モードを参照してください。

*dwクリエーションディスポジション*<br/>
作成の破棄。 *で dw 作成の破棄*を`CreateFile`参照してください。

*属性*<br/>
フラグと属性。 *の「 」を*参照`CreateFile`してください。

*lpsa*<br/>
セキュリティ属性。 の 「 lp `CreateFile`*セキュリティ属性*」を参照してください。

*ファイル*<br/>
テンプレート ファイル。 の*hTemplate* `CreateFile`ファイルを参照してください。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

[CreateFile を](/windows/win32/api/fileapi/nf-fileapi-createfilew)呼び出して、ファイルを作成または開きます。

## <a name="catlfileflush"></a><a name="flush"></a>カトルファイル::フラッシュ

ファイルのバッファをクリアし、バッファリングされたデータをすべてファイルに書き込みます。

```
HRESULT Flush() throw();
```

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

バッファされたデータをファイルにフラッシュするために[FlushFileBuffers](/windows/win32/api/fileapi/nf-fileapi-flushfilebuffers)を呼び出します。

## <a name="catlfilegetoverlappedresult"></a><a name="getoverlappedresult"></a>ファイル::オーバーラップ結果を取得します。

ファイルに対する重複した操作の結果を取得します。

```
HRESULT GetOverlappedResult(
    LPOVERLAPPED pOverlapped,
    DWORD& dwBytesTransferred,
    BOOL bWait) throw();
```

### <a name="parameters"></a>パラメーター

*オーバーラップ*<br/>
重複した構造。 Windows SDK の[「オーバーラップされた結果」](/windows/win32/api/ioapiset/nf-ioapiset-getoverlappedresult)の lp オーバー*ラップ*を参照してください。

*転送された dw バイト*<br/>
転送されたバイト数。 で*転送された lpNumberOf バイトを*`GetOverlappedResult`参照してください。

*b待ち時間*<br/>
待機オプション。 *bwait*の`GetOverlappedResult`を参照してください。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

ファイルに対する重複操作の結果を取得するには[、GetOverlappedResult](/windows/win32/api/ioapiset/nf-ioapiset-getoverlappedresult)を呼び出します。

## <a name="catlfilegetposition"></a><a name="getposition"></a>カトルファイル::ゲットポジション

現在のファイル ポインターの位置を取得します。

```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```

### <a name="parameters"></a>パラメーター

*Npo*<br/>
バイト単位の位置。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

[現在のファイル ポインター](/windows/win32/api/fileapi/nf-fileapi-setfilepointer)の位置を取得する SetFilePointer を呼び出します。

## <a name="catlfilegetsize"></a><a name="getsize"></a>カトルファイル::ゲットサイズ

ファイルのサイズ (バイト単位) を取得します。

```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>パラメーター

*nlen*<br/>
ファイル内のバイト数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

[GetFileSize](/windows/win32/api/fileapi/nf-fileapi-getfilesize)を呼び出して、ファイルのサイズをバイト単位で取得します。

## <a name="catlfilelockrange"></a><a name="lockrange"></a>カトルファイル::ロックレンジ

他のプロセスがアクセスできないように、ファイル内の領域をロックします。

```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>パラメーター

*Npo*<br/>
ロックを開始するファイル内の位置。

*nカウント*<br/>
ロックするバイト範囲の長さ。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

[LockFile](/windows/win32/api/fileapi/nf-fileapi-lockfile)を呼び出して、ファイル内の領域をロックします。 ファイル内のバイトをロックすると、他のプロセスがそれらのバイトにアクセスできなくなります。 ファイルの複数の領域をロックできますが、重複する領域は使用できません。 [CAtlFile::UnlockRange](#unlockrange)を使用して領域のロックを解除する場合、バイト範囲は以前にロックされていた領域に正確に対応している必要があります。 `LockRange`隣接する領域はマージされません。2 つのロックされた領域が隣接している場合は、それぞれ個別にロックを解除する必要があります。

## <a name="catlfilem_ptm"></a><a name="m_ptm"></a>カトルファイル::m_pTM

`CAtlTransactionManager`オブジェクトへのポインター。

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>解説

## <a name="catlfileread"></a><a name="read"></a>カトルファイル::読み取り

ファイル ポインターで指定された位置から開始するファイルからデータを読み取ります。

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
ファイルから読み取ったデータを受け取るバッファーへのポインター。

*サイズを変更します。*<br/>
バイト単位のバッファー サイズ。

*バイト読み取り*<br/>
読み取るバイト数。

*オーバーラップ*<br/>
重複した構造。 Windows SDK の[ReadFile](/windows/win32/api/fileapi/nf-fileapi-readfile)で*lp オーバーラップ*を参照してください。

*完了ルーチン*<br/>
完了ルーチン。 Windows SDK[の読み取りファイルの lpCompletion](/windows/win32/api/fileapi/nf-fileapi-readfileex) *ルーチン*を参照してください。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

最初の 3 つの形式は[、ファイル](/windows/win32/api/fileapi/nf-fileapi-readfile)からデータを読み取るために最後の[ReadFileEx を](/windows/win32/api/fileapi/nf-fileapi-readfileex)呼び出します。 [CAtlFile::Seek](#seek)を使用してファイル ポインタを移動します。

## <a name="catlfileseek"></a><a name="seek"></a>カトルファイル::シーク

ファイルのファイル ポインタを移動します。

```
HRESULT Seek(
    LONGLONG nOffset,
    DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>パラメーター

*オフセット*<br/>
*dwFrom*によって指定された開始点からのオフセット。

*dwから*<br/>
開始点 (FILE_BEGIN、FILE_CURRENT、またはFILE_END)。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

ファイル ポインタを移動するために[、SetFilePointer](/windows/win32/api/fileapi/nf-fileapi-setfilepointer)を呼び出します。

## <a name="catlfilesetsize"></a><a name="setsize"></a>カトルファイル::セットサイズ

ファイルのサイズを設定します。

```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>パラメーター

*nニューレン*<br/>
ファイルの新しい長さ (バイト単位)。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

ファイルのサイズを設定するために、[ファイルポインタ](/windows/win32/api/fileapi/nf-fileapi-setfilepointer)と[ファイル](/windows/win32/api/fileapi/nf-fileapi-setendoffile)のサイズを設定します。 戻り値の場合、ファイル ポインタはファイルの末尾に置かれる。

## <a name="catlfileunlockrange"></a><a name="unlockrange"></a>カトルファイル::ロック解除範囲

ファイルの領域をロック解除します。

```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>パラメーター

*Npo*<br/>
ファイル内でのロック解除の開始位置。

*nカウント*<br/>
ロック解除するバイト範囲の長さ。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

[UnlockFile](/windows/win32/api/fileapi/nf-fileapi-unlockfile)を呼び出して、ファイルの領域をロック解除します。

## <a name="catlfilewrite"></a><a name="write"></a>カトルファイル::書き込み

ファイル ポインターで指定された位置からファイルにデータを書き込みます。

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
ファイルに書き込むデータを格納しているバッファー。

*サイズを変更します。*<br/>
バッファーから転送されるバイト数。

*オーバーラップ*<br/>
重複した構造。 Windows SDK の[「書き込みファイル](/windows/win32/api/fileapi/nf-fileapi-writefile)」の*lp オーバーラップ*を参照してください。

*完了ルーチン*<br/>
完了ルーチン。 Windows SDK[の「ファイルエクスックス」の](/windows/win32/api/fileapi/nf-fileapi-writefileex) *lpCompletion ルーチン*を参照してください。

*書き込まれたバイト*<br/>
書き込まれたバイト数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

最初の 3 つの形式は[WriteFile](/windows/win32/api/fileapi/nf-fileapi-writefile)を呼び出し、最後の呼び出し[は WriteFileEx](/windows/win32/api/fileapi/nf-fileapi-writefileex)ファイルにデータを書き込みます。 [CAtlFile::Seek](#seek)を使用してファイル ポインタを移動します。

## <a name="see-also"></a>関連項目

[マーキーサンプル](../../overview/visual-cpp-samples.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[クラスを処理します。](../../atl/reference/chandle-class.md)
