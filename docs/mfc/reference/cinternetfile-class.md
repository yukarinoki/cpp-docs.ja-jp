---
title: クラス
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
ms.openlocfilehash: e3f1a7167f5464423754951764c4441513197841
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372401"
---
# <a name="cinternetfile-class"></a>クラス

インターネット プロトコルを使用するリモート システム上のファイルへのアクセスを許可します。

## <a name="syntax"></a>構文

```
class CInternetFile : public CStdioFile
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[ファイル::Cインターネットファイル](#cinternetfile)|`CInternetFile` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cインターネットファイル::中止](#abort)|警告とエラーをすべて無視してファイルを閉じます。|
|[ファイルを閉じる](#close)|を`CInternetFile`閉じて、そのリソースを解放します。|
|[ファイル::フラッシュ](#flush)|書き込みバッファーの内容をフラッシュし、メモリ内のデータがターゲット コンピューターに書き込まれるかどうかを確認します。|
|[ファイルを取得します。](#getlength)|ファイルのサイズを返します。|
|[ファイルを読み取る](#read)|指定されたバイト数を読み取ります。|
|[ファイルを読み取る](#readstring)|文字のストリームを読み取ります。|
|[ファイル::シーク](#seek)|開いているファイル内でポインターを再配置します。|
|[ファイルサイズ](#setreadbuffersize)|データを読み取るバッファのサイズを設定します。|
|[ファイルサイズ](#setwritebuffersize)|データが書き込まれるバッファのサイズを設定します。|
|[ファイル::書き込み](#write)|指定したバイト数を書き込みます。|
|[ファイルを書き込む](#writestring)|null で終わる文字列をファイルに書き込みます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[Cインターネットファイル::オペレータHインターネット](#operator_hinternet)|インターネット ハンドルのキャスト演算子。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[ファイル:m_hFile](#m_hfile)|ファイルへのハンドル。|

## <a name="remarks"></a>解説

[ファイル](../../mfc/reference/chttpfile-class.md)クラスの基本[クラスを提供](../../mfc/reference/cgopherfile-class.md)します。 オブジェクトを`CInternetFile`直接作成することはありません。 代わりに[、CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile)または[CHttpConnection:::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest)を呼び出すことによって、その派生クラスの 1 つのオブジェクトを作成します。 オブジェクトを`CInternetFile`作成する方法は[、CFtp 接続::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile)を呼び出すこともできます。

`CInternetFile``Open`メンバ関数 、 `LockRange` `UnlockRange`、、`Duplicate`および は、`CInternetFile`に実装されていません。 オブジェクトに対してこれらの関数を`CInternetFile`呼び出すと、 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)が表示されます。

他の MFC`CInternetFile`インターネット クラスとの動作の詳細については[、「WinInet を使用したインターネット プログラミング](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

`CInternetFile`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

## <a name="cinternetfileabort"></a><a name="abort"></a>Cインターネットファイル::中止

このオブジェクトに関連付けられたファイルを閉じ、ファイルを読み取りまたは書き込みできないようにします。

```
virtual void Abort();
```

### <a name="remarks"></a>解説

オブジェクトを破棄する前にファイルを閉じなかった場合、デストラクタはオブジェクトを閉じます。

例外を処理する場合`Abort`[、2](#close)つの重要な方法で Close とは異なります。 まず、関数`Abort`はエラーを無視するため、エラーの例外をスローしません。 次に`Abort`、ファイルが開かれていないか、以前に閉じられた場合は **、ASSERT**を実行しません。

## <a name="cinternetfilecinternetfile"></a><a name="cinternetfile"></a>ファイル::Cインターネットファイル

このメンバー関数は、オブジェクトが`CInternetFile`作成されるときに呼び出されます。

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

*hファイル*<br/>
インターネット ファイルへのハンドル。

*ファイル名*<br/>
ファイル名を含む文字列へのポインター。

*pConnection*<br/>
[オブジェクトへの](../../mfc/reference/cinternetconnection-class.md)ポインター。

*読み取りモード*<br/>
ファイルが読み取り専用かどうかを示します。

*hセッション*<br/>
インターネット セッションへのハンドル。

*を行う*<br/>
サーバーの名前を含む文字列へのポインター。

*dw コンテキスト*<br/>
`CInternetFile`オブジェクトのコンテキスト識別子。 コンテキスト識別子の詳細については[、「WinInet](../../mfc/wininet-basics.md)の基本」を参照してください。

### <a name="remarks"></a>解説

オブジェクトを`CInternetFile`直接作成することはありません。 代わりに[、CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile)または[CHttpConnection:::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest)を呼び出すことによって、その派生クラスの 1 つのオブジェクトを作成します。 オブジェクトを`CInternetFile`作成する方法は[、CFtp 接続::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile)を呼び出すこともできます。

## <a name="cinternetfileclose"></a><a name="close"></a>ファイルを閉じる

を`CInternetFile`閉じて、そのリソースを解放します。

```
virtual void Close();
```

### <a name="remarks"></a>解説

ファイルが書き込み用にオープンされた場合[、Flush](#flush)に対して暗黙的な呼び出しが行えられ、バッファーに格納されたすべてのデータがホストに書き込まれます。 ファイルの使用`Close`が終了したら、呼び出す必要があります。

## <a name="cinternetfileflush"></a><a name="flush"></a>ファイル::フラッシュ

書き込みバッファーの内容をフラッシュします。

```
virtual void Flush();
```

### <a name="remarks"></a>解説

メモリ`Flush`内のすべてのデータが実際にターゲット マシンに書き込まれたことを確認し、ホスト マシンとのトランザクションが完了したことを保証するために使用します。 `Flush`は、書き`CInternetFile`込みのために開かれたオブジェクトに対してのみ有効です。

## <a name="cinternetfilegetlength"></a><a name="getlength"></a>ファイルを取得します。

ファイルのサイズを返します。

```
virtual ULONGLONG GetLength() const;
```

## <a name="cinternetfilem_hfile"></a><a name="m_hfile"></a>ファイル:m_hFile

このオブジェクトに関連付けられているファイルへのハンドル。

```
HINTERNET m_hFile;
```

## <a name="cinternetfileoperator-hinternet"></a><a name="operator_hinternet"></a>Cインターネットファイル::オペレータHインターネット

この演算子を使用して、現在のインターネット セッションの Windows ハンドルを取得します。

```
operator HINTERNET() const;
```

## <a name="cinternetfileread"></a><a name="read"></a>ファイルを読み取る

指定したメモリを読み取*るために、この*メンバー関数を呼び出*します。*

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>パラメーター

*lpBuf*<br/>
ファイル データを読み込むメモリ アドレスへのポインター。

*nカウント*<br/>
書き込むバイト数。

### <a name="return-value"></a>戻り値

バッファーに転送するバイト数。 ファイルの末尾に達した場合、戻り値は*nCount*より小さい値になる可能性があります。

### <a name="remarks"></a>解説

この関数は、実際に読み込まれたバイト数を返します。 *nCount* ファイルの読み取り中にエラーが発生した場合、この関数はエラーを記述する[CInternetException](../../mfc/reference/cinternetexception-class.md)オブジェクトをスローします。 ファイルの末尾を越える読み取りはエラーとは見なされず、例外がスローされないことに注意してください。

すべてのデータが確実に取得されるようにするには、アプリケーションはメソッドが 0`CInternetFile::Read`を返すまでメソッドを呼び出し続ける必要があります。

## <a name="cinternetfilereadstring"></a><a name="readstring"></a>ファイルを読み取る

改行文字が見つかるまで文字のストリームを読み取る場合に、このメンバー関数を呼び出します。

```
virtual BOOL ReadString(CString& rString);

virtual LPTSTR ReadString(
    LPTSTR pstr,
    UINT nMax);
```

### <a name="parameters"></a>パラメーター

*プストル*<br/>
読み取り対象の行を受け取る文字列へのポインター。

*nMax*<br/>
読み取る最大文字数。

*文字列*<br/>
読み取り行を受け取る[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトへの参照。

### <a name="return-value"></a>戻り値

[CInternetFile](../../mfc/reference/cinternetfile-class.md)オブジェクトから取得したプレーン データを含むバッファーへのポインター。 このメソッドに渡されるバッファーのデータ型に関係なく、データに対する操作 (Unicode への変換など) は実行されないため、返されたデータを **、void**<strong>\*</strong>型が返されたかのように、予期した構造体にマップする必要があります。

データを読み取らずにファイルの終わりに達した場合は NULL。データを読み取らずにファイルの終わりに達した場合は FALSE を返します。

### <a name="remarks"></a>解説

この関数は、結果の行を*pstr*パラメーターで参照されるメモリに配置します。 *nMax*で指定された最大文字数に達すると、文字の読み取りを停止します。 バッファは常に終端の NULL 文字を受け取ります。

最初に呼`ReadString`び出さずに呼び出すと、4096 バイトのバッファーが取得されます。 [SetReadBufferSize](#setreadbuffersize)

## <a name="cinternetfileseek"></a><a name="seek"></a>ファイル::シーク

以前に開いたファイル内でポインターの位置を変更します。

```
virtual ULONGLONG Seek(
    LONGLONG lOffset,
    UINT nFrom);
```

### <a name="parameters"></a>パラメーター

*lオフセット*<br/>
ファイル内の読み取り/書き込みポインターを移動するバイト単位でオフセットします。

*nから*<br/>
オフセットの相対参照。 次のいずれかの値を指定する必要があります。

- `CFile::begin`ファイル ポインタ*lOff*バイトをファイルの先頭から前方に移動します。

- `CFile::current`ファイル ポインタ*lOff*バイトをファイル内の現在の位置から移動します。

- `CFile::end`ファイルポインタ*lOff*バイトをファイルの末尾から移動します。 *lOff*は、既存のファイルをシークする場合は負の値にする必要があります。正の値は、ファイルの末尾を越えてシークします。

### <a name="return-value"></a>戻り値

要求された位置が有効である場合は、ファイルの先頭からの新しいバイト オフセット。それ以外の場合、値は未定義になり[、CInternetException](../../mfc/reference/cinternetexception-class.md)オブジェクトがスローされます。

### <a name="remarks"></a>解説

この`Seek`関数は、指定された量(絶対または相対的)にポインタを移動することによって、ファイルの内容にランダムにアクセスすることを許可します。 シーク中に実際に読み取られるデータはありません。

このとき、このメンバー関数の呼び出しは、オブジェクトに関連`CHttpFile`付けられたデータに対してのみサポートされます。 FTP または gopher 要求ではサポートされません。 これらのサポートされていない`Seek`サービスのいずれかを呼び出すと、Win32 エラー コード ERROR_INTERNET_INVALID_OPERATIONに戻ります。

ファイルを開くと、ファイルポインタはファイルの先頭であるオフセット 0 になります。

> [!NOTE]
> を`Seek`使用すると、 [Flush](#flush)を暗黙的に呼び出す可能性があります。

### <a name="example"></a>例

  基本クラスの実装の例 ( [CFile:シーク](../../mfc/reference/cfile-class.md#seek)) を参照してください。

## <a name="cinternetfilesetreadbuffersize"></a><a name="setreadbuffersize"></a>ファイルサイズ

派生オブジェクトによって使用される一時的な読み取りバッファーのサイズを`CInternetFile`設定します。

```
BOOL SetReadBufferSize(UINT nReadSize);
```

### <a name="parameters"></a>パラメーター

*を読み取る*<br/>
バイト単位のバッファー サイズ。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)が呼び出され、エラーの原因を特定できます。

### <a name="remarks"></a>解説

基になる WinInet API はバッファリングを実行しません。 [Read](#read)の各呼び出しが通常は大きなデータ (たとえば、4 KB 以上) を伴う場合は、バッファは必要ありません。 ただし、小さなデータ`Read`のチャンクを取得するために呼び出す場合、または[ReadString](#readstring)を使用して一度に個々の行を読み取る場合、読み取りバッファーは、アプリケーションのパフォーマンスを向上させます。

既定では、オブジェクト`CInternetFile`は読み取り用のバッファリングを提供しません。 このメンバー関数を呼び出す場合は、ファイルが読み取りアクセス用に開かれていたことを確認する必要があります。

バッファー サイズはいつでも増やすことができますが、バッファーを縮小しても効果はありません。 最初に呼び出さずに`SetReadBufferSize`[ReadString](#readstring)を呼び出すと、4096 バイトのバッファーが取得されます。

## <a name="cinternetfilesetwritebuffersize"></a><a name="setwritebuffersize"></a>ファイルサイズ

派生オブジェクトによって使用される一時的な書き込みバッファーのサイズを`CInternetFile`設定します。

```
BOOL SetWriteBufferSize(UINT nWriteSize);
```

### <a name="parameters"></a>パラメーター

*サイズを変更します。*<br/>
バッファーのサイズ (バイト単位)。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)が呼び出され、エラーの原因を特定できます。

### <a name="remarks"></a>解説

基になる WinInet API はバッファリングを実行しません。 [通常、Write](#write)を呼び出すたびに大量のデータが含まれる場合 (たとえば、一度に 4 KB 以上)、バッファは必要ありません。 ただし[、Write](#write)を呼び出して小さなデータのチャンクを書き込む場合、書き込みバッファーを使用すると、アプリケーションのパフォーマンスが向上します。

既定では、オブジェクト`CInternetFile`は書き込み用のバッファリングを提供しません。 このメンバー関数を呼び出す場合は、ファイルが書き込みアクセスで開かれていたことを確認する必要があります。 書き込みバッファのサイズはいつでも変更できますが、その場合は[Flush](#flush)が暗黙的に呼び出されます。

## <a name="cinternetfilewrite"></a><a name="write"></a>ファイル::書き込み

指定されたメモリ*lpvBuf*に書き込むには、このメンバー関数を呼び出*します*。

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>パラメーター

*lpBuf*<br/>
書き込まれる最初のバイトへのポインター。

*nカウント*<br/>
書き込むバイト数を指定します。

### <a name="remarks"></a>解説

データの書き込み中にエラーが発生した場合、関数はエラーを記述する[CInternetException](../../mfc/reference/cinternetexception-class.md)オブジェクトをスローします。

## <a name="cinternetfilewritestring"></a><a name="writestring"></a>ファイルを書き込む

この関数は、関連付けられたファイルに null で終わる文字列を書き込みます。

```
virtual void WriteString(LPCTSTR pstr);
```

### <a name="parameters"></a>パラメーター

*プストル*<br/>
書き込む内容を含む文字列へのポインター。

### <a name="remarks"></a>解説

データの書き込み中にエラーが発生した場合、関数はエラーを記述する[CInternetException](../../mfc/reference/cinternetexception-class.md)オブジェクトをスローします。

## <a name="see-also"></a>関連項目

[クラスを指定します。](../../mfc/reference/cstdiofile-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection クラス](../../mfc/reference/cinternetconnection-class.md)
