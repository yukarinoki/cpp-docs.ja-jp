---
title: CFtpFileFind クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFtpFileFind
- AFXINET/CFtpFileFind
- AFXINET/CFtpFileFind::CFtpFileFind
- AFXINET/CFtpFileFind::FindFile
- AFXINET/CFtpFileFind::FindNextFile
- AFXINET/CFtpFileFind::GetFileURL
dev_langs:
- C++
helpviewer_keywords:
- CFtpFileFind [MFC], CFtpFileFind
- CFtpFileFind [MFC], FindFile
- CFtpFileFind [MFC], FindNextFile
- CFtpFileFind [MFC], GetFileURL
ms.assetid: 9667cf01-657f-4b11-b9db-f11e5a7b4e4c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6ba8f6d8cf90e7523fe4497cfc3b36c3616a8f10
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956279"
---
# <a name="cftpfilefind-class"></a>CFtpFileFind クラス
FTP サーバーのインターネット ファイル検索を支援します。  
  
## <a name="syntax"></a>構文  
  
```  
class CFtpFileFind : public CFileFind  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFtpFileFind::CFtpFileFind](#cftpfilefind)|`CFtpFileFind` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFtpFileFind::FindFile](#findfile)|FTP サーバー上のファイルを検索します。|  
|[CFtpFileFind::FindNextFile](#findnextfile)|以前の呼び出しからファイル検索を続行[FindFile](#findfile)です。|  
|[CFtpFileFind::GetFileURL](#getfileurl)|見つかったファイルのパスを含む URL を取得します。|  
  
## <a name="remarks"></a>Remarks  
 `CFtpFileFind` 検索を開始し、ファイルを検索し、URL またはファイルに関するその他のわかりやすい情報を返すメンバー関数が含まれます。  
  
 インターネットとローカル ファイルの検索を含めるために設計されて他の MFC クラス[CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)と[CFileFind](../../mfc/reference/cfilefind-class.md)です。 と共に`CFtpFileFind`、これらのクラスは、クライアント プロトコルまたはファイルの種類 (ローカル コンピューターまたはリモート サーバー)、サーバーに関係なく、特定のファイルを検索するためのシームレスなメカニズムを提供します。 HTTP は検索に必要なファイルを直接操作をサポートしていないために、HTTP サーバーで検索するための MFC クラスがないことに注意してください。  
  
 使用する方法の詳細についての`CFtpFileFind`し、その他の WinInet クラスは、記事を参照して[wininet の基礎を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)です。  
  
## <a name="example"></a>例  
 次のコードでは、FTP サーバーの現在のディレクトリ内のすべてのファイルを列挙する方法を示します。  
  
 [!code-cpp[NVC_MFCWinInet#8](../../mfc/codesnippet/cpp/cftpfilefind-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CFtpFileFind`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxinet.h  
  
##  <a name="cftpfilefind"></a>  CFtpFileFind::CFtpFileFind  
 このメンバー関数は構築するために、`CFtpFileFind`オブジェクト。  
  
```  
explicit CFtpFileFind(
    CFtpConnection* pConnection,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 *pConnection*  
 ポインター、`CFtpConnection`オブジェクト。 FTP 接続を取得するには呼び出すことによって[CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)です。  
  
 *独自*  
 コンテキスト識別子、`CFtpFileFind`オブジェクト。 参照してください**解説**このパラメーターの詳細についてはします。  
  
### <a name="remarks"></a>Remarks  
 既定値*独自*に MFC によって送信される、`CFtpFileFind`オブジェクトから、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトの作成、`CFtpFileFind`オブジェクト。 コンテキスト識別子を独自の値に設定する既定をオーバーライドすることができます。 コンテキスト識別子に返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)いる識別されるオブジェクトの状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
### <a name="example"></a>例  
  このトピックの「クラスの概要の例を参照してください。  
  
##  <a name="findfile"></a>  CFtpFileFind::FindFile  
 FTP ファイルを検索するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```  
  
### <a name="parameters"></a>パラメーター  
 *pstrName*  
 検索するファイルの名前を含む文字列へのポインター。 場合**NULL**呼び出しは (*) ワイルドカード検索を実行します。  
  
 *dwFlags*  
 このセッションを処理する方法を示すフラグ。 これらのフラグは、ビットごとの OR 演算子と組み合わせることができます (&#124;) し、次に示します。  
  
-   INTERNET_FLAG_RELOAD がローカルにキャッシュされている場合でも、通信回線からデータを取得します。 これは、既定のフラグです。  
  
-   ローカルまたはすべてのゲートウェイには、データをキャッシュ INTERNET_FLAG_DONT_CACHE しません。  
  
-   INTERNET_FLAG_RAW_DATA が生データを返す既定値を上書き ( [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) FTP の構造体)。  
  
-   Secure Sockets Layer や率とネットワーク上でのトランザクションの INTERNET_FLAG_SECURE をセキュリティで保護 このフラグは、HTTP 要求のみに適用します。  
  
-   INTERNET_FLAG_EXISTING_CONNECT 可能な場合は、新しいサーバーに既存の接続を再利用**FindFile**要求ごとに新しいセッションを作成する代わりに要求します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 拡張エラー情報を取得する Win32 関数を呼び出す[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)です。  
  
### <a name="remarks"></a>Remarks  
 呼び出した後**FindFile** FTP の最初のファイルを取得するを呼び出すことができます[FindNextFile](#findnextfile)を後続の FTP のファイルを取得します。  
  
### <a name="example"></a>例  
  このトピックで前の例を参照してください。  
  
##  <a name="findnextfile"></a>  CFtpFileFind::FindNextFile  
 呼び出しで開始されたファイルの検索を続行するには、このメンバー関数を呼び出す、 [FindFile](#findfile)メンバー関数。  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>戻り値  
 多くのファイルがある場合は 0 以外。見つかったファイルがディレクトリに最後の 1 つである場合、またはエラーが発生した場合は 0 します。 拡張エラー情報を取得する Win32 関数を呼び出す[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)です。 見つかったファイルがディレクトリに最後のファイルまたは一致するファイルが見つからないことができる場合、 `GetLastError` ERROR_NO_MORE_FILES を返します。  
  
### <a name="remarks"></a>Remarks  
 任意の属性の関数を呼び出す前に少なくとも 1 回この関数を呼び出す必要があります (を参照してください[呼び出しておく](../../mfc/reference/cfilefind-class.md#findnextfile))。  
  
 `FindNextFile` Win32 関数をラップ[FindNextFile](http://msdn.microsoft.com/library/windows/desktop/aa364428)です。  
  
### <a name="example"></a>例  
  このトピックの前半の例を参照してください。  
  
##  <a name="getfileurl"></a>  CFtpFileFind::GetFileURL  
 指定されたファイルの URL を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ファイル名とパスの Universal Resource Locator (URL)。  
  
### <a name="remarks"></a>Remarks  
 `GetFileURL` このメンバー関数に似ています[CFileFind::GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)形式で URL を返します点を除き、`ftp://moose/dir/file.txt`です。  
  
## <a name="see-also"></a>関連項目  
 [CFileFind クラス](../../mfc/reference/cfilefind-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CGopherFileFind クラス](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile クラス](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile クラス](../../mfc/reference/chttpfile-class.md)
