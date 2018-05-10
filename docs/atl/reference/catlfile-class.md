---
title: CAtlFile クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlFile class
ms.assetid: 93ed160b-af2a-448c-9cbe-e5fa46c199bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43ee71aae842ca7100f70af67cd8845d31e39a96
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="catlfile-class"></a>CAtlFile クラス
このクラスは、ファイル処理 API、Windows の周囲に thin ラッパーを提供します。  
  
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
|[CAtlFile::Create](#create)|このメソッドを呼び出して作成するか、ファイルを開きます。|  
|[CAtlFile::Flush](#flush)|このメソッドを呼び出してファイルに書き込まれるバッファー内のすべてのデータになり、ファイルのバッファーをクリアします。|  
|[CAtlFile::GetOverlappedResult](#getoverlappedresult)|このメソッドを呼び出してファイルに重複した操作の結果を取得します。|  
|[CAtlFile::GetPosition](#getposition)|このメソッドを呼び出して、ファイルから現在のファイル ポインターの位置を取得します。|  
|[CAtlFile::GetSize](#getsize)|ファイルのバイト単位のサイズを取得するには、このメソッドを呼び出します。|  
|[CAtlFile::LockRange](#lockrange)|ファイル内の他のプロセスがアクセスできないようにする領域をロックするには、このメソッドを呼び出します。|  
|[CAtlFile::Read](#read)|ファイル ポインターによって示される位置以降にあるファイルからデータを読み取るには、このメソッドを呼び出します。|  
|[CAtlFile::Seek](#seek)|ファイルのファイル ポインターを移動するには、このメソッドを呼び出します。|  
|[CAtlFile::SetSize](#setsize)|ファイルのサイズを設定するには、このメソッドを呼び出します。|  
|[CAtlFile::UnlockRange](#unlockrange)|ファイルの領域のロックを解除するには、このメソッドを呼び出します。|  
|[CAtlFile::Write](#write)|ファイル ポインターによって示される位置以降にあるファイルにデータを書き込むには、このメソッドを呼び出します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlFile::m_pTM](#m_ptm)|ポインター`CAtlTransactionManager`オブジェクト|  
  
## <a name="remarks"></a>コメント  
 ファイル処理要件は比較的単純な MFC の依存関係を含めずに Windows API で提供される多くの抽象化は、必要な場合は、このクラスを使用します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CHandle](../../atl/reference/chandle-class.md)  
  
 `CAtlFile`  
  
## <a name="requirements"></a>要件  
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
 `file`  
 ファイル オブジェクト。  
  
 `hFile`  
 ファイル ハンドル。  
  
 `pTM`  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 コピー コンス トラクターは、元のファイル ハンドルの所有権を譲渡`CAtlFile`オブジェクトを新しく構築されたオブジェクト。  
  
##  <a name="create"></a>  CAtlFile::Create  
 このメソッドを呼び出して作成するか、ファイルを開きます。  
  
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
 *szFilename*  
 ファイル名。  
  
 `dwDesiredAccess`  
 必要なアクセス。 参照してください`dwDesiredAccess`で[CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858) Windows SDK にします。  
  
 `dwShareMode`  
 共有モードです。 参照してください`dwShareMode`で**CreateFile**です。  
  
 `dwCreationDisposition`  
 作成処理します。 参照してください`dwCreationDisposition`で**CreateFile**です。  
  
 `dwFlagsAndAttributes`  
 フラグと属性。 参照してください`dwFlagsAndAttributes`で**CreateFile**です。  
  
 `lpsa`  
 セキュリティ属性。 参照してください*lpSecurityAttributes*で**CreateFile**です。  
  
 `hTemplateFile`  
 テンプレート ファイル。 参照してください`hTemplateFile`で**CreateFile**です。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 呼び出し[CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858)を作成またはファイルを開きます。  
  
##  <a name="flush"></a>  CAtlFile::Flush  
 このメソッドを呼び出してファイルに書き込まれるバッファー内のすべてのデータになり、ファイルのバッファーをクリアします。  
  
```
HRESULT Flush() throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 呼び出し[FlushFileBuffers](http://msdn.microsoft.com/library/windows/desktop/aa364439)バッファー内のデータをファイルにフラッシュします。  
  
##  <a name="getoverlappedresult"></a>  CAtlFile::GetOverlappedResult  
 このメソッドを呼び出してファイルに重複した操作の結果を取得します。  
  
```
HRESULT GetOverlappedResult(
    LPOVERLAPPED pOverlapped,
    DWORD& dwBytesTransferred,
    BOOL bWait) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pOverlapped`  
 オーバー ラップ構造体。 参照してください`lpOverlapped`で[GetOverlappedResult](http://msdn.microsoft.com/library/windows/desktop/ms683209) Windows SDK にします。  
  
 *dwBytesTransferred*  
 バイトが転送されます。 参照してください*lpNumberOfBytesTransferred*で`GetOverlappedResult`です。  
  
 `bWait`  
 待機のオプションです。 「`bWait`」の「`GetOverlappedResult`」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 呼び出し[GetOverlappedResult](http://msdn.microsoft.com/library/windows/desktop/ms683209)ファイルに重複した操作の結果を取得します。  
  
##  <a name="getposition"></a>  CAtlFile::GetPosition  
 このメソッドを呼び出して、現在のファイル ポインターの位置を取得します。  
  
```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 位置 (バイト単位)。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 呼び出し[SetFilePointer](http://msdn.microsoft.com/library/windows/desktop/aa365541)を現在のファイル ポインターの位置を取得します。  
  
##  <a name="getsize"></a>  CAtlFile::GetSize  
 ファイルのバイト単位のサイズを取得するには、このメソッドを呼び出します。  
  
```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nLen`  
 ファイル内のバイト数。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 呼び出し[GetFileSize](http://msdn.microsoft.com/library/windows/desktop/aa364955)ファイルのバイト単位でサイズを取得します。  
  
##  <a name="lockrange"></a>  CAtlFile::LockRange  
 ファイル内の他のプロセスがアクセスできないようにする領域をロックするには、このメソッドを呼び出します。  
  
```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 ロックの開始位置を示すファイル内の位置。  
  
 `nCount`  
 ロックするバイト範囲の長さ。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 呼び出し[ロック ファイル](http://msdn.microsoft.com/library/windows/desktop/aa365202)ファイルに領域をロックします。 ファイル内のバイトをロックすると、他のプロセスがそれらのバイトにアクセスできなくなります。 ファイルの 1 つ以上の領域をロックすることができますが、重なり合う領域は許可されていません。 使用して、領域のロックを解除するときに[CAtlFile::UnlockRange](#unlockrange)、バイト範囲は、以前にロックされている領域に正確に対応する必要があります。 `LockRange` 隣接する領域をマージしませんロックされている 2 つの領域が隣接している場合は、する必要がありますロックを解除する各とは別にします。  
  
##  <a name="m_ptm"></a>  CAtlFile::m_pTM  
 ポインター、`CAtlTransactionManager`オブジェクト。  
  
```
CAtlTransactionManager* m_pTM;
```  
  
### <a name="remarks"></a>コメント  
  
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
 `pBuffer`  
 ファイルから読み取られるデータを受け取るバッファーへのポインター。  
  
 `nBufSize`  
 バイト単位のバッファー サイズ。  
  
 `nBytesRead`  
 読み取られたバイト数。  
  
 `pOverlapped`  
 オーバー ラップ構造体。 参照してください`lpOverlapped`で[ReadFile](http://msdn.microsoft.com/library/windows/desktop/aa365467) Windows SDK にします。  
  
 `pfnCompletionRoutine`  
 メモリを割り当てます。 参照してください*lpCompletionRoutine*で[ReadFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365468) Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 最初の 3 つを呼び出す[ReadFile](http://msdn.microsoft.com/library/windows/desktop/aa365467)、最後の[ReadFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365468)ファイルからデータを読み取る。 使用して[CAtlFile::Seek](#seek)ファイル ポインターを移動します。  
  
##  <a name="seek"></a>  CAtlFile::Seek  
 ファイルのファイル ポインターを移動するには、このメソッドを呼び出します。  
  
```
HRESULT Seek(
    LONGLONG nOffset,
    DWORD dwFrom = FILE_CURRENT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nOffset`  
 指定した開始ポイントからのオフセット`dwFrom`です。  
  
 `dwFrom`  
 (FILE_BEGIN、FILE_CURRENT、または FILE_END) の開始点。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 呼び出し[SetFilePointer](http://msdn.microsoft.com/library/windows/desktop/aa365541)ファイル ポインターを移動します。  
  
##  <a name="setsize"></a>  CAtlFile::SetSize  
 ファイルのサイズを設定するには、このメソッドを呼び出します。  
  
```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nNewLen`  
 (バイト単位)、ファイルの新しい長さ。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 呼び出し[SetFilePointer](http://msdn.microsoft.com/library/windows/desktop/aa365541)と[SetEndOfFile](http://msdn.microsoft.com/library/windows/desktop/aa365531)ファイルのサイズを設定します。 返された場合は、ファイル ポインターは、ファイルの末尾に配置されます。  
  
##  <a name="unlockrange"></a>  CAtlFile::UnlockRange  
 ファイルの領域のロックを解除するには、このメソッドを呼び出します。  
  
```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 ロックの解除が開始する必要がありますファイル内の位置。  
  
 `nCount`  
 ロックを解除するのには、このバイト範囲の長さ。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 呼び出し[UnlockFile](http://msdn.microsoft.com/library/windows/desktop/aa365715)ファイルの領域のロックを解除します。  
  
##  <a name="write"></a>  CAtlFile::Write  
 ファイル ポインターによって示される位置以降にあるファイルにデータを書き込むには、このメソッドを呼び出します。  
  
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
 `pBuffer`  
 ファイルに書き込まれるデータを保持するバッファー。  
  
 `nBufSize`  
 バッファーから転送されるバイト数。  
  
 `pOverlapped`  
 オーバー ラップ構造体。 参照してください`lpOverlapped`で[WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747) Windows SDK にします。  
  
 `pfnCompletionRoutine`  
 メモリを割り当てます。 参照してください*lpCompletionRoutine*で[WriteFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365748) Windows SDK に含まれています。  
  
 `pnBytesWritten`  
 書き込むバイト。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 最初の 3 つを呼び出す[WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747)、最後の呼び出し[WriteFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365748)データ ファイルを書き込めません。 使用して[CAtlFile::Seek](#seek)ファイル ポインターを移動します。  
  
## <a name="see-also"></a>関連項目  
 [マーキーのサンプル](../../visual-cpp-samples.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CHandle クラス](../../atl/reference/chandle-class.md)
