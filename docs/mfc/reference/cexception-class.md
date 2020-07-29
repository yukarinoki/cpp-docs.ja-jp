---
title: CException クラス
ms.date: 11/04/2016
f1_keywords:
- CException
- AFX/CException
- AFX/CException::CException
- AFX/CException::Delete
- AFX/CException::ReportError
helpviewer_keywords:
- CException [MFC], CException
- CException [MFC], Delete
- CException [MFC], ReportError
ms.assetid: cfacf14d-bfe4-4666-a5c7-38b800512920
ms.openlocfilehash: a24f324576c872e7fe509b742aa58d6c230ec24a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212489"
---
# <a name="cexception-class"></a>CException クラス

MFC (Microsoft Foundation Class) ライブラリ内のすべての例外に関する基底クラスです。

## <a name="syntax"></a>構文

```
class AFX_NOVTABLE CException : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CException:: CException](#cexception)|`CException` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CException::D e)](#delete)|オブジェクトを削除 `CException` します。|
|[CException:: ReportError](#reporterror)|メッセージボックス内のエラーメッセージをユーザーに報告します。|

## <a name="remarks"></a>解説

`CException`は抽象基本クラスであるため、オブジェクトを直接作成することはできません。 `CException` 派生クラスのオブジェクトを作成する必要があります。 独自のスタイルのクラスを作成する必要がある場合は `CException` 、上記の派生クラスのいずれかをモデルとして使用します。 派生クラスでもが使用されていることを確認し `IMPLEMENT_DYNAMIC` ます。

派生クラスとその説明を次に示します。

|||
|-|-|
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|リソースクリティカルな MFC 例外の基底クラスです。|
|[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|無効な引数の例外条件|
|[CMemoryException](../../mfc/reference/cmemoryexception-class.md)|メモリ不足の例外|
|[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|サポートされていない操作の要求|
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|アーカイブ固有の例外|
|[CFileException](../../mfc/reference/cfileexception-class.md)|ファイル固有の例外|
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Windows リソースが見つからないか、作成できません|
|[COleException](../../mfc/reference/coleexception-class.md)|OLE 例外|
|[CDBException](../../mfc/reference/cdbexception-class.md)|データベース例外 (Open Database Connectivity に基づく MFC データベースクラスで発生する例外条件)|
|[COleDispatchException](../../mfc/reference/coledispatchexception-class.md)|OLE ディスパッチ (オートメーション) の例外|
|[CUserException](../../mfc/reference/cuserexception-class.md)|リソースが見つからなかったことを示す例外|
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|データアクセスオブジェクトの例外 (DAO クラスで発生する例外条件)|
|[CInternetException](../../mfc/reference/cinternetexception-class.md)|インターネット例外 (インターネットクラスで発生する例外条件)。|

これらの例外は、 [THROW](exception-processing.md#throw)、 [THROW_LAST](exception-processing.md#throw_last)、 [try](exception-processing.md#try)、 [catch](exception-processing.md#catch)、 [and_catch](exception-processing.md#and_catch)、および[end_catch](exception-processing.md#end_catch)マクロと共に使用することを意図しています。 例外の詳細については、「[例外処理](exception-processing.md)」を参照するか、「[例外処理 (MFC)](../exception-handling-in-mfc.md)」を参照してください。

特定の例外をキャッチするには、適切な派生クラスを使用します。 すべての種類の例外をキャッチするには `CException` 、を使用してから、 [CObject:: IsKindOf](cobject-class.md#iskindof)を使用して、派生クラスを区別し `CException` ます。 は、 `CObject::IsKindOf` 動的な型チェックを利用するために、 [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)マクロで宣言されたクラスに対してのみ機能することに注意してください。 `CException`作成する任意の派生クラスでもマクロを使用する必要があり `IMPLEMENT_DYNAMIC` ます。

[GetErrorMessage](cfileexception-class.md#geterrormessage)または[ReportError](#reporterror)を呼び出すことによって、ユーザーに例外の詳細を報告できます。この場合、の派生クラスのいずれかを操作する2つのメンバー関数が使用さ `CException` れます。

マクロのいずれかによって例外がキャッチされると、 `CException` オブジェクトは自動的に削除されます。自分で削除しないでください。 キーワードを使用して例外がキャッチされた場合 **`catch`** 、その例外は自動的に削除されません。 どのような場合にオブジェクトを削除するかの詳細については、「[例外処理 (MFC)](../exception-handling-in-mfc.md) 」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](cobject-class.md)

`CException`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx

## <a name="cexceptioncexception"></a><a name="cexception"></a>CException:: CException

このメンバー関数は、 `CException` オブジェクトを構築します。

```
explicit CException(BOOL bAutoDelete);
```

### <a name="parameters"></a>パラメーター

*b_AutoDelete*<br/>
オブジェクトのメモリが `CException` ヒープに割り当てられている場合は TRUE を指定します。 これにより、 `CException` `Delete` 例外を削除するためにメンバー関数が呼び出されたときに、オブジェクトが削除されます。 `CException`オブジェクトがスタック上にあるか、またはグローバルオブジェクトである場合は、FALSE を指定します。 この場合、メンバー関数が呼び出されても、 `CException` オブジェクトは削除されません `Delete` 。

### <a name="remarks"></a>解説

通常、このコンストラクターを直接呼び出す必要はありません。 例外をスローする関数は、派生クラスのインスタンスを作成 `CException` してそのコンストラクターを呼び出す必要があります。または、 [AfxThrowFileException](exception-processing.md#afxthrowfileexception)などの MFC スロー関数のいずれかを使用して、定義済みの型をスローする必要があります。 このドキュメントは、完全を期すためだけに提供されています。

## <a name="cexceptiondelete"></a><a name="delete"></a>CException::D e)

この関数は、オブジェクトがヒープ上に作成されたかどうかを確認 `CException` し、存在する場合は、 **`delete`** オブジェクトに対して演算子を呼び出します。

```cpp
void Delete();
```

### <a name="remarks"></a>解説

オブジェクトを削除する場合は、 `CException` メンバー関数を使用し `Delete` て例外を削除します。 **`delete`** `CException` オブジェクトはグローバルオブジェクトであるか、またはスタック上に作成されている可能性があるため、演算子を直接使用しないでください。

オブジェクトを構築するときにオブジェクトを削除するかどうかを指定できます。 詳細については、「 [CException:: CException](#cexception)」を参照してください。

は `Delete` 、C++ 機構を使用している場合にのみ呼び出す必要があり **`try`** -  **`catch`** ます。 MFC マクロを使用している場合、Try と**CATCH**を**実行**すると、これらのマクロは自動的にこの関数を呼び出します。

### <a name="example"></a>例

```cpp
CFile* pFile = NULL;
// Constructing a CFile object with this override may throw
// a CFile exception, and won't throw any other exceptions.
// Calling CString::Format() may throw a CMemoryException,
// so we have a catch block for such exceptions, too. Any
// other exception types this function throws will be
// routed to the calling function.
// Note that this example performs the same actions as the
// example for CATCH, but uses C++ try/catch syntax instead
// of using the MFC TRY/CATCH macros. This sample must use
// CException::Delete() to delete the exception objects
// before closing the catch block, while the CATCH example
// implicitly performs the deletion via the macros.
try
{
   pFile = new CFile(_T("C:\\WINDOWS\\SYSTEM.INI"),
      CFile::modeRead | CFile::shareDenyNone);
   ULONGLONG ullLength = pFile->GetLength();
   CString str;
   str.Format(_T("Your SYSTEM.INI file is %u bytes long."), ullLength);
   AfxMessageBox(str);
}
catch(CFileException* pEx)
{
   // Simply show an error message to the user.
   pEx->ReportError();
   pEx->Delete();
}
catch(CMemoryException* pEx)
{
   // We can't recover from this memory exception, so we'll
   // just terminate the app without any cleanup. Normally, an
   // an application should do everything it possibly can to
   // clean up properly and _not_ call AfxAbort().
   pEx->Delete();
   AfxAbort();
}
// If an exception occurrs in the CFile constructor,
// the language will free the memory allocated by new
// and will not complete the assignment to pFile.
// Thus, our clean-up code needs to test for NULL.
if (pFile != NULL)
{
   pFile->Close();
   delete pFile;
}
```

## <a name="cexceptionreporterror"></a><a name="reporterror"></a>CException:: ReportError

このメンバー関数を呼び出して、メッセージボックス内のエラーテキストをユーザーに報告します。

```
virtual int ReportError(
    UINT nType = MB_OK,
    UINT nMessageID = 0);
```

### <a name="parameters"></a>パラメーター

*nType*<br/>
メッセージボックスのスタイルを指定します。 [メッセージボックススタイル](styles-used-by-mfc.md#message-box-styles)の任意の組み合わせをボックスに適用します。 このパラメーターを指定しない場合、既定値は MB_OK になります。

*nMessageID*<br/>
例外オブジェクトにエラーメッセージがない場合に表示するメッセージのリソース ID (文字列テーブルエントリ) を指定します。 0の場合は、"エラーメッセージがありません" というメッセージが表示されます。

### <a name="return-value"></a>戻り値

`AfxMessageBox`値。メッセージボックスを表示するのに十分なメモリがない場合は0。 返される可能性のある戻り値については、 [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)を参照してください。

### <a name="example"></a>例

の使用例を次に示し `CException::ReportError` ます。 別の例については、 [CATCH](exception-processing.md#catch)の例を参照してください。

```cpp
CFile fileInput;
CFileException ex;

// try to open a file for reading.
// The file will certainly not
// exist because there are too many explicit
// directories in the name.

// if the call to Open() fails, ex will be
// initialized with exception
// information.  the call to ex.ReportError() will
// display an appropriate
// error message to the user, such as
// "\Too\Many\Bad\Dirs.DAT contains an
// invalid path."  The error message text will be
// appropriate for the
// file name and error condition.

if (!fileInput.Open(_T("\\Too\\Many\\Bad\\Dirs.DAT"), CFile::modeRead, &ex))
{
  ex.ReportError();
}
else
{
  // the file was opened, so do whatever work
  // with fileInput we were planning...

  fileInput.Close();
}
```

## <a name="see-also"></a>関連項目

[CObject クラス](cobject-class.md)<br/>
[階層図](../hierarchy-chart.md)<br/>
[例外処理](exception-processing.md)<br/>
[操作方法: 独自のカスタム例外クラスを作成する](https://go.microsoft.com/fwlink/p/?linkid=128045)
