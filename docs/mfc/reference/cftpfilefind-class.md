---
title: CFtpFileFind クラス
ms.date: 11/04/2016
f1_keywords:
- CFtpFileFind
- AFXINET/CFtpFileFind
- AFXINET/CFtpFileFind::CFtpFileFind
- AFXINET/CFtpFileFind::FindFile
- AFXINET/CFtpFileFind::FindNextFile
- AFXINET/CFtpFileFind::GetFileURL
helpviewer_keywords:
- CFtpFileFind [MFC], CFtpFileFind
- CFtpFileFind [MFC], FindFile
- CFtpFileFind [MFC], FindNextFile
- CFtpFileFind [MFC], GetFileURL
ms.assetid: 9667cf01-657f-4b11-b9db-f11e5a7b4e4c
ms.openlocfilehash: cf4afb4a683c2d0cf5f2977107d02ee300a53cb0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373753"
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
|[ファイル検索::CFtp ファイルの検索](#cftpfilefind)|`CFtpFileFind` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ファイルを検索します。](#findfile)|FTP サーバー上のファイルを検索します。|
|[ファイル検索:次のファイルを検索します。](#findnextfile)|[FindFile](#findfile)への以前の呼び出しからファイル検索を続行します。|
|[ファイルの検索::ファイルの取得](#getfileurl)|見つかったファイルの URL (パスを含む) を取得します。|

## <a name="remarks"></a>解説

`CFtpFileFind`には、検索を開始し、ファイルを検索し、URL またはその他の説明情報を返すメンバー関数が含まれます。

インターネット用に設計されたその他の MFC クラスと、検索されるローカル ファイルには[、CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)と[CFileFind](../../mfc/reference/cfilefind-class.md)が含まれます。 これらのクラス`CFtpFileFind`を使用すると、サーバー プロトコルやファイルの種類 (ローカル マシンまたはリモート サーバー) に関係なく、クライアントが特定のファイルを検索するシームレスなメカニズムが提供されます。 HTTP は検索に必要な直接ファイル操作をサポートしていないため、HTTP サーバー上で検索するための MFC クラスはありません。

その他の WinInet`CFtpFileFind`クラスの使用方法の詳細については[、「WinInet を使用したインターネット プログラミング](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。

## <a name="example"></a>例

次のコードは、FTP サーバーの現在のディレクトリにあるすべてのファイルを列挙する方法を示しています。

[!code-cpp[NVC_MFCWinInet#8](../../mfc/codesnippet/cpp/cftpfilefind-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFileFind](../../mfc/reference/cfilefind-class.md)

`CFtpFileFind`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

## <a name="cftpfilefindcftpfilefind"></a><a name="cftpfilefind"></a>ファイル検索::CFtp ファイルの検索

このメンバー関数は、`CFtpFileFind`オブジェクトを構築するために呼び出されます。

```
explicit CFtpFileFind(
    CFtpConnection* pConnection,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>パラメーター

*pConnection*<br/>
`CFtpConnection` オブジェクトを指すポインターです。 FTP 接続を取得するには[、C インターネットセッション::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)を呼び出します。

*dw コンテキスト*<br/>
`CFtpFileFind`オブジェクトのコンテキスト識別子。 このパラメータの詳細については **、「解説」** を参照してください。

### <a name="remarks"></a>解説

*dwContext*の既定値は、オブジェクトを作成した`CFtpFileFind` [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトからオブジェクトに MFC`CFtpFileFind`によって送信されます。 デフォルトをオーバーライドして、コンテキスト識別子を選択した値に設定できます。 コンテキスト識別子は、識別されるオブジェクトのステータスを提供するために[、CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)に返されます。 コンテキスト識別子の詳細については、「[インターネットの最初の手順: WinInet」](../../mfc/wininet-basics.md)を参照してください。

### <a name="example"></a>例

  このトピックで前述したクラスの概要の例を参照してください。

## <a name="cftpfilefindfindfile"></a><a name="findfile"></a>ファイルを検索します。

FTP ファイルを検索するには、このメンバー関数を呼び出します。

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```

### <a name="parameters"></a>パラメーター

*名前*<br/>
検索するファイルの名前を含む文字列へのポインター。 NULL の場合、呼び出しはワイルドカード検索 (*) を実行します。

*dwFlags*<br/>
このセッションの処理方法を説明するフラグ。 これらのフラグは、ビットごとの OR 演算子 (&#124;) と組み合わせることができ、次のようになります。

- INTERNET_FLAG_RELOAD ローカルにキャッシュされている場合でも、ワイヤからデータを取得します。 これはデフォルトのフラグです。

- INTERNET_FLAG_DONT_CACHE ローカルまたはゲートウェイにデータをキャッシュしません。

- INTERNET_FLAG_RAW_DATA デフォルトをオーバーライドして、生データ (FTP の[WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw)構造) を返します。

- INTERNET_FLAG_SECURE セキュア ソケット レイヤまたは PCT を使用して、ネットワーク上のトランザクションを保護します。 このフラグは HTTP 要求にのみ適用されます。

- INTERNET_FLAG_EXISTING_CONNECT 可能であれば、要求ごとに新しいセッションを作成するのではなく、`FindFile`サーバーへの既存の接続を新しい要求に再利用します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 拡張エラー情報を取得するには、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)を呼び出します。

### <a name="remarks"></a>解説

最初の`FindFile`FTP ファイルを取得するために呼び出した後[、FindNextFile](#findnextfile)を呼び出して、後続の FTP ファイルを取得できます。

### <a name="example"></a>例

  このトピックの前の例を参照してください。

## <a name="cftpfilefindfindnextfile"></a><a name="findnextfile"></a>ファイル検索:次のファイルを検索します。

[FindFile](#findfile)メンバー関数の呼び出しで開始されたファイル検索を続行するには、このメンバー関数を呼び出します。

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>戻り値

ファイルが多い場合は 0 以外。見つかったファイルがディレクトリ内の最後のファイルである場合、またはエラーが発生した場合は 0。 拡張エラー情報を取得するには、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)を呼び出します。 見つかったファイルがディレクトリ内の最後のファイルである場合、または一致するファイルが見つからない場合`GetLastError`、関数はERROR_NO_MORE_FILESを返します。

### <a name="remarks"></a>解説

属性関数を呼び出す前に、この関数を少なくとも 1 回呼び出す必要があります ( [CFileFind::FindNextFile](../../mfc/reference/cfilefind-class.md#findnextfile)を参照してください )。

`FindNextFile`関数をラップ[します。](/windows/win32/api/fileapi/nf-fileapi-findnextfilew)

### <a name="example"></a>例

  このトピックの前の例を参照してください。

## <a name="cftpfilefindgetfileurl"></a><a name="getfileurl"></a>ファイルの検索::ファイルの取得

指定したファイルの URL を取得します。

```
CString GetFileURL() const;
```

### <a name="return-value"></a>戻り値

ユニバーサル リソース ロケーター (URL) のファイルとパス。

### <a name="remarks"></a>解説

`GetFileURL`はメンバー関数[CFileFind::GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)に似ていますが、URL を返す点`ftp://moose/dir/file.txt`が異なっています。

## <a name="see-also"></a>関連項目

[クラスを検索します。](../../mfc/reference/cfilefind-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CGopherFileFind クラス](../../mfc/reference/cgopherfilefind-class.md)<br/>
[クラス](../../mfc/reference/cinternetfile-class.md)<br/>
[クラス](../../mfc/reference/cgopherfile-class.md)<br/>
[クラス](../../mfc/reference/chttpfile-class.md)
