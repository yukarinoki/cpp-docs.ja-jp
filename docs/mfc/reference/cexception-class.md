---
title: クラスの例外
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
ms.openlocfilehash: 93901f6f92ee79bd893b2ec0d1e341e77749d951
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753180"
---
# <a name="cexception-class"></a>クラスの例外

MFC (Microsoft Foundation Class) ライブラリ内のすべての例外に関する基底クラスです。

## <a name="syntax"></a>構文

```
class AFX_NOVTABLE CException : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[::C例外](#cexception)|`CException` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[例外::Dエレテ](#delete)|オブジェクトを`CException`削除します。|
|[例外::レポートエラー](#reporterror)|ユーザーにメッセージ ボックスにエラー メッセージを報告します。|

## <a name="remarks"></a>解説

抽象`CException`基本クラスであるため、オブジェクトを直接作成`CException`することはできません。派生クラスのオブジェクトを作成する必要があります。 独自`CException`の -style クラスを作成する必要がある場合は、モデルとして上記の派生クラスのいずれかを使用します。 派生クラスでも を使用`IMPLEMENT_DYNAMIC`していることを確認します。

派生クラスとその説明を以下に示します。

|||
|-|-|
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|リソース クリティカルな MFC 例外の基本クラス|
|[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|無効な引数例外条件|
|[CMemoryException](../../mfc/reference/cmemoryexception-class.md)|メモリ不足の例外|
|[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|サポートされていない操作の要求|
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|アーカイブ固有の例外|
|[CFileException](../../mfc/reference/cfileexception-class.md)|ファイル固有の例外|
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Windows リソースが見つからないか、または作成可能でない|
|[COleException](../../mfc/reference/coleexception-class.md)|OLE 例外|
|[CDBException](../../mfc/reference/cdbexception-class.md)|データベース例外 (オープン データベース接続に基づく MFC データベース クラスに発生する例外条件)|
|[COleDispatchException](../../mfc/reference/coledispatchexception-class.md)|OLE ディスパッチ (オートメーション) 例外|
|[CUserException](../../mfc/reference/cuserexception-class.md)|リソースが見つからなかったことを示す例外|
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|データ アクセス オブジェクト例外 (DAO クラスに対して発生する例外条件)|
|[CInternetException](../../mfc/reference/cinternetexception-class.md)|インターネット例外 (つまり、インターネット クラスに発生する例外条件)。|

これらの例外は、 [THROW](exception-processing.md#throw)、 [THROW_LAST](exception-processing.md#throw_last)、 [try](exception-processing.md#try)、[キャッチ](exception-processing.md#catch)、 [and_catch](exception-processing.md#and_catch)、および[end_catch](exception-processing.md#end_catch)マクロで使用することを目的としています。 例外の詳細については、「[例外処理](exception-processing.md)」を参照[してください。](../exception-handling-in-mfc.md)

特定の例外をキャッチするには、適切な派生クラスを使用します。 すべての種類の例外をキャッチするには、`CException`を使用し[、CObject::IsKindOf](cobject-class.md#iskindof)を使用`CException`して派生クラスを区別します。 動的型`CObject::IsKindOf`チェックを利用するために[、IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)マクロで宣言されたクラスに対してのみ機能することに注意してください。 作成`CException`する派生クラスは、マクロも使用する`IMPLEMENT_DYNAMIC`必要があります。

任意の派生クラスを処理する 2 つのメンバー関数[を呼び](cfileexception-class.md#geterrormessage)出[すことによって、例外](#reporterror)の詳細を`CException`ユーザーに報告できます。

いずれかのマクロによって例外がキャッチされた場合、`CException`オブジェクトは自動的に削除されます。自分で削除しないでください。 **catch**キーワードを使用して例外がキャッチされた場合、自動的に削除されません。 例外オブジェクトを削除するタイミングの詳細については、「[例外処理 (MFC)」](../exception-handling-in-mfc.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](cobject-class.md)

`CException`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="cexceptioncexception"></a><a name="cexception"></a>::C例外

このメンバー関数は、オブジェクト`CException`を構築します。

```
explicit CException(BOOL bAutoDelete);
```

### <a name="parameters"></a>パラメーター

*b_AutoDelete*<br/>
オブジェクトのメモリがヒープに`CException`割り当てられている場合は、TRUE を指定します。 これにより、メンバー関数`CException`が呼び出されたときに、例外`Delete`を削除するオブジェクトが削除されます。 オブジェクトがスタック上`CException`にある場合、またはグローバルオブジェクトである場合は、FALSE を指定します。 この場合、`Delete`メンバー関数`CException`が呼び出されたときにオブジェクトは削除されません。

### <a name="remarks"></a>解説

通常、このコンストラクターを直接呼び出す必要はありません。 例外をスローする関数は`CException`、派生クラスのインスタンスを作成してそのコンストラクターを呼び出すか、または MFC の throw 関数[(AfxThrowFileException](exception-processing.md#afxthrowfileexception)など) のいずれかを使用して定義済みの型をスローする必要があります。 このドキュメントは、完全性を目的として提供されています。

## <a name="cexceptiondelete"></a><a name="delete"></a>例外::Dエレテ

この関数は、オブジェクトが`CException`ヒープ上で作成されているかどうかを確認し、作成されている場合は、オブジェクトの**delete**演算子を呼び出します。

```cpp
void Delete();
```

### <a name="remarks"></a>解説

オブジェクトを`CException`削除する場合は、メンバー`Delete`関数を使用して例外を削除します。 オブジェクトがグローバル オブジェクトである可能性があるため、またはスタック上に作成されているため、delete 演算子を直接使用しないでください。 **delete** `CException`

オブジェクトの作成時にオブジェクトを削除するかどうかを指定できます。 詳細については[、「CException::CException」](#cexception)を参照してください。

C++ **try**-  `Delete` **catch**メカニズムを使用している場合にのみ呼び出す必要があります。 MFC マクロ**TRY**と**CATCH**を使用している場合、これらのマクロは自動的にこの関数を呼び出します。

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

## <a name="cexceptionreporterror"></a><a name="reporterror"></a>例外::レポートエラー

メッセージ ボックスのエラー テキストをユーザーに報告します。

```
virtual int ReportError(
    UINT nType = MB_OK,
    UINT nMessageID = 0);
```

### <a name="parameters"></a>パラメーター

*nType*<br/>
メッセージ ボックスのスタイルを指定します。 [メッセージ ボックスのスタイル](styles-used-by-mfc.md#message-box-styles)を任意に組み合わせてボックスに適用します。 このパラメーターを指定しない場合、デフォルトはMB_OKです。

*メッセージ ID*<br/>
例外オブジェクトにエラー メッセージがない場合に表示するメッセージのリソース ID (文字列テーブル エントリ) を指定します。 0 の場合は、「エラー メッセージがありません」というメッセージが表示されます。

### <a name="return-value"></a>戻り値

値`AfxMessageBox`。メモリ不足の場合は、メッセージ ボックスを表示できません。 可能な戻り値については[、AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)を参照してください。

### <a name="example"></a>例

の使用例を次に`CException::ReportError`示します。 別の例については[、CATCH](exception-processing.md#catch)の例を参照してください。

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

[Cオブジェクトクラス](cobject-class.md)<br/>
[階層グラフ](../hierarchy-chart.md)<br/>
[例外処理](exception-processing.md)<br/>
[方法 : 独自のカスタム例外クラスを作成する](https://go.microsoft.com/fwlink/p/?linkid=128045)
