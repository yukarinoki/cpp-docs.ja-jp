---
title: CAtlTemporaryFile クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 49adcb572e355c62e6f21081eb033496e60e2369
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="catltemporaryfile-class"></a>CAtlTemporaryFile クラス
このクラスは、作成および一時ファイルを使用するメソッドを提供します。  
  
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
|[CAtlTemporaryFile::Close](#close)|一時ファイルを閉じるには、このメソッドを呼び出すし、その内容を削除するか、または、指定したファイル名の下に格納します。|  
|[CAtlTemporaryFile::Create](#create)|一時ファイルを作成するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::Flush](#flush)|このメソッドを呼び出して強制的に一時ファイルに書き込まれるファイル バッファーの残りの部分です。|  
|[CAtlTemporaryFile::GetPosition](#getposition)|このメソッドを呼び出して、現在のファイル ポインターの位置を取得します。|  
|[CAtlTemporaryFile::GetSize](#getsize)|一時ファイルのバイト単位のサイズを取得するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::HandsOff](#handsoff)|ファイルの関連付けを解除するには、このメソッドを呼び出して、`CAtlTemporaryFile`オブジェクト。|  
|[CAtlTemporaryFile::HandsOn](#handson)|このメソッドを呼び出して既存の一時ファイルを開き、ファイルの末尾にカーソルを移動します。|  
|[CAtlTemporaryFile::LockRange](#lockrange)|ファイル内の他のプロセスがアクセスできないようにする領域をロックするには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::Read](#read)|ファイル ポインターによって示される位置から一時ファイルからデータを読み取るには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::Seek](#seek)|一時ファイルのファイル ポインターを移動するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::SetSize](#setsize)|一時ファイルのサイズを設定するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::TempFileName](#tempfilename)|このメソッドを呼び出して、一時ファイルの名前を返します。|  
|[CAtlTemporaryFile::UnlockRange](#unlockrange)|一時ファイルの領域のロックを解除するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::Write](#write)|ファイル ポインターによって示される位置から一時ファイルにデータを書き込むには、このメソッドを呼び出します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlTemporaryFile::operator ハンドル](#operator_handle)|一時ファイルへのハンドルを返します。|  
  
## <a name="remarks"></a>コメント  
 `CAtlTemporaryFile` 作成し、一時ファイルを使用して簡単にできます。 ファイルは自動的にという名前を開く、閉じると、および削除します。 ファイルが閉じられた後、ファイルの内容が必要な場合は、指定した名前の新しいファイルに保存できます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlfile.h  
  
## <a name="example"></a>例  
 例を参照して[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)です。  
  
##  <a name="catltemporaryfile"></a>  CAtlTemporaryFile::CAtlTemporaryFile  
 コンストラクターです。  
  
```
CAtlTemporaryFile() throw();
```  
  
### <a name="remarks"></a>コメント  
 ファイルが実際に開かれていないへの呼び出しがなされるまで[CAtlTemporaryFile::Create](#create)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#73](../../atl/codesnippet/cpp/catltemporaryfile-class_1.cpp)]  
  
##  <a name="dtor"></a>  CAtlTemporaryFile:: ~ CAtlTemporaryFile  
 デストラクターです。  
  
```
~CAtlTemporaryFile() throw();
```  
  
### <a name="remarks"></a>コメント  
 デストラクター [CAtlTemporaryFile::Close](#close)です。  
  
##  <a name="close"></a>  CAtlTemporaryFile::Close  
 一時ファイルを閉じるには、このメソッドを呼び出すし、その内容を削除するか、または、指定したファイル名の下に格納します。  
  
```
HRESULT Close(LPCTSTR szNewName = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *szNewName*  
 一時ファイルの内容を格納する新しいファイルの名前です。 この引数が NULL の場合は、一時ファイルの内容は削除されます。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="example"></a>例  
 例を参照して[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)です。  
  
##  <a name="create"></a>  CAtlTemporaryFile::Create  
 一時ファイルを作成するには、このメソッドを呼び出します。  
  
```
HRESULT Create(LPCTSTR pszDir = NULL, DWORD dwDesiredAccess = GENERIC_WRITE) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszDir`  
 一時ファイルのパス。 これは、NULL の場合場合、[値](http://msdn.microsoft.com/library/windows/desktop/aa364992)パスを割り当てるには、呼び出されます。  
  
 `dwDesiredAccess`  
 必要なアクセス。 参照してください`dwDesiredAccess`で[CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858) Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="example"></a>例  
 例を参照して[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)です。  
  
##  <a name="flush"></a>  CAtlTemporaryFile::Flush  
 このメソッドを呼び出して強制的に一時ファイルに書き込まれるファイル バッファーの残りの部分です。  
  
```
HRESULT Flush() throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 ような[CAtlTemporaryFile::HandsOff](#handsoff)ただし、ファイルが閉じられていません。  
  
### <a name="example"></a>例  
 例を参照して[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)です。  
  
##  <a name="getposition"></a>  CAtlTemporaryFile::GetPosition  
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
 ファイル ポインターの位置を変更するには、使用[CAtlTemporaryFile::Seek](#seek)です。  
  
##  <a name="getsize"></a>  CAtlTemporaryFile::GetSize  
 一時ファイルのバイト単位のサイズを取得するには、このメソッドを呼び出します。  
  
```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nLen`  
 ファイル内のバイト数。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
##  <a name="handsoff"></a>  CAtlTemporaryFile::HandsOff  
 ファイルの関連付けを解除するには、このメソッドを呼び出して、`CAtlTemporaryFile`オブジェクト。  
  
```
HRESULT HandsOff() throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 `HandsOff` および[CAtlTemporaryFile::HandsOn](#handson)オブジェクトからファイルの関連付けを解除して、再接続し、必要な場合に使用されます。 `HandsOff` 強制的に一時ファイルに書き込まれるファイル バッファーの残りの部分とし、ファイルを閉じます。 閉じるし、ファイルを完全に削除する場合、または閉じると、指定した名前のファイルの内容を保持、および使用する場合[CAtlTemporaryFile::Close](#close)です。  
  
##  <a name="handson"></a>  CAtlTemporaryFile::HandsOn  
 このメソッドを呼び出して既存の一時ファイルを開き、ファイルの末尾にカーソルを移動します。  
  
```
HRESULT HandsOn() throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 [CAtlTemporaryFile::HandsOff](#handsoff)と`HandsOn`オブジェクトからファイルの関連付けを解除して、再接続し、必要な場合に使用されます。  
  
##  <a name="lockrange"></a>  CAtlTemporaryFile::LockRange  
 他のプロセスがアクセスできないようにする一時ファイル内の領域をロックするには、このメソッドを呼び出します。  
  
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
 ファイル内のバイトをロックすると、他のプロセスがそれらのバイトにアクセスできなくなります。 ファイルの 1 つ以上の領域をロックすることができますが、重なり合う領域は許可されていません。 領域を正常にロックを解除するには使用[CAtlTemporaryFile::UnlockRange](#unlockrange)、以前にロックされている領域に正確に対応するバイトの範囲のことを確認します。 `LockRange` 隣接する領域をマージしませんロックされている 2 つの領域が隣接している場合は、する必要がありますロックを解除する各とは別にします。  
  
##  <a name="operator_handle"></a>  CAtlTemporaryFile::operator ハンドル  
 一時ファイルへのハンドルを返します。  
  
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
 `pBuffer`  
 ファイルから読み取られるデータを受け取るバッファーへのポインター。  
  
 `nBufSize`  
 バイト単位のバッファー サイズ。  
  
 `nBytesRead`  
 読み取られたバイト数。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 呼び出し[CAtlFile::Read](../../atl/reference/catlfile-class.md#read)です。 ファイル ポインターの位置を変更するには、呼び出す[CAtlTemporaryFile::Seek](#seek)です。  
  
### <a name="example"></a>例  
 例を参照して[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)です。  
  
##  <a name="seek"></a>  CAtlTemporaryFile::Seek  
 一時ファイルのファイル ポインターを移動するには、このメソッドを呼び出します。  
  
```
HRESULT Seek(LONGLONG nOffset, DWORD dwFrom = FILE_CURRENT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nOffset`  
 指定した開始ポイントからのバイト単位のオフセット*dwFrom です。*  
  
 `dwFrom`  
 (FILE_BEGIN、FILE_CURRENT、または FILE_END) の開始点。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 呼び出し[CAtlFile::Seek](../../atl/reference/catlfile-class.md#seek)です。 現在のファイル ポインターの位置を取得するを呼び出す[CAtlTemporaryFile::GetPosition](#getposition)です。  
  
### <a name="example"></a>例  
 例を参照して[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)です。  
  
##  <a name="setsize"></a>  CAtlTemporaryFile::SetSize  
 一時ファイルのサイズを設定するには、このメソッドを呼び出します。  
  
```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nNewLen`  
 (バイト単位)、ファイルの新しい長さ。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 呼び出し[CAtlFile::SetSize](../../atl/reference/catlfile-class.md#setsize)です。 返された場合は、ファイル ポインターは、ファイルの末尾に配置されます。  
  
##  <a name="tempfilename"></a>  CAtlTemporaryFile::TempFileName  
 一時ファイルの名前を返すには、このメソッドを呼び出します。  
  
```
LPCTSTR TempFileName() throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します、`LPCTSTR`ファイル名をポイントします。  
  
### <a name="remarks"></a>コメント  
 ファイル名が生成された[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)を呼び出して、 [GetTempFile](http://msdn.microsoft.com/library/windows/desktop/aa364991)Windows SDK 関数。 ファイル拡張子には、一時ファイル用 tfr「と」常になります。  
  
##  <a name="unlockrange"></a>  CAtlTemporaryFile::UnlockRange  
 一時ファイルの領域のロックを解除するには、このメソッドを呼び出します。  
  
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
 呼び出し[CAtlFile::UnlockRange](../../atl/reference/catlfile-class.md#unlockrange)です。  
  
##  <a name="write"></a>  CAtlTemporaryFile::Write  
 ファイル ポインターによって示される位置から一時ファイルにデータを書き込むには、このメソッドを呼び出します。  
  
```
HRESULT Write(  
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pBuffer`  
 ファイルに書き込まれるデータを保持するバッファー。  
  
 `nBufSize`  
 バッファーから転送されるバイト数。  
  
 `pnBytesWritten`  
 書き込むバイト数。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 呼び出し[CAtlFile::Write](../../atl/reference/catlfile-class.md#write)です。  
  
### <a name="example"></a>例  
 例を参照して[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)です。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CAtlFile クラス](../../atl/reference/catlfile-class.md)
