---
description: '詳細情報: CFileException クラス'
title: CFileException クラス
ms.date: 06/09/2020
f1_keywords:
- CFileException
- AFX/CFileException
- AFX/CFileException::CFileException
- AFX/CFileException::ErrnoToException
- AFX/CFileException::GetErrorMessage
- AFX/CFileException::OsErrorToException
- AFX/CFileException::ThrowErrno
- AFX/CFileException::ThrowOsError
- AFX/CFileException::m_cause
- AFX/CFileException::m_lOsError
- AFX/CFileException::m_strFileName
helpviewer_keywords:
- CFileException [MFC], CFileException
- CFileException [MFC], ErrnoToException
- CFileException [MFC], GetErrorMessage
- CFileException [MFC], OsErrorToException
- CFileException [MFC], ThrowErrno
- CFileException [MFC], ThrowOsError
- CFileException [MFC], m_cause
- CFileException [MFC], m_lOsError
- CFileException [MFC], m_strFileName
ms.assetid: f6491bb9-bfbc-42fd-a952-b33f9b62323f
ms.openlocfilehash: a7540ffb22005ef0fe93954396f6fca1a5ae93af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184518"
---
# <a name="cfileexception-class"></a>CFileException クラス

ファイルに関連した例外状態を表します。

## <a name="syntax"></a>構文

```
class CFileException : public CException
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CFileException:: CFileException](#cfileexception)|`CFileException` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CFileException:: ErrnoToException](#errnotoexception)|実行時エラー番号に対応する原因コードを返します。|
|[CFileException:: GetErrorMessage](#geterrormessage)|例外を説明するメッセージを取得します。|
|[CFileException:: OsErrorToException](#oserrortoexception)|オペレーティングシステムのエラーコードに対応する原因コードを返します。|
|[CFileException:: ThrowErrno](#throwerrno)|ランタイムエラー番号に基づいてファイル例外をスローします。|
|[CFileException:: ThrowOsError](#throwoserror)|オペレーティングシステムのエラー番号に基づいて、ファイル例外をスローします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CFileException:: m_cause](#m_cause)|例外の原因に対応する移植可能なコードが含まれています。|
|[CFileException:: m_lOsError](#m_loserror)|関連するオペレーティングシステムのエラー番号を格納します。|
|[CFileException:: m_strFileName](#m_strfilename)|この例外のファイルの名前を格納します。|

## <a name="remarks"></a>解説

クラスには、 `CFileException` 移植可能な原因コードとオペレーティングシステム固有のエラー番号を保持するパブリックデータメンバーが含まれています。 クラスには、ファイル例外をスローし、オペレーティングシステムエラーと C ランタイムエラーの両方の原因コードを返すための静的メンバー関数も用意されています。

`CFileException` オブジェクトは、 `CFile` メンバー関数および派生クラスのメンバー関数で構築およびスローされます。 これらのオブジェクトには、 **CATCH** 式のスコープ内でアクセスできます。 移植性を確保するには、例外の原因を取得するために原因コードだけを使用します。 例外の詳細については、「 [例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CFileException`

## <a name="requirements"></a>要件

**ヘッダー:** afx

## <a name="cfileexceptioncfileexception"></a><a name="cfileexception"></a> CFileException:: CFileException

オブジェクトの `CFileException` 原因コードとオペレーティングシステムコードを格納するオブジェクトを構築します。

```
CFileException(
    int cause = CFileException::none,
    LONG lOsError = -1,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>パラメーター

*cause*<br/>
例外の理由を示す列挙型変数。 使用可能な値の一覧については、「 [CFileException:: m_cause](#m_cause) 」を参照してください。

*lOsError*<br/>
例外のオペレーティングシステム固有の理由 (使用可能な場合)。 *LOsError* パラメーターは、の *原因* よりも詳細な情報を提供します。

*Lpszアーカイブ*<br/>
例外を発生させたオブジェクトの名前を含む文字列を指し `CFile` ます。

### <a name="remarks"></a>解説

このコンストラクターを直接使用するのではなく、グローバル関数 [AfxThrowFileException](exception-processing.md#afxthrowfileexception)を呼び出します。

> [!NOTE]
> 変数 *lOsError* は、オブジェクトおよびオブジェクトにのみ適用され `CFile` `CStdioFile` ます。 `CMemFile`クラスでは、このエラーコードは処理されません。

## <a name="cfileexceptionerrnotoexception"></a><a name="errnotoexception"></a> CFileException:: ErrnoToException

指定したランタイムライブラリのエラー値を、列挙された `CFileException` エラー値に変換します。

```
static int PASCAL ErrnoToException(int nErrno);
```

### <a name="parameters"></a>パラメーター

*nErrno*<br/>
実行時インクルードファイルに定義されているような整数エラーコード ERRNO. H.

### <a name="return-value"></a>戻り値

特定のランタイムライブラリエラー値に対応する列挙値。

### <a name="remarks"></a>解説

列挙可能な値の一覧については、「 [CFileException:: m_cause](#m_cause) 」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#26](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_1.cpp)]

## <a name="cfileexceptiongeterrormessage"></a><a name="geterrormessage"></a> CFileException:: GetErrorMessage

例外を説明するテキストを取得します。

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT nMaxError,
    PUINT pnHelpContext = NULL) const;
```

### <a name="parameters"></a>パラメーター

*lpszError*<br/>
[入力、出力]エラーメッセージを受信するバッファーへのポインター。

*nMaxError*<br/>
から指定したバッファーが保持できる最大文字数。 これには、終端の null 文字が含まれます。

*pnHelpContext*<br/>
[入力、出力]ヘルプコンテキスト ID を受け取る符号なし整数へのポインター。 `NULL`の場合、ID は返されません。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

指定されたバッファーが小さすぎる場合、エラーメッセージは切り捨てられます。

### <a name="example"></a>例

`CFileException::GetErrorMessage` の使用例を次に示します。

[!code-cpp[NVC_MFCExceptions#22](../../mfc/codesnippet/cpp/cfileexception-class_2.cpp)]

## <a name="cfileexceptionm_cause"></a><a name="m_cause"></a> CFileException:: m_cause

`CFileException` 列挙型によって定義された値が含まれます。

```
int m_cause;
```

### <a name="remarks"></a>解説

このデータメンバーは、型のパブリック変数です **`int`** 。 列挙子とその意味は次のとおりです。

| エラー | 値と意味 |
|--|--|
| `CFileException::none` |    0: エラーは発生しませんでした。 |
| `CFileException::genericException` |    1: 未指定のエラーが発生しました。 |
| `CFileException::fileNotFound` |    2: ファイルが見つかりませんでした。 |
| `CFileException::badPath` |    3: パスの一部またはすべてが無効です。 |
| `CFileException::tooManyOpenFiles` |    4: 開いているファイル数の制限を超えました。 |
| `CFileException::accessDenied` |    5: ファイルにアクセスできませんでした。 |
| `CFileException::invalidFile` |    6: 無効なファイル ハンドルを使用しようとしました。 |
| `CFileException::removeCurrentDir` |    7: 現在の作業ディレクトリは削除できません。 |
| `CFileException::directoryFull` |    8: ディレクトリ エントリがこれ以上ありません。 |
| `CFileException::badSeek` |    9: ファイル ポインターを設定しようとしてエラーが発生しました。 |
| `CFileException::hardIO` |    10: ハードウェア エラーが発生しました。 |
| `CFileException::sharingViolation` |    11: SHARE.EXE が読み込まれなかったか、共有領域がロックされました。 |
| `CFileException::lockViolation` |    12: 既にロックされている領域をロックしようとしました。 |
| `CFileException::diskFull` | 13: ディスクがいっぱいです。 |
| `CFileException::endOfFile` | 14: ファイルの終わりに達しました。 |

> [!NOTE]
> これらの `CFileException` 原因列挙子は、`CArchiveException` 原因列挙子とは異なります。

> [!NOTE]
> `CArchiveException::generic` は非推奨とされます。 代わりに、`genericException` を使用してください。 **Generic** をアプリケーションで使用し、/clr を使用してビルドした場合、結果の構文エラーは解読が容易ではありません。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#30](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_3.cpp)]

## <a name="cfileexceptionm_loserror"></a><a name="m_loserror"></a> CFileException:: m_lOsError

この例外のオペレーティングシステムエラーコードを格納します。

```
LONG m_lOsError;
```

### <a name="remarks"></a>解説

エラーコードの一覧については、オペレーティングシステムの技術マニュアルを参照してください。 このデータメンバーは LONG 型のパブリック変数です。

## <a name="cfileexceptionm_strfilename"></a><a name="m_strfilename"></a> CFileException:: m_strFileName

この例外条件のファイルの名前を格納します。

```
CString m_strFileName;
```

## <a name="cfileexceptionoserrortoexception"></a><a name="oserrortoexception"></a> CFileException:: OsErrorToException

指定された *lOsError* 値に対応する列挙子を返します。 エラーコードが不明の場合、関数はを返し `CFileException::generic` ます。

```
static int PASCAL OsErrorToException(LONG lOsError);
```

### <a name="parameters"></a>パラメーター

*lOsError*<br/>
オペレーティングシステム固有のエラーコード。

### <a name="return-value"></a>戻り値

指定されたオペレーティングシステムエラー値に対応する列挙値。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#27](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_4.cpp)]

## <a name="cfileexceptionthrowerrno"></a><a name="throwerrno"></a> CFileException:: ThrowErrno

`CFileException`指定された *nerrno* 値に対応するオブジェクトを構築し、例外をスローします。

```
static void PASCAL ThrowErrno(int nErrno, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>パラメーター

*nErrno*<br/>
実行時インクルードファイルに定義されているような整数エラーコード ERRNO. H.

*lpszFileName*<br/>
例外の原因となったファイルの名前を格納している文字列へのポインター (存在する場合)。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#28](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_5.cpp)]

## <a name="cfileexceptionthrowoserror"></a><a name="throwoserror"></a> CFileException:: ThrowOsError

`CFileException`指定された *lOsError* 値に対応するをスローします。 エラーコードが不明の場合、関数はとしてコード化された例外をスローし `CFileException::generic` ます。

```
static void PASCAL ThrowOsError(LONG lOsError, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>パラメーター

*lOsError*<br/>
オペレーティングシステム固有のエラーコード。

*lpszFileName*<br/>
例外の原因となったファイルの名前を格納している文字列へのポインター (存在する場合)。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#29](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_6.cpp)]

## <a name="see-also"></a>関連項目

[CException クラス](../../mfc/reference/cexception-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[例外処理](../../mfc/reference/exception-processing.md)
