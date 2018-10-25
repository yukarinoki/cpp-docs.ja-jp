---
title: CFtpConnection クラス |Microsoft Docs
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
ms.openlocfilehash: 4b3e340f00170eb8351cb66e816cbaa7dc76fbd6
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50075542"
---
# <a name="cftpconnection-class"></a>CFtpConnection クラス

インターネット サーバーに FTP 接続を管理でき、そのサーバー上のディレクトリおよびファイルを直接操作できます。

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
|[CFtpConnection::GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)|この接続を URL として、現在のディレクトリを取得します。|
|[CFtpConnection::GetFile](#getfile)|接続先のサーバーからファイルを取得します。|
|[CFtpConnection::OpenFile](#openfile)|接続されているサーバー上のファイルを開きます。|
|[CFtpConnection::PutFile](#putfile)|サーバー上のファイルを配置します。|
|[CFtpConnection::Remove](#remove)|サーバーからファイルを削除します。|
|[CFtpConnection::RemoveDirectory](#removedirectory)|サーバーから、指定されたディレクトリを削除します。|
|[CFtpConnection::Rename](#rename)|サーバー上のファイルの名前を変更します。|
|[CFtpConnection::SetCurrentDirectory](#setcurrentdirectory)|現在の FTP ディレクトリを設定します。|

## <a name="remarks"></a>Remarks

FTP では、MFC WinInet クラスによって認識される 3 つのインターネット サービスの 1 つです。

Ftp サーバーとの通信のインスタンスを作成する必要がありますまず[CInternetSession](../../mfc/reference/cinternetsession-class.md)、し、作成、`CFtpConnection`オブジェクト。 作成することはありません、`CFtpConnection`オブジェクトに直接; 呼び出しではなく、 [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)、作成し、`CFtpConnection`オブジェクトし、ポインターを返します。

方法の詳細については、`CFtpConnection`クラスでは、その他の MFC インターネット機能は、記事をご覧ください。[インターネットが WinInet を使用したプログラミング](../../mfc/win32-internet-extensions-wininet.md)します。 サービス、HTTP、および、gopher は、クラスを参照してください。 サポートされている他の 2 つの通信の詳細については[CHttpConnection](../../mfc/reference/chttpconnection-class.md)と[CGopherConnection](../../mfc/reference/cgopherconnection-class.md)します。

## <a name="example"></a>例

  例を参照してください、 [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)クラスの概要。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CFtpConnection`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

##  <a name="cftpconnection"></a>  CFtpConnection::CFtpConnection

このメンバー関数が構築すると呼ばれる、`CFtpConnection`オブジェクト。

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

*pSession*<br/>
関連するへのポインター [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクト。

*hConnected*<br/>
現在のインターネット セッションの Windows ハンドル。

*pstrServer*<br/>
FTP サーバーの名前を含む文字列へのポインター。

*独自*<br/>
操作のコンテキストの識別子。 *独自*によって返される操作の状態情報を識別する[対応](../../mfc/reference/cinternetsession-class.md#onstatuscallback)します。 既定値を 1 に設定します。ただし、操作の特定のコンテキスト ID を明示的に割り当てることができます。 オブジェクトとその動作はコンテキスト ID に関連付けられる

*pstrUserName*<br/>
ログインするユーザーの名前を指定する null で終わる文字列へのポインター。 NULL の場合、既定値は匿名です。

*pstrPassword*<br/>
ログインに使用するパスワードを指定する null で終わる文字列へのポインター。 両方*pstrPassword*と*pstrUserName*匿名の既定のパスワードはユーザーの電子メール名が NULL の場合。 場合*pstrPassword*が NULL (または空の文字列) が、 *pstrUserName*が NULL でない空白のパスワードを使用します。 次の表の 4 種類の設定の動作は、 *pstrUserName*と*pstrPassword*:

|*pstrUserName*|*pstrPassword*|FTP サーバーに送信されるユーザー名|FTP サーバーに送信されたパスワード|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL または""|NULL または""|「匿名」|ユーザーの電子メール名|
|NULL 以外の文字列|NULL または""|*pstrUserName*|" "|
|NULL 以外の文字列が NULL|ERROR|ERROR||
|NULL 以外の文字列|NULL 以外の文字列|*pstrUserName*|*pstrPassword*|

*ポート*<br/>
サーバーで使用する TCP/IP ポートを識別する番号。

*bPassive*<br/>
この FTP セッションをパッシブまたはアクティブ モードを指定します。 かどうかは TRUE に設定すると、設定、Win32 API *dwFlag* INTERNET_FLAG_PASSIVE にします。

### <a name="remarks"></a>Remarks

作成することはありません、`CFtpConnection`オブジェクトに直接します。 代わりに、 [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)を作成し、`CFptConnection`オブジェクト。

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

*pszCommand*<br/>
送信されるコマンドが含まれている文字列へのポインター。

*eResponse*<br/>
FTP サーバーからの応答が予期されているかどうかを判断します。 次のいずれかの値になります。

- `CmdRespNone` 応答は発生しません。

- `CmdRespRead` 応答が必要です。

*dwFlags*<br/>
この関数を制御するフラグが含まれている値。 完全な一覧についてを参照してください。 [FTPCommand](/windows/desktop/api/wininet/nf-wininet-ftpcommanda)します。

*独自*<br/>
コールバックでアプリケーションのコンテキストを識別するために使用されるアプリケーション定義の値が含まれている値へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

このメンバー関数の機能をエミュレートする、 [FTPCommand](/windows/desktop/api/wininet/nf-wininet-ftpcommanda)関数は、Windows SDK で説明されているとします。

エラーが発生する場合、MFC は型の例外をスロー [CInternetException](../../mfc/reference/cinternetexception-class.md)します。

##  <a name="createdirectory"></a>  CFtpConnection::CreateDirectory

接続されたサーバーのディレクトリを作成するには、このメンバー関数を呼び出します。

```
BOOL CreateDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>パラメーター

*pstrDirName*<br/>
作成するディレクトリの名前を含む文字列へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Windows 関数[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するということがあります。

### <a name="remarks"></a>Remarks

使用`GetCurrentDirectory`をサーバーにこの接続の現在の作業ディレクトリを決定します。 リモート システムがルート ディレクトリにするに接続を前提としてはいません。

`pstrDirName`いずれかのパラメーターには、部分的にまたは現在のディレクトリに対して相対的な完全修飾ファイル名。 円記号 (\\) またはフォワード スラッシュ (/) は、いずれかの名前のディレクトリの区切り記号として使用できます。 `CreateDirectory` 使用されるように、適切な文字にディレクトリ名の区切り記号を変換します。

##  <a name="getcurrentdirectory"></a>  CFtpConnection::GetCurrentDirectory

現在のディレクトリの名前を取得するには、このメンバー関数を呼び出します。

```
BOOL GetCurrentDirectory(CString& strDirName) const;

BOOL GetCurrentDirectory(
    LPTSTR pstrDirName,
    LPDWORD lpdwLen) const;
```

### <a name="parameters"></a>パラメーター

*strDirName*<br/>
ディレクトリの名前を受け取る文字列への参照。

*pstrDirName*<br/>
ディレクトリの名前を受け取る文字列へのポインター。

*lpdwLen*<br/>
次の情報を含む DWORD へのポインター。

|||
|-|-|
|エントリを|によって参照されるバッファーのサイズ*pstrDirName*します。|
|返された場合|格納されている文字数*pstrDirName*します。 メンバー関数が失敗したし、し、ERROR_INSUFFICIENT_BUFFER が返されます*lpdwLen*アプリケーションは、文字列を受信するために割り当てる必要がありますバイト数が含まれています。|

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するということがあります。

### <a name="remarks"></a>Remarks

URL として代わりに、ディレクトリ名を取得する[GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)します。

パラメーター *pstrDirName*または*strDirName*現在のディレクトリに対して相対的か部分的に修飾ファイル名または完全修飾します。 円記号 (\\) またはフォワード スラッシュ (/) は、いずれかの名前のディレクトリの区切り記号として使用できます。 `GetCurrentDirectory` 使用されるように、適切な文字にディレクトリ名の区切り記号を変換します。

##  <a name="getcurrentdirectoryasurl"></a>  CFtpConnection::GetCurrentDirectoryAsURL

URL として現在のディレクトリの名前を取得するには、このメンバー関数を呼び出します。

```
BOOL GetCurrentDirectoryAsURL(CString& strDirName) const;

BOOL GetCurrentDirectoryAsURL(
    LPTSTR pstrName,
    LPDWORD lpdwLen) const;
```

### <a name="parameters"></a>パラメーター

*strDirName*<br/>
ディレクトリの名前を受け取る文字列への参照。

*pstrDirName*<br/>
ディレクトリの名前を受け取る文字列へのポインター。

*lpdwLen*<br/>
次の情報を含む DWORD へのポインター。

|||
|-|-|
|エントリを|によって参照されるバッファーのサイズ*pstrDirName*します。|
|返された場合|格納されている文字数*pstrDirName*します。 メンバー関数が失敗したし、し、ERROR_INSUFFICIENT_BUFFER が返されます*lpdwLen*アプリケーションは、文字列を受信するために割り当てる必要がありますバイト数が含まれています。|

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するということがあります。

### <a name="remarks"></a>Remarks

`GetCurrentDirectoryAsURL` 同じように動作[GetCurrentDirectory](#getcurrentdirectory)

パラメーター *strDirName*現在のディレクトリに対して相対的か部分的に修飾ファイル名または完全修飾します。 円記号 (\\) またはフォワード スラッシュ (/) は、いずれかの名前のディレクトリの区切り記号として使用できます。 `GetCurrentDirectoryAsURL` 使用されるように、適切な文字にディレクトリ名の区切り記号を変換します。

##  <a name="getfile"></a>  CFtpConnection::GetFile

FTP サーバーからファイルを取得し、ローカル コンピューターに保存するには、このメンバー関数を呼び出します。

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

*pstrRemoteFile*<br/>
FTP サーバーから取得するファイルの名前を含む null で終わる文字列へのポインター。

*pstrLocalFile*<br/>
ローカル システムで作成するファイルの名前を含む null で終わる文字列へのポインター。

*bFailIfExists*<br/>
かどうか、ファイル名は既存のファイルで既に使用可能性がありますを示します。 場合は、ローカル ファイル名が既に存在して、このパラメーターが true の場合、`GetFile`は失敗します。 それ以外の場合、`GetFile`既存のファイルのコピーが消去されます。

*dwAttributes*<br/>
ファイルの属性を示します。 次の FILE_ATTRIBUTE_ * フラグの任意の組み合わせを指定できます。

- FILE_ATTRIBUTE_ARCHIVE ファイルは、アーカイブ ファイルです。 アプリケーションでは、この属性を使用して、ファイルをバックアップまたは削除のマークします。

- FILE_ATTRIBUTE_COMPRESSED ファイルまたはディレクトリは圧縮されます。 ファイルの場合は、圧縮は、すべてのファイルにデータが圧縮されているを意味します。 ディレクトリの場合は、圧縮は、新しく作成されたファイルとサブディレクトリの既定値です。

- FILE_ATTRIBUTE_DIRECTORY ファイルはディレクトリです。

- FILE_ATTRIBUTE_NORMAL ファイルには、他の属性セットがありません。 この属性は、単独で使用される場合にのみ有効です。 その他のすべてのファイル属性は、FILE_ATTRIBUTE_NORMAL をオーバーライドします。

- FILE_ATTRIBUTE_HIDDEN ファイルは表示されません。 通常のディレクトリ一覧に含めることは。

- FILE_ATTRIBUTE_READONLY ファイルは読み取り専用です。 アプリケーションできますファイルの読み取りことはできませんへの書き込みまたは削除します。

- FILE_ATTRIBUTE_SYSTEM ファイルの一部であるまたはオペレーティング システムによって排他的に使用されます。

- FILE_ATTRIBUTE_TEMPORARY ファイルは、一時的なストレージの使用されています。 アプリケーションは、どうしても必要な場合にのみ、ファイルを書き込む必要があります。 ファイルのデータのほとんどは、ファイルがすぐに削除されるため、メディアに書き込まれずに、メモリに残ります。

*dwFlags*<br/>
転送が発生する条件を指定します。 このパラメーターには、いずれかを指定できます、 *dwFlags*で説明されている値[FtpGetFile](/windows/desktop/api/wininet/nf-wininet-ftpgetfilea) Windows SDK に含まれています。

*独自*<br/>
ファイルを取得するためのコンテキストの識別子です。 参照してください**解説**の詳細については*独自*します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するということがあります。

### <a name="remarks"></a>Remarks

`GetFile` FTP サーバーからファイルの読み取りをローカルに格納することに関連するオーバーヘッドのすべてを処理する高レベルのルーチンです。 ファイルのデータのみを取得するか閉じるファイル転送では、制御を必要とするアプリケーションを使用する必要があります`OpenFile`と[細かい](../../mfc/reference/cinternetfile-class.md#read)代わりにします。

場合*dwFlags* FILE_TRANSFER_TYPE_ASCII、ファイル データの翻訳も変換コントロール、および Windows の対応する文字の書式設定します。 既定の転送は、バイナリ モードの場合は、サーバーに格納されている同じ形式でにダウンロードは、ファイルの場所です。

両方*pstrRemoteFile*と*pstrLocalFile*現在のディレクトリに対して相対的か部分的に修飾ファイル名または完全修飾します。 円記号 (\\) またはフォワード スラッシュ (/) は、いずれかの名前のディレクトリの区切り記号として使用できます。 `GetFile` 使用されるように、適切な文字にディレクトリ名の区切り記号を変換します。

上書き、*独自*の既定値は、独自の値にコンテキスト id を設定します。 コンテキスト識別子にこの特定の操作に関連付けられて、`CFtpConnection`によって作成されたオブジェクトの[CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクト。 値が返される[対応](../../mfc/reference/cinternetsession-class.md#onstatuscallback)が識別される操作の状態を提供します。 記事をご覧ください[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)コンテキスト識別子の詳細についてはします。

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

*pstrFileName*<br/>
開かれるファイルの名前を含む文字列へのポインター。

*dwAccess*<br/>
ファイルへのアクセス方法を決定します。 GENERIC_READ と GENERIC_WRITE の両方ではなくいずれかを指定できます。

*dwFlags*<br/>
後続の転送が発生する条件を指定します。 次の FTP_TRANSFER_ * 定数のいずれかを指定できます。

- FTP_TRANSFER_TYPE_ASCII ファイルは、FTP ASCII (タイプ A) 転送メソッドを使用して転送します。 変換コントロールと書式設定情報を対応するローカル。

- FTP_TRANSFER_TYPE_BINARY ファイルは、(タイプ I) FTP's イメージ転送メソッドを使用してデータを転送します。 変更せずに、これとまったく同じデータを転送するファイルが存在します。 これは、既定の転送方法です。

*独自*<br/>
ファイルを開くためのコンテキストの識別子です。 参照してください**解説**の詳細については*独自*します。

### <a name="return-value"></a>戻り値

ポインターを[CInternetFile](../../mfc/reference/cinternetfile-class.md)オブジェクト。

### <a name="remarks"></a>Remarks

`OpenFile` 次の状況で使用する必要があります。

- アプリケーションでは、ローカル ファイルにデータがないことが、送信して、FTP サーバー上のファイルとして作成する必要があるデータがあります。 1 回`OpenFile`、アプリケーションはファイルを開き[CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write)サーバーに FTP のファイル データを送信します。

- アプリケーションは、サーバーからファイルを取得しをディスクに書き込む代わりに、アプリケーションによって制御され、メモリに配置する必要があります。 アプリケーションを使用して[細かい](../../mfc/reference/cinternetfile-class.md#read)を使用した後`OpenFile`ファイルを開きます。

- アプリケーションをきめ細かなファイル転送の制御レベルが必要です。 進行状況を表示するアプリケーションなど、コントロールは、ファイルのダウンロード中にファイル転送の状態の進行状況を示します。

呼び出した後`OpenFile`呼び出しまで`CInternetConnection::Close`、アプリケーションを呼び出すことができますのみ[細かい](../../mfc/reference/cinternetfile-class.md#read)、 [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write)、 `CInternetConnection::Close`、または[CFtpFileFind::FindFile](../../mfc/reference/cftpfilefind-class.md#findfile)します。 同じ FTP セッションの他の FTP 関数への呼び出しは失敗し、FTP_ETRANSFER_IN_PROGRESS にエラー コードを設定します。

*PstrFileName*パラメーターは、いずれか、部分的に修飾ファイル名、現在のディレクトリに相対パスまたは完全修飾を指定できます。 円記号 (\\) またはフォワード スラッシュ (/) は、いずれかの名前のディレクトリの区切り記号として使用できます。 `OpenFile` 適切な文字にディレクトリ名の区切り記号を使用する前に変換します。

上書き、*独自*の既定値は、独自の値にコンテキスト id を設定します。 コンテキスト識別子にこの特定の操作に関連付けられて、`CFtpConnection`によって作成されたオブジェクトの[CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクト。 値が返される[対応](../../mfc/reference/cinternetsession-class.md#onstatuscallback)が識別される操作の状態を提供します。 記事をご覧ください[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)コンテキスト識別子の詳細についてはします。

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

*pstrLocalFile*<br/>
ローカル システムから送信するファイルの名前を含む文字列へのポインター。

*pstrRemoteFile*<br/>
FTP サーバー上に作成するファイルの名前を含む文字列へのポインター。

*dwFlags*<br/>
ファイルの転送が発生する条件を指定します。 説明されている FTP_TRANSFER_ * 定数のいずれか[OpenFile](#openfile)します。

*独自*<br/>
ファイルを配置するためのコンテキストの識別子です。 参照してください**解説**の詳細については*独自*します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するということがあります。

### <a name="remarks"></a>Remarks

`PutFile` すべての FTP サーバー上のファイルを格納することに関連付けられている操作を処理する高度なルーチン。 のみ、データを送信するか、ファイルの転送の詳細にコントロールを必要とするアプリケーションを使用する必要があります[OpenFile](#openfile)と[CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write)します。

`dwContext` の既定値をオーバーライドして、コンテキスト識別子を独自の値に設定します。 コンテキスト識別子にこの特定の操作に関連付けられて、`CFtpConnection`によって作成されたオブジェクトの[CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクト。 値が返される[対応](../../mfc/reference/cinternetsession-class.md#onstatuscallback)が識別される操作の状態を提供します。 記事をご覧ください[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)コンテキスト識別子の詳細についてはします。

##  <a name="remove"></a>  CFtpConnection::Remove

接続先のサーバーから、指定したファイルを削除するには、このメンバー関数を呼び出します。

```
BOOL Remove(LPCTSTR pstrFileName);
```

### <a name="parameters"></a>パラメーター

*pstrFileName*<br/>
削除するファイル名を含む文字列へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するということがあります。

### <a name="remarks"></a>Remarks

*PstrFileName*パラメーターは、いずれか、部分的に修飾ファイル名、現在のディレクトリに相対パスまたは完全修飾を指定できます。 円記号 (\\) またはフォワード スラッシュ (/) は、いずれかの名前のディレクトリの区切り記号として使用できます。 `Remove`関数が使用されるように、適切な文字にディレクトリ名の区切り記号を変換します。

##  <a name="removedirectory"></a>  CFtpConnection::RemoveDirectory

接続先のサーバーから、指定されたディレクトリを削除するには、このメンバー関数を呼び出します。

```
BOOL RemoveDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>パラメーター

*pstrDirName*<br/>
削除するディレクトリを含む文字列へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するということがあります。

### <a name="remarks"></a>Remarks

使用[GetCurrentDirectory](#getcurrentdirectory)をサーバーの現在の作業ディレクトリを決定します。 リモート システムがルート ディレクトリにするに接続を前提としてはいません。

*PstrDirName*パラメーターに現在のディレクトリに対して相対的なファイルが部分的または完全修飾することができます。 円記号 (\\) またはフォワード スラッシュ (/) は、いずれかの名前のディレクトリの区切り記号として使用できます。 `RemoveDirectory` 使用されるように、適切な文字にディレクトリ名の区切り記号を変換します。

##  <a name="rename"></a>  CFtpConnection::Rename

接続されているサーバー上の指定のファイルの名前を変更するには、このメンバー関数を呼び出します。

```
BOOL Rename(
    LPCTSTR pstrExisting,
    LPCTSTR pstrNew);
```

### <a name="parameters"></a>パラメーター

*pstrExisting*<br/>
名前を変更するファイルの現在の名前を含む文字列へのポインター。

*pstrNew*<br/>
ファイルの新しい名前を含む文字列へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するということがあります。

### <a name="remarks"></a>Remarks

*PstrExisting*と*pstrNew*パラメーターは、いずれか、部分的に修飾ファイル名、現在のディレクトリに相対パスまたは完全修飾を指定できます。 円記号 (\\) またはフォワード スラッシュ (/) は、いずれかの名前のディレクトリの区切り記号として使用できます。 `Rename` 使用されるように、適切な文字にディレクトリ名の区切り記号を変換します。

##  <a name="setcurrentdirectory"></a>  CFtpConnection::SetCurrentDirectory

FTP サーバー上の別のディレクトリに変更するには、このメンバー関数を呼び出します。

```
BOOL SetCurrentDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>パラメーター

*pstrDirName*<br/>
ディレクトリの名前を含む文字列へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するということがあります。

### <a name="remarks"></a>Remarks

*PstrDirName*パラメーターに現在のディレクトリに対して相対的なファイルが部分的または完全修飾することができます。 円記号 (\\) またはフォワード スラッシュ (/) は、いずれかの名前のディレクトリの区切り記号として使用できます。 `SetCurrentDirectory` 使用されるように、適切な文字にディレクトリ名の区切り記号を変換します。

使用[GetCurrentDirectory](#getcurrentdirectory)を FTP サーバーの現在の作業ディレクトリを決定します。 リモート システムがルート ディレクトリにするに接続を前提としてはいません。

## <a name="see-also"></a>関連項目

[CInternetConnection クラス](../../mfc/reference/cinternetconnection-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection クラス](../../mfc/reference/cinternetconnection-class.md)<br/>
[CInternetSession クラス](../../mfc/reference/cinternetsession-class.md)
