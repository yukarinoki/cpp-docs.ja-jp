---
title: CFtpConnection クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFtpConnection
- AFXINET/CFtpConnection
- AFXINET/CFtpConnection::CFtpConnection
- AFXINET/CFtpConnection::Command
- AFXINET/CFtpConnection::CreateDirectory
- AFXINET/CFtpConnection::GetCurrentDirectory
- AFXINET/CFtpConnection::GetCurrentDirectoryAsURL
- AFXINET/CFtpConnection::GetFile
- AFXINET/CFtpConnection::OpenFile
- AFXINET/CFtpConnection::PutFile
- AFXINET/CFtpConnection::Remove
- AFXINET/CFtpConnection::RemoveDirectory
- AFXINET/CFtpConnection::Rename
- AFXINET/CFtpConnection::SetCurrentDirectory
dev_langs:
- C++
helpviewer_keywords:
- CFtpConnection [MFC], CFtpConnection
- CFtpConnection [MFC], Command
- CFtpConnection [MFC], CreateDirectory
- CFtpConnection [MFC], GetCurrentDirectory
- CFtpConnection [MFC], GetCurrentDirectoryAsURL
- CFtpConnection [MFC], GetFile
- CFtpConnection [MFC], OpenFile
- CFtpConnection [MFC], PutFile
- CFtpConnection [MFC], Remove
- CFtpConnection [MFC], RemoveDirectory
- CFtpConnection [MFC], Rename
- CFtpConnection [MFC], SetCurrentDirectory
ms.assetid: 5e3a0501-8893-49cf-a3d5-0628d8d6b936
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f43df1cb610c785688db982be2ddc4a19cf140b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374537"
---
# <a name="cftpconnection-class"></a>CFtpConnection クラス
FTP サーバーへの接続、インターネットを管理し、そのサーバー上のディレクトリおよびファイルの直接の操作を実行できます。  
  
## <a name="syntax"></a>構文  
  
```  
class CFtpConnection : public CInternetConnection  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFtpConnection::CFtpConnection](#cftpconnection)|`CFtpConnection` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFtpConnection::Command](#command)|FTP サーバーに直接コマンドを送信します。|  
|[CFtpConnection::CreateDirectory](#createdirectory)|サーバー上のディレクトリを作成します。|  
|[CFtpConnection::GetCurrentDirectory](#getcurrentdirectory)|この接続の現在のディレクトリを取得します。|  
|[CFtpConnection::GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)|この接続を URL としての現在のディレクトリを取得します。|  
|[CFtpConnection::GetFile](#getfile)|接続先のサーバーからファイルを取得します。|  
|[CFtpConnection::OpenFile](#openfile)|接続先のサーバー上のファイルを開きます。|  
|[CFtpConnection::PutFile](#putfile)|サーバー上のファイルを配置します。|  
|[CFtpConnection::Remove](#remove)|サーバーからファイルを削除します。|  
|[CFtpConnection::RemoveDirectory](#removedirectory)|サーバーから指定されたディレクトリを削除します。|  
|[CFtpConnection::Rename](#rename)|サーバー上のファイルの名前を変更します。|  
|[CFtpConnection::SetCurrentDirectory](#setcurrentdirectory)|現在の FTP ディレクトリを設定します。|  
  
## <a name="remarks"></a>コメント  
 FTP では、MFC WinInet クラスによって認識される 3 つのインターネット サービスの 1 つです。  
  
 Ftp サーバーを通信するためのインスタンスを作成する必要がありますまず[CInternetSession](../../mfc/reference/cinternetsession-class.md)、し、作成、`CFtpConnection`オブジェクト。 作成することはありません、`CFtpConnection`オブジェクトに直接。 関数を呼び出す代わりに、 [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)、作成する、`CFtpConnection`オブジェクトと、ポインターを返します。  
  
 方法の詳細について`CFtpConnection`クラスでは、その他の MFC インターネット機能が、記事を参照して[wininet の基礎を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)です。 サービス、HTTP、gopher は、クラスを参照してください。 サポートされている他の 2 つとの通信の詳細については[CHttpConnection](../../mfc/reference/chttpconnection-class.md)と[関数](../../mfc/reference/cgopherconnection-class.md)です。  
  
## <a name="example"></a>例  
  例を参照してください、 [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)クラスの概要です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CFtpConnection`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxinet.h  
  
##  <a name="cftpconnection"></a>  CFtpConnection::CFtpConnection  
 このメンバー関数は構築するために、`CFtpConnection`オブジェクト。  
  
```  
CFtpConnection(
    CInternetSession* pSession,  
    HINTERNET hConnected,  
    LPCTSTR pstrServer,  
    DWORD_PTR dwContext);

 
CFtpConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    DWORD_PTR dwContext = 0,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    BOOL bPassive = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSession`  
 関連するへのポインター [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクト。  
  
 `hConnected`  
 現在のインターネット セッションの Windows ハンドル。  
  
 `pstrServer`  
 FTP サーバーの名前を含む文字列へのポインター。  
  
 `dwContext`  
 操作のコンテキストの識別子。 `dwContext` によって返される操作のステータス情報を識別する[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)です。 既定値を 1 に設定します。ただし、操作の特定のコンテキスト ID を明示的に割り当てることができます。 オブジェクトとその動作はしたコンテキスト ID と関連付けられます  
  
 `pstrUserName`  
 ログインするユーザーの名前を指定する null で終わる文字列へのポインター。 場合**NULL**、既定値は匿名です。  
  
 `pstrPassword`  
 ログインに使用するパスワードを指定する null で終わる文字列へのポインター。 両方`pstrPassword`と`pstrUserName`は**NULL**既定の匿名パスワードはユーザーの電子メール名。 場合`pstrPassword`は**NULL** (または空の文字列) が、`pstrUserName`は**NULL**、空白のパスワードを使用します。 次の表の 4 種類の設定の動作は、`pstrUserName`と`pstrPassword`:  
  
|`pstrUserName`|`pstrPassword`|FTP サーバーに送信されるユーザー名|FTP サーバーに送信されたパスワード|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|**NULL**または""|**NULL**または""|「匿名」|ユーザーの電子メール名|  
|非- **NULL**文字列|**NULL**または""|`pstrUserName`|" "|  
|**NULL**以外**NULL**文字列|**エラー**|**エラー**||  
|非- **NULL**文字列|非- **NULL**文字列|`pstrUserName`|`pstrPassword`|  
  
 `nPort`  
 サーバーで使用する TCP/IP ポートを識別する番号。  
  
 `bPassive`  
 この FTP セッションのパッシブまたはアクティブ モードを指定します。 場合に設定**TRUE**、Win32 API を設定して`dwFlag`に**INTERNET_FLAG_PASSIVE**です。  
  
### <a name="remarks"></a>コメント  
 作成することはありません、`CFtpConnection`オブジェクトに直接できます。 代わりに、 [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)、作成する、 **CFptConnection**オブジェクト。  
  
##  <a name="command"></a>  CFtpConnection::Command  
 FTP サーバーに直接コマンドを送信します。  
  
```  
CInternetFile* Command(
    LPCTSTR pszCommand,  
    CmdResponseType eResponse = CmdRespNone,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszCommand`  
 送信されるコマンドが含まれている文字列へのポインター。  
  
 *eResponse*  
 FTP サーバーからの応答が予期されているかどうかを判断します。 次のいずれかの値になります。  
  
- **CmdRespNone**応答は発生しません。  
  
- **CmdRespRead**の応答を想定します。  
  
 `dwFlags`  
 この関数を制御するフラグが含まれている値。 完全な一覧についてを参照してください。 [FTPCommand](http://msdn.microsoft.com/library/windows/desktop/aa384133)です。  
  
 `dwContext`  
 コールバックでアプリケーションのコンテキストを識別するために使用されるアプリケーション定義の値が含まれている値へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [FTPCommand](http://msdn.microsoft.com/library/windows/desktop/aa384133)関数は、Windows SDK で説明します。  
  
 エラーが発生する場合、MFC に型の例外がスロー [CInternetException](../../mfc/reference/cinternetexception-class.md)です。  
  
##  <a name="createdirectory"></a>  CFtpConnection::CreateDirectory  
 接続先のサーバーでディレクトリを作成するには、このメンバー関数を呼び出します。  
  
```  
BOOL CreateDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrDirName`  
 作成するディレクトリの名前を含む文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Windows の関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのに呼び出せる可能性があります。  
  
### <a name="remarks"></a>コメント  
 使用して`GetCurrentDirectory`をこのサーバーへの接続の現在の作業ディレクトリを決定します。 リモート システムに接続されていることをルート ディレクトリとは限りません。  
  
 `pstrDirName`パラメーターには、いずれかを指定できます、部分的または完全修飾ファイル名、現在のディレクトリに対して相対的です。 円記号 (\\) またはいずれかの名前のディレクトリの区切り記号としてスラッシュ (/) を使用できます。 `CreateDirectory` 使用される前に、ディレクトリ名の区切り記号を適切な文字を変換します。  
  
##  <a name="getcurrentdirectory"></a>  CFtpConnection::GetCurrentDirectory  
 現在のディレクトリの名前を取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetCurrentDirectory(CString& strDirName) const;  
  
BOOL GetCurrentDirectory(
    LPTSTR pstrDirName,  
    LPDWORD lpdwLen) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `strDirName`  
 ディレクトリの名前を受け取る文字列への参照。  
  
 `pstrDirName`  
 ディレクトリの名前を受け取る文字列へのポインター。  
  
 `lpdwLen`  
 次の情報を含む DWORD へのポインター。  
  
|||  
|-|-|  
|エントリ|によって参照されるバッファーのサイズ`pstrDirName`です。|  
|返された場合|格納されている文字数`pstrDirName`です。 かどうか、メンバー関数は失敗し、ERROR_INSUFFICIENT_BUFFER が戻り、`lpdwLen`バイト数、アプリケーションが、文字列を受信するために割り当てる必要がありますにはが含まれています。|  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのに呼び出せる可能性があります。  
  
### <a name="remarks"></a>コメント  
 URL として代わりに、ディレクトリ名を取得する[GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)です。  
  
 パラメーター`pstrDirName`または`strDirName`は現在のディレクトリに対して相対的か部分修飾ファイル名または完全修飾します。 円記号 (\\) またはいずれかの名前のディレクトリの区切り記号としてスラッシュ (/) を使用できます。 `GetCurrentDirectory` 使用される前に、ディレクトリ名の区切り記号を適切な文字を変換します。  
  
##  <a name="getcurrentdirectoryasurl"></a>  CFtpConnection::GetCurrentDirectoryAsURL  
 URL として現在のディレクトリの名前を取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetCurrentDirectoryAsURL(CString& strDirName) const;  
  
BOOL GetCurrentDirectoryAsURL(
    LPTSTR pstrName,  
    LPDWORD lpdwLen) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `strDirName`  
 ディレクトリの名前を受け取る文字列への参照。  
  
 `pstrDirName`  
 ディレクトリの名前を受け取る文字列へのポインター。  
  
 `lpdwLen`  
 次の情報を含む DWORD へのポインター。  
  
|||  
|-|-|  
|エントリ|によって参照されるバッファーのサイズ`pstrDirName`です。|  
|返された場合|格納されている文字数`pstrDirName`です。 かどうか、メンバー関数は失敗し、ERROR_INSUFFICIENT_BUFFER が戻り、`lpdwLen`バイト数、アプリケーションが、文字列を受信するために割り当てる必要がありますにはが含まれています。|  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのに呼び出せる可能性があります。  
  
### <a name="remarks"></a>コメント  
 `GetCurrentDirectoryAsURL` 同じように動作[GetCurrentDirectory](#getcurrentdirectory)  
  
 パラメーター`strDirName`は現在のディレクトリに対して相対的か部分修飾ファイル名または完全修飾します。 円記号 (\\) またはいずれかの名前のディレクトリの区切り記号としてスラッシュ (/) を使用できます。 `GetCurrentDirectoryAsURL` 使用される前に、ディレクトリ名の区切り記号を適切な文字を変換します。  
  
##  <a name="getfile"></a>  CFtpConnection::GetFile  
 FTP サーバーからファイルを取得し、ローカル コンピューターに格納するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetFile(
    LPCTSTR pstrRemoteFile,  
    LPCTSTR pstrLocalFile,  
    BOOL bFailIfExists = TRUE,  
    DWORD dwAttributes = FILE_ATTRIBUTE_NORMAL,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrRemoteFile`  
 FTP サーバーから取得するファイルの名前を表す null で終わる文字列へのポインター。  
  
 `pstrLocalFile`  
 ローカル システム上に作成するファイルの名前を表す null で終わる文字列へのポインター。  
  
 *bFailIfExists*  
 かどうかファイル名は既存のファイルで既に使用可能性がありますを示します。 ローカル ファイルの名前が既に存在するかどうかと、このパラメーターは**TRUE**、`GetFile`は失敗します。 それ以外の場合、`GetFile`既存のファイルのコピーが消去されます。  
  
 `dwAttributes`  
 ファイルの属性を示します。 次の FILE_ATTRIBUTE_ * フラグの任意の組み合わせを指定できます。  
  
-   FILE_ATTRIBUTE_ARCHIVE ファイルは、アーカイブ ファイルです。 アプリケーションでは、この属性を使用して、ファイルをバックアップまたは削除としてマークします。  
  
-   FILE_ATTRIBUTE_COMPRESSED ファイルまたはディレクトリが圧縮されます。 ファイルの場合、圧縮はのすべてのファイルにデータが圧縮されていることを意味します。 ディレクトリの場合は、圧縮は、新しく作成されたファイルとサブディレクトリの既定値です。  
  
-   FILE_ATTRIBUTE_DIRECTORY ファイルは、ディレクトリです。  
  
-   FILE_ATTRIBUTE_NORMAL ファイルには、他の属性セットがありません。 この属性は、単独で使用される場合にのみ有効です。 その他のすべてのファイル属性は、FILE_ATTRIBUTE_NORMAL をオーバーライドします。  
  
-   FILE_ATTRIBUTE_HIDDEN ファイルは表示されません。 通常のディレクトリ一覧に含めることは。  
  
-   FILE_ATTRIBUTE_READONLY ファイルは読み取り専用です。 アプリケーションできますファイルの読み取りことはできませんへの書き込みまたは削除。  
  
-   FILE_ATTRIBUTE_SYSTEM ファイルの一部であるか、オペレーティング システムのみで使用します。  
  
-   FILE_ATTRIBUTE_TEMPORARY ファイルは、一時的なストレージの使用されています。 アプリケーションは、絶対に必要な場合にのみ、ファイルに書き込む必要があります。 ファイルのデータの大部分は、ファイルがすぐに削除されるため、メディアに書き込まれずに、メモリに残ります。  
  
 `dwFlags`  
 転送が発生する条件を指定します。 このパラメーターには、いずれかを指定できます、`dwFlags`で説明されている値[FtpGetFile](http://msdn.microsoft.com/library/windows/desktop/aa384157) Windows SDK に含まれています。  
  
 `dwContext`  
 ファイルを取得するためのコンテキスト識別子です。 参照してください**解説**の詳細については`dwContext`します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのに呼び出せる可能性があります。  
  
### <a name="remarks"></a>コメント  
 `GetFile` FTP サーバーからファイルを読み取ったり、ローカルに保存することに関連するオーバーヘッドのすべてを処理する高度なルーチンです。 ファイル データのみを取得する、またはファイル転送を閉じる制御を必要とするアプリケーションを使用する必要があります`OpenFile`と[細かい](../../mfc/reference/cinternetfile-class.md#read)代わりにします。  
  
 場合`dwFlags`FILE_TRANSFER_TYPE_ASCII、ファイル データの翻訳も変換コントロールおよび同等の Windows に文字の書式設定します。 既定の転送は、場所、ファイルは、同じ形式でサーバーに格納されているバイナリ モードは、です。  
  
 両方`pstrRemoteFile`と`pstrLocalFile`は現在のディレクトリに対して相対的か部分修飾ファイル名または完全修飾します。 円記号 (\\) またはいずれかの名前のディレクトリの区切り記号としてスラッシュ (/) を使用できます。 `GetFile` 使用される前に、ディレクトリ名の区切り記号を適切な文字を変換します。  
  
 `dwContext` の既定値をオーバーライドして、コンテキスト識別子を独自の値に設定します。 コンテキスト識別子にこの特定の操作に関連付けられて、`CFtpConnection`によって作成されたオブジェクトの[CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクト。 値が返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)特定ために使用する操作の状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
##  <a name="openfile"></a>  CFtpConnection::OpenFile  
 読み取りまたは書き込み用に FTP サーバー上にあるファイルを開くには、このメンバー関数を呼び出します。  
  
```  
CInternetFile* OpenFile(
    LPCTSTR pstrFileName,  
    DWORD dwAccess = GENERIC_READ,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrFileName`  
 開かれるファイルの名前を含む文字列へのポインター。  
  
 *dwAccess*  
 ファイルへのアクセス方法を決定します。 GENERIC_READ と GENERIC_WRITE の両方ではなくはどちらかを指定できます。  
  
 `dwFlags`  
 その後の転送が発生する状況を指定します。 次の FTP_TRANSFER_ * 定数のいずれかを指定できます。  
  
-   FTP_TRANSFER_TYPE_ASCII ファイルは、FTP ASCII (A の種類) 転送メソッドを使用して転送します。 変換コントロールと同等のローカルに書式設定情報。  
  
-   FTP_TRANSFER_TYPE_BINARY ファイルは、(タイプ I) FTP's イメージの転送方法を使用してデータを転送します。 正確にデータを転送するファイルが存在する変更はありません。 これは、既定の転送方法です。  
  
 `dwContext`  
 ファイルを開くためのコンテキスト識別子です。 参照してください**解説**の詳細については`dwContext`します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CInternetFile](../../mfc/reference/cinternetfile-class.md)オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `OpenFile` 次の状況で使用する必要があります。  
  
-   アプリケーション データを持っているが、そのデータはローカル ファイルに送信して、FTP サーバー上のファイルとして作成する必要があります。 1 回`OpenFile`、アプリケーションはファイルを開き[CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write) FTP ファイル データをサーバーに送信します。  
  
-   アプリケーションは、サーバーからファイルを取得しをディスクに書き込むのではなく、アプリケーションが制御するメモリに配置する必要があります。 アプリケーションを使用して[細かい](../../mfc/reference/cinternetfile-class.md#read)を使用した後`OpenFile`ファイルを開きます。  
  
-   アプリケーションでは、細かいレベルのファイル転送で制御が必要です。 たとえば、アプリケーションが、進行状況を表示できます。 コントロールは、ファイルのダウンロード中にファイル転送の状態の進行状況を示します。  
  
 呼び出した後`OpenFile`通話まで**CInternetConnection::Close**、アプリケーションが呼び出すことができますのみ[細かい](../../mfc/reference/cinternetfile-class.md#read)、 [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write)、**CInternetConnection::Close**、または[CFtpFileFind::FindFile](../../mfc/reference/cftpfilefind-class.md#findfile)です。 FTP セッションを同じの他の FTP 関数への呼び出しは失敗し、FTP_ETRANSFER_IN_PROGRESS にエラー コードを設定します。  
  
 `pstrFileName`パラメーターは、部分修飾ファイル名、現在のディレクトリに相対パスまたは完全修飾を指定できます。 円記号 (\\) またはいずれかの名前のディレクトリの区切り記号としてスラッシュ (/) を使用できます。 `OpenFile` 使用する前に、ディレクトリ名の区切り記号を適切な文字を変換します。  
  
 `dwContext` の既定値をオーバーライドして、コンテキスト識別子を独自の値に設定します。 コンテキスト識別子にこの特定の操作に関連付けられて、`CFtpConnection`によって作成されたオブジェクトの[CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクト。 値が返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)特定ために使用する操作の状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
##  <a name="putfile"></a>  CFtpConnection::PutFile  
 FTP サーバー上のファイルを保存するには、このメンバー関数を呼び出します。  
  
```  
BOOL PutFile(
    LPCTSTR pstrLocalFile,  
    LPCTSTR pstrRemoteFile,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrLocalFile`  
 ローカル システムから送信するファイルの名前を含む文字列へのポインター。  
  
 `pstrRemoteFile`  
 FTP サーバー上に作成するファイルの名前を含む文字列へのポインター。  
  
 `dwFlags`  
 ファイルの転送が発生する条件を指定します。 説明されている FTP_TRANSFER_ * 定数のいずれかの[OpenFile](#openfile)です。  
  
 `dwContext`  
 ファイルを配置するためのコンテキスト識別子です。 参照してください**解説**の詳細については`dwContext`します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのに呼び出せる可能性があります。  
  
### <a name="remarks"></a>コメント  
 `PutFile` すべての FTP サーバー上のファイルを保存するのに関連付けられている操作を処理する高度なルーチン。 のみ、データを送信する、またはファイル転送によく制御を必要とするアプリケーションを使用する必要があります[OpenFile](#openfile)と[CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write)です。  
  
 `dwContext` の既定値をオーバーライドして、コンテキスト識別子を独自の値に設定します。 コンテキスト識別子にこの特定の操作に関連付けられて、`CFtpConnection`によって作成されたオブジェクトの[CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクト。 値が返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)特定ために使用する操作の状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
##  <a name="remove"></a>  CFtpConnection::Remove  
 接続先のサーバーから、指定したファイルを削除するには、このメンバー関数を呼び出します。  
  
```  
BOOL Remove(LPCTSTR pstrFileName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrFileName`  
 削除するファイル名を含む文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのに呼び出せる可能性があります。  
  
### <a name="remarks"></a>コメント  
 `pstrFileName`パラメーターは、部分修飾ファイル名、現在のディレクトリに相対パスまたは完全修飾を指定できます。 円記号 (\\) またはいずれかの名前のディレクトリの区切り記号としてスラッシュ (/) を使用できます。 **削除**関数は、使用される前に、ディレクトリ名の区切り記号を適切な文字を変換します。  
  
##  <a name="removedirectory"></a>  CFtpConnection::RemoveDirectory  
 接続先のサーバーから指定されたディレクトリを削除するには、このメンバー関数を呼び出します。  
  
```  
BOOL RemoveDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrDirName`  
 削除するディレクトリを含む文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのに呼び出せる可能性があります。  
  
### <a name="remarks"></a>コメント  
 使用して[GetCurrentDirectory](#getcurrentdirectory)をサーバーの現在の作業ディレクトリを決定します。 リモート システムに接続されていることをルート ディレクトリとは限りません。  
  
 `pstrDirName`パラメーターか、部分的または完全修飾ファイル名の現在のディレクトリに対して相対的に指定できます。 円記号 (\\) またはいずれかの名前のディレクトリの区切り記号としてスラッシュ (/) を使用できます。 `RemoveDirectory` 使用される前に、ディレクトリ名の区切り記号を適切な文字を変換します。  
  
##  <a name="rename"></a>  CFtpConnection::Rename  
 接続先のサーバー上の指定のファイルの名前を変更するには、このメンバー関数を呼び出します。  
  
```  
BOOL Rename(
    LPCTSTR pstrExisting,  
    LPCTSTR pstrNew);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrExisting`  
 名前を変更するファイルの現在の名前を含む文字列へのポインター。  
  
 `pstrNew`  
 ファイルの新しい名前を含む文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのに呼び出せる可能性があります。  
  
### <a name="remarks"></a>コメント  
 `pstrExisting`と`pstrNew`パラメーターは、部分修飾ファイル名、現在のディレクトリに相対パスまたは完全修飾できます。 円記号 (\\) またはいずれかの名前のディレクトリの区切り記号としてスラッシュ (/) を使用できます。 **名前を変更**される前に、ディレクトリ名の区切り記号を適切な文字に変換します。  
  
##  <a name="setcurrentdirectory"></a>  CFtpConnection::SetCurrentDirectory  
 FTP サーバー上の別のディレクトリに変更するには、このメンバー関数を呼び出します。  
  
```  
BOOL SetCurrentDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrDirName`  
 ディレクトリの名前を含む文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのに呼び出せる可能性があります。  
  
### <a name="remarks"></a>コメント  
 `pstrDirName`パラメーターか、部分的または完全修飾ファイル名の現在のディレクトリに対して相対的に指定できます。 円記号 (\\) またはいずれかの名前のディレクトリの区切り記号としてスラッシュ (/) を使用できます。 `SetCurrentDirectory` 使用される前に、ディレクトリ名の区切り記号を適切な文字を変換します。  
  
 使用して[GetCurrentDirectory](#getcurrentdirectory)を FTP サーバーの現在の作業ディレクトリを決定します。 リモート システムに接続されていることをルート ディレクトリとは限りません。  
  
## <a name="see-also"></a>関連項目  
 [関数クラス](../../mfc/reference/cinternetconnection-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数クラス](../../mfc/reference/cinternetconnection-class.md)   
 [CInternetSession クラス](../../mfc/reference/cinternetsession-class.md)
