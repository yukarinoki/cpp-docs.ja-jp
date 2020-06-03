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
ms.openlocfilehash: bdf9dee88c29621bdc77c83d2633d93b4b9d10a7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751616"
---
# <a name="exception-processing"></a>例外処理

プログラムの実行時に、"例外" と呼ばれる異常な状態やエラーが数多く発生する可能性があります。 メモリ不足、リソース割り当てエラー、ファイルの検索の失敗などが考えられます。

Microsoft Foundation クラス ライブラリでは、C++ の ANSI 標準委員会が提案した例外処理スキームの後に厳密にモデル化された例外処理スキームを使用します。 例外ハンドラは、異常な状態に遭遇する可能性のある関数を呼び出す前に設定する必要があります。 関数が異常な条件を検出すると、例外がスローされ、制御が例外ハンドラーに渡されます。

Microsoft Foundation クラス ライブラリに含まれるいくつかのマクロは、例外ハンドラーを設定します。 他の多くのグローバル関数は、必要に応じて特殊な例外をスローし、プログラムを終了するのに役立ちます。 これらのマクロとグローバル関数は、次のカテゴリに分類されます。

- 例外マクロは、例外ハンドラーを構成します。

- 例外をスローする関数) を指定すると、特定の型の例外が生成されます。

- 終了機能で、プログラムの終了を引き起こします。

例と詳細については、記事[「例外](../../mfc/exception-handling-in-mfc.md)」を参照してください。

### <a name="exception-macros"></a>例外マクロ

|||
|-|-|
|[TRY](#try)|例外処理用のコード ブロックを指定します。|
|[キャッチ](#catch)|上記の**TRY**ブロックから例外をキャッチするためのコード ブロックを指定します。|
|[CATCH_ALL](#catch_all)|上記の**TRY**ブロックからのすべての例外をキャッチするためのコード ブロックを指定します。|
|[AND_CATCH](#and_catch)|上記の**TRY**ブロックから追加の例外の種類をキャッチするコードのブロックを指定します。|
|[AND_CATCH_ALL](#and_catch_all)|前の**TRY**ブロックでスローされたその他すべての追加の例外の種類をキャッチするコードのブロックを指定します。|
|[END_CATCH](#end_catch)|最後の**CATCH**またはAND_CATCHコード ブロック**を**終了します。|
|[END_CATCH_ALL](#end_catch_all)|最後の**CATCH_ALL**コード ブロックを終了します。|
|[THROW](#throw)|指定した例外をスローします。|
|[THROW_LAST](#throw_last)|現在処理されている例外を次の外部ハンドラーにスローします。|

### <a name="exception-throwing-functions"></a>例外スロー関数

|||
|-|-|
|[AfxThrowArchiveException](#afxthrowarchiveexception)|アーカイブ例外をスローします。|
|[AfxThrowFileException](#afxthrowfileexception)|ファイル例外をスローします。|
|[AfxThrowInvalidArgException](#afxthrowinvalidargexception)|無効な引数例外をスローします。|
|[AfxThrowMemoryException](#afxthrowmemoryexception)|メモリ例外をスローします。|
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|サポートされていない例外をスローします。|
|[AfxThrowResourceException](#afxthrowresourceexception)|Windows リソースが見つからない例外をスローします。|
|[AfxThrowUserException](#afxthrowuserexception)|ユーザーが開始したプログラムアクションで例外をスローします。|

MFC には、OLE 例外専用の例外スロー関数が 2 つあります。

### <a name="ole-exception-functions"></a>OLE 例外関数

|||
|-|-|
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|OLE オートメーション関数内で例外をスローします。|
|[AfxThrowOleException](#afxthrowoleexception)|OLE 例外をスローします。|

データベース例外をサポートするために、データベース クラスには 2 つの`CDBException`例外`CDaoException`クラスと、例外の種類をサポートするグローバル関数が用意されています。

### <a name="dao-exception-functions"></a>DAO 例外関数

|||
|-|-|
|[アfxスローダオ例外](#afxthrowdaoexception)|独自のコードから[CDaoException](../../mfc/reference/cdaoexception-class.md)をスローします。|
|[AfxThrowDBException](#afxthrowdbexception)|独自のコードから[CDBException](../../mfc/reference/cdbexception-class.md)をスローします。|

MFC には、次の終了関数が用意されています。

### <a name="termination-functions"></a>終了関数

|||
|-|-|
|[AfxAbort](#afxabort)|致命的なエラーが発生したときにアプリケーションを終了するために呼び出されます。|

## <a name="try"></a><a name="try"></a>試してみる

**TRY**ブロックを設定します。

```
TRY
```

### <a name="remarks"></a>解説

**TRY**ブロックは、例外をスローする可能性のあるコードブロックを識別します。 これらの例外は、次の**CATCH**ブロックと**AND_CATCH**ブロックで処理されます。 再帰が可能: 例外は、外部**の TRY**ブロックに渡すことができます( 無視するか、THROW_LAST マクロを使用します)。 **TRY**ブロックをEND_CATCHまたはEND_CATCH_ALLマクロで終了します。

詳細については、記事[「例外](../../mfc/exception-handling-in-mfc.md)」を参照してください。

### <a name="example"></a>例

[CATCH](#catch)の例を参照してください。

### <a name="requirements"></a>必要条件

ヘッダー: afx.h

## <a name="catch"></a><a name="catch"></a>キャッチ

上記の**TRY**ブロックでスローされた最初の例外の型をキャッチするコードのブロックを定義します。

```
CATCH(exception_class, exception_object_pointer_name)
```

### <a name="parameters"></a>パラメーター

*exception_class*<br/>
テスト対象の例外の種類を指定します。 標準例外クラスの一覧については、クラス[CException](../../mfc/reference/cexception-class.md)を参照してください。

*exception_object_pointer_name*<br/>
マクロによって作成される例外オブジェクト ポインタの名前を指定します。 CATCH**ブロック内**の例外オブジェクトにアクセスするには、ポインター名を使用します。 この変数は、あなたのために宣言されています。

### <a name="remarks"></a>解説

例外処理コードは、例外オブジェクトを問い合わせる場合は、例外の特定の原因に関する詳細情報を取得できます。 THROW_LASTマクロを呼び出して、処理を次の外部例外フレームにシフトします。 **TRY**ブロックをEND_CATCHマクロで終了します。

*exception_class*がクラス`CException`の場合、すべての例外タイプがキャッチされます。 [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)メンバー関数を使用して、スローされた特定の例外を特定できます。 いくつかの種類の例外をキャッチする方法としては、順次**AND_CATCH**ステートメントを使用する方法がそれぞれ異なる例外タイプを使用することをおしいます。

例外オブジェクトポインタはマクロによって作成されます。 自分で宣言する必要はありません。

> [!NOTE]
> **CATCH**ブロックは、中かっこで囲まれた C++ スコープとして定義されます。 このスコープで変数を宣言した場合、変数はそのスコープ内でのみアクセス可能です。 これは *、exception_object_pointer_name*にも適用されます。

例外と CATCH マクロの詳細については、記事[「例外](../../mfc/exception-handling-in-mfc.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCExceptions#26](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]

## <a name="catch_all"></a><a name="catch_all"></a>CATCH_ALL

上記の**TRY**ブロックでスローされたすべての例外型をキャッチするコード ブロックを定義します。

```
CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>パラメーター

*exception_object_pointer_name*<br/>
マクロによって作成される例外オブジェクト ポインタの名前を指定します。 ブロック内の例外オブジェクトにアクセスするには、ポインター名を`CATCH_ALL`使用します。 この変数は、あなたのために宣言されています。

### <a name="remarks"></a>解説

例外処理コードは、例外オブジェクトを問い合わせる場合は、例外の特定の原因に関する詳細情報を取得できます。 マクロを`THROW_LAST`呼び出して、処理を次の外部例外フレームにシフトします。 **CATCH_ALL**を使用する場合は **、TRY**ブロックをEND_CATCH_ALL マクロで終了します。

> [!NOTE]
> **CATCH_ALL**ブロックは、中かっこで囲まれた C++ スコープとして定義されます。 このスコープで変数を宣言した場合、変数はそのスコープ内でのみアクセス可能です。

例外の詳細については、記事「[例外](../../mfc/exception-handling-in-mfc.md)」を参照してください。

### <a name="example"></a>例

[CFile::Abort](../../mfc/reference/cfile-class.md#abort)の例を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

## <a name="and_catch"></a><a name="and_catch"></a>AND_CATCH

前の**TRY**ブロックでスローされる追加の例外型をキャッチするためのコード ブロックを定義します。

```
AND_CATCH(exception_class, exception_object_pointer_name)
```

### <a name="parameters"></a>パラメーター

*exception_class*<br/>
テスト対象の例外の種類を指定します。 標準例外クラスの一覧については、クラス[CException](../../mfc/reference/cexception-class.md)を参照してください。

*exception_object_pointer_name*<br/>
マクロによって作成される例外オブジェクト ポインターの名前。 AND_CATCH**ブロック内**の例外オブジェクトにアクセスするには、ポインター名を使用します。 この変数は、あなたのために宣言されています。

### <a name="remarks"></a>解説

CATCH マクロを使用して 1 つの例外タイプをキャッチし、次にAND_CATCHマクロを使用して後続の各型をキャッチします。 **TRY**ブロックをEND_CATCHマクロで終了します。

例外処理コードは、例外オブジェクトを問い合わせる場合は、例外の特定の原因に関する詳細情報を取得できます。 **AND_CATCH**ブロック内でTHROW_LAST マクロを呼び出して、処理を次の外部例外フレームにシフトします。 **AND_CATCH**は、前の**CATCH**ブロックまたは**AND_CATCH**ブロックの末尾をマークします。

> [!NOTE]
> **AND_CATCH**ブロックは、C++ スコープとして定義されます (中かっこで囲まれます)。 このスコープで変数を宣言する場合、変数はそのスコープ内でのみアクセス可能であることを覚えておいてください。 これは *、exception_object_pointer_name*変数にも適用されます。

### <a name="example"></a>例

[CATCH](#catch)の例を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

## <a name="and_catch_all"></a><a name="and_catch_all"></a>AND_CATCH_ALL

前の**TRY**ブロックでスローされる追加の例外型をキャッチするためのコード ブロックを定義します。

```
AND_CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>パラメーター

*exception_object_pointer_name*<br/>
マクロによって作成される例外オブジェクト ポインターの名前。 ポインター名を使用して **、AND_CATCH_ALL**ブロック内の例外オブジェクトにアクセスできます。 この変数は、あなたのために宣言されています。

### <a name="remarks"></a>解説

**CATCH**マクロを使用して 1 つの例外タイプをキャッチし、その後に後続のすべての型をキャッチするAND_CATCH_ALLマクロを使用します。 AND_CATCH_ALLを使用する場合は **、TRY**ブロックをEND_CATCH_ALLマクロで終了します。

例外処理コードは、例外オブジェクトを問い合わせる場合は、例外の特定の原因に関する詳細情報を取得できます。 **AND_CATCH_ALL**ブロック内でTHROW_LAST マクロを呼び出して、処理を次の外部例外フレームにシフトします。 **AND_CATCH_ALL**は、前の**CATCH**ブロックまたは**AND_CATCH_ALL**ブロックの末尾をマークします。

> [!NOTE]
> **AND_CATCH_ALL**ブロックは、C++ スコープとして定義されます (中かっこで囲みます)。 このスコープで変数を宣言する場合、変数はそのスコープ内でのみアクセス可能であることを覚えておいてください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

## <a name="end_catch"></a><a name="end_catch"></a>END_CATCH

最後の**CATCH**ブロックまたは**AND_CATCH**ブロックの末尾をマークします。

```
END_CATCH
```

### <a name="remarks"></a>解説

END_CATCH マクロの詳細については、[記事「例外](../../mfc/exception-handling-in-mfc.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

## <a name="end_catch_all"></a><a name="end_catch_all"></a>END_CATCH_ALL

最後の**CATCH_ALL88**またはブロックの終わりを**マークAND_CATCH_ALL**します。

```
END_CATCH_ALL
```

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

## <a name="throw-mfc"></a><a name="throw"></a>スロー (MFC)

指定した例外をスローします。

```
THROW(exception_object_pointer)
```

### <a name="parameters"></a>パラメーター

*exception_object_pointer*<br/>
から`CException`派生した例外オブジェクトへのポイント。

### <a name="remarks"></a>解説

**THROW**はプログラムの実行を中断し、プログラム内の関連する**CATCH**ブロックに制御を渡します。 **CATCH**ブロックを指定していない場合は、エラー メッセージを出力して終了する Microsoft Foundation クラス ライブラリ モジュールに制御が渡されます。

詳細については、記事[「例外](../../mfc/exception-handling-in-mfc.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

## <a name="throw_last"></a><a name="throw_last"></a>THROW_LAST

例外を次の外部**CATCH**ブロックにスローします。

```
THROW_LAST()
```

### <a name="remarks"></a>解説

このマクロを使用すると、ローカルに作成された例外をスローできます。 キャッチした例外をスローしようとすると、通常はスコープ外に出て削除されます。 **THROW_LAST**を使用すると、例外は次の**CATCH**ハンドラに正しく渡されます。

詳細については、記事[「例外](../../mfc/exception-handling-in-mfc.md)」を参照してください。

### <a name="example"></a>例

[CFile::Abort](../../mfc/reference/cfile-class.md#abort)の例を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

## <a name="afxthrowarchiveexception"></a><a name="afxthrowarchiveexception"></a>アfxスローアーカイブ例外

アーカイブ例外をスローします。

```cpp
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName);
```

### <a name="parameters"></a>パラメーター

*原因*<br/>
例外の理由を示す整数を指定します。 指定できる値の一覧については[、「CArchiveException::m_cause」](../../mfc/reference/carchiveexception-class.md#m_cause)を参照してください。

*名前を変更します。*<br/>
例外の原因となったオブジェクトの名前を`CArchive`含む文字列を指します (可能な場合)。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

## <a name="afxthrowfileexception"></a><a name="afxthrowfileexception"></a>ファイルの例外

ファイル例外をスローします。

```cpp
void AfxThrowFileException(
    int cause,
    LONG lOsError = -1,
    LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>パラメーター

*原因*<br/>
例外の理由を示す整数を指定します。 指定できる値の一覧については[、「CFileException::m_cause」](../../mfc/reference/cfileexception-class.md#m_cause)を参照してください。

*エラー*<br/>
例外の理由を示すオペレーティング システムエラー番号 (使用可能な場合) が含まれます。 エラー コードのリストについては、オペレーティング システムのマニュアルを参照してください。

*ファイル名*<br/>
例外の原因となったファイルの名前を含む文字列を指します (可能な場合)。

### <a name="remarks"></a>解説

オペレーティング システムのエラー コードに基づいて原因を特定する必要があります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

## <a name="afxthrowinvalidargexception"></a><a name="afxthrowinvalidargexception"></a>例外をスローします。

無効な引数例外をスローします。

### <a name="syntax"></a>構文

```cpp
void AfxThrowInvalidArgException( );
```

### <a name="remarks"></a>解説

この関数は、無効な引数が使用されるときに呼び出されます。

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="afxthrowmemoryexception"></a><a name="afxthrowmemoryexception"></a>アfxスローメモリ例外

メモリ例外をスローします。

```cpp
void AfxThrowMemoryException();
```

### <a name="remarks"></a>解説

基になるシステム メモリ アロケーター **(malloc**や[GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) Windows 関数など) の呼び出しが失敗した場合に、この関数を呼び出します。 new はメモリ割り当てが失敗した場合にメモリ例外を自動的に**スローするため****、new**に対して呼び出す必要はありません。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

## <a name="afxthrownotsupportedexception"></a><a name="afxthrownotsupportedexception"></a>例外を処理しません。

サポートされていない機能の要求の結果である例外をスローします。

```cpp
void AfxThrowNotSupportedException();
```

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

## <a name="afxthrowresourceexception"></a><a name="afxthrowresourceexception"></a>を使用します。

リソース例外をスローします。

```cpp
void  AfxThrowResourceException();
```

### <a name="remarks"></a>解説

この関数は、通常、Windows リソースを読み込めないときに呼び出されます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

## <a name="afxthrowuserexception"></a><a name="afxthrowuserexception"></a>アfxスローユーザー例外

エンド ユーザー操作を停止する例外をスローします。

```cpp
void AfxThrowUserException();
```

### <a name="remarks"></a>解説

この関数は通常、ユーザーにエラー`AfxMessageBox`を報告した直後に呼び出されます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

## <a name="afxthrowoledispatchexception"></a><a name="afxthrowoledispatchexception"></a>を返します。

この関数を使用して、OLE オートメーション関数内で例外をスローします。

```cpp
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

*wコード*<br/>
アプリケーションに固有のエラー コード。

*説明をします。*<br/>
エラーの口頭での説明。

*説明 ID*<br/>
口頭エラーの説明のリソース ID。

*ヘルプID*<br/>
アプリケーションのヘルプ (.HLP) ファイル。

### <a name="remarks"></a>解説

この関数に提供される情報は、駆動アプリケーション (Microsoft Visual Basic または他の OLE オートメーション クライアント アプリケーション) によって表示できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCExceptions#25](../../mfc/codesnippet/cpp/exception-processing_2.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

## <a name="afxthrowoleexception"></a><a name="afxthrowoleexception"></a>アfxスローオーレ例外

型`COleException`のオブジェクトを作成し、例外をスローします。

```cpp
void AFXAPI AfxThrowOleException(SCODE sc);
void AFXAPI AfxThrowOleException(HRESULT hr);
```

### <a name="parameters"></a>パラメーター

*Sc*<br/>
例外の理由を示す OLE 状態コード。

*人事*<br/>
例外の理由を示す結果コードへのハンドル。

### <a name="remarks"></a>解説

引数として HRESULT を受け取るバージョンは、その結果のコードを対応する SCODE に変換します。 HRESULT と SCODE の詳細については、Windows SDK[の COM エラー コードの構造](/windows/win32/com/structure-of-com-error-codes)を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

## <a name="afxthrowdaoexception"></a><a name="afxthrowdaoexception"></a>アプスローダオ例外

独自のコードから[型 CDaoException](../../mfc/reference/cdaoexception-class.md)の例外をスローします。

```cpp
void AFXAPI AfxThrowDaoException(
    int nAfxDaoError = NO_AFX_DAO_ERROR,
    SCODE scode = S_OK);
```

### <a name="parameters"></a>パラメーター

*エラーメッセージ*<br/>
[m_nAfxDaoError DAO](../../mfc/reference/cdaoexception-class.md#m_nafxdaoerror)拡張エラー コードを表す整数値 。

*Scode*<br/>
SCODE 型の DAO からの OLE エラー コード。 詳細については[、「CDaoException::m_scode」](../../mfc/reference/cdaoexception-class.md#m_scode)を参照してください。

### <a name="remarks"></a>解説

フレームワークは、`AfxThrowDaoException`も呼び出します。 呼び出しでは、パラメーターのいずれか、または両方を渡すことができます。 たとえば **、CDaoException::nAfxDaoError**で定義されているエラーのいずれかを発生させるが *、scode*パラメーターを気にしない場合は *、nAfxDaoError*パラメーターに有効なコードを渡し *、scode*の既定値を受け入れます。

MFC DAO クラスに関連する例外については、このマニュアルの`CDaoException`クラスおよび記事「[例外: データベース例外](../../mfc/exceptions-database-exceptions.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdb.h

## <a name="afxthrowdbexception"></a><a name="afxthrowdbexception"></a>例外

独自のコードから型`CDBException`の例外をスローします。

```cpp
void AfxThrowDBException(
    RETCODE nRetCode,
    CDatabase* pdb,
    HSTMT hstmt);
```

### <a name="parameters"></a>パラメーター

*nレットコード*<br/>
例外がスローされる原因となったエラーのタイプを定義する、タイプ RETCODE の値。

*Pdb*<br/>
例外が`CDatabase`関連付けられているデータ ソース接続を表すオブジェクトへのポインター。

*hstmt*<br/>
例外が関連付けられているステートメント ハンドルを指定する ODBC HSTMT ハンドル。

### <a name="remarks"></a>解説

フレームワークは、ODBC API 関数の呼び出しから ODBC RETCODE を受け取ると呼び出`AfxThrowDBException`し、RETCODE を予期されるエラーではなく例外的な条件として解釈します。 たとえば、ディスク読み取りエラーが原因でデータ アクセス操作が失敗する場合があります。

ODBC で定義された RETCODE 値の詳細については、Windows SDK の「第 8 章 ステータスおよびエラー情報の取得」を参照してください。 これらのコードに対する MFC 拡張機能については[、「CDBException](../../mfc/reference/cdbexception-class.md)クラス」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

## <a name="afxabort"></a><a name="afxabort"></a>アfxアボート

MFC によって提供される既定の終了関数。

```cpp
void  AfxAbort();
```

### <a name="remarks"></a>解説

`AfxAbort`は、処理できないキャッチされていない例外などの致命的なエラーが発生した場合に、MFC メンバー関数によって内部的に呼び出されます。 回復できない致命的`AfxAbort`なエラーが発生した場合は、まれに呼び出すことができます。

### <a name="example"></a>例

[CATCH](#catch)の例を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afx.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)<br/>
[クラスの例外](cexception-class.md)<br/>
[クラスを無効にします。](cinvalidargexception-class.md)
