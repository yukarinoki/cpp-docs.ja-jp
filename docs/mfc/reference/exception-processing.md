---
title: 例外処理
ms.date: 11/04/2016
helpviewer_keywords:
- macros [MFC], exception handling
- DAO (Data Access Objects), exceptions [MFC]
- OLE exceptions [MFC], MFC functions
- exceptions [MFC], processing
- exception macros [MFC]
- termination functions, MFC
- MFC, exceptions
- exceptions [MFC], MFC throwing functions
ms.assetid: 26d4457c-8350-48f5-916e-78f919787c30
ms.openlocfilehash: e1d70505013553e27130d9d9042b0c8e5c074ab5
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65612212"
---
# <a name="exception-processing"></a>例外処理

プログラムが実行されると、さまざまな異常な状態と「例外」というエラーが発生します。 これらには、メモリ、リソース割り当てのエラー、およびファイルを検索する障害の不足が含まれます。

Microsoft Foundation Class ライブラリでは、いずれかの C++ 用 ANSI 標準委員会によって提案された後に密接にモデル化例外処理パターンを使用します。 異常状態に陥る可能性があります関数を呼び出す前に、この例外ハンドラーを設定する必要があります。 関数には、異常な条件が発生すると、例外がスローし、例外ハンドラーに制御が渡されます。

Microsoft Foundation Class ライブラリに含まれているいくつかのマクロは、例外ハンドラーを設定します。 多数の他のグローバル関数は、必要な場合に、特殊な例外をスローして、プログラムを終了するのに役立ちます。 これらのマクロとグローバル関数は、次のカテゴリに分類されます。

- 例外処理マクロは、例外ハンドラーを構成します。

- 関数を Exception-throwing)、特定の種類の例外を生成します。

- 終了関数には、プログラムの終了が発生します。

例と詳細については、[例外処理](../../mfc/exception-handling-in-mfc.md) を参照してください。
 
### <a name="exception-macros"></a>例外処理マクロ

|||
|-|-|
|[TRY](#try)|例外の処理のコードのブロックを指定します。|
|[CATCH](#catch)|上記からの例外をキャッチするためのコードのブロックを指定**TRY**ブロックします。|
|[CATCH_ALL](#catch_all)|上記からのすべての例外をキャッチするためのコードのブロックを指定**TRY**ブロックします。|
|[AND_CATCH](#and_catch)|上記から追加の例外の種類をキャッチするためのコードのブロックを指定**TRY**ブロックします。|
|[AND_CATCH_ALL](#and_catch_all)|他のすべての直前に追加の例外の種類をキャッチするためのコードのブロックを指定**TRY**ブロックします。|
|[END_CATCH](#end_catch)|最後の終了**CATCH**または**AND_CATCH**コード ブロックです。|
|[END_CATCH_ALL](#end_catch_all)|最後の終了**CATCH_ALL**コード ブロックです。|
|[THROW](#throw)|指定した例外をスローします。|
|[THROW_LAST](#throw_last)|[次へ] の外側のハンドラーを現在処理されている例外をスローします。|

### <a name="exception-throwing-functions"></a>例外スロー関数

|||
|-|-|
|[AfxThrowArchiveException](#afxthrowarchiveexception)|アーカイブの例外をスローします。|
|[AfxThrowFileException](#afxthrowfileexception)|ファイルの例外をスローします。|
|[AfxThrowInvalidArgException](#afxthrowinvalidargexception)|無効な引数の例外をスローします。|
|[AfxThrowMemoryException](#afxthrowmemoryexception)|メモリ不足の例外をスローします。|
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|サポートされていない例外をスローします。|
|[AfxThrowResourceException](#afxthrowresourceexception)|Windows リソースが見つからないの例外をスローします。|
|[AfxThrowUserException](#afxthrowuserexception)|プログラムのユーザーが開始したアクションでは、例外をスローします。|

MFC には、OLE の例外を具体的には 2 つの例外のスロー関数が用意されています。

### <a name="ole-exception-functions"></a>OLE 例外関数

|||
|-|-|
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|OLE オートメーション関数内で例外をスローします。|
|[AfxThrowOleException](#afxthrowoleexception)|OLE 例外をスローします。|

データベース クラスが 2 つの例外クラスを提供するデータベースの例外をサポートする`CDBException`と`CDaoException`、および例外の種類をサポートするためにグローバル関数。

### <a name="dao-exception-functions"></a>DAO 例外関数

|||
|-|-|
|[AfxThrowDAOException](#afxthrowdaoexception)|スローされます、 [CDaoException](../../mfc/reference/cdaoexception-class.md)独自のコードから。|
|[AfxThrowDBException](#afxthrowdbexception)|スローされます、 [CDBException](../../mfc/reference/cdbexception-class.md)独自のコードから。|

MFC には、次の終了関数が用意されています。

### <a name="termination-functions"></a>終了関数

|||
|-|-|
|[AfxAbort](#afxabort)|呼ばれるときに致命的なエラーは、アプリケーションを終了に発生します。|

##  <a name="try"></a>  TRY

設定、**TRY**ブロックします。

```
TRY
```

### <a name="remarks"></a>Remarks

**TRY**ブロックが例外をスローするコードのブロックを識別します。 これらの例外は、次に**CATCH**と**AND_CATCH**ブロックします。 再帰が許可されている: 例外が外部に渡される**TRY**を無視するか、THROW_LAST マクロを使用して、ブロック。 終了、**TRY**END_CATCH または END_CATCH_ALL マクロを使用してブロックします。

詳細については、[例外処理](../../mfc/exception-handling-in-mfc.md)を参照してください。

### <a name="example"></a>例

例をご覧ください[キャッチ](#catch)します。

### <a name="requirements"></a>必要条件

ヘッダー: afx.h

##  <a name="catch"></a>  CATCH

最初に、上記でスローされた例外の種類をキャッチするコードのブロックを定義します**TRY**ブロックします。

```
CATCH(exception_class, exception_object_pointer_name)
```

### <a name="parameters"></a>パラメーター

*exception_class*<br/>
テストする例外の種類を指定します。 標準の例外クラスの一覧は、クラスを参照してください。 [CException](../../mfc/reference/cexception-class.md)します。

*exception_object_pointer_name*<br/>
マクロによって作成される例外オブジェクト ポインターの名前を指定します。 内の例外オブジェクトにアクセスするポインターの名前を使用することができます、**CATCH**ブロックします。 この変数が宣言されています。

### <a name="remarks"></a>Remarks

例外処理コードは、必要に応じて、例外の原因を特定に関する詳細を取得する場合、例外オブジェクトを問い合わせることができます。 次のフレームの外側の例外処理をシフトする THROW_LAST マクロを呼び出します。 終了、**TRY**END_CATCH マクロを使用してブロックします。

場合*exception_class*クラス`CException`、すべての例外の種類をキャッチし、します。 使用することができます、[CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)メンバー関数を決定する特定の例外がスローされました。 シーケンシャルを使用する、いくつかの種類の例外をキャッチするには、 **AND_CATCH**ステートメントでは、それぞれ別の例外型を持つ。

例外オブジェクトへのポインターがマクロによって作成されます。 自分で宣言する必要はありません。

> [!NOTE]
>  **CATCH**ブロックは、中かっこで囲まれたC ++スコープとして定義されます。 このスコープで変数を宣言すると、そのスコープ内でのみアクセスできます。 これにも当てはまります*exception_object_pointer_name*にも適用されます。

例外とキャッチのマクロの詳細については、[例外処理](../../mfc/exception-handling-in-mfc.md)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCExceptions#26](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]

##  <a name="catch_all"></a>  CATCH_ALL

上記でスローされたすべての例外の種類をキャッチするコードのブロックを定義します**TRY**ブロックします。

```
CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>パラメーター

*exception_object_pointer_name*<br/>
マクロによって作成される例外オブジェクト ポインターの名前を指定します。 内の例外オブジェクトにアクセスするポインターの名前を使用することができます、`CATCH_ALL`ブロックします。 この変数が宣言されています。

### <a name="remarks"></a>Remarks

例外処理コードは、必要に応じて、例外の原因を特定に関する詳細を取得する場合、例外オブジェクトを問い合わせることができます。 呼び出す、`THROW_LAST`マクロは次のフレームの外側の例外処理をシフトします。 使用する場合**CATCH_ALL**、終了、**TRY**END_CATCH_ALL マクロを使用してブロックします。

> [!NOTE]
>  **AND_CATCH_ALL**ブロックは、C++スコープとして定義されます（中かっこで囲まれています）。 このスコープで変数を宣言する場合、そのスコープ内でのみアクセス可能であることに注意してください。

例外の詳細については、[例外処理](../../mfc/exception-handling-in-mfc.md) を参照してください。。

### <a name="example"></a>例

例をご覧ください[解放](../../mfc/reference/cfile-class.md#abort)します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

##  <a name="and_catch"></a>  AND_CATCH

直前に追加の例外の種類をキャッチするためのコードのブロックを定義します**TRY**ブロックします。

```
AND_CATCH(exception_class, exception_object_pointer_name)
```

### <a name="parameters"></a>パラメーター

*exception_class*<br/>
テストする例外の種類を指定します。 標準の例外クラスの一覧は、クラスを参照してください。 [CException](../../mfc/reference/cexception-class.md)します。

*exception_object_pointer_name*<br/>
マクロによって作成される例外オブジェクトのポインターの名前。 内の例外オブジェクトにアクセスするポインターの名前を使用することができます、 **AND_CATCH**ブロックします。 この変数が宣言されています。

### <a name="remarks"></a>Remarks

CATCH マクロの 1 つの例外タイプをキャッチする AND_CATCH マクロを使用します。 終了、**TRY**END_CATCH マクロを使用してブロックします。

例外処理コードは、必要に応じて、例外の原因を特定に関する詳細を取得する場合、例外オブジェクトを問い合わせることができます。 内で THROW_LAST マクロを呼び出し、 **AND_CATCH** shift キーを押し、次のフレームの外側の例外を処理するブロックします。 **AND_CATCH** 、上記の終了をマーク**CATCH**または**AND_CATCH**ブロックします。

> [!NOTE]
>  **AND_CATCH**ブロックは、C++として定義されます（中かっこで区切られます）。 このスコープで変数を宣言する場合、そのスコープ内でのみアクセス可能であることに注意してください。 これは*exception_object_pointer_name*変数にも適用されます。

### <a name="example"></a>例

例をご覧ください[キャッチ](#catch)します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h
##  <a name="and_catch_all"></a>  AND_CATCH_ALL

直前に追加の例外の種類をキャッチするためのコードのブロックを定義します**TRY**ブロックします。

```
AND_CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>パラメーター

*exception_object_pointer_name*<br/>
マクロによって作成される例外オブジェクトのポインターの名前。 内の例外オブジェクトにアクセスするポインターの名前を使用することができます、 **AND_CATCH_ALL**ブロックします。 この変数が宣言されています。

### <a name="remarks"></a>Remarks

使用して、**CATCH**マクロを 1 つの例外の種類をキャッチし、AND_CATCH_ALL マクロの他のすべての後続の種類をキャッチします。 AND_CATCH_ALL を使用する場合は、終了、**TRY**END_CATCH_ALL マクロを使用してブロックします。

例外処理コードは、必要に応じて、例外の原因を特定に関する詳細を取得する場合、例外オブジェクトを問い合わせることができます。 内で THROW_LAST マクロを呼び出し、 **AND_CATCH_ALL** shift キーを押し、次のフレームの外側の例外を処理するブロックします。 **AND_CATCH_ALL** 、上記の終了をマーク**CATCH**または**AND_CATCH_ALL**ブロックします。

> [!NOTE]
>  **AND_CATCH_ALL**としてブロックが定義されている、C++スコープ (中かっこで区切られています)。 このスコープで変数を宣言する場合は、そのスコープ内でのみアクセスされることに注意してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

##  <a name="end_catch"></a>  END_CATCH

最後の終了をマーク**CATCH**または**AND_CATCH**ブロックします。

```
END_CATCH
```

### <a name="remarks"></a>Remarks

END_CATCH マクロの詳細については、[例外処理](../../mfc/exception-handling-in-mfc.md) を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

##  <a name="end_catch_all"></a>  END_CATCH_ALL

最後の終了をマーク**CATCH_ALL88** または **AND_CATCH_ALL**ブロックします。

```
END_CATCH_ALL
```

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

##  <a name="throw"></a>  THROW (MFC)

指定した例外をスローします。

```
THROW(exception_object_pointer)
```

### <a name="parameters"></a>パラメーター

*exception_object_pointer*<br/>
派生した例外オブジェクトへのポイント`CException`します。

### <a name="remarks"></a>Remarks

**スロー**プログラムに関連付けられているコントロールを渡して、実行に割り込みます**CATCH**でプログラムをブロックします。 提供されていない場合、**CATCH**ブロック、エラーが出力メッセージを終了する Microsoft Foundation Class ライブラリ モジュールに制御が渡されます。

詳細については、[例外処理](../../mfc/exception-handling-in-mfc.md)を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

##  <a name="throw_last"></a>  THROW_LAST

次に戻り、例外をスロー外部**CATCH**ブロックします。

```
THROW_LAST()
```

### <a name="remarks"></a>Remarks

このマクロを使用すると、ローカルで作成された例外をスローすることができます。 キャッチした例外をスローしようとする場合は、通常はスコープ外に移動され、削除されます。 **THROW_LAST**、[次へ] を正常に渡された例外**CATCH**ハンドラー。

詳細については、[例外処理](../../mfc/exception-handling-in-mfc.md) を参照してください。

### <a name="example"></a>例

[CFile::Abort](../../mfc/reference/cfile-class.md#abort) の例を参照してください。。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

##  <a name="afxthrowarchiveexception"></a>  AfxThrowArchiveException

アーカイブの例外をスローします。

```
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName);
```

### <a name="parameters"></a>パラメーター

*cause*<br/>
例外の原因を示す整数を指定します。 使用可能な値については、次を参照してください。 [CArchiveException::m_cause](../../mfc/reference/carchiveexception-class.md#m_cause)します。

*lpszArchiveName*<br/>
名前を含む文字列の指す、 `CArchive` (該当する場合)、例外の原因となったオブジェクト。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

##  <a name="afxthrowfileexception"></a>  AfxThrowFileException

ファイルの例外をスローします。

```
void AfxThrowFileException(
    int cause,
    LONG lOsError = -1,
    LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>パラメーター

*cause*<br/>
例外の原因を示す整数を指定します。 使用可能な値については、[CFileException::m_cause](../../mfc/reference/cfileexception-class.md#m_cause)を参照してください。

*lOsError*<br/>
オペレーティング システムのエラー番号が含まれています (ある場合)、例外の原因を示します。 エラー コードの一覧については、オペレーティング システムのマニュアルを参照してください。

*lpszFileName*<br/>
(該当する場合)、例外の原因となったファイルの名前を含む文字列を指します。

### <a name="remarks"></a>Remarks

オペレーティング システム エラー コードに基づいて、原因を判断するためにあります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

## <a name="afxthrowinvalidargexception"></a>  AfxThrowInvalidArgException

無効な引数の例外をスローします。

### <a name="syntax"></a>構文

```
void AfxThrowInvalidArgException( );
```

### <a name="remarks"></a>Remarks

無効な引数を使用する場合は、この関数が呼び出されます。

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

##  <a name="afxthrowmemoryexception"></a>  AfxThrowMemoryException

メモリ不足の例外をスローします。

```
void AfxThrowMemoryException();
```

### <a name="remarks"></a>Remarks

場合、この関数を呼び出す基になるシステム メモリ アロケーターの呼び出し (など**malloc**と[GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc) Windows 関数) は失敗します。 呼び出す必要はありません**new**ため**new**メモリの割り当てが失敗した場合に自動的にメモリ不足例外がスローされます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

##  <a name="afxthrownotsupportedexception"></a>  AfxThrowNotSupportedException

サポートされていない機能の要求の結果である例外をスローします。

```
void AfxThrowNotSupportedException();
```

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

##  <a name="afxthrowresourceexception"></a>  AfxThrowResourceException

リソースの例外をスローします。

```
void  AfxThrowResourceException();
```

### <a name="remarks"></a>Remarks

Windows のリソースを読み込むことができないときに、この関数は通常呼び出されます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

##  <a name="afxthrowuserexception"></a>  AfxThrowUserException

エンドユーザーの操作を停止する例外をスローします。

```
void AfxThrowUserException();
```

### <a name="remarks"></a>Remarks

この関数は、直後後に呼び出される通常`AfxMessageBox`ユーザーにエラーが報告されます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

##  <a name="afxthrowoledispatchexception"></a>  AfxThrowOleDispatchException

OLE オートメーション関数内で例外をスローするのにには、この関数を使用します。

```
void AFXAPI AfxThrowOleDispatchException(
    WORD wCode ,
    LPCSTR lpszDescription,
    UINT nHelpID = 0);

void AFXAPI AfxThrowOleDispatchException(
    WORD wCode,
    UINT nDescriptionID,
    UINT nHelpID = -1);
```

### <a name="parameters"></a>パラメーター

*WCode*<br/>
アプリケーションに固有のエラー コード。

*lpszDescription*<br/>
エラーの口頭で説明します。

*nDescriptionID*<br/>
文章によるエラーの説明のリソース ID。

*nHelpID*<br/>
アプリケーションのヘルプのヘルプ コンテキスト (します。HLP) ファイルです。

### <a name="remarks"></a>Remarks

この関数に提供される情報は、運転のアプリケーション (Microsoft Visual Basic または別の OLE オートメーション クライアント アプリケーション) で表示できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCExceptions#25](../../mfc/codesnippet/cpp/exception-processing_2.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

##  <a name="afxthrowoleexception"></a>  AfxThrowOleException

型のオブジェクトを作成します。 `COleException` 、例外をスローします。

```
void AFXAPI AfxThrowOleException(SCODE sc);
void AFXAPI AfxThrowOleException(HRESULT hr);
```

### <a name="parameters"></a>パラメーター

*sc*<br/>
例外の理由を示す OLE のステータス コード。

*hr*<br/>
例外の理由を示す結果コードへのハンドルします。

### <a name="remarks"></a>Remarks

引数として HRESULT を受け取るバージョンでは、その結果コードを対応する SCODE に変換します。 HRESULT と SCODE の詳細については、次を参照してください。 [COM エラー コードの構造](/windows/desktop/com/structure-of-com-error-codes)Windows SDK に含まれています。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

##  <a name="afxthrowdaoexception"></a>  AfxThrowDaoException

型の例外をスローするには、この関数を呼び出す[CDaoException](../../mfc/reference/cdaoexception-class.md)独自のコードから。

```
void AFXAPI AfxThrowDaoException(
    int nAfxDaoError = NO_AFX_DAO_ERROR,
    SCODE scode = S_OK);
```

### <a name="parameters"></a>パラメーター

*nAfxDaoError*<br/>
DAO の拡張エラー コードを表す整数値、することができます、値の 1 つ下に表示されます[CDaoException::m_nAfxDaoError](../../mfc/reference/cdaoexception-class.md#m_nafxdaoerror)します。

*scode*<br/>
DAO、SCODE 型から OLE エラー コード。 詳しくは、次を参照してください。 [CDaoException::m_scode](../../mfc/reference/cdaoexception-class.md#m_scode)します。

### <a name="remarks"></a>Remarks

フレームワークも呼び出します`AfxThrowDaoException`します。 呼び出しでは、パラメーターのいずれかまたは両方を渡すことができます。 たとえばのいずれかが発生する場合、エラーで定義されている**CDaoException::nAfxDaoError**についてもかまわないが、 *scode*パラメーターで有効なコードを渡す、 *nAfxDaoError*パラメーターの既定値をそのまま使用し、 *scode*します。

MFC DAO クラスに関連する例外については、クラスを参照してください。`CDaoException`この書籍と記事[例外:データベース例外](../../mfc/exceptions-database-exceptions.md)します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdb.h

##  <a name="afxthrowdbexception"></a>  AfxThrowDBException

型の例外をスローするには、この関数を呼び出す`CDBException`独自のコードから。

```
void AfxThrowDBException(
    RETCODE nRetCode,
    CDatabase* pdb,
    HSTMT hstmt);
```

### <a name="parameters"></a>パラメーター

*nRetCode*<br/>
RETCODE がスローされる例外の原因となったエラーの種類を定義する型の値。

*pdb*<br/>
ポインター、`CDatabase`例外が関連付けられているデータ ソース接続を表すオブジェクト。

*hstmt*<br/>
例外が関連付けられているステートメント ハンドルを指定する ODBC HSTMT ハンドル。

### <a name="remarks"></a>Remarks

Framework 呼び出し`AfxThrowDBException`ときに、ODBC API 関数の呼び出しから、ODBC RETCODE を受信し、expectable エラーではなく、例外的な条件として、RETCODE を解釈します。 たとえば、データ アクセス操作が失敗するディスクの読み取りエラーが原因です。

ODBC で定義された RETCODE 値については、Windows SDK の第 8 章「を取得する状態とエラー情報」を参照してください。 これらのコードを MFC の拡張機能については、クラスを参照してください。 [CDBException](../../mfc/reference/cdbexception-class.md)します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

##  <a name="afxabort"></a>  AfxAbort

MFC によって提供される既定の終了関数。

```
void  AfxAbort();
```

### <a name="remarks"></a>Remarks

`AfxAbort` 内部的に呼び出されます MFC メンバー関数によってキャッチされない例外は処理できないなどの致命的なエラーがある場合。 呼び出すことができます`AfxAbort`回復することはできません、致命的なエラーが発生した場合は、まれなケースです。

### <a name="example"></a>例

[CATCH](#catch) の例を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)<br/>
[CException クラス](cexception-class.md)<br/>
[CInvalidArgException クラス](cinvalidargexception-class.md)
