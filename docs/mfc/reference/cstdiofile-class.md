---
title: CStdioFile クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStdioFile
- AFX/CStdioFile
- AFX/CStdioFile::CStdioFile
- AFX/CStdioFile::Open
- AFX/CStdioFile::ReadString
- AFX/CStdioFile::Seek
- AFX/CStdioFile::WriteString
- AFX/CStdioFile::m_pStream
dev_langs:
- C++
helpviewer_keywords:
- CStdioFile [MFC], CStdioFile
- CStdioFile [MFC], Open
- CStdioFile [MFC], ReadString
- CStdioFile [MFC], Seek
- CStdioFile [MFC], WriteString
- CStdioFile [MFC], m_pStream
ms.assetid: 88c2274c-4f0e-4327-882a-557ba4b3ae15
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bbe6d2bd5ea8d03a73fd7389da9eeb0e7ca32cdf
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442423"
---
# <a name="cstdiofile-class"></a>CStdioFile クラス

実行時の関数で開かれた C ランタイム ストリーム ファイルを表す[fopen](../../c-runtime-library/reference/fopen-wfopen.md)します。

## <a name="syntax"></a>構文

```
class CStdioFile : public CFile
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CStdioFile::CStdioFile](#cstdiofile)|構築、`CStdioFile`パスまたはファイルのポインターからのオブジェクト。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CStdioFile::Open](#open)|オーバーロードされます。 開くが、既定で使用するために設計された`CStdioFile`コンス トラクター (オーバーライド[CFile::Open](../../mfc/reference/cfile-class.md#open))。|
|[CStdioFile::ReadString](#readstring)|1 行のテキストを読み取ります。|
|[CStdioFile::Seek](#seek)|現在のファイル ポインターを移動します。|
|[CStdioFile::WriteString](#writestring)|1 行のテキストを書き込みます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CStdioFile::m_pStream](#m_pstream)|開いているファイルへのポインターが含まれています。|

## <a name="remarks"></a>Remarks

Stream ファイルは、バッファーに格納され、テキスト モード (既定値) またはバイナリ モードのいずれかで開くことができます。

テキスト モードでは、復帰と改行のペアの特殊な処理を提供します。 改行文字を記述するとき文字 (0x0A) テキスト モードを`CStdioFile`オブジェクト、バイトのペア (0x0D、0x0A) ファイルに送信されます。 読み込みのときは、バイトのペア (0x0D、0x0A) 1 0x0A バイトに変換されます。

[CFile](../../mfc/reference/cfile-class.md)関数[複製](../../mfc/reference/cfile-class.md#duplicate)、 [LockRange](../../mfc/reference/cfile-class.md#lockrange)、および[UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)はサポートされていません`CStdioFile`します。

これらの関数を呼び出す場合、`CStdioFile`が表示されます、 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)します。

使用しての詳細については`CStdioFile`、記事をご覧ください[MFC のファイル](../../mfc/files-in-mfc.md)と[ファイル処理](../../c-runtime-library/file-handling.md)で、*ランタイム ライブラリ リファレンス*します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CStdioFile`

## <a name="requirements"></a>要件

**ヘッダー:** afx.h

##  <a name="cstdiofile"></a>  CStdioFile::CStdioFile

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

*pOpenStream*<br/>
C ランタイム関数の呼び出しによって返されたファイル ポインターを指定します[fopen](../../c-runtime-library/reference/fopen-wfopen.md)します。

*場合*<br/>
目的のファイルへのパスを表す文字列を指定します。 相対パスまたは絶対パスができます。

*nOpenFlags*<br/>
ファイルの作成、ファイルの共有、およびファイル アクセス モードのオプションを指定します。 ビットごとの OR を使用して複数のオプションを指定することができます ( **|** ) 演算子。

1 つのファイル アクセス モード オプションが必要です。その他のモードでは、省略可能です。 参照してください[ほか](../../mfc/reference/cfile-class.md#cfile)モード オプションとその他のフラグの一覧についてはします。 Mfc バージョン 3.0 以降では、共有フラグが許可されます。

*pTM*<br/>
CAtlTransactionManager オブジェクトへのポインター。

### <a name="remarks"></a>Remarks

既定のコンス トラクターにファイルをアタッチできません、`CStdioFile`オブジェクト。 使用する必要がありますこのコンス トラクターを使用する場合、`CStdioFile::Open`にファイルを開くし、アタッチ先のメソッド、`CStdioFile`オブジェクト。

単一パラメーター コンス トラクターは、アタッチするためのファイルを開くストリーム、`CStdioFile`オブジェクト。 ポインター値に定義済みの入力/出力ファイル ポインターは、許可されている*stdin*、 *stdout*、または*stderr*します。

2 つのパラメーターのコンス トラクターを作成、`CStdioFile`オブジェクトし、指定されたパスに対応するファイルを開きます。

いずれかの場合は NULL を渡す場合*pOpenStream*または*場合*、コンス トラクターがスローされます、`CInvalidArgException*`します。

コンス トラクターがスローする場合は、ファイルを開けないか、作成、`CFileException*`します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#37](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_1.cpp)]

##  <a name="m_pstream"></a>  CStdioFile::m_pStream

`m_pStream`データ メンバーは、C ランタイム関数によって返される、開いているファイルへのポインターを`fopen`します。

```
FILE* m_pStream;
```

### <a name="remarks"></a>Remarks

ファイルが開かれていなかったかが閉じられている場合は NULL になります。

##  <a name="open"></a>  CStdioFile::Open

オーバーロードされます。 開くが、既定で使用するために設計された`CStdioFile`コンス トラクター。

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

*場合*<br/>
目的のファイルのパスを表す文字列。 相対パスまたは絶対パスができます。

*nOpenFlags*<br/>
共有とアクセス モード。 ファイルを開くときに実行するアクションを指定します。 ビットごとの OR を使用してオプションを組み合わせることができます (&#124;) 演算子。 1 つのアクセス許可と 1 つの共有オプションが必要です。modeCreate と modeNoInherit モードでは、省略可能です。

*pError*<br/>
失敗した操作の状態を受信する既存のファイルの例外オブジェクトへのポインター。

*pTM*<br/>
ポインターを`CAtlTransactionManager`オブジェクト。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>Remarks

##  <a name="readstring"></a>  CStdioFile::ReadString

上限まで、バッファーにテキスト データを読み取ります*nMax*に関連付けられているファイルから、-1 が文字、`CStdioFile`オブジェクト。

```
virtual LPTSTR ReadString(
    LPTSTR lpsz,
    UINT nMax);

virtual BOOL ReadString(CString& rString);
```

### <a name="parameters"></a>パラメーター

*lpsz*<br/>
Null で終わる文字列を受け取るユーザーが指定したバッファーへのポインターを指定します。

*nMax*<br/>
終端の null 文字をカウントせず、読み取る文字の最大数を指定します。

*rString*<br/>
参照を`CString`関数が戻るときに、文字列を格納するオブジェクト。

### <a name="return-value"></a>戻り値

テキスト データを格納しているバッファーへのポインター。 すべてのデータを読み取り中にファイルの終わりに達した場合は NULL です。または、データを読み込まずにブール型、FALSE の場合、ファイルの終わりに達した場合。

### <a name="remarks"></a>Remarks

最初の改行文字では、読み取りが停止します。 その場合より少ない場合、 *nMax*-1 文字が読み取られた、改行文字がバッファーに格納します。 いずれの場合も、null 文字 ('\0') が追加されます。

[:Read](../../mfc/reference/cfile-class.md#read)はテキスト モードの入力が復帰と改行のペアで終了しないにも使用できます。

> [!NOTE]
>  `CString`この関数のバージョンを削除、 `'\n'` LPTSTR バージョンは含みません。 存在する場合。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#38](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_2.cpp)]

##  <a name="seek"></a>  CStdioFile::Seek

以前に開かれたファイルでポインターを移動します。

```
virtual ULONGLONG Seek(
    LONGLONG lOff,
    UINT nFrom);
```

### <a name="parameters"></a>パラメーター

*lOff*<br/>
ポインターを移動するバイト数。

*nFrom*<br/>
ポインターの移動モード。 値は次のいずれかを指定する必要があります。

- `CFile::begin`: ファイル ポインターを移動する*lOff*ファイルの先頭からバイトを転送します。

- `CFile::current`: ファイル ポインターを移動する*lOff*ファイル内の現在位置からのバイト数。

- `CFile::end`: ファイル ポインターを移動する*lOff*ファイルの終端からのバイト。 なお*lOff*する必要がありますが負では、既存をシークするファイル; 正の値は、ファイルの末尾を越えたシークします。

### <a name="return-value"></a>戻り値

要求された位置が、有効な場合`Seek`ファイルの先頭から新しいバイト オフセットを返します。 それ以外の場合、戻り値は未定義と`CFileException`オブジェクトがスローされます。

### <a name="remarks"></a>Remarks

`Seek`関数を使用するランダム アクセス ファイルの内容をポインターを移動することによって、指定した時間、絶対的または相対的です。 データは、検索中に実際には読み込まれません。 要求された位置がファイルのサイズよりも大きい場合は、ファイルの長さは、その位置まで拡張して、例外はスローされません。

ファイルが開かれたときに、ファイル ポインターがオフセット 0 で、ファイルの先頭に配置されます。

この実装の`Seek`ランタイム ライブラリ (CRT) 関数に基づく`fseek`します。 使用法にいくつかの制限があります`Seek`テキスト モードで開かれたストリームにします。 詳細については、次を参照してください。 [fseek、_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)します。

### <a name="example"></a>例

次の例は、使用する方法を示します`Seek`の先頭から 1,000 バイトのポインターを移動する、`cfile`ファイル。 なお`Seek`後で呼び出す必要があるため、データを読み取らない[CStdioFile::ReadString](#readstring)データを読み取る。

[!code-cpp[NVC_MFCFiles#39](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_3.cpp)]

##  <a name="writestring"></a>  CStdioFile::WriteString

バッファーからデータに関連付けられているファイルに書き込みます、`CStdioFile`オブジェクト。

```
virtual void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>パラメーター

*lpsz*<br/>
Null で終わる文字列を格納しているバッファーへのポインターを指定します。

### <a name="remarks"></a>Remarks

終端の null 文字 ( `\0`) は、ファイルに書き込まれません。 このメソッドでは、改行文字を書き込みます*lpsz*キャリッジ リターンとライン フィードのペアとしてファイルにします。

Null で終わるファイルを使用するデータを書き込む場合`CStdioFile::Write`または[CFile::Write](../../mfc/reference/cfile-class.md#write)します。

このメソッドは、 `CInvalidArgException*` NULL を指定する場合、 *lpsz*パラメーター。

このメソッドは、`CFileException*`ファイル システム エラーに応答します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#40](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_4.cpp)]

## <a name="see-also"></a>関連項目

[CFile クラス](../../mfc/reference/cfile-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CFile クラス](../../mfc/reference/cfile-class.md)<br/>
[CFile::Duplicate](../../mfc/reference/cfile-class.md#duplicate)<br/>
[CFile::LockRange](../../mfc/reference/cfile-class.md#lockrange)<br/>
[CFile::UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)<br/>
[CNotSupportedException クラス](../../mfc/reference/cnotsupportedexception-class.md)
