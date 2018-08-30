---
title: CAtlTemporaryFile クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile::CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile::Close
- ATLFILE/ATL::CAtlTemporaryFile::Create
- ATLFILE/ATL::CAtlTemporaryFile::Flush
- ATLFILE/ATL::CAtlTemporaryFile::GetPosition
- ATLFILE/ATL::CAtlTemporaryFile::GetSize
- ATLFILE/ATL::CAtlTemporaryFile::HandsOff
- ATLFILE/ATL::CAtlTemporaryFile::HandsOn
- ATLFILE/ATL::CAtlTemporaryFile::LockRange
- ATLFILE/ATL::CAtlTemporaryFile::Read
- ATLFILE/ATL::CAtlTemporaryFile::Seek
- ATLFILE/ATL::CAtlTemporaryFile::SetSize
- ATLFILE/ATL::CAtlTemporaryFile::TempFileName
- ATLFILE/ATL::CAtlTemporaryFile::UnlockRange
- ATLFILE/ATL::CAtlTemporaryFile::Write
dev_langs:
- C++
helpviewer_keywords:
- CAtlTemporaryFile class
ms.assetid: 05f0f2a5-94f6-4594-8dae-b114292ff5f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6eee23ebbfc25d76ca255505322f609973f79f57
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222873"
---
# <a name="catltemporaryfile-class"></a>CAtlTemporaryFile クラス
このクラスは、一時ファイルを使用して作成メソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CAtlTemporaryFile
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)|コンストラクターです。|  
|[CAtlTemporaryFile:: ~ CAtlTemporaryFile](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlTemporaryFile::Close](#close)|その内容を削除するか、一時ファイルを閉じるには、このメソッドを呼び出すか、指定したファイル名の下に保存します。|  
|[CAtlTemporaryFile::Create](#create)|一時ファイルを作成するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::Flush](#flush)|一時ファイルに書き込まれるファイル バッファーの残りの部分を強制するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::GetPosition](#getposition)|現在のファイル ポインターの位置を取得するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::GetSize](#getsize)|一時ファイルのバイト単位のサイズを取得するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::HandsOff](#handsoff)|ファイルの関連付けを解除するには、このメソッドを呼び出す、`CAtlTemporaryFile`オブジェクト。|  
|[CAtlTemporaryFile::HandsOn](#handson)|既存の一時ファイルを開き、ファイルの末尾にカーソルを移動するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::LockRange](#lockrange)|他のプロセスがそれにアクセスすることを防ぐために、ファイル内の領域をロックするには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::Read](#read)|ファイル ポインターによって示される位置から一時ファイルからデータを読み取るには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::Seek](#seek)|一時ファイルのファイル ポインターを移動するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::SetSize](#setsize)|一時ファイルのサイズを設定するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::TempFileName](#tempfilename)|一時ファイルの名前を返すには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::UnlockRange](#unlockrange)|一時ファイルの領域のロックを解除するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::Write](#write)|ファイル ポインターによって示される位置から一時ファイルにデータを書き込むには、このメソッドを呼び出します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlTemporaryFile::operator ハンドル](#operator_handle)|一時ファイルを識別するハンドルを返します。|  
  
## <a name="remarks"></a>Remarks  
 `CAtlTemporaryFile` 作成し、一時ファイルを使用できるようになります。 ファイルが自動的にという名前の開く、閉じられ、削除します。 ファイルが閉じられた後、ファイルの内容が必要な場合は、指定した名前の新しいファイルに保存できます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlfile.h  
  
## <a name="example"></a>例  
 例をご覧ください[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)します。  
  
##  <a name="catltemporaryfile"></a>  CAtlTemporaryFile::CAtlTemporaryFile  
 コンストラクターです。  
  
```
CAtlTemporaryFile() throw();
```  
  
### <a name="remarks"></a>Remarks  
 ファイルが実際に開かれていないへの呼び出しが行われるまで[CAtlTemporaryFile::Create](#create)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#73](../../atl/codesnippet/cpp/catltemporaryfile-class_1.cpp)]  
  
##  <a name="dtor"></a>  CAtlTemporaryFile:: ~ CAtlTemporaryFile  
 デストラクターです。  
  
```
~CAtlTemporaryFile() throw();
```  
  
### <a name="remarks"></a>Remarks  
 デストラクターの呼び出し[CAtlTemporaryFile::Close](#close)します。  
  
##  <a name="close"></a>  CAtlTemporaryFile::Close  
 その内容を削除するか、一時ファイルを閉じるには、このメソッドを呼び出すか、指定したファイル名の下に保存します。  
  
```
HRESULT Close(LPCTSTR szNewName = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *szNewName*  
 一時ファイルの内容を格納する新しいファイルの名前。 この引数が NULL の場合は、一時ファイルの内容が削除されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="example"></a>例  
 例をご覧ください[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)します。  
  
##  <a name="create"></a>  CAtlTemporaryFile::Create  
 一時ファイルを作成するには、このメソッドを呼び出します。  
  
```
HRESULT Create(LPCTSTR pszDir = NULL, DWORD dwDesiredAccess = GENERIC_WRITE) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pszDir*  
 一時ファイルのパス。 この場合、null の場合、 [GetTempPath](/windows/desktop/api/fileapi/nf-fileapi-gettemppatha)パスを割り当てるには呼び出されます。  
  
 *dwDesiredAccess*  
 必要なアクセス。 参照してください*dwDesiredAccess*で[CreateFile](/windows/desktop/api/fileapi/nf-fileapi-createfilea) Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="example"></a>例  
 例をご覧ください[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)します。  
  
##  <a name="flush"></a>  CAtlTemporaryFile::Flush  
 一時ファイルに書き込まれるファイル バッファーの残りの部分を強制するには、このメソッドを呼び出します。  
  
```
HRESULT Flush() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 ような[CAtlTemporaryFile::HandsOff](#handsoff), 点が、ファイルが閉じられていません。  
  
### <a name="example"></a>例  
 例をご覧ください[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)します。  
  
##  <a name="getposition"></a>  CAtlTemporaryFile::GetPosition  
 現在のファイル ポインターの位置を取得するには、このメソッドを呼び出します。  
  
```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *nPos*  
 位置 (バイト単位)。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 ファイル ポインターの位置を変更する[CAtlTemporaryFile::Seek](#seek)します。  
  
##  <a name="getsize"></a>  CAtlTemporaryFile::GetSize  
 一時ファイルのバイト単位のサイズを取得するには、このメソッドを呼び出します。  
  
```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *nLen*  
 ファイル内のバイト数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
##  <a name="handsoff"></a>  CAtlTemporaryFile::HandsOff  
 ファイルの関連付けを解除するには、このメソッドを呼び出す、`CAtlTemporaryFile`オブジェクト。  
  
```
HRESULT HandsOff() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 `HandsOff` [CAtlTemporaryFile::HandsOn](#handson)オブジェクトからファイルの関連付けを解除して、再接続し、必要な場合に使用されます。 `HandsOff` 強制的に一時ファイルに書き込まれるファイルのバッファーに残っているすべてのデータをファイルを閉じます。 閉じるし、ファイルを完全に削除する場合、または閉じるには名前が指定されたファイルの内容を保持しを使用する場合[CAtlTemporaryFile::Close](#close)します。  
  
##  <a name="handson"></a>  CAtlTemporaryFile::HandsOn  
 既存の一時ファイルを開き、ファイルの末尾にカーソルを移動するには、このメソッドを呼び出します。  
  
```
HRESULT HandsOn() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 [CAtlTemporaryFile::HandsOff](#handsoff)と`HandsOn`オブジェクトからファイルの関連付けを解除して、再接続し、必要な場合に使用されます。  
  
##  <a name="lockrange"></a>  CAtlTemporaryFile::LockRange  
 他のプロセスがアクセスできないようにする一時ファイル内の領域をロックするには、このメソッドを呼び出します。  
  
```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *nPos*  
 ロックの開始位置、ファイル内の位置。  
  
 *nCount*  
 ロックするバイト範囲の長さ。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 ファイル内のバイトをロックすると、他のプロセスがそれらのバイトにアクセスできなくなります。 ファイルの 1 つ以上の領域をロックすることができますが、重なり合う領域は許可されません。 領域を正常にロックを解除するには使用[CAtlTemporaryFile::UnlockRange](#unlockrange)、以前にロックされた領域に正確に対応するバイト範囲のことを確認します。 `LockRange` 隣接する領域をマージできません。ロックされている 2 つの領域が隣接している場合とは別に解除各する必要があります。  
  
##  <a name="operator_handle"></a>  CAtlTemporaryFile::operator ハンドル  
 一時ファイルを識別するハンドルを返します。  
  
```  
operator HANDLE() throw();
```  
  
##  <a name="read"></a>  CAtlTemporaryFile::Read  
 ファイル ポインターによって示される位置から一時ファイルからデータを読み取るには、このメソッドを呼び出します。  
  
```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pBuffer*  
 ファイルから読み取られるデータを受け取るバッファーへのポインター。  
  
 *nBufSize*  
 バイト単位のバッファー サイズ。  
  
 *nBytesRead*  
 読み取られたバイト数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 呼び出し[CAtlFile::Read](../../atl/reference/catlfile-class.md#read)します。 ファイル ポインターの位置を変更するには、呼び出す[CAtlTemporaryFile::Seek](#seek)します。  
  
### <a name="example"></a>例  
 例をご覧ください[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)します。  
  
##  <a name="seek"></a>  CAtlTemporaryFile::Seek  
 一時ファイルのファイル ポインターを移動するには、このメソッドを呼び出します。  
  
```
HRESULT Seek(LONGLONG nOffset, DWORD dwFrom = FILE_CURRENT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *nOffset*  
 指定された開始点からのバイト単位のオフセット*dwFrom します。*  
  
 *dwFrom*  
 (FILE_BEGIN、FILE_CURRENT、または FILE_END) の開始点。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 呼び出し[CAtlFile::Seek](../../atl/reference/catlfile-class.md#seek)します。 現在のファイル ポインターの位置を取得する呼び出し[CAtlTemporaryFile::GetPosition](#getposition)します。  
  
### <a name="example"></a>例  
 例をご覧ください[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)します。  
  
##  <a name="setsize"></a>  CAtlTemporaryFile::SetSize  
 一時ファイルのサイズを設定するには、このメソッドを呼び出します。  
  
```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *nNewLen*  
 ファイルのバイトの新しい長さ。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 呼び出し[CAtlFile::SetSize](../../atl/reference/catlfile-class.md#setsize)します。 返された場合は、ファイル ポインターは、ファイルの末尾に配置されます。  
  
##  <a name="tempfilename"></a>  CAtlTemporaryFile::TempFileName  
 一時ファイルの名前を返すには、このメソッドを呼び出します。  
  
```
LPCTSTR TempFileName() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ファイル名を指すを返します。  
  
### <a name="remarks"></a>Remarks  
 ファイル名が生成された[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)を呼び出して、 [GetTempFile](/windows/desktop/api/fileapi/nf-fileapi-gettempfilenamea)Windows SDK 関数。 ファイル拡張子は、一時ファイル用 tfr「と」を必ずします。  
  
##  <a name="unlockrange"></a>  CAtlTemporaryFile::UnlockRange  
 一時ファイルの領域のロックを解除するには、このメソッドを呼び出します。  
  
```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *nPos*  
 ロックの解除の開始位置、ファイル内の位置。  
  
 *nCount*  
 ロックするバイト範囲の長さ。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 呼び出し[CAtlFile::UnlockRange](../../atl/reference/catlfile-class.md#unlockrange)します。  
  
##  <a name="write"></a>  CAtlTemporaryFile::Write  
 ファイル ポインターによって示される位置から一時ファイルにデータを書き込むには、このメソッドを呼び出します。  
  
```
HRESULT Write(  
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pBuffer*  
 ファイルに書き込まれるデータを保持するバッファー。  
  
 *nBufSize*  
 バッファーから転送されるバイト数。  
  
 *pnBytesWritten*  
 書き込むバイト数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 呼び出し[CAtlFile::Write](../../atl/reference/catlfile-class.md#write)します。  
  
### <a name="example"></a>例  
 例をご覧ください[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CAtlFile クラス](../../atl/reference/catlfile-class.md)
