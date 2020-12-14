---
description: 詳細については、「例外処理」を参照してください。
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
ms.openlocfilehash: add942991a4792cb88e82dee0bfd033612b68eb2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219825"
---
# <a name="exception-processing"></a>例外処理

プログラムを実行すると、多くの異常な状態と "例外" と呼ばれるエラーが発生する可能性があります。 これには、メモリ不足、リソース割り当てエラー、およびファイルの検索エラーが含まれます。

この Microsoft Foundation Class ライブラリでは、C++ の ANSI 規格委員会によって提案されたものを厳密にモデル化した例外処理スキームを使用します。 異常な状況が発生する可能性のある関数を呼び出す前に、例外ハンドラーを設定する必要があります。 関数で異常な状態が発生した場合、例外がスローされ、制御が例外ハンドラーに渡されます。

Microsoft Foundation Class ライブラリに含まれるいくつかのマクロでは、例外ハンドラーが設定されます。 他の多くのグローバル関数は、必要に応じて、特殊な例外をスローしたり、プログラムを終了したりするのに役立ちます。 これらのマクロとグローバル関数は、次のカテゴリに分類されます。

- 例外ハンドラーを構成する例外マクロ。

- 例外スロー関数)。特定の型の例外を生成します。

- 終了関数。これにより、プログラムが終了します。

例と詳細については、「 [例外](../../mfc/exception-handling-in-mfc.md)」を参照してください。

### <a name="exception-macros"></a>例外マクロ

|名前|説明|
|-|-|
|[やり直し](#try)|例外処理のコードブロックを指定します。|
|[できれ](#catch)|前の **TRY** ブロックから例外をキャッチするためのコードブロックを指定します。|
|[CATCH_ALL](#catch_all)|前の **TRY** ブロックからのすべての例外をキャッチするコードブロックを指定します。|
|[AND_CATCH](#and_catch)|前の **TRY** ブロックから追加の例外の種類をキャッチするためのコードブロックを指定します。|
|[AND_CATCH_ALL](#and_catch_all)|前の **TRY** ブロックでスローされた他のすべての例外の種類をキャッチするためのコードブロックを指定します。|
|[END_CATCH](#end_catch)|最後の **CATCH** または **AND_CATCH** コードブロックを終了します。|
|[END_CATCH_ALL](#end_catch_all)|最後の **CATCH_ALL** コードブロックを終了します。|
|[THROW](#throw)|指定された例外をスローします。|
|[THROW_LAST](#throw_last)|現在処理されている例外を次の外部ハンドラーにスローします。|

### <a name="exception-throwing-functions"></a>Exception-Throwing 関数

|名前|説明|
|-|-|
|[AfxThrowArchiveException](#afxthrowarchiveexception)|アーカイブの例外をスローします。|
|[AfxThrowFileException](#afxthrowfileexception)|ファイル例外をスローします。|
|[AfxThrowInvalidArgException](#afxthrowinvalidargexception)|無効な引数の例外をスローします。|
|[AfxThrowMemoryException](#afxthrowmemoryexception)|メモリ例外をスローします。|
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|サポートされていない例外をスローします。|
|[AfxThrowResourceException](#afxthrowresourceexception)|Windows リソース-検出されない例外をスローします。|
|[AfxThrowUserException](#afxthrowuserexception)|ユーザーが開始したプログラムアクションで例外をスローします。|

MFC には、OLE 例外専用の次の2つの例外スロー関数が用意されています。

### <a name="ole-exception-functions"></a>OLE 例外関数

|名前|説明|
|-|-|
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|OLE オートメーション関数内で例外をスローします。|
|[AfxThrowOleException](#afxthrowoleexception)|OLE 例外をスローします。|

データベースの例外をサポートするために、データベースクラスには、とという2つの例外クラス `CDBException` `CDaoException` と、例外の種類をサポートするためのグローバル関数が用意されています。

### <a name="dao-exception-functions"></a>DAO 例外関数

|名前|説明|
|-|-|
|[AfxThrowDAOException](#afxthrowdaoexception)|独自のコードから [CDaoException](../../mfc/reference/cdaoexception-class.md) をスローします。|
|[AfxThrowDBException](#afxthrowdbexception)|独自のコードから [CDBException](../../mfc/reference/cdbexception-class.md) をスローします。|

MFC には、次の終了関数が用意されています。

### <a name="termination-functions"></a>終了関数

|名前|説明|
|-|-|
|[AfxAbort](#afxabort)|致命的なエラーが発生したときにアプリケーションを終了するために呼び出されます。|

## <a name="try"></a><a name="try"></a> やり直し

**TRY** ブロックを設定します。

```
TRY
```

### <a name="remarks"></a>解説

**TRY** ブロックは、例外をスローする可能性のあるコードのブロックを識別します。 これらの例外は、次の **CATCH** および **AND_CATCH** ブロックで処理されます。 再帰が許可されています。例外を無視するか、THROW_LAST マクロを使用して、外側の **TRY** ブロックに例外を渡すことができます。 END_CATCH または END_CATCH_ALL マクロを使用し **て、TRY** ブロックを終了します。

詳細については、「 [例外](../../mfc/exception-handling-in-mfc.md)」を参照してください。

### <a name="example"></a>例

[CATCH](#catch)の例を参照してください。

### <a name="requirements"></a>要件

ヘッダー: afx.h

## <a name="catch"></a><a name="catch"></a> できれ

前の **TRY** ブロックでスローされた最初の例外の種類をキャッチするコードブロックを定義します。

```
CATCH(exception_class, exception_object_pointer_name)
```

### <a name="parameters"></a>パラメーター

*exception_class*<br/>
テストする例外の種類を指定します。 標準の例外クラスの一覧については、「クラス [CException](../../mfc/reference/cexception-class.md)」を参照してください。

*exception_object_pointer_name*<br/>
マクロによって作成される例外オブジェクトポインターの名前を指定します。 ポインター名を使用して、 **CATCH** ブロック内の例外オブジェクトにアクセスできます。 この変数は、ユーザーに対して宣言されます。

### <a name="remarks"></a>解説

例外処理コードは、必要に応じて例外オブジェクトを問い合わせて、例外の特定の原因に関する詳細情報を取得することができます。 THROW_LAST マクロを呼び出して、処理を次の外側の例外フレームにシフトします。 END_CATCH マクロを使用し **て、TRY** ブロックを終了します。

*Exception_class* がクラスの場合は `CException` 、すべての例外の種類がキャッチされます。 [CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof)メンバー関数を使用すると、スローされた特定の例外を特定できます。 複数の種類の例外をキャッチするより優れた方法は、それぞれが異なる例外の種類を持つシーケンシャル **AND_CATCH** ステートメントを使用することです。

例外オブジェクトのポインターはマクロによって作成されます。 自分で宣言する必要はありません。

> [!NOTE]
> **CATCH** ブロックは、中かっこで囲まれた C++ スコープとして定義されます。 このスコープで変数を宣言する場合、変数はそのスコープ内でのみアクセスできます。 これは *exception_object_pointer_name* にも適用されます。

例外と CATCH マクロの詳細については、「 [例外](../../mfc/exception-handling-in-mfc.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCExceptions#26](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]

## <a name="catch_all"></a><a name="catch_all"></a> CATCH_ALL

前の **TRY** ブロックでスローされたすべての例外の種類をキャッチするコードブロックを定義します。

```
CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>パラメーター

*exception_object_pointer_name*<br/>
マクロによって作成される例外オブジェクトポインターの名前を指定します。 ポインター名を使用して、ブロック内の例外オブジェクトにアクセスでき `CATCH_ALL` ます。 この変数は、ユーザーに対して宣言されます。

### <a name="remarks"></a>解説

例外処理コードは、必要に応じて例外オブジェクトを問い合わせて、例外の特定の原因に関する詳細情報を取得することができます。 マクロを呼び出して、 `THROW_LAST` 処理を次の外側の例外フレームにシフトします。 **CATCH_ALL** を使用する場合は、END_CATCH_ALL マクロを使用し **て TRY** ブロックを終了します。

> [!NOTE]
> **CATCH_ALL** ブロックは、中かっこで囲まれた C++ スコープとして定義されます。 このスコープで変数を宣言する場合、変数はそのスコープ内でのみアクセスできます。

例外の詳細については、「 [例外](../../mfc/exception-handling-in-mfc.md)」を参照してください。

### <a name="example"></a>例

[CFile:: Abort](../../mfc/reference/cfile-class.md#abort)の例を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afx

## <a name="and_catch"></a><a name="and_catch"></a> AND_CATCH

前の **TRY** ブロックでスローされた追加の例外の種類をキャッチするためのコードブロックを定義します。

```
AND_CATCH(exception_class, exception_object_pointer_name)
```

### <a name="parameters"></a>パラメーター

*exception_class*<br/>
テストする例外の種類を指定します。 標準の例外クラスの一覧については、「クラス [CException](../../mfc/reference/cexception-class.md)」を参照してください。

*exception_object_pointer_name*<br/>
マクロによって作成される例外オブジェクトポインターの名前。 ポインター名を使用して、 **AND_CATCH** ブロック内の例外オブジェクトにアクセスできます。 この変数は、ユーザーに対して宣言されます。

### <a name="remarks"></a>解説

CATCH マクロを使用して1つの例外の種類をキャッチし、AND_CATCH マクロを使用して、後続の各型をキャッチします。 END_CATCH マクロを使用し **て、TRY** ブロックを終了します。

例外処理コードは、必要に応じて例外オブジェクトを問い合わせて、例外の特定の原因に関する詳細情報を取得することができます。 **AND_CATCH** ブロック内で THROW_LAST マクロを呼び出して、処理を次の外側の例外フレームにシフトします。 **AND_CATCH** は、前の **CATCH** または **AND_CATCH** ブロックの末尾をマークします。

> [!NOTE]
> **AND_CATCH** ブロックは、(中かっこで囲まれた) C++ スコープとして定義されます。 このスコープで変数を宣言する場合は、そのスコープ内でのみアクセス可能であることに注意してください。 これは、 *exception_object_pointer_name* 変数にも適用されます。

### <a name="example"></a>例

[CATCH](#catch)の例を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afx

## <a name="and_catch_all"></a><a name="and_catch_all"></a> AND_CATCH_ALL

前の **TRY** ブロックでスローされた追加の例外の種類をキャッチするためのコードブロックを定義します。

```
AND_CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>パラメーター

*exception_object_pointer_name*<br/>
マクロによって作成される例外オブジェクトポインターの名前。 ポインター名を使用して、 **AND_CATCH_ALL** ブロック内の例外オブジェクトにアクセスできます。 この変数は、ユーザーに対して宣言されます。

### <a name="remarks"></a>解説

**Catch** マクロを使用して1つの例外の種類をキャッチした後、AND_CATCH_ALL マクロを使用して、それ以外のすべての型をキャッチします。 AND_CATCH_ALL を使用する場合は、END_CATCH_ALL マクロを使用し **て TRY** ブロックを終了します。

例外処理コードは、必要に応じて例外オブジェクトを問い合わせて、例外の特定の原因に関する詳細情報を取得することができます。 **AND_CATCH_ALL** ブロック内で THROW_LAST マクロを呼び出して、処理を次の外側の例外フレームにシフトします。 **AND_CATCH_ALL** は、前の **CATCH** または **AND_CATCH_ALL** ブロックの末尾をマークします。

> [!NOTE]
> **AND_CATCH_ALL** ブロックは、(中かっこで囲まれた) C++ スコープとして定義されます。 このスコープで変数を宣言する場合は、そのスコープ内でのみアクセス可能であることに注意してください。

### <a name="requirements"></a>要件

  **ヘッダー** afx

## <a name="end_catch"></a><a name="end_catch"></a> END_CATCH

最後の **CATCH** または **AND_CATCH** ブロックの末尾をマークします。

```
END_CATCH
```

### <a name="remarks"></a>解説

END_CATCH マクロの詳細については、「 [例外](../../mfc/exception-handling-in-mfc.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afx

## <a name="end_catch_all"></a><a name="end_catch_all"></a> END_CATCH_ALL

最後の **CATCH_ALL88** または **AND_CATCH_ALL** ブロックの末尾をマークします。

```
END_CATCH_ALL
```

### <a name="requirements"></a>要件

  **ヘッダー** afx

## <a name="throw-mfc"></a><a name="throw"></a> THROW (MFC)

指定された例外をスローします。

```
THROW(exception_object_pointer)
```

### <a name="parameters"></a>パラメーター

*exception_object_pointer*<br/>
から派生した例外オブジェクトを指し `CException` ます。

### <a name="remarks"></a>解説

プログラム内の関連する **CATCH** ブロックに制御を渡すことにより、プログラムの実行 **を中断し** ます。 **CATCH** ブロックを指定していない場合は、エラーメッセージを出力して終了する Microsoft Foundation Class ライブラリモジュールに制御が渡されます。

詳細については、「 [例外](../../mfc/exception-handling-in-mfc.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afx

## <a name="throw_last"></a><a name="throw_last"></a> THROW_LAST

次の外側の **CATCH** ブロックに例外をスローします。

```
THROW_LAST()
```

### <a name="remarks"></a>解説

このマクロを使用すると、ローカルで作成された例外をスローできます。 キャッチした例外をスローしようとすると、通常はスコープ外になり、削除されます。 **THROW_LAST** では、例外は次の **CATCH** ハンドラーに正しく渡されます。

詳細については、「 [例外](../../mfc/exception-handling-in-mfc.md)」を参照してください。

### <a name="example"></a>例

[CFile:: Abort](../../mfc/reference/cfile-class.md#abort)の例を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afx

## <a name="afxthrowarchiveexception"></a><a name="afxthrowarchiveexception"></a> AfxThrowArchiveException

アーカイブの例外をスローします。

```cpp
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName);
```

### <a name="parameters"></a>パラメーター

*cause*<br/>
例外の理由を示す整数を指定します。 使用可能な値の一覧については、「 [Cアーカイブ例外:: m_cause](../../mfc/reference/carchiveexception-class.md#m_cause)」を参照してください。

*Lpszアーカイブ*<br/>
`CArchive`例外の原因となったオブジェクトの名前を含む文字列を指します (使用可能な場合)。

### <a name="requirements"></a>要件

  **ヘッダー** afx

## <a name="afxthrowfileexception"></a><a name="afxthrowfileexception"></a> AfxThrowFileException

ファイル例外をスローします。

```cpp
void AfxThrowFileException(
    int cause,
    LONG lOsError = -1,
    LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>パラメーター

*cause*<br/>
例外の理由を示す整数を指定します。 使用可能な値の一覧については、「 [CFileException:: m_cause](../../mfc/reference/cfileexception-class.md#m_cause)」を参照してください。

*lOsError*<br/>
例外の原因を示すオペレーティングシステムエラー番号 (使用可能な場合) が含まれます。 エラーコードの一覧については、オペレーティングシステムのマニュアルを参照してください。

*lpszFileName*<br/>
例外の原因となったファイルの名前を含む文字列を指します (使用可能な場合)。

### <a name="remarks"></a>解説

オペレーティングシステムのエラーコードに基づいて、原因を特定する責任があります。

### <a name="requirements"></a>要件

  **ヘッダー** afx

## <a name="afxthrowinvalidargexception"></a><a name="afxthrowinvalidargexception"></a> AfxThrowInvalidArgException

無効な引数の例外をスローします。

### <a name="syntax"></a>構文

```cpp
void AfxThrowInvalidArgException( );
```

### <a name="remarks"></a>解説

無効な引数が使用されると、この関数が呼び出されます。

### <a name="requirements"></a>要件

**ヘッダー:** afx

## <a name="afxthrowmemoryexception"></a><a name="afxthrowmemoryexception"></a> AfxThrowMemoryException

メモリ例外をスローします。

```cpp
void AfxThrowMemoryException();
```

### <a name="remarks"></a>解説

基になるシステムメモリアロケーター ( **malloc** や [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) Windows 関数など) への呼び出しが失敗した場合に、この関数を呼び出します。 **`new`** **`new`** メモリ割り当てが失敗した場合、はメモリ例外を自動的にスローするため、に対してを呼び出す必要はありません。

### <a name="requirements"></a>要件

  **ヘッダー** afx

## <a name="afxthrownotsupportedexception"></a><a name="afxthrownotsupportedexception"></a> AfxThrowNotSupportedException

サポートされていない機能に対する要求の結果である例外をスローします。

```cpp
void AfxThrowNotSupportedException();
```

### <a name="requirements"></a>要件

  **ヘッダー** afx

## <a name="afxthrowresourceexception"></a><a name="afxthrowresourceexception"></a> AfxThrowResourceException

リソース例外をスローします。

```cpp
void  AfxThrowResourceException();
```

### <a name="remarks"></a>解説

通常、この関数は、Windows リソースを読み込むことができないときに呼び出されます。

### <a name="requirements"></a>要件

  **ヘッダー** afx

## <a name="afxthrowuserexception"></a><a name="afxthrowuserexception"></a> AfxThrowUserException

エンドユーザーの操作を停止する例外をスローします。

```cpp
void AfxThrowUserException();
```

### <a name="remarks"></a>解説

通常、この関数は、 `AfxMessageBox` がユーザーにエラーを報告した直後に呼び出されます。

### <a name="requirements"></a>要件

  **ヘッダー** afx

## <a name="afxthrowoledispatchexception"></a><a name="afxthrowoledispatchexception"></a> AfxThrowOleDispatchException

OLE オートメーション関数内で例外をスローするには、この関数を使用します。

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

*wCode*<br/>
アプリケーション固有のエラーコード。

*lpszDescription*<br/>
エラーの説明。

*nDescriptionID*<br/>
音声エラーの説明のリソース ID。

*nHelpID*<br/>
アプリケーションのヘルプのヘルプコンテキスト (.HLP) ファイル。

### <a name="remarks"></a>解説

この関数に提供される情報は、運転アプリケーション (Microsoft Visual Basic またはその他の OLE オートメーションクライアントアプリケーション) によって表示できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCExceptions#25](../../mfc/codesnippet/cpp/exception-processing_2.cpp)]

### <a name="requirements"></a>要件

  **ヘッダー** afx

## <a name="afxthrowoleexception"></a><a name="afxthrowoleexception"></a> AfxThrowOleException

型のオブジェクトを作成 `COleException` し、例外をスローします。

```cpp
void AFXAPI AfxThrowOleException(SCODE sc);
void AFXAPI AfxThrowOleException(HRESULT hr);
```

### <a name="parameters"></a>パラメーター

*sc*<br/>
例外の理由を示す OLE ステータスコード。

*時間*<br/>
例外の理由を示す結果コードを処理します。

### <a name="remarks"></a>解説

引数として HRESULT を受け取るバージョンは、その結果コードを対応する SCODE に変換します。 HRESULT と SCODE の詳細については、「Windows SDK の [COM エラーコードの構造](/windows/win32/com/structure-of-com-error-codes) 」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdao

## <a name="afxthrowdaoexception"></a><a name="afxthrowdaoexception"></a> AfxThrowDaoException

独自のコードから [CDaoException](../../mfc/reference/cdaoexception-class.md) 型の例外をスローするには、この関数を呼び出します。

```cpp
void AFXAPI AfxThrowDaoException(
    int nAfxDaoError = NO_AFX_DAO_ERROR,
    SCODE scode = S_OK);
```

### <a name="parameters"></a>パラメーター

*nAfxDaoError*<br/>
DAO 拡張エラーコードを表す整数値。 [CDaoException:: m_nAfxDaoError](../../mfc/reference/cdaoexception-class.md#m_nafxdaoerror)の下に一覧表示されている値のいずれかを指定できます。

*scode*<br/>
型 SCODE の DAO からの OLE エラーコード。 詳細については、「 [CDaoException:: m_scode](../../mfc/reference/cdaoexception-class.md#m_scode)」を参照してください。

### <a name="remarks"></a>解説

フレームワークもを呼び出し `AfxThrowDaoException` ます。 の呼び出しでは、いずれかのパラメーターまたは両方を渡すことができます。 たとえば、 **CDaoException:: nAfxDaoError** で定義されているいずれかのエラーを発生させても、 *scode* パラメーターを気にする必要がない場合は、 *nAfxDaoError* パラメーターに有効なコードを渡し、 *scode* の既定値をそのまま使用します。

MFC DAO クラスに関連する例外の詳細については、 `CDaoException` このブックの「クラス」および「 [例外: データベース例外](../../mfc/exceptions-database-exceptions.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdb.h

## <a name="afxthrowdbexception"></a><a name="afxthrowdbexception"></a> AfxThrowDBException

独自のコードから型の例外をスローするには、この関数を呼び出し `CDBException` ます。

```cpp
void AfxThrowDBException(
    RETCODE nRetCode,
    CDatabase* pdb,
    HSTMT hstmt);
```

### <a name="parameters"></a>パラメーター

*nRetCode*<br/>
例外がスローされる原因となったエラーの種類を定義する RETCODE 型の値。

*pdb*<br/>
`CDatabase`例外が関連付けられているデータソース接続を表すオブジェクトへのポインター。

*hstmt*<br/>
例外が関連付けられているステートメントハンドルを指定する ODBC HSTMT ハンドル。

### <a name="remarks"></a>解説

このフレームワークは、 `AfxThrowDBException` ODBC API 関数の呼び出しから ODBC RETCODE を受け取ったときにを呼び出し、expectable エラーではなく例外的な条件として RETCODE を解釈します。 たとえば、データアクセス操作がディスク読み取りエラーのために失敗する場合があります。

ODBC で定義されている RETCODE 値の詳細については、「」の「Windows SDK の「状態とエラー情報の取得」を参照してください。 これらのコードに対する MFC の拡張機能の詳細については、「クラス [CDBException](../../mfc/reference/cdbexception-class.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afx

## <a name="afxabort"></a><a name="afxabort"></a> AfxAbort

MFC によって提供される既定の終了関数。

```cpp
void  AfxAbort();
```

### <a name="remarks"></a>解説

`AfxAbort` は、キャッチできない例外などの致命的なエラーが発生した場合に、MFC メンバー関数によって内部的に呼び出されます。 を復元でき `AfxAbort` ない致命的なエラーが発生した場合は、まれにを呼び出すことができます。

### <a name="example"></a>例

[CATCH](#catch)の例を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afx

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)<br/>
[CException クラス](cexception-class.md)<br/>
[CInvalidArgException クラス](cinvalidargexception-class.md)
