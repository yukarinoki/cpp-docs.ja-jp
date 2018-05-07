---
title: CFileException クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f94d6fc19879da1dd1dcaa94ab7a177fb86d5186
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
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
|[CFileException::CFileException](#cfileexception)|`CFileException` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFileException::ErrnoToException](#errnotoexception)|原因、実行時のエラー番号に対応するコードを返します。|  
|[CFileException::GetErrorMessage](#geterrormessage)|例外を説明するメッセージを取得します。|  
|[CFileException::OsErrorToException](#oserrortoexception)|オペレーティング システム エラー コードに対応する原因のコードを返します。|  
|[CFileException::ThrowErrno](#throwerrno)|ランタイム エラー番号に基づいたファイルの例外をスローします。|  
|[CFileException::ThrowOsError](#throwoserror)|オペレーティング システム エラー番号に基づくファイルの例外をスローします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[については、「](#m_cause)|例外の原因に対応するコード移植性にはが含まれています。|  
|[CFileException::m_lOsError](#m_loserror)|関連するオペレーティング システム エラー番号が含まれています。|  
|[CFileException::m_strFileName](#m_strfilename)|この例外のファイルの名前が含まれています。|  
  
## <a name="remarks"></a>コメント  
 `CFileException`クラスには、移植性の原因のコードとオペレーティング システム固有のエラー番号を保持するパブリック データ メンバーが含まれています。 クラスは、ファイルの例外をスローして、オペレーティング システム エラーと C ランタイム エラーの原因のコードを返すためにも静的メンバー関数を提供します。  
  
 `CFileException` オブジェクトが構築されでスロー`CFile`メンバー関数、派生クラスのメンバー関数でします。 これらのオブジェクトのスコープ内にアクセスすることができます、**キャッチ**式。 移植性のため、原因コードのみを使用して、例外の理由を取得します。 例外の詳細については、記事を参照してください。[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CFileException`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="cfileexception"></a>  CFileException::CFileException  
 構築、`CFileException`オブジェクトで原因コードとオペレーティング システムのコードを格納するオブジェクト。  
  
```  
CFileException(
    int cause = CFileException::none,  
    LONG lOsError = -1,  
    LPCTSTR lpszArchiveName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cause`  
 例外の理由を示す列挙型の変数です。 参照してください[については、「](#m_cause)有効な値の一覧についてはします。  
  
 `lOsError`  
 使用可能な場合は、例外のオペレーティング システム固有理由です。 `lOsError`パラメーターより多くの情報を提供`cause`はします。  
  
 `lpszArchiveName`  
 名前を含む文字列を指す、`CFile`例外の原因とします。  
  
### <a name="remarks"></a>コメント  
 このコンス トラクターを直接使用しないでくださいではなくグローバル関数を呼び出すことは[AfxThrowFileException](exception-processing.md#afxthrowfileexception)です。  
  
> [!NOTE]
>  変数`lOsError`にのみ適用されます`CFile`と`CStdioFile`オブジェクト。 `CMemFile`クラスは、このエラー コードを処理しません。  
  
##  <a name="errnotoexception"></a>  CFileException::ErrnoToException  
 特定のランタイム ライブラリのエラー値を変換、`CFileException`エラー値を列挙します。  
  
```  
static int PASCAL ErrnoToException(int nErrno);
```  
  
### <a name="parameters"></a>パラメーター  
 `nErrno`  
 整数エラー コード、実行時のインクルード ファイル ERRNO で定義されています。H.  
  
### <a name="return-value"></a>戻り値  
 特定のランタイム ライブラリのエラー値に対応する列挙値。  
  
### <a name="remarks"></a>コメント  
 参照してください[については、「](#m_cause) 、候補のリストの値を列挙します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#26](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_1.cpp)]  
  
##  <a name="geterrormessage"></a>  CFileException::GetErrorMessage  
 例外を説明するテキストを取得します。  
  
```  
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,  
    UINT nMaxError,  
    PUINT pnHelpContext = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `lpszError`  
 エラー メッセージを受け取るバッファーへのポインター。  
  
 [入力] `nMaxError`  
 指定されたバッファーが保持できる文字の最大数。 これには、終端の null 文字が含まれます。  
  
 [入力、出力] `pnHelpContext`  
 ヘルプ コンテキスト ID を受信する符号なし整数へのポインター 場合`NULL`ID は返されません。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功した場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 指定されたバッファーが小さすぎる場合、エラー メッセージは切り捨てられます。  
  
### <a name="example"></a>例  
 次の例で`CFileException::GetErrorMessage`です。  
  
 [!code-cpp[NVC_MFCExceptions#22](../../mfc/codesnippet/cpp/cfileexception-class_2.cpp)]  
  
##  <a name="m_cause"></a>  については、「  
 `CFileException` 列挙型によって定義された値が含まれます。  
  
```  
int m_cause;  
```  
  
### <a name="remarks"></a>コメント  
 このデータ メンバーは `int` 型のパブリック変数です。 列挙子とその意味は次のとおりです。  
  
- `CFileException::none` 0: エラーが発生していません。  
  
- `CFileException::genericException` 1: 未指定のエラーが発生しました。  
  
- `CFileException::fileNotFound` 2: ファイルが見つかりませんでした。  
  
- `CFileException::badPath` 3: パスの全部または一部が無効です。  
  
- `CFileException::tooManyOpenFiles` 4: 開いているファイルの許容回数を超えました。  
  
- `CFileException::accessDenied` 5: ファイルにアクセスできませんでした。  
  
- `CFileException::invalidFile` 6: 無効なファイル ハンドルを使用するが試行されました。  
  
- `CFileException::removeCurrentDir` 7: 現在の作業ディレクトリを削除することはできません。  
  
- `CFileException::directoryFull` 8: 複数のディレクトリ エントリはありません。  
  
- `CFileException::badSeek` 9: ファイル ポインターを設定しようとしてエラーが発生しました。  
  
- `CFileException::hardIO` 10: ハードウェア エラーが発生しました。  
  
- `CFileException::sharingViolation` 11: 共有します。EXE が読み込まれていない、または共有領域がロックされました。  
  
- `CFileException::lockViolation` 12: 既にロックされている領域をロックしようとしましたがあります。  
  
- `CFileException::diskFull` 14: ディスクがいっぱいです。  
  
- `CFileException::endOfFile` 15: ファイルの終わりに達しました。  
  
    > [!NOTE]
    >  これらの `CFileException` 原因列挙子は、`CArchiveException` 原因列挙子とは異なります。  
  
    > [!NOTE]
    > `CArchiveException::generic` は使用されなくなりました。 代わりに、`genericException` を使用してください。 `generic` をアプリケーションで使用して /clr でビルドした場合、発生した構文エラーを解読するのは困難です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#30](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_3.cpp)]  
  
##  <a name="m_loserror"></a>  CFileException::m_lOsError  
 この例外のオペレーティング システム エラー コードが含まれています。  
  
```  
LONG m_lOsError;  
```  
  
### <a name="remarks"></a>コメント  
 エラー コードの一覧については、オペレーティング システムの技術的なマニュアルを参照してください。 このデータ メンバーは型のパブリック変数**長い**です。  
  
##  <a name="m_strfilename"></a>  CFileException::m_strFileName  
 この例外条件については、ファイルの名前が含まれています。  
  
```  
CString m_strFileName;  
```  
  
##  <a name="oserrortoexception"></a>  CFileException::OsErrorToException  
 対応する列挙子を返します、指定された`lOsError`値。 かどうかはエラー コードは不明で、この関数を返します**定義**です。  
  
```  
static int PASCAL OsErrorToException(LONG lOsError);
```  
  
### <a name="parameters"></a>パラメーター  
 `lOsError`  
 オペレーティング システム固有のエラー コード。  
  
### <a name="return-value"></a>戻り値  
 指定したオペレーティング システムのエラー値に対応する列挙値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#27](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_4.cpp)]  
  
##  <a name="throwerrno"></a>  CFileException::ThrowErrno  
 構築、`CFileException`オブジェクトに対応する、指定された`nErrno`値、その例外をスローします。  
  
```  
static void PASCAL ThrowErrno(int nErrno, LPCTSTR lpszFileName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nErrno`  
 整数エラー コード、実行時のインクルード ファイル ERRNO で定義されています。H.  
  
 `lpszFileName`  
 ファイルの名前を含む文字列へのポインターの原因となった例外は、使用可能な場合です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#28](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_5.cpp)]  
  
##  <a name="throwoserror"></a>  CFileException::ThrowOsError  
 スロー、`CFileException`に対応する、指定された`lOsError`値。 エラー コードは、不明なかどうかは、関数としてコード化された例外をスローする**定義**です。  
  
```  
static void PASCAL ThrowOsError(LONG lOsError, LPCTSTR lpszFileName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lOsError`  
 オペレーティング システム固有のエラー コード。  
  
 `lpszFileName`  
 ファイルの名前を含む文字列へのポインターの原因となった例外は、使用可能な場合です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#29](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_6.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [例外処理](../../mfc/reference/exception-processing.md)



