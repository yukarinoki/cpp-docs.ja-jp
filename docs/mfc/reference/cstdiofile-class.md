---
title: クラスを指定します。
ms.date: 08/29/2019
f1_keywords:
- CStdioFile
- AFX/CStdioFile
- AFX/CStdioFile::CStdioFile
- AFX/CStdioFile::Open
- AFX/CStdioFile::ReadString
- AFX/CStdioFile::Seek
- AFX/CStdioFile::WriteString
- AFX/CStdioFile::m_pStream
helpviewer_keywords:
- CStdioFile [MFC], CStdioFile
- CStdioFile [MFC], Open
- CStdioFile [MFC], ReadString
- CStdioFile [MFC], Seek
- CStdioFile [MFC], WriteString
- CStdioFile [MFC], m_pStream
ms.assetid: 88c2274c-4f0e-4327-882a-557ba4b3ae15
ms.openlocfilehash: 80ee65aa339a38b3d8434bc4c7cb977e263f037b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366015"
---
# <a name="cstdiofile-class"></a>クラスを指定します。

ランタイム関数[fopen](../../c-runtime-library/reference/fopen-wfopen.md)によって開かれた C ランタイム ストリーム ファイルを表します。

## <a name="syntax"></a>構文

```
class CStdioFile : public CFile
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CStdio ファイル::CStdio ファイル](#cstdiofile)|パスまたはファイル`CStdioFile`ポインタからオブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CStdioファイル::オープン](#open)|オーバーロードされます。 開くは、既定`CStdioFile`のコンストラクターで使用するように設計されています[(CFile::Open](../../mfc/reference/cfile-class.md#open)をオーバーライドします)。|
|[CStdio ファイル::読み取り文字列](#readstring)|1 行のテキストを読み取ります。|
|[CStdio ファイル::シーク](#seek)|現在のファイル ポインタを配置します。|
|[CStdio ファイル::書き込み文字列](#writestring)|1 行のテキストを書き込みます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CStdio ファイル::m_pStream](#m_pstream)|開いているファイルへのポインターを含みます。|

## <a name="remarks"></a>解説

ストリーム ファイルはバッファリングされ、テキスト モード (既定) またはバイナリ モードで開くことができます。

テキスト モードでは、復帰と改行のペアに対して特別な処理を行うことができます。 改行 (改行) 文字 (0x0A) をテキスト モード`CStdioFile`オブジェクトに書き込むとき、バイトペア (0x0D, 0x0A) がファイルに送信されます。 読み取り時に、バイトペア(0x0D,0x0A)は単一の0x0Aバイトに変換されます。

[CFile](../../mfc/reference/cfile-class.md)関数[重複](../../mfc/reference/cfile-class.md#duplicate)、[ロック範囲](../../mfc/reference/cfile-class.md#lockrange)、および[ロック範囲](../../mfc/reference/cfile-class.md#unlockrange)は、`CStdioFile`ではサポートされていません。

でこれらの関数を`CStdioFile`呼び出すと、 [CNotSupportedException が表示されます](../../mfc/reference/cnotsupportedexception-class.md)。

`CStdioFile`の使用方法の詳細については、『 ランタイム ライブラリ リファレンス 』[の「MFC のファイル](../../mfc/files-in-mfc.md)」および[「ファイル処理](../../c-runtime-library/file-handling.md)」を*参照してください*。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CStdioFile`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="cstdiofilecstdiofile"></a><a name="cstdiofile"></a>CStdio ファイル::CStdio ファイル

`CStdioFile` オブジェクトを構築して初期化します。

```
CStdioFile();
CStdioFile(CAtlTransactionManager* pTM);
CStdioFile(FILE* pOpenStream);

CStdioFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags);

CStdioFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>パラメーター

*ストリームを開く*<br/>
C ランタイム関数[fopen](../../c-runtime-library/reference/fopen-wfopen.md)の呼び出しによって返されるファイル ポインタを指定します。

*ファイル名*<br/>
目的のファイルへのパスを示す文字列を指定します。 相対パスと絶対パスのどちらでも構いません。

*フラグを開く*<br/>
ファイル作成、ファイル共有、およびファイル アクセス モードのオプションを指定します。 ビットごとの OR ( **|** ) 演算子を使用して、複数のオプションを指定できます。

ファイル アクセス モード オプションは 1 つ必要です。その他のモードはオプションです。 モード オプションとその他のフラグの一覧については[、CFile::CFile](../../mfc/reference/cfile-class.md#cfile)を参照してください。 MFC バージョン 3.0 以降では、共有フラグを使用できます。

*Ptm*<br/>
オブジェクトへのポインター。

### <a name="remarks"></a>解説

既定のコンストラクターは、オブジェクトにファイルを`CStdioFile`アタッチしません。 このコンストラクターを使用する場合は、メソッド`CStdioFile::Open`を使用してファイルを開き、オブジェクトに`CStdioFile`アタッチする必要があります。

単一パラメーターのコンストラクターは、開いているファイル ストリームを`CStdioFile`オブジェクトにアタッチします。 許可されるポインター値には、定義済みの入出力ファイル・ポインター *stdin*、 *stdout*、または*stderr*が含まれます。

2 つのパラメーターを持つ`CStdioFile`コンストラクターは、オブジェクトを作成し、指定されたパスを持つ対応するファイルを開きます。

*pOpenStream*または*lpszFileName*のいずれかに NULL を渡すと、コンストラクター`CInvalidArgException*`は .

ファイルを開いたり作成したりできない場合、コンストラクタは`CFileException*`.

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#37](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_1.cpp)]

## <a name="cstdiofilem_pstream"></a><a name="m_pstream"></a>CStdio ファイル::m_pStream

データ`m_pStream`メンバーは、C ランタイム関数`fopen`によって返されるオープン ファイルへのポインターです。

```
FILE* m_pStream;
```

### <a name="remarks"></a>解説

ファイルが開いたことがないか、閉じられている場合は NULL です。

## <a name="cstdiofileopen"></a><a name="open"></a>CStdioファイル::オープン

オーバーロードされます。 Open は、既定`CStdioFile`のコンストラクターで使用するように設計されています。

```
virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
目的のファイルへのパスを表す文字列。 相対パスと絶対パスのどちらでも構いません。

*フラグを開く*<br/>
共有モードとアクセスモード。 ファイルを開くときに実行するアクションを指定します。 オプションは、ビットごとの OR (&#124;) 演算子を使用して組み合わせることができます。 アクセス権と共有オプションが 1 つ必要です。モード作成モードとモードなし継承モードはオプションです。

*pError*<br/>
失敗した操作の状態を受け取る既存のファイル例外オブジェクトへのポインター。

*Ptm*<br/>
`CAtlTransactionManager`オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cstdiofilereadstring"></a><a name="readstring"></a>CStdio ファイル::読み取り文字列

テキスト データを、オブジェクトに関連付けられたファイルから *、nMax*-1 文字の制限までバッファ`CStdioFile`に読み込みます。

```
virtual LPTSTR ReadString(
    LPTSTR lpsz,
    UINT nMax);

virtual BOOL ReadString(CString& rString);
```

### <a name="parameters"></a>パラメーター

*lpsz*<br/>
null で終わるテキスト文字列を受け取るユーザー指定のバッファーへのポインターを指定します。

*nMax*<br/>
終了する NULL 文字をカウントしない、読み取る最大文字数を指定します。

*文字列*<br/>
関数が`CString`返されるときに文字列を格納するオブジェクトへの参照。

### <a name="return-value"></a>戻り値

テキスト データを格納しているバッファーへのポインター。 データを読み取らずにファイルの終わりに達した場合は NULL。または、データを読み取らずにファイルの終わりに達した場合は FALSE を返します。

### <a name="remarks"></a>解説

読み取りは、最初の改行文字によって停止されます。 その場合 *、nMax*-1 文字より少ない文字が読み取られた場合、改行文字がバッファーに格納されます。 いずれの場合も、NULL 文字 ('\0') が追加されます。

[CFile::Read](../../mfc/reference/cfile-class.md#read)はテキストモード入力でも使用できますが、キャリッジリターンとラインフィードのペアでは終了しません。

> [!NOTE]
> この`CString`関数のバージョンは、存在する`'\n'`場合を削除します。LPTSTR バージョンでは、そうではありません。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#38](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_2.cpp)]

## <a name="cstdiofileseek"></a><a name="seek"></a>CStdio ファイル::シーク

以前に開いたファイル内でポインタを再配置します。

```
virtual ULONGLONG Seek(
    LONGLONG lOff,
    UINT nFrom);
```

### <a name="parameters"></a>パラメーター

*lオフ*<br/>
ポインターを移動するバイト数。

*nから*<br/>
ポインター移動モード。 次のいずれかの値を指定する必要があります。

- `CFile::begin`: ファイルポインタ*lOff*バイトをファイルの先頭から前方に移動します。

- `CFile::current`: ファイル ポインタ*lOff*バイトをファイル内の現在の位置から移動します。

- `CFile::end`: ファイルポインタ*lOff*バイトをファイルの末尾から移動します。 既存のファイルをシークするには*lOff*が負の値でなければならないことに注意してください。正の値は、ファイルの末尾を越えてシークします。

### <a name="return-value"></a>戻り値

要求された位置が有効である場合`Seek`は、ファイルの先頭からの新しいバイト オフセットを返します。 それ以外の場合、戻り値は未`CFileException`定義になり、オブジェクトがスローされます。

### <a name="remarks"></a>解説

この`Seek`関数は、指定された量(絶対または相対的)にポインタを移動することによって、ファイルの内容にランダムにアクセスすることを許可します。 シーク中に実際に読み取られるデータはありません。 要求された位置がファイルのサイズより大きい場合、ファイルの長さは、その位置まで拡張され、例外はスローされません。

ファイルを開くと、ファイル ポインタはファイルの先頭のオフセット 0 に置かれます。

この実装`Seek`は、ランタイム ライブラリ (CRT) 関数`fseek`に基づいています。 テキストモードで開かれたストリームの`Seek`使用には、いくつかの制限があります。 詳細については、「 [fseek , _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)」を参照してください。

### <a name="example"></a>例

次の例は、ファイルの`Seek`先頭からポインターを 1000 バイト移動する方法`cfile`を示しています。 データを`Seek`読み取らないので、後で[CStdioFile::ReadString](#readstring)を呼び出してデータを読み取る必要があります。

[!code-cpp[NVC_MFCFiles#39](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_3.cpp)]

## <a name="cstdiofilewritestring"></a><a name="writestring"></a>CStdio ファイル::書き込み文字列

バッファーからオブジェクトに関連付けられたファイルにデータを`CStdioFile`書き込みます。

```
virtual void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>パラメーター

*lpsz*<br/>
null で終わる文字列を含むバッファーへのポインターを指定します。

### <a name="remarks"></a>解説

終端の NULL 文字`\0`( ) はファイルに書き込まれません。 このメソッドは *、改行*文字を改行と改行のペアとしてファイルに書き込みます。

null で終わるデータをファイルに書き込む場合は、CFile::Write を使用`CStdioFile::Write`します。 [CFile::Write](../../mfc/reference/cfile-class.md#write)

このメソッドは`CInvalidArgException*`*、lpsz*パラメーターに NULL を指定するとスローされます。

このメソッドは、ファイル`CFileException*`システム エラーに応答してをスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#40](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_4.cpp)]

## <a name="see-also"></a>関連項目

[CFile クラス](../../mfc/reference/cfile-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CFile クラス](../../mfc/reference/cfile-class.md)<br/>
[ファイル::D](../../mfc/reference/cfile-class.md#duplicate)<br/>
[ファイル::ロックレンジ](../../mfc/reference/cfile-class.md#lockrange)<br/>
[ファイル::ロック解除範囲](../../mfc/reference/cfile-class.md#unlockrange)<br/>
[クラスをサポートしていません。](../../mfc/reference/cnotsupportedexception-class.md)
