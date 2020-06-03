---
title: クラス
ms.date: 08/29/2019
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
ms.openlocfilehash: a1fe516869aa98cc291597211eee175ef591e45d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373776"
---
# <a name="cftpconnection-class"></a>クラス

インターネット サーバーへの FTP 接続を管理し、そのサーバー上のディレクトリとファイルを直接操作できるようにします。

## <a name="syntax"></a>構文

```
class CFtpConnection : public CInternetConnection
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[接続::CFtp接続](#cftpconnection)|`CFtpConnection` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コマンド接続:コマンド](#command)|FTP サーバーに直接コマンドを送信します。|
|[をクリックします。](#createdirectory)|サーバー上にディレクトリを作成します。|
|[接続::ゲットカレントディレクトリ](#getcurrentdirectory)|この接続の現在のディレクトリを取得します。|
|[接続::取得ディレクトリのURL](#getcurrentdirectoryasurl)|この接続の現在のディレクトリを URL として取得します。|
|[ファイルを取得します。](#getfile)|接続されているサーバーからファイルを取得します。|
|[ファイルを開く](#openfile)|接続されているサーバー上のファイルを開きます。|
|[接続::Pファイル](#putfile)|サーバーにファイルを配置します。|
|[接続::削除](#remove)|サーバーからファイルを削除します。|
|[ディレクトリを削除します。](#removedirectory)|指定したディレクトリをサーバーから削除します。|
|[CFtp接続::名前の変更](#rename)|サーバー上のファイルの名前を変更します。|
|[接続::セットカレントディレクトリ](#setcurrentdirectory)|現在の FTP ディレクトリを設定します。|

## <a name="remarks"></a>解説

FTP は、MFC WinInet クラスで認識される 3 つのインターネット サービスの 1 つです。

FTP インターネット サーバーと通信するには、まず[CInternetSession](../../mfc/reference/cinternetsession-class.md)のインスタンスを作成してから、オブジェクトを`CFtpConnection`作成する必要があります。 オブジェクトを`CFtpConnection`直接作成することはありません。むしろ、`CFtpConnection`オブジェクトを作成し、それにポインターを返す[C インターネットセッション::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)を呼び出します。

他の MFC`CFtpConnection`インターネット クラスとの動作の詳細については[、「WinInet を使用したインターネット プログラミング](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。 サポートされているその他の 2 つのサービス HTTP と gopher との通信の詳細については、[クラス CHttpConnection](../../mfc/reference/chttpconnection-class.md)と[CGopherConnection](../../mfc/reference/cgopherconnection-class.md)を参照してください。

## <a name="example"></a>例

  クラスの概要の例[を](../../mfc/reference/cftpfilefind-class.md)参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CFtpConnection`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

## <a name="cftpconnectioncftpconnection"></a><a name="cftpconnection"></a>接続::CFtp接続

このメンバー関数は、`CFtpConnection`オブジェクトを構築するために呼び出されます。

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

*セッション*<br/>
関連する C[インターネット セッション](../../mfc/reference/cinternetsession-class.md)オブジェクトへのポインター。

*hコネクテッド*<br/>
現在のインターネット セッションの Windows ハンドル。

*を行う*<br/>
FTP サーバー名を含む文字列へのポインター。

*dw コンテキスト*<br/>
操作のコンテキスト識別子。 *dwContext*は[、CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)によって返される操作の状態情報を識別します。 デフォルトは 1 に設定されています。ただし、操作に対して特定のコンテキスト ID を明示的に割り当てることができます。 オブジェクトとオブジェクトが行うすべての作業は、そのコンテキスト ID に関連付けられます。

*ユーザー名*<br/>
ログインするユーザーの名前を指定する、NULL で終わる文字列へのポインター。 NULL の場合、デフォルトは匿名です。

*パスワード*<br/>
ログインに使用するパスワードを指定する、null で終わる文字列へのポインター。 *pstrPassword*と*pstrUserName*の両方が NULL の場合、既定の匿名パスワードはユーザーの電子メール名です。 *pstrPassword*が NULL (または空の文字列) で *、pstrUserName*が NULL でない場合は、空白のパスワードが使用されます。 次の表は、4 つの設定の*pstrUserName*と*pstrPassword*の動作を示しています。

|*ユーザー名*|*パスワード*|FTP サーバーに送信されたユーザー名|FTP サーバーに送信されるパスワード|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL または " "|NULL または " "|「匿名」|ユーザーの電子メール名|
|NULL 以外の文字列|NULL または " "|*ユーザー名*|" "|
|NULL 非 NULL 文字列|ERROR|ERROR||
|NULL 以外の文字列|NULL 以外の文字列|*ユーザー名*|*パスワード*|

*nポート*<br/>
サーバーで使用する TCP/IP ポートを識別する番号。

*bパッシブ*<br/>
この FTP セッションのパッシブ モードまたはアクティブ モードを指定します。 TRUE に設定すると、Win32 API *dwFlag*がINTERNET_FLAG_PASSIVEに設定されます。

### <a name="remarks"></a>解説

オブジェクトを`CFtpConnection`直接作成することはありません。 代わりに、オブジェクトを作成する[C インターネットセッション::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)を呼び出します`CFptConnection`。

## <a name="cftpconnectioncommand"></a><a name="command"></a>コマンド接続:コマンド

FTP サーバーに直接コマンドを送信します。

```
CInternetFile* Command(
    LPCTSTR pszCommand,
    CmdResponseType eResponse = CmdRespNone,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>パラメーター

*コマンド*<br/>
送信されるコマンドが含まれている文字列へのポインター。

*eResponse*<br/>
FTP サーバーからの応答が必要かどうかを指定します。 次の値のいずれかです。

- `CmdRespNone`応答は期待されていません。
- `CmdRespRead`応答が必要です。
- `CmdRespWrite`使用されていません。

応答タイプは *、afxinet.h*で定義された CFtpConnection のメンバーです。

*dwFlags*<br/>
この関数を制御するフラグが含まれている値。 完全な一覧については、 [FTPCommand](/windows/win32/api/wininet/nf-wininet-ftpcommandw)を参照してください。

*dw コンテキスト*<br/>
コールバックでアプリケーションのコンテキストを識別するために使用されるアプリケーション定義の値が含まれている値へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように[、FTP コマンド](/windows/win32/api/wininet/nf-wininet-ftpcommandw)関数の機能をエミュレートします。

エラーが発生すると、MFC は[型 CInternetException](../../mfc/reference/cinternetexception-class.md)の例外をスローします。

## <a name="cftpconnectioncreatedirectory"></a><a name="createdirectory"></a>をクリックします。

接続先のサーバーにディレクトリを作成します。

```
BOOL CreateDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>パラメーター

*名前*<br/>
作成するディレクトリの名前を含む文字列へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、エラーの原因を特定するために Windows 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)が呼び出されることがあります。

### <a name="remarks"></a>解説

サーバー`GetCurrentDirectory`へのこの接続の現在の作業ディレクトリを確認するために使用します。 リモート・システムがルート・ディレクトリーに接続したとは想定しないでください。

この`pstrDirName`パラメーターは、現在のディレクトリーに対する部分的または完全修飾ファイル名のいずれかです。 円記号 (\\) またはスラッシュ (/) は、どちらの名前のディレクトリ区切り記号としても使用できます。 `CreateDirectory`は、使用する前に、ディレクトリ名の区切り記号を適切な文字に変換します。

## <a name="cftpconnectiongetcurrentdirectory"></a><a name="getcurrentdirectory"></a>接続::ゲットカレントディレクトリ

現在のディレクトリの名前を取得します。

```
BOOL GetCurrentDirectory(CString& strDirName) const;

BOOL GetCurrentDirectory(
    LPTSTR pstrDirName,
    LPDWORD lpdwLen) const;
```

### <a name="parameters"></a>パラメーター

*ストルディルネーム*<br/>
ディレクトリの名前を受け取る文字列への参照。

*名前*<br/>
ディレクトリの名前を受け取る文字列へのポインター。

*lpdwLen*<br/>
次の情報を含む DWORD へのポインター。

|||
|-|-|
|入口時|*によって*参照されるバッファーのサイズです。|
|お返し時|*に*格納される文字数です。 メンバー関数が失敗し、ERROR_INSUFFICIENT_BUFFERが返された場合 *、lpdwLen*には、アプリケーションが文字列を受け取るために割り当てる必要があるバイト数が含まれます。|

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)が呼び出され、エラーの原因を特定できます。

### <a name="remarks"></a>解説

代わりに URL としてディレクトリ名を取得するには、呼び出します[。](#getcurrentdirectoryasurl)

パラメーター *pstrDirName*または*strDirName*は、現在のディレクトリに対する部分的な修飾ファイル名または完全修飾ファイル名のいずれかです。 円記号 (\\) またはスラッシュ (/) は、どちらの名前のディレクトリ区切り記号としても使用できます。 `GetCurrentDirectory`は、使用する前に、ディレクトリ名の区切り記号を適切な文字に変換します。

## <a name="cftpconnectiongetcurrentdirectoryasurl"></a><a name="getcurrentdirectoryasurl"></a>接続::取得ディレクトリのURL

現在のディレクトリの名前を URL として取得します。

```
BOOL GetCurrentDirectoryAsURL(CString& strDirName) const;

BOOL GetCurrentDirectoryAsURL(
    LPTSTR pstrName,
    LPDWORD lpdwLen) const;
```

### <a name="parameters"></a>パラメーター

*ストルディルネーム*<br/>
ディレクトリの名前を受け取る文字列への参照。

*名前*<br/>
ディレクトリの名前を受け取る文字列へのポインター。

*lpdwLen*<br/>
次の情報を含む DWORD へのポインター。

|||
|-|-|
|入口時|*によって*参照されるバッファーのサイズです。|
|お返し時|*に*格納される文字数です。 メンバー関数が失敗し、ERROR_INSUFFICIENT_BUFFERが返された場合 *、lpdwLen*には、アプリケーションが文字列を受け取るために割り当てる必要があるバイト数が含まれます。|

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)が呼び出され、エラーの原因を特定できます。

### <a name="remarks"></a>解説

`GetCurrentDirectoryAsURL`同じ動作[をします。](#getcurrentdirectory)

*strDirName*パラメータは、現在のディレクトリに対する部分的な修飾ファイル名または完全修飾ファイル名のいずれかです。 円記号 (\\) またはスラッシュ (/) は、どちらの名前のディレクトリ区切り記号としても使用できます。 `GetCurrentDirectoryAsURL`は、使用する前に、ディレクトリ名の区切り記号を適切な文字に変換します。

## <a name="cftpconnectiongetfile"></a><a name="getfile"></a>ファイルを取得します。

FTP サーバーからファイルを取得し、ローカル マシンに格納します。

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

*ファイル*<br/>
FTP サーバーから取得するファイルの名前を含む null で終わる文字列へのポインター。

*ローカル ファイル*<br/>
ローカル システム上に作成するファイルの名前を含む null で終わる文字列へのポインター。

*存在する*<br/>
既存のファイルでファイル名が既に使用されているかどうかを示します。 ローカル ファイル名が既に存在し、このパラメーターが`GetFile`TRUE の場合は、失敗します。 それ以外`GetFile`の場合は、ファイルの既存のコピーを消去します。

*dw属性*<br/>
ファイルの属性を示します。 これは、次の FILE_ATTRIBUTE_* フラグの任意の組み合わせです。

- FILE_ATTRIBUTE_ARCHIVE ファイルがアーカイブ ファイルです。 アプリケーションは、この属性を使用して、バックアップまたは削除用のファイルをマークします。

- FILE_ATTRIBUTE_COMPRESSED ファイルまたはディレクトリが圧縮されます。 ファイルの場合、圧縮とは、ファイル内のすべてのデータが圧縮されることを意味します。 ディレクトリの場合、圧縮は新しく作成されたファイルおよびサブディレクトリのデフォルトです。

- FILE_ATTRIBUTE_DIRECTORY ファイルはディレクトリです。

- FILE_ATTRIBUTE_NORMAL ファイルに他の属性が設定されていない。 この属性は、単独で使用する場合にのみ有効です。 その他のファイル属性はすべて、FILE_ATTRIBUTE_NORMALをオーバーライドします。

- FILE_ATTRIBUTE_HIDDEN ファイルが非表示になっています。 通常のディレクトリリストには含まれません。

- FILE_ATTRIBUTE_READONLY ファイルは読み取り専用です。 アプリケーションはファイルを読み取ることができますが、書き込みや削除はできません。

- FILE_ATTRIBUTE_SYSTEM ファイルはオペレーティング システムの一部であるか、オペレーティング システムによって排他的に使用されます。

- FILE_ATTRIBUTE_TEMPORARY ファイルは一時記憶域に使用されています。 アプリケーションは、絶対に必要な場合にのみファイルに書き込む必要があります。 ファイルのデータのほとんどは、メディアにフラッシュされずにメモリに残ります。

*dwFlags*<br/>
転送が行われる条件を指定します。 このパラメーターは、Windows SDK の[FtpGet ファイル](/windows/win32/api/wininet/nf-wininet-ftpgetfilew)で説明されている*dwFlags*値のいずれかです。

*dw コンテキスト*<br/>
ファイル取得のコンテキスト識別子。 *dwContext*の詳細については **、「解説**」を参照してください。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)が呼び出され、エラーの原因を特定できます。

### <a name="remarks"></a>解説

`GetFile`は、FTP サーバーからのファイルの読み取りとローカルの格納に関連するすべてのオーバーヘッドを処理する高レベルのルーチンです。 ファイル データのみを取得するアプリケーション、またはファイル転送を厳密に制御する必要があるアプリケーション`OpenFile`では[、CInternetFile::Read](../../mfc/reference/cinternetfile-class.md#read)を使用する必要があります。

*dwFlags*がFILE_TRANSFER_TYPE_ASCII場合、ファイル データの変換は、コントロールと書式設定の文字を Windows の対応する文字に変換します。 デフォルトの転送はバイナリモードで、ファイルはサーバーに保存されているのと同じ形式でダウンロードされます。

*pstrRemoteFile*と*pstrLocalFile*は、現在のディレクトリに対する部分的な修飾ファイル名か、完全修飾ファイルのいずれかです。 円記号 (\\) またはスラッシュ (/) は、どちらの名前のディレクトリ区切り記号としても使用できます。 `GetFile`は、使用する前に、ディレクトリ名の区切り記号を適切な文字に変換します。

コンテキスト識別子を選択した値に設定するには *、dwContext*の既定値をオーバーライドします。 コンテキスト識別子は、[その CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクト`CFtpConnection`によって作成されたオブジェクトのこの特定の操作に関連付けられます。 値は、それが識別される操作の状態を提供するために[CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)に返されます。 コンテキスト識別子の詳細については、「[インターネットの最初の手順: WinInet」](../../mfc/wininet-basics.md)を参照してください。

## <a name="cftpconnectionopenfile"></a><a name="openfile"></a>ファイルを開く

FTP サーバー上のファイルを読み取りまたは書き込み用に開きます。

```
CInternetFile* OpenFile(
    LPCTSTR pstrFileName,
    DWORD dwAccess = GENERIC_READ,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
開くファイルの名前を含む文字列へのポインター。

*ドウアクセス*<br/>
ファイルへのアクセス方法を決定します。 GENERIC_READまたはGENERIC_WRITEのいずれかになりますが、両方を使用することはできません。

*dwFlags*<br/>
後続の転送が行われる条件を指定します。 これは、次の FTP_TRANSFER_* 定数のいずれかです。

- FTP_TRANSFER_TYPE_ASCII FTP ASCII (タイプ A) 転送方式を使用してファイル転送を行います。 コントロールと書式設定の情報をローカルの対応する情報に変換します。

- FTP_TRANSFER_TYPE_BINARY FTP のイメージ (タイプ I) 転送方式を使用して、ファイルがデータを転送します。 ファイルは、データをそのまま正確に転送しますが、変更はありません。 これはデフォルトの転送方法です。

*dw コンテキスト*<br/>
ファイルを開くためのコンテキスト識別子。 *dwContext*の詳細については **、「解説**」を参照してください。

### <a name="return-value"></a>戻り値

[オブジェクト](../../mfc/reference/cinternetfile-class.md)へのポインター。

### <a name="remarks"></a>解説

`OpenFile`は、次の状況で使用する必要があります。

- アプリケーションには、FTP サーバー上のファイルとして送信および作成する必要があるデータがありますが、そのデータはローカル ファイルにありません。 ファイル`OpenFile`を開くと、アプリケーションは[CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write)を使用して FTP ファイル データをサーバーに送信します。

- アプリケーションは、ディスクに書き込むのではなく、サーバーからファイルを取得し、アプリケーション制御メモリに配置する必要があります。 アプリケーションは、ファイルを開くために使用した後[、CInternetFile::Read](../../mfc/reference/cinternetfile-class.md#read)を使用`OpenFile`します。

- アプリケーションでは、ファイル転送を細かく制御する必要があります。 たとえば、アプリケーションは、ファイルのダウンロード中にファイル転送ステータスの進行状況を示す進捗コントロールを表示する場合があります。

呼び`OpenFile`出し後`CInternetConnection::Close`、呼び出すまで、アプリケーションは[CInternetFile::読み取り](../../mfc/reference/cinternetfile-class.md#read)[、CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write) `CInternetConnection::Close`、または[CFtpFileFind::FindFile](../../mfc/reference/cftpfilefind-class.md#findfile)のみを呼び出すことができます。 同じ FTP セッションに対する他の FTP 関数の呼び出しは失敗し、エラー・コードをFTP_ETRANSFER_IN_PROGRESSに設定します。

*pstrFileName*パラメーターは、現在のディレクトリーに対する部分的に修飾されたファイル名または完全修飾ファイル名のいずれかです。 円記号 (\\) またはスラッシュ (/) は、どちらの名前のディレクトリ区切り記号としても使用できます。 `OpenFile`は、ディレクトリ名の区切り記号を使用する前に適切な文字に変換します。

コンテキスト識別子を選択した値に設定するには *、dwContext*の既定値をオーバーライドします。 コンテキスト識別子は、[その CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクト`CFtpConnection`によって作成されたオブジェクトのこの特定の操作に関連付けられます。 値は、それが識別される操作の状態を提供するために[CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)に返されます。 コンテキスト識別子の詳細については、「[インターネットの最初の手順: WinInet」](../../mfc/wininet-basics.md)を参照してください。

## <a name="cftpconnectionputfile"></a><a name="putfile"></a>接続::Pファイル

FTP サーバーにファイルを格納するには、このメンバー関数を呼び出します。

```
BOOL PutFile(
    LPCTSTR pstrLocalFile,
    LPCTSTR pstrRemoteFile,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>パラメーター

*ローカル ファイル*<br/>
ローカル システムから送信するファイルの名前を含む文字列へのポインター。

*ファイル*<br/>
FTP サーバー上に作成するファイルの名前を含む文字列へのポインター。

*dwFlags*<br/>
ファイルの転送が行われる条件を指定します。 [OpenFile](#openfile)で説明されているFTP_TRANSFER_* 定数のいずれかを指定できます。

*dw コンテキスト*<br/>
ファイルを配置するためのコンテキスト識別子。 *dwContext*の詳細については **、「解説**」を参照してください。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)が呼び出され、エラーの原因を特定できます。

### <a name="remarks"></a>解説

`PutFile`は、FTP サーバー上のファイルの保管に関連するすべての操作を処理する高水準ルーチンです。 データを送信するだけのアプリケーション、またはファイル転送を詳細に制御する必要があるアプリケーションでは[、OpenFile](#openfile)と[CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write)を使用する必要があります。

`dwContext` の既定値をオーバーライドして、コンテキスト識別子を独自の値に設定します。 コンテキスト識別子は、[その CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクト`CFtpConnection`によって作成されたオブジェクトのこの特定の操作に関連付けられます。 値は、それが識別される操作の状態を提供するために[CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)に返されます。 コンテキスト識別子の詳細については、「[インターネットの最初の手順: WinInet」](../../mfc/wininet-basics.md)を参照してください。

## <a name="cftpconnectionremove"></a><a name="remove"></a>接続::削除

接続されているサーバーから指定したファイルを削除します。

```
BOOL Remove(LPCTSTR pstrFileName);
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
削除するファイル名を含む文字列へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)が呼び出され、エラーの原因を特定できます。

### <a name="remarks"></a>解説

*pstrFileName*パラメーターは、現在のディレクトリーに対する部分的に修飾されたファイル名または完全修飾ファイル名のいずれかです。 円記号 (\\) またはスラッシュ (/) は、どちらの名前のディレクトリ区切り記号としても使用できます。 この`Remove`関数は、使用する前に、ディレクトリー名の区切り記号を適切な文字に変換します。

## <a name="cftpconnectionremovedirectory"></a><a name="removedirectory"></a>ディレクトリを削除します。

接続先のサーバーから指定したディレクトリを削除します。

```
BOOL RemoveDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>パラメーター

*名前*<br/>
削除するディレクトリを含む文字列へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)が呼び出され、エラーの原因を特定できます。

### <a name="remarks"></a>解説

[GetCurrentDirectory](#getcurrentdirectory)を使用して、サーバーの現在の作業ディレクトリを確認します。 リモート・システムがルート・ディレクトリーに接続したとは想定しないでください。

*pstrDirName*パラメーターは、現在のディレクトリーに対する部分的または完全修飾ファイル名のいずれかです。 円記号 (\\) またはスラッシュ (/) は、どちらの名前のディレクトリ区切り記号としても使用できます。 `RemoveDirectory`は、使用する前に、ディレクトリ名の区切り記号を適切な文字に変換します。

## <a name="cftpconnectionrename"></a><a name="rename"></a>CFtp接続::名前の変更

接続先のサーバー上の指定したファイルの名前を変更します。

```
BOOL Rename(
    LPCTSTR pstrExisting,
    LPCTSTR pstrNew);
```

### <a name="parameters"></a>パラメーター

*既存の*<br/>
名前を変更するファイルの現在の名前を含む文字列へのポインター。

*新しい*<br/>
ファイルの新しい名前を含む文字列へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)が呼び出され、エラーの原因を特定できます。

### <a name="remarks"></a>解説

*pstrExisting*および*pstrNew*パラメーターは、現在のディレクトリに対する部分的に修飾されたファイル名か、完全修飾ファイル名のいずれかです。 円記号 (\\) またはスラッシュ (/) は、どちらの名前のディレクトリ区切り記号としても使用できます。 `Rename`は、使用する前に、ディレクトリ名の区切り記号を適切な文字に変換します。

## <a name="cftpconnectionsetcurrentdirectory"></a><a name="setcurrentdirectory"></a>接続::セットカレントディレクトリ

FTP サーバー上の別のディレクトリに変更するには、このメンバー関数を呼び出します。

```
BOOL SetCurrentDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>パラメーター

*名前*<br/>
ディレクトリの名前を含む文字列へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)が呼び出され、エラーの原因を特定できます。

### <a name="remarks"></a>解説

*pstrDirName*パラメーターは、現在のディレクトリーに対する部分的または完全修飾ファイル名のいずれかです。 円記号 (\\) またはスラッシュ (/) は、どちらの名前のディレクトリ区切り記号としても使用できます。 `SetCurrentDirectory`は、使用する前に、ディレクトリ名の区切り記号を適切な文字に変換します。

[GETCurrentDirectory](#getcurrentdirectory)を使用して、FTP サーバーの現在の作業ディレクトリを確認します。 リモート・システムがルート・ディレクトリーに接続したとは想定しないでください。

## <a name="see-also"></a>関連項目

[CInternetConnection クラス](../../mfc/reference/cinternetconnection-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection クラス](../../mfc/reference/cinternetconnection-class.md)<br/>
[CInternetSession クラス](../../mfc/reference/cinternetsession-class.md)
