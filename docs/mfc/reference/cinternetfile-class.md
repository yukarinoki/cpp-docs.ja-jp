---
title: CInternetFile クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 65bc36856e253d086cc430a600daa9255e21ea75
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405743"
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
|[CInternetFile::Close](#close)|閉じる、`CInternetFile`し、そのリソースを解放します。|
|[CInternetFile::Flush](#flush)|書き込みバッファーの内容をフラッシュし、ターゲット コンピューターにメモリ内のデータが書き込まれるようにします。|
|[CInternetFile::GetLength](#getlength)|ファイルのサイズを返します。|
|[CInternetFile::Read](#read)|指定されたバイト数を読み取ります。|
|[CInternetFile::ReadString](#readstring)|文字のストリームを読み取ります。|
|[CInternetFile::Seek](#seek)|ファイルを開くには、ポインターを移動します。|
|[CInternetFile::SetReadBufferSize](#setreadbuffersize)|データが読み取られるバッファーのサイズを設定します。|
|[CInternetFile::SetWriteBufferSize](#setwritebuffersize)|データが書き込まれるバッファーのサイズを設定します。|
|[CInternetFile::Write](#write)|指定されたバイト数を書き込みます。|
|[CInternetFile::WriteString](#writestring)|Null で終わる文字列をファイルに書き込みます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CInternetFile::operator HINTERNET](#operator_hinternet)|インターネット ハンドルのキャスト演算子。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CInternetFile::m_hFile](#m_hfile)|ファイルへのハンドル。|

## <a name="remarks"></a>Remarks

基本クラスを提供します、 [CHttpFile](../../mfc/reference/chttpfile-class.md)と[CGopherFile](../../mfc/reference/cgopherfile-class.md)ファイル クラス。 作成することはありません、`CInternetFile`オブジェクトに直接します。 代わりに、その派生クラスのいずれかのオブジェクトを呼び出すことによって作成[CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile)または[しないで](../../mfc/reference/chttpconnection-class.md#openrequest)します。 作成することも、`CInternetFile`オブジェクトを呼び出すことによって[CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile)します。

`CInternetFile`メンバー関数`Open`、 `LockRange`、 `UnlockRange`、および`Duplicate`に実装されていない`CInternetFile`します。 これらの関数を呼び出す場合、`CInternetFile`オブジェクトの取得は、 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)します。

方法の詳細については、`CInternetFile`クラスでは、その他の MFC インターネット機能は、記事をご覧ください。[インターネットが WinInet を使用したプログラミング](../../mfc/win32-internet-extensions-wininet.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

`CInternetFile`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

##  <a name="abort"></a>  CInternetFile::Abort

このオブジェクトに関連付けられたファイルを閉じて、ファイルを読み取りまたは書き込みに使用できなくなります。

```
virtual void Abort();
```

### <a name="remarks"></a>Remarks

オブジェクトを破棄する前に、ファイルを閉じていない場合、デストラクターがファイルを閉じます。

例外を処理するときに`Abort`異なります[閉じる](#close)2 つの重要な点でします。 まず、`Abort`障害を無視するため、関数がエラーに例外をスローしません。 2 番目、`Abort`しない**ASSERT**ファイルが開いていない、または以前に閉じられました。

##  <a name="cinternetfile"></a>  CInternetFile::CInternetFile

このメンバー関数が呼び出されます、`CInternetFile`オブジェクトが作成されます。

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

*hFile*<br/>
インターネット ファイルへのハンドル。

*pstrFileName*<br/>
ファイル名を含む文字列へのポインター。

*pConnection*<br/>
ポインターを[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)オブジェクト。

*bReadMode*<br/>
ファイルが読み取り専用かどうかを示します。

*hSession*<br/>
インターネット セッションへのハンドル。

*pstrServer*<br/>
サーバーの名前を含む文字列へのポインター。

*dwContext*<br/>
コンテキスト識別子を`CInternetFile`オブジェクト。 参照してください[WinInet の基礎](../../mfc/wininet-basics.md)コンテキスト識別子の詳細についてはします。

### <a name="remarks"></a>Remarks

作成することはありません、`CInternetFile`オブジェクトに直接します。 代わりに、その派生クラスのいずれかのオブジェクトを呼び出すことによって作成[CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile)または[しないで](../../mfc/reference/chttpconnection-class.md#openrequest)します。 作成することも、`CInternetFile`オブジェクトを呼び出すことによって[CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile)します。

##  <a name="close"></a>  CInternetFile::Close

閉じる、`CInternetFile`し、そのリソースのいずれかを解放します。

```
virtual void Close();
```

### <a name="remarks"></a>Remarks

書き込みのため、ファイルが開かれた場合は、暗黙的な呼び出しを[フラッシュ](#flush)バッファーされたデータを確保するためには、ホストに書き込まれます。 呼び出す必要があります`Close`ファイルの使用が終了するときにします。

##  <a name="flush"></a>  CInternetFile::Flush

書き込みバッファーの内容をフラッシュするには、このメンバー関数を呼び出します。

```
virtual void Flush();
```

### <a name="remarks"></a>Remarks

使用`Flush`とホスト マシンと、トランザクションの完了を保証するために、ターゲット コンピューターにメモリ内のすべてのデータが実際に書き込まれたことを保証するためにします。 `Flush` 有効になるのみ`CInternetFile`オブジェクトが書き込み用に開きます。

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

##  <a name="read"></a>  CInternetFile::Read

開始位置として、指定されたメモリに読み込むには、このメンバー関数を呼び出す*lpvBuf*、指定された数 (バイト単位) の*nCount*します。

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>パラメーター

*lpBuf*<br/>
ファイル データを読み込むメモリ アドレスへのポインター。

*nCount*<br/>
書き込むバイト数。

### <a name="return-value"></a>戻り値

バッファーに転送するバイト数。 戻り値より小さい*nCount*ファイルの末尾に達した場合。

### <a name="remarks"></a>Remarks

実際に読み取られたバイト数を返します、可能性のある数より小さい*nCount*ファイルが終了した場合。 ファイルの読み取り中にエラーが発生した場合、関数、 [CInternetException](../../mfc/reference/cinternetexception-class.md)エラーを説明するオブジェクト。 ファイルの末尾を越える読み取りはエラーとは見なされず、例外がスローされないことに注意してください。

呼び出すすべてのデータが取得されるためには、アプリケーションを継続する必要があります、`CInternetFile::Read`メソッドまで、メソッドは 0 を返します。

##  <a name="readstring"></a>  CInternetFile::ReadString

改行文字が見つかるまでの文字のストリームを読み取るには、このメンバー関数を呼び出します。

```
virtual BOOL ReadString(CString& rString);

virtual LPTSTR ReadString(
    LPTSTR pstr,
    UINT nMax);
```

### <a name="parameters"></a>パラメーター

*pstr*<br/>
読み取られる行を受け取る文字列へのポインター。

*nMax*<br/>
読み取り対象の文字の最大数。

*rString*<br/>
参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)を読み取り、行を受け取るオブジェクト。

### <a name="return-value"></a>戻り値

取得されるプレーンなデータを格納しているバッファーへのポインター、 [CInternetFile](../../mfc/reference/cinternetfile-class.md)オブジェクト。 このメソッドに渡されたバッファーのデータ型に関係なく (たとえば、Unicode に変換) のデータに任意の操作を行いません、返されたデータを構造にマップする必要がありますので、予想として、 **void** <strong>\*</strong> 型が返されました。

すべてのデータを読み取り中にファイルの終わりに達した場合は NULL です。または、データを読み込まずにブール型、FALSE の場合、ファイルの終わりに達した場合。

### <a name="remarks"></a>Remarks

関数によって参照されるメモリに、その結果、行の配置、 *pstr*パラメーター。 文字の読み取りを停止することで指定された文字の最大数に達したとき*nMax*します。 バッファーは、常に終端の null 文字を受け取ります。

呼び出す場合`ReadString`最初に呼び出さず[SetReadBufferSize](#setreadbuffersize)、4096 バイトのバッファーが表示されます。

##  <a name="seek"></a>  CInternetFile::Seek

以前に開かれたファイルで、ポインターの位置を変更するには、このメンバー関数を呼び出します。

```
virtual ULONGLONG Seek(
    LONGLONG lOffset,
    UINT nFrom);
```

### <a name="parameters"></a>パラメーター

*lOffset*<br/>
ファイルの読み取り/書き込みのポインターを移動するバイト オフセットします。

*nFrom*<br/>
オフセットの相対参照。 値は次のいずれかを指定する必要があります。

- `CFile::begin` ファイル ポインターを移動*lOff*ファイルの先頭からバイトを転送します。

- `CFile::current` ファイル ポインターを移動*lOff*ファイル内の現在位置からのバイト数。

- `CFile::end` ファイル ポインターを移動*lOff*ファイルの終端からのバイト。 *lOff*する必要がありますが負では、既存をシークするファイル; 正の値は、ファイルの末尾を越えたシークします。

### <a name="return-value"></a>戻り値

要求された位置が; 有効な場合は、ファイルの先頭からのオフセットの新しいバイトそれ以外の場合、値は未定義と[CInternetException](../../mfc/reference/cinternetexception-class.md)オブジェクトがスローされます。

### <a name="remarks"></a>Remarks

`Seek`関数を使用するランダム アクセス ファイルの内容をポインターを移動することによって、指定した時間、絶対的または相対的です。 データは、検索中に実際には読み込まれません。

この時点でこのメンバー関数への呼び出しはのみに関連付けられたデータ サポート`CHttpFile`オブジェクト。 Gopher、FTP、または要求はサポートされません。 呼び出す場合`Seek`これらのサポートされていないサービスの 1 つは、処理、バックアップするを ERROR_INTERNET_INVALID_OPERATION Win32 エラー コード。

ファイルが開かれたときに、ファイル ポインターがオフセット 0 で、ファイルの先頭には。

> [!NOTE]
>  使用して`Seek`への暗黙的な呼び出しが発生する可能性があります[フラッシュ](#flush)します。

### <a name="example"></a>例

  基本クラスの実装の例を参照してください ( [CFile::Seek](../../mfc/reference/cfile-class.md#seek))。

##  <a name="setreadbuffersize"></a>  CInternetFile::SetReadBufferSize

使用される一時的な読み取りバッファーのサイズを設定するには、このメンバー関数を呼び出す、 `CInternetFile`-派生オブジェクト。

```
BOOL SetReadBufferSize(UINT nReadSize);
```

### <a name="parameters"></a>パラメーター

*nReadSize*<br/>
バイト単位のバッファー サイズ。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するということがあります。

### <a name="remarks"></a>Remarks

基になる WinInet Api はバッファー処理を実行しない、ので読み取られるデータの量に関係なく、効率的にデータを読み取るアプリケーションは、バッファー サイズを選択します。 各呼び出しの場合[読み取り](#read)通常で大量のデータ (たとえば、4 つ以上のキロバイト) は必要ありませんバッファー。 ただし、呼び出す場合`Read`、データの小さなチャンクを取得するを使用する場合または[ReadString](#readstring)読み取りバッファーはアプリケーションのパフォーマンスを向上し、一度に 1 行ずつを読み取る。

既定で、`CInternetFile`オブジェクトが読み取りのすべてのバッファーを提供していません。 このメンバー関数を呼び出す場合は、読み取りアクセスのため、ファイルが開かれたことを確認する必要があります。

いつでも、バッファー サイズを増やすことができますが、バッファーを縮小効果がありません。 呼び出す場合[ReadString](#readstring)最初に呼び出さず`SetReadBufferSize`、4096 バイトのバッファーが表示されます。

##  <a name="setwritebuffersize"></a>  CInternetFile::SetWriteBufferSize

使用される一時的な書き込みバッファーのサイズを設定するには、このメンバー関数を呼び出す、 `CInternetFile`-派生オブジェクト。

```
BOOL SetWriteBufferSize(UINT nWriteSize);
```

### <a name="parameters"></a>パラメーター

*nWriteSize*<br/>
バッファーのサイズ (バイト単位)。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するということがあります。

### <a name="remarks"></a>Remarks

したがって、デバッグ情報を基になる、バッファリング、WinInet Api を実行しないと選択、バッファー サイズが書き込まれるデータの量に関係なく効率的にデータを書き込むアプリケーションは、します。 各呼び出しの場合[書き込み](#write)は通常、大量のデータ (たとえば、次の 4 つまたは複数キロバイト一度に) の必要はありません、バッファー。 ただし、呼び出す場合[書き込み](#write)書き込みバッファー少量のデータを書き込むには、アプリケーションのパフォーマンスが向上します。

既定で、`CInternetFile`オブジェクトがすべての書き込みバッファーを提供していません。 このメンバー関数を呼び出す場合は、書き込みアクセスのため、ファイルが開かれたことを確認する必要があります。 書き込みバッファーのサイズを変更するには、いつでも、そのようにすると暗黙的な呼び出しを[フラッシュ](#flush)します。

##  <a name="write"></a>  CInternetFile::Write

特定のメモリに書き込むには、このメンバー関数を呼び出す*lpvBuf*、指定された数 (バイト単位) の*nCount*します。

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>パラメーター

*lpBuf*<br/>
書き込まれる最初のバイトへのポインター。

*nCount*<br/>
書き込むバイト数を指定します。

### <a name="remarks"></a>Remarks

データの書き込み中にエラーが発生した場合、関数、 [CInternetException](../../mfc/reference/cinternetexception-class.md)エラーを説明するオブジェクト。

##  <a name="writestring"></a>  CInternetFile::WriteString

この関数は、関連付けられているファイルを null で終わる文字列を書き込みます。

```
virtual void WriteString(LPCTSTR pstr);
```

### <a name="parameters"></a>パラメーター

*pstr*<br/>
書き込まれるコンテンツを含む文字列へのポインター。

### <a name="remarks"></a>Remarks

データの書き込み中にエラーが発生した場合、関数、 [CInternetException](../../mfc/reference/cinternetexception-class.md)エラーを説明するオブジェクト。

## <a name="see-also"></a>関連項目

[CStdioFile クラス](../../mfc/reference/cstdiofile-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection クラス](../../mfc/reference/cinternetconnection-class.md)
