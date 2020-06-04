---
title: CFileException クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 2d1025ca33d5641982ba52f1ac539db85df3bfd5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373893"
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
|[ファイル例外::Cファイル例外](#cfileexception)|`CFileException` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[例外を処理します。](#errnotoexception)|ランタイム エラー番号に対応する原因コードを返します。|
|[を指定します。](#geterrormessage)|例外を説明するメッセージを取得します。|
|[例外を処理します。](#oserrortoexception)|オペレーティング システムのエラー コードに対応する原因コードを返します。|
|[ファイル例外::スローエラーノ](#throwerrno)|ランタイム エラー番号に基づいてファイル例外をスローします。|
|[ファイル例外::スローオスエラー](#throwoserror)|オペレーティング システムのエラー番号に基づいてファイル例外をスローします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ファイル例外::m_cause](#m_cause)|例外の原因に対応する移植可能なコードが含まれています。|
|[ファイル例外::m_lOsError](#m_loserror)|関連するオペレーティング システムエラー番号が含まれます。|
|[ファイル例外::m_strFileName](#m_strfilename)|この例外のファイル名を格納します。|

## <a name="remarks"></a>解説

この`CFileException`クラスには、移植可能な原因コードとオペレーティング システム固有のエラー番号を保持するパブリック データ メンバーが含まれます。 また、このクラスには、ファイル例外をスローする静的メンバー関数や、オペレーティング システム エラーと C ランタイム エラーの両方の原因コードを返す静的メンバー関数も用意されています。

`CFileException`オブジェクトは、`CFile`メンバー関数および派生クラスのメンバー関数で構築およびスローされます。 CATCH**式の**スコープ内でこれらのオブジェクトにアクセスできます。 移植性のために、例外の理由を取得するには、原因コードのみを使用します。 例外の詳細については、「[例外処理 (MFC) 」](../../mfc/exception-handling-in-mfc.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CFileException`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="cfileexceptioncfileexception"></a><a name="cfileexception"></a>ファイル例外::Cファイル例外

`CFileException`原因コードとオペレーティング システム コードを格納するオブジェクトを構築します。

```
CFileException(
    int cause = CFileException::none,
    LONG lOsError = -1,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>パラメーター

*原因*<br/>
例外の理由を示す列挙型変数。 可能な値のリストについては[、CFileException::m_cause](#m_cause)を参照してください。

*エラー*<br/>
例外のオペレーティング システム固有の理由 (使用可能な場合)。 *lOsError*パラメーターは *、原因*よりも多くの情報を提供します。

*名前を変更します。*<br/>
例外の原因となっているオブジェクトの名前を`CFile`含む文字列へのアクセスをポイントします。

### <a name="remarks"></a>解説

このコンストラクターを直接使用するのではなく、グローバル関数[AfxThrowFileException](exception-processing.md#afxthrowfileexception)を呼び出してください。

> [!NOTE]
> 変数*lOsError*は`CFile`、`CStdioFile`オブジェクトにのみ適用されます。 この`CMemFile`エラー コードはクラスで処理されません。

## <a name="cfileexceptionerrnotoexception"></a><a name="errnotoexception"></a>例外を処理します。

指定されたランタイム ライブラリのエラー値を列挙されたエラー`CFileException`値に変換します。

```
static int PASCAL ErrnoToException(int nErrno);
```

### <a name="parameters"></a>パラメーター

*ネルノ*<br/>
実行時インクルード ファイル ERRNO で定義されている整数のエラー コード。H。

### <a name="return-value"></a>戻り値

指定されたランタイム ライブラリエラー値に対応する列挙値。

### <a name="remarks"></a>解説

可能な列挙値の一覧については[、「CFileException::m_cause」](#m_cause)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#26](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_1.cpp)]

## <a name="cfileexceptiongeterrormessage"></a><a name="geterrormessage"></a>を指定します。

例外を説明するテキストを取得します。

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT nMaxError,
    PUINT pnHelpContext = NULL) const;
```

### <a name="parameters"></a>パラメーター

*エラー*<br/>
[イン、アウト]エラー メッセージを受け取るバッファーへのポインター。

*エラー*<br/>
[in]指定されたバッファーが保持できる最大文字数。 これには、終端の NULL 文字が含まれます。

*コンテキスト*<br/>
[イン、アウト]ヘルプ コンテキスト ID を受け取る符号なし整数へのポインター。 の`NULL`場合、ID は返されません。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

指定されたバッファーが小さすぎる場合、エラー メッセージは切り捨てられます。

### <a name="example"></a>例

`CFileException::GetErrorMessage` の使用例を次に示します。

[!code-cpp[NVC_MFCExceptions#22](../../mfc/codesnippet/cpp/cfileexception-class_2.cpp)]

## <a name="cfileexceptionm_cause"></a><a name="m_cause"></a>ファイル例外::m_cause

`CFileException` 列挙型によって定義された値が含まれます。

```
int m_cause;
```

### <a name="remarks"></a>解説

このデータ メンバは、 **int**型のパブリック変数です。列挙子とその意味は次のとおりです。

- `CFileException::none`0: エラーは発生しません。

- `CFileException::genericException`1: 未指定のエラーが発生しました。

- `CFileException::fileNotFound`2: ファイルが見つかりませんでした。

- `CFileException::badPath`3: パスのすべてまたは一部が無効です。

- `CFileException::tooManyOpenFiles`4: 開いているファイルの数が制限されています。

- `CFileException::accessDenied`5: ファイルにアクセスできませんでした。

- `CFileException::invalidFile`6: 無効なファイル ハンドルを使用しようとしました。

- `CFileException::removeCurrentDir`7: 現在の作業ディレクトリを削除できません。

- `CFileException::directoryFull`8: ディレクトリエントリがなくなります。

- `CFileException::badSeek`9: ファイルポインタの設定中にエラーが発生しました。

- `CFileException::hardIO`10: ハードウェアエラーが発生しました。

- `CFileException::sharingViolation`11:共有します。EXE が読み込まれていないか、共有領域がロックされています。

- `CFileException::lockViolation`12: 既にロックされている領域をロックしようとしました。

- `CFileException::diskFull`14: ディスクがいっぱいです。

- `CFileException::endOfFile`15: ファイルの終わりに達しました。

    > [!NOTE]
    >  これらの `CFileException` 原因列挙子は、`CArchiveException` 原因列挙子とは異なります。

    > [!NOTE]
    > `CArchiveException::generic` は非推奨とされます。 代わりに `genericException` を使用してください **ジェネリック**がアプリケーションで使用され、/clr でビルドされた場合、結果として生じる構文エラーを解読するのは容易ではありません。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#30](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_3.cpp)]

## <a name="cfileexceptionm_loserror"></a><a name="m_loserror"></a>ファイル例外::m_lOsError

この例外のオペレーティング システム エラー コードが含まれています。

```
LONG m_lOsError;
```

### <a name="remarks"></a>解説

エラー コードのリストについては、オペレーティング システムのテクニカル マニュアルを参照してください。 このデータ メンバーは LONG 型のパブリック変数です。

## <a name="cfileexceptionm_strfilename"></a><a name="m_strfilename"></a>ファイル例外::m_strFileName

この例外条件のファイル名を格納します。

```
CString m_strFileName;
```

## <a name="cfileexceptionoserrortoexception"></a><a name="oserrortoexception"></a>例外を処理します。

指定された*lOsError*値に対応する列挙子を返します。 エラー コードが不明な場合、関数は`CFileException::generic`を返します。

```
static int PASCAL OsErrorToException(LONG lOsError);
```

### <a name="parameters"></a>パラメーター

*エラー*<br/>
オペレーティング システム固有のエラー コード。

### <a name="return-value"></a>戻り値

指定されたオペレーティング システムエラー値に対応する列挙値。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#27](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_4.cpp)]

## <a name="cfileexceptionthrowerrno"></a><a name="throwerrno"></a>ファイル例外::スローエラーノ

指定された`CFileException` *nErrno*値に対応するオブジェクトを構築し、例外をスローします。

```
static void PASCAL ThrowErrno(int nErrno, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>パラメーター

*ネルノ*<br/>
実行時インクルード ファイル ERRNO で定義されている整数のエラー コード。H。

*ファイル名*<br/>
例外の原因となったファイルの名前を含む文字列へのポインター (可能な場合)。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#28](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_5.cpp)]

## <a name="cfileexceptionthrowoserror"></a><a name="throwoserror"></a>ファイル例外::スローオスエラー

指定された`CFileException` *lOsError*値に対応する値をスローします。 エラー コードが不明な場合、関数`CFileException::generic`は .

```
static void PASCAL ThrowOsError(LONG lOsError, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>パラメーター

*エラー*<br/>
オペレーティング システム固有のエラー コード。

*ファイル名*<br/>
例外の原因となったファイルの名前を含む文字列へのポインター (可能な場合)。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#29](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_6.cpp)]

## <a name="see-also"></a>関連項目

[クラスの例外](../../mfc/reference/cexception-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[例外処理](../../mfc/reference/exception-processing.md)
