---
title: CFtpFileFind クラス |Microsoft Docs
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
ms.openlocfilehash: eaa080460a545e56fcb527f3b8bf4dc57e008e3c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392100"
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
|[CFtpFileFind::FindNextFile](#findnextfile)|以前の呼び出しからのファイル検索を続行[FindFile](#findfile)します。|
|[CFtpFileFind::GetFileURL](#getfileurl)|見つかったファイルのパスを含む URL を取得します。|

## <a name="remarks"></a>Remarks

`CFtpFileFind` 検索を開始し、ファイルを検索し、URL またはその他のファイルに関する情報を返すメンバー関数が含まれています。

インターネットとローカル ファイルの検索含む向けに設計されたその他の MFC クラス[CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)と[CFileFind](../../mfc/reference/cfilefind-class.md)します。 組み合わせて`CFtpFileFind`、これらのクラスは、クライアント プロトコルまたはファイルの種類 (ローカル コンピューターまたはリモート サーバー)、サーバーに関係なく、特定のファイルを検索するためのシームレスなメカニズムを提供します。 HTTP は検索に必要なファイルを直接操作をサポートしていないために、HTTP サーバー上で検索するための MFC クラスがないことに注意してください。

使用する方法の詳細についての`CFtpFileFind`他 WinInet クラスは、記事を参照して、[インターネットが WinInet を使用したプログラミング](../../mfc/win32-internet-extensions-wininet.md)。

## <a name="example"></a>例

次のコードでは、FTP サーバーの現在のディレクトリのすべてのファイルを列挙する方法を示します。

[!code-cpp[NVC_MFCWinInet#8](../../mfc/codesnippet/cpp/cftpfilefind-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFileFind](../../mfc/reference/cfilefind-class.md)

`CFtpFileFind`

## <a name="requirements"></a>要件

**ヘッダー:** afxinet.h

##  <a name="cftpfilefind"></a>  CFtpFileFind::CFtpFileFind

このメンバー関数が構築すると呼ばれる、`CFtpFileFind`オブジェクト。

```
explicit CFtpFileFind(
    CFtpConnection* pConnection,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>パラメーター

*pConnection*<br/>
ポインターを`CFtpConnection`オブジェクト。 FTP 接続を取得するには、呼び出す[CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)します。

*独自*<br/>
コンテキスト識別子を`CFtpFileFind`オブジェクト。 参照してください**解説**このパラメーターの詳細についてはします。

### <a name="remarks"></a>Remarks

既定値*独自*に MFC によって送信される、`CFtpFileFind`オブジェクトから、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトの作成、`CFtpFileFind`オブジェクト。 コンテキスト識別子を独自の値に設定する既定をオーバーライドすることができます。 コンテキスト識別子が返される[対応](../../mfc/reference/cinternetsession-class.md#onstatuscallback)が識別されるオブジェクトの状態を提供します。 記事をご覧ください[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)コンテキスト識別子の詳細についてはします。

### <a name="example"></a>例

  このトピックの「クラスの概要の例で、を参照してください。

##  <a name="findfile"></a>  CFtpFileFind::FindFile

FTP ファイルを検索するには、このメンバー関数を呼び出します。

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```

### <a name="parameters"></a>パラメーター

*pstrName*<br/>
検索するファイルの名前を含む文字列へのポインター。 NULL の場合、呼び出しはワイルドカード検索 (*) を実行します。

*dwFlags*<br/>
このセッションを処理する方法を記述するフラグ。 これらのフラグをビットごとの OR 演算子と組み合わせることができます (&#124;) し、次に示します。

- INTERNET_FLAG_RELOAD は、ローカルにキャッシュされている場合でも、ネットワークからデータを取得します。 これは、既定のフラグです。

- ローカル、またはすべてのゲートウェイでは、データをキャッシュ INTERNET_FLAG_DONT_CACHE しません。

- 生データを返す既定値 INTERNET_FLAG_RAW_DATA ( [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa)構造体が FTP)。

- Secure Sockets Layer やの割合で、ネットワーク上でトランザクションを INTERNET_FLAG_SECURE をセキュリティで保護 このフラグは、HTTP 要求のみに適用されます。

- INTERNET_FLAG_EXISTING_CONNECT 可能な場合は、新しいサーバーに既存の接続を再利用`FindFile`要求ごとに新しいセッションを作成する代わりに要求します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 拡張エラー情報を取得するには、Win32 関数を呼び出す[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)します。

### <a name="remarks"></a>Remarks

呼び出した後`FindFile`FTP の最初のファイルを取得するを呼び出すことができます[FindNextFile](#findnextfile)を後続の FTP ファイルを取得します。

### <a name="example"></a>例

  このトピックでは、前の例を参照してください。

##  <a name="findnextfile"></a>  CFtpFileFind::FindNextFile

呼び出しで開始されたファイルの検索を続行するには、このメンバー関数を呼び出す、 [FindFile](#findfile)メンバー関数。

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>戻り値

以上のファイルがある場合、0 以外の場合ファイルが見つかりましたが、ディレクトリ内の最後の 1 つである場合や、エラーが発生した場合は 0 します。 拡張エラー情報を取得するには、Win32 関数を呼び出す[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)します。 ファイルが見つかりましたが、ディレクトリ内の最後のファイル、または一致する場合は、ファイルが見つからなかんだことができます、 `GetLastError` ERROR_NO_MORE_FILES を返します。

### <a name="remarks"></a>Remarks

任意の属性の関数を呼び出す前に少なくとも 1 回この関数を呼び出す必要があります (を参照してください[呼び出しておく](../../mfc/reference/cfilefind-class.md#findnextfile))。

`FindNextFile` Win32 関数をラップ[FindNextFile](/windows/desktop/api/fileapi/nf-fileapi-findnextfilea)します。

### <a name="example"></a>例

  このトピックの例を参照してください。

##  <a name="getfileurl"></a>  CFtpFileFind::GetFileURL

指定したファイルの URL を取得するには、このメンバー関数を呼び出します。

```
CString GetFileURL() const;
```

### <a name="return-value"></a>戻り値

ファイル名とパスの Universal Resource Locator (URL)。

### <a name="remarks"></a>Remarks

`GetFileURL` メンバー関数のような[CFileFind::GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)形式で URL を返す点が、`ftp://moose/dir/file.txt`します。

## <a name="see-also"></a>関連項目

[CFileFind クラス](../../mfc/reference/cfilefind-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CGopherFileFind クラス](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile クラス](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpFile クラス](../../mfc/reference/chttpfile-class.md)
