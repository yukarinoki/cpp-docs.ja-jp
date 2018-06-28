---
title: CInternetFile クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CInternetFile
- AFXINET/CInternetFile
- AFXINET/CInternetFile::CInternetFile
- AFXINET/CInternetFile::Abort
- AFXINET/CInternetFile::Close
- AFXINET/CInternetFile::Flush
- AFXINET/CInternetFile::GetLength
- AFXINET/CInternetFile::Read
- AFXINET/CInternetFile::ReadString
- AFXINET/CInternetFile::Seek
- AFXINET/CInternetFile::SetReadBufferSize
- AFXINET/CInternetFile::SetWriteBufferSize
- AFXINET/CInternetFile::Write
- AFXINET/CInternetFile::WriteString
- AFXINET/CInternetFile::m_hFile
dev_langs:
- C++
helpviewer_keywords:
- CInternetFile [MFC], CInternetFile
- CInternetFile [MFC], Abort
- CInternetFile [MFC], Close
- CInternetFile [MFC], Flush
- CInternetFile [MFC], GetLength
- CInternetFile [MFC], Read
- CInternetFile [MFC], ReadString
- CInternetFile [MFC], Seek
- CInternetFile [MFC], SetReadBufferSize
- CInternetFile [MFC], SetWriteBufferSize
- CInternetFile [MFC], Write
- CInternetFile [MFC], WriteString
- CInternetFile [MFC], m_hFile
ms.assetid: 96935681-ee71-4a8d-9783-5abc7b3e6f10
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c60027195024a9abb1af5ce5ec47dc6f6a6bfbf8
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038986"
---
# <a name="cinternetfile-class"></a>CInternetFile クラス
インターネット プロトコルを使用するリモート システム上のファイルにアクセスをできます。  
  
## <a name="syntax"></a>構文  
  
```  
class CInternetFile : public CStdioFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CInternetFile::CInternetFile](#cinternetfile)|`CInternetFile` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CInternetFile::Abort](#abort)|すべての警告とエラーを無視して、ファイルを閉じます。|  
|[CInternetFile::Close](#close)|閉じる、`CInternetFile`とそのリソースを解放します。|  
|[CInternetFile::Flush](#flush)|書き込みバッファーの内容をフラッシュし、ターゲット コンピューターにメモリ内のデータが書き込まれるようにします。|  
|[CInternetFile::GetLength](#getlength)|ファイルのサイズを返します。|  
|[細かい](#read)|指定されたバイト数を読み取ります。|  
|[CInternetFile::ReadString](#readstring)|文字のストリームを読み取ります。|  
|[CInternetFile::Seek](#seek)|開いているファイルのポインターを移動します。|  
|[CInternetFile::SetReadBufferSize](#setreadbuffersize)|データが読み取られるバッファーのサイズを設定します。|  
|[CInternetFile::SetWriteBufferSize](#setwritebuffersize)|データが書き込まれるバッファーのサイズを設定します。|  
|[CInternetFile::Write](#write)|指定されたバイト数を書き込みます。|  
|[CInternetFile::WriteString](#writestring)|Null で終わる文字列をファイルに書き込みます。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CInternetFile::operator HINTERNET](#operator_hinternet)|インターネット ハンドルのキャスト演算子です。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CInternetFile::m_hFile](#m_hfile)|ファイルへのハンドル。|  
  
## <a name="remarks"></a>Remarks  
 基本クラスを提供、 [CHttpFile](../../mfc/reference/chttpfile-class.md)と[CGopherFile](../../mfc/reference/cgopherfile-class.md)ファイル クラスです。 作成することはありません、`CInternetFile`オブジェクトに直接できます。 代わりに、呼び出すことによってその派生クラスの 1 つのオブジェクトを作成[CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile)または[しないで](../../mfc/reference/chttpconnection-class.md#openrequest)です。 作成することも、`CInternetFile`呼び出して[CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile)です。  
  
 `CInternetFile`メンバー関数`Open`、 `LockRange`、 `UnlockRange`、および`Duplicate`は適用されていない`CInternetFile`です。 これらの関数を呼び出す場合、`CInternetFile`オブジェクトを取得するが、[行わない](../../mfc/reference/cnotsupportedexception-class.md)です。  
  
 方法の詳細について`CInternetFile`クラスでは、その他の MFC インターネット機能が、記事を参照して[wininet の基礎を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 `CInternetFile`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxinet.h  
  
##  <a name="abort"></a>  CInternetFile::Abort  
 このオブジェクトに関連付けられているファイルを閉じ、ファイルを読み取りや書き込みに対して使用できなくなります。  
  
```  
virtual void Abort();
```  
  
### <a name="remarks"></a>Remarks  
 オブジェクトを破棄する前に、ファイルを閉じていない場合、デストラクターがファイルを閉じます。  
  
 例外を処理するときに`Abort`異なる[閉じる](#close)2 つの重要な点でします。 最初に、`Abort`障害を無視するため、関数がエラーに例外をスローしません。 2 番目、`Abort`しない**ASSERT**ファイルが開かれていない、またはが以前に閉じられました。  
  
##  <a name="cinternetfile"></a>  CInternetFile::CInternetFile  
 このメンバー関数が呼び出されます、`CInternetFile`オブジェクトを作成します。  
  
```  
CInternetFile(
    HINTERNET hFile,  
    LPCTSTR pstrFileName,  
    CInternetConnection* pConnection,  
    BOOL bReadMode);

 
CInternetFile(
    HINTERNET hFile,  
    HINTERNET hSession,  
    LPCTSTR pstrFileName,  
    LPCTSTR pstrServer,  
    DWORD_PTR dwContext,  
    BOOL bReadMode);
```  
  
### <a name="parameters"></a>パラメーター  
 *hFile*  
 インターネット ファイルへのハンドル。  
  
 *pstrFileName*  
 ファイル名を含む文字列へのポインター。  
  
 *pConnection*  
 ポインター、[関数](../../mfc/reference/cinternetconnection-class.md)オブジェクト。  
  
 *bReadMode*  
 ファイルは読み取り専用であるかどうかを示します。  
  
 *hSession*  
 インターネット セッションへのハンドル。  
  
 *pstrServer*  
 サーバーの名前を含む文字列へのポインター。  
  
 *独自*  
 コンテキスト識別子、`CInternetFile`オブジェクト。 参照してください[WinInet の基礎](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
### <a name="remarks"></a>Remarks  
 作成することはありません、`CInternetFile`オブジェクトに直接できます。 代わりに、呼び出すことによってその派生クラスの 1 つのオブジェクトを作成[CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile)または[しないで](../../mfc/reference/chttpconnection-class.md#openrequest)です。 作成することも、`CInternetFile`呼び出して[CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile)です。  
  
##  <a name="close"></a>  CInternetFile::Close  
 閉じる、`CInternetFile`のリソースを解放します。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Remarks  
 書き込みのため、ファイルが開かれた場合は、暗黙的な呼び出しを[フラッシュ](#flush)バッファーされたデータを確実には、ホストに書き込まれます。 呼び出す必要があります**閉じる**ファイルの使用が終了したときにします。  
  
##  <a name="flush"></a>  CInternetFile::Flush  
 書き込みバッファーの内容をフラッシュするには、このメンバー関数を呼び出します。  
  
```  
virtual void Flush();
```  
  
### <a name="remarks"></a>Remarks  
 使用して`Flush`ターゲット マシンにメモリ内のすべてのデータが実際に書き込まれたことを保証して、ホスト コンピューターとのトランザクションの完了を保証します。 `Flush` 有効になるのみ`CInternetFile`オブジェクトが書き込み用に開きます。  
  
##  <a name="getlength"></a>  CInternetFile::GetLength  
 ファイルのサイズを返します。  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
##  <a name="m_hfile"></a>  CInternetFile::m_hFile  
 このオブジェクトに関連付けられているファイルへのハンドル。  
  
```  
HINTERNET m_hFile;  
```  
  
##  <a name="operator_hinternet"></a>  CInternetFile::operator HINTERNET  
 この演算子を使用して、現在のインターネット セッションの Windows ハンドルを取得します。  
  
```  
operator HINTERNET() const;  
```  
  
##  <a name="read"></a>  細かい  
 開始位置として、指定されたメモリに読み込むには、このメンバー関数を呼び出す*lpvBuf*では、指定された数 (バイト単位) の*nCount*です。  
  
```  
virtual UINT Read(
    void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpBuf*  
 ファイル データを読み込むメモリ アドレスへのポインター。  
  
 *nCount*  
 書き込むバイト数。  
  
### <a name="return-value"></a>戻り値  
 バッファーに転送するバイト数。 戻り値より小さい*nCount*ファイルの末尾に達した場合。  
  
### <a name="remarks"></a>Remarks  
 実際に読み取られたバイト数を返します: 可能性のある数より小さい*nCount*ファイルが終了した場合。 ファイルの読み取り中にエラーが発生した場合、関数、 [CInternetException](../../mfc/reference/cinternetexception-class.md)エラーを説明するオブジェクト。 ファイルの末尾を越える読み取りはエラーとは見なされず、例外がスローされないことに注意してください。  
  
 すべてのデータが取得されることを確認するには、アプリケーションする必要がありますを引き続き呼び出す、**細かい**メソッドまで、0 を返します。  
  
##  <a name="readstring"></a>  CInternetFile::ReadString  
 改行文字が見つかるまでの文字のストリームを読み取るには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL ReadString(CString& rString);

 
virtual LPTSTR ReadString(
    LPTSTR pstr,  
    UINT nMax);
```  
  
### <a name="parameters"></a>パラメーター  
 *pstr*  
 読み取られる行を受け取る文字列へのポインター。  
  
 *nMax*  
 読み取り対象の文字の最大数。  
  
 *rString*  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)読み取り行を受け取るオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 取得した通常のデータを格納するバッファーへのポインター、 [CInternetFile](../../mfc/reference/cinternetfile-class.md)オブジェクト。 このメソッドに渡されたバッファーのデータ型に関係なく、データ (たとえば、Unicode に変換する) に任意の操作は行いません、構造体に返されるデータをマップする必要がありますので、予想として、 **void\*** 型が返されました。  
  
 **NULL**場合はブール値、またはすべてのデータを読み取り中にファイルの終端に達した場合**FALSE**データを読み込まずにファイルの終端に達した場合。  
  
### <a name="remarks"></a>Remarks  
 関数によって参照されるメモリに結果の行を配置する、 *pstr*パラメーター。 文字の読み取りを停止することによって指定された文字の最大数に達したとき*nMax*です。 バッファーは、常に終端の null 文字を受け取ります。  
  
 呼び出す場合`ReadString`最初呼び出さず[SetReadBufferSize](#setreadbuffersize)、4096 バイトまでのバッファーが表示されます。  
  
##  <a name="seek"></a>  CInternetFile::Seek  
 以前に開かれたファイルで、ポインターの位置を変更するには、このメンバー関数を呼び出します。  
  
```  
virtual ULONGLONG Seek(
    LONGLONG lOffset,  
    UINT nFrom);
```  
  
### <a name="parameters"></a>パラメーター  
 *lOffset*  
 ファイルの読み取り/書き込みのポインターを移動するバイト オフセットします。  
  
 *nFrom*  
 オフセットの相対参照します。 次の値のいずれかを指定する必要があります。  
  
- **CFile::begin**ファイル ポインターを移動*lOff*ファイルの先頭からのバイト数を転送します。  
  
- **CFile::current**ファイル ポインターを移動*lOff*ファイル内の現在位置からのバイト数。  
  
- **CFile::end**ファイル ポインターを移動*lOff*ファイルの末尾からのバイト数。 *lOff*必要がある既存にシークする負ファイルです。 正の値は、ファイルの末尾を越えたシークします。  
  
### <a name="return-value"></a>戻り値  
 要求された位置が正しい; 場合、ファイルの先頭からのオフセットの新しいバイトそれ以外の場合、値は未定義と[CInternetException](../../mfc/reference/cinternetexception-class.md)オブジェクトがスローされます。  
  
### <a name="remarks"></a>Remarks  
 `Seek`関数により、ファイルの内容へのランダム アクセス、ポインターを移動することによって、指定した量絶対的または相対的です。 データは、検索中に実際には読み込まれません。  
  
 この時点でこのメンバー関数への呼び出しのみがサポートされてデータに関連付けられている`CHttpFile`オブジェクト。 FTP または gopher 要求に対してはサポートされません。 呼び出す場合`Seek`これらのサポートされていないサービスの 1 つ、合格戻るする Win32 エラー コードを**ERROR_INTERNET_INVALID_OPERATION**です。  
  
 ファイルが開かれたときに、ファイル ポインターがオフセット 0 の場合、ファイルの先頭には。  
  
> [!NOTE]
>  使用して`Seek`暗黙的な呼び出しを生じる[フラッシュ](#flush)です。  
  
### <a name="example"></a>例  
  基本クラスの実装の例を参照してください ( [CFile::Seek](../../mfc/reference/cfile-class.md#seek))。  
  
##  <a name="setreadbuffersize"></a>  CInternetFile::SetReadBufferSize  
 によって使用される一時的な読み取りバッファーのサイズを設定するには、このメンバー関数を呼び出す、 `CInternetFile`-派生オブジェクト。  
  
```  
BOOL SetReadBufferSize(UINT nReadSize);
```  
  
### <a name="parameters"></a>パラメーター  
 *nReadSize*  
 バイト単位のバッファー サイズ。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのに呼び出せる可能性があります。  
  
### <a name="remarks"></a>Remarks  
 基になる WinInet Api はバッファー処理を実行できません、ように選択できるようにアプリケーションが読み取られるデータの量に関係なく、効率的にデータを読み取るバッファー サイズ。 各呼び出し場合[読み取り](#read)通常で大量 (たとえば、4 つ以上のキロバイト)、データの必要はありませんバッファー。 ただし、呼び出した場合`Read`、データの小さなチャンクを取得するを使用する場合、または[ReadString](#readstring)読み取りバッファーは、アプリケーションのパフォーマンスを向上し、一度に 1 行ずつを読み取る。  
  
 既定では、`CInternetFile`オブジェクトがすべての読み取りバッファーを提供していません。 このメンバー関数を呼び出す場合は、ファイルが読み取りアクセスで開かれたことを確認する必要があります。  
  
 いつでも、バッファー サイズを増やすことができますが、バッファーを縮小効果がありません。 呼び出す場合[ReadString](#readstring)最初呼び出さず`SetReadBufferSize`、4096 バイトまでのバッファーが表示されます。  
  
##  <a name="setwritebuffersize"></a>  CInternetFile::SetWriteBufferSize  
 によって使用される一時的な書き込みバッファーのサイズを設定するには、このメンバー関数を呼び出す、 `CInternetFile`-派生オブジェクト。  
  
```  
BOOL SetWriteBufferSize(UINT nWriteSize);
```  
  
### <a name="parameters"></a>パラメーター  
 *nWriteSize*  
 バッファーのサイズ (バイト単位)。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのに呼び出せる可能性があります。  
  
### <a name="remarks"></a>Remarks  
 デバッグ情報を基になる、WinInet Api は、バッファリングを実行しないよう書き込まれるデータの量に関係なく効率的にデータを書き込むアプリケーションは、バッファー サイズに選択します。 各呼び出し場合[書き込み](#write)膨大な量は通常、(たとえば、次の 4 つまたは複数キロバイト一度に)、データの必要はありませんバッファー。 ただし、呼び出した場合[書き込み](#write)書き込みバッファーを記述するには、データの小さなチャンクには、アプリケーションのパフォーマンスを向上させます。  
  
 既定では、`CInternetFile`オブジェクトがすべての書き込みバッファーを提供していません。 このメンバー関数を呼び出す場合は、書き込みアクセス用のファイルが開かれたことを確認する必要があります。 書き込みバッファーのサイズを変更するには、いつでも、その場合、暗黙的な呼び出しを[フラッシュ](#flush)です。  
  
##  <a name="write"></a>  CInternetFile::Write  
 特定のメモリに書き込むには、このメンバー関数を呼び出す*lpvBuf*では、(バイト単位) の数を指定した*nCount*です。  
  
```  
virtual void Write(
    const void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpBuf*  
 書き込まれる最初のバイトへのポインター。  
  
 *nCount*  
 書き込むバイト数を指定します。  
  
### <a name="remarks"></a>Remarks  
 データの書き込み中にエラーが発生した場合、関数、 [CInternetException](../../mfc/reference/cinternetexception-class.md)エラーを説明するオブジェクト。  
  
##  <a name="writestring"></a>  CInternetFile::WriteString  
 この関数は、null で終わる文字列を関連付けられたファイルに書き込みます。  
  
```  
virtual void WriteString(LPCTSTR pstr);
```  
  
### <a name="parameters"></a>パラメーター  
 *pstr*  
 書き込まれるコンテンツを含む文字列へのポインター。  
  
### <a name="remarks"></a>Remarks  
 データの書き込み中にエラーが発生した場合、関数、 [CInternetException](../../mfc/reference/cinternetexception-class.md)エラーを説明するオブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [CStdioFile クラス](../../mfc/reference/cstdiofile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CInternetConnection クラス](../../mfc/reference/cinternetconnection-class.md)
