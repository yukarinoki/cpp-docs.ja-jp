---
title: CException クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CException
- AFX/CException
- AFX/CException::CException
- AFX/CException::Delete
- AFX/CException::ReportError
dev_langs:
- C++
helpviewer_keywords:
- CException [MFC], CException
- CException [MFC], Delete
- CException [MFC], ReportError
ms.assetid: cfacf14d-bfe4-4666-a5c7-38b800512920
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a152c55944fca5fa858c148c009ef6301ff0f762
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368034"
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
|[CException::CException](#cexception)|`CException` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CException::Delete](#delete)|削除、`CException`オブジェクト。|  
|[CException::ReportError](#reporterror)|ユーザーにメッセージ ボックスに、エラー メッセージを報告します。|  
  
## <a name="remarks"></a>コメント  
 `CException`抽象基本クラスを作成することはできませんが`CException`オブジェクト直接派生クラスのオブジェクトを作成する必要があります。 独自に作成する必要がある場合`CException`-スタイル クラスは、モデルとして上記の派生クラスのいずれかを使用します。 派生クラスも使用するように`IMPLEMENT_DYNAMIC`です。  
  
 派生クラスとその説明を次に示します。  
  
|||  
|-|-|  
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|リソース クリティカルな MFC 例外の基本クラス|  
|[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|無効な引数の例外状態|  
|[CMemoryException](../../mfc/reference/cmemoryexception-class.md)|メモリ不足の例外|  
|[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|サポートされていない操作の要求|  
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|アーカイブ固有の例外|  
|[CFileException](../../mfc/reference/cfileexception-class.md)|特定のファイルの例外|  
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Windows リソース見つからないか、または不可能|  
|[COleException](../../mfc/reference/coleexception-class.md)|OLE 例外|  
|[CDBException](../../mfc/reference/cdbexception-class.md)|データベースの例外 (つまり、Open Database Connectivity に基づいて MFC データベース クラス用により発生する例外条件)|  
|[COleDispatchException](../../mfc/reference/coledispatchexception-class.md)|OLE ディスパッチ (オートメーション) 例外|  
|[CUserException](../../mfc/reference/cuserexception-class.md)|リソースが検出できなかったことを示す例外|  
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|データ アクセス オブジェクト例外 (つまり、DAO クラスにより発生する例外条件)|  
|[CInternetException](../../mfc/reference/cinternetexception-class.md)|インターネットの例外 (つまり、インターネット クラスが原因で起こる例外条件)。|  
  
 これらの例外で使用するものでは、[スロー](exception-processing.md#throw)、 [THROW_LAST](exception-processing.md#throw_last)、[を再試行してください](exception-processing.md#try)、[キャッチ](exception-processing.md#catch)、 [and_catch](exception-processing.md#and_catch)、および[end_catch](exception-processing.md#end_catch)マクロです。 例外の詳細については、次を参照してください。[例外処理](exception-processing.md)、」または「[例外処理 (MFC)](../exception-handling-in-mfc.md)です。  
  
 特定の例外をキャッチするには、適切な派生クラスを使用します。 すべての種類の例外を使用して`CException`、しを使用して[使うため](cobject-class.md#iskindof)中で区別する`CException`-クラスを派生します。 なお`CObject::IsKindOf`で宣言されたクラスに対してのみ機能します、 [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)マクロ、動的な型チェックのメリットを活かすためです。 任意`CException`-作成した派生クラスを使用する必要があります、`IMPLEMENT_DYNAMIC`マクロ、すぎます。  
  
 ユーザーに例外に関する詳細情報を報告するには呼び出すことによって[GetErrorMessage](cfileexception-class.md#geterrormessage)または[ReportError](#reporterror)、2 つのメンバー関数のいずれかを操作する`CException`派生クラス。  
  
 例外が、マクロのいずれかで検出された場合、`CException`オブジェクトが自動的に削除されます。 削除しないで自分でします。 使用して、例外がキャッチされた場合、**キャッチ**キーワードは自動的に削除されません。 記事を参照して[例外処理 (MFC)](../exception-handling-in-mfc.md)の詳細については、例外オブジェクトを削除する場合。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](cobject-class.md)  
  
 `CException`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="cexception"></a>  CException::CException  
 このメンバー関数を作成、`CException`オブジェクト。  
  
```  
explicit CException(BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>パラメーター  
 *b_AutoDelete*  
 指定**TRUE**場合のメモリを`CException`オブジェクトは、ヒープに割り当てられました。 これにより、`CException`ときに削除されるオブジェクト、**削除**例外を削除するメンバー関数が呼び出されます。 指定**FALSE**場合、`CException`オブジェクトがスタック上またはグローバル オブジェクトです。 この場合、`CException`されない時に削除、**削除**メンバー関数が呼び出されます。  
  
### <a name="remarks"></a>コメント  
 このコンス トラクターを直接呼び出す必要は通常ありません。 例外をスローした関数がのインスタンスを作成する必要があります、 `CException`-クラスを派生し、そのコンス トラクター、または呼び出しが、MFC のいずれかを使用スローすることは、関数など[AfxThrowFileException](exception-processing.md#afxthrowfileexception)、定義済みの型をスローします。 このドキュメントは完全を期すのためだけに提供します。  
  
##  <a name="delete"></a>  CException::Delete  
 この関数は、かどうかを**CException** 、ヒープのオブジェクトが作成され、それを呼び出す場合は、**削除**演算子をオブジェクトにします。  
  
```  
void Delete();
```  
  
### <a name="remarks"></a>コメント  
 削除するときに、 **CException**オブジェクトを使用して、**削除**例外を削除するメンバー関数。 使用しないで、**削除**演算子を直接ため、`CException`オブジェクトのグローバル オブジェクトである可能性がありますまたはスタック上に作成されました。  
  
 オブジェクトを作成するときに、オブジェクトを削除するかどうかを指定することができます。 詳細については、次を参照してください。 [CException::CException](#cexception)です。  
  
 のみを呼び出す必要がある**削除**、C++ を使用している場合**を再試行してください**- **キャッチ**メカニズムです。 MFC のマクロを使用している場合**を再試行してください**と**キャッチ**、これらのマクロはこの関数を呼び出しては自動的にします。  
  
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
  
##  <a name="reporterror"></a>  CException::ReportError  
 ユーザーにメッセージ ボックスにエラー テキストをレポートするには、このメンバー関数を呼び出します。  
  
```  
virtual int ReportError(
    UINT nType = MB_OK,  
    UINT nMessageID = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nType`  
 メッセージ ボックスのスタイルを指定します。 任意の組み合わせを適用、[メッセージ ボックス スタイル](styles-used-by-mfc.md#message-box-styles)をボックスにします。 このパラメーターを指定しない場合、既定値は**MB_OK**です。  
  
 *nMessageID*  
 例外オブジェクトには、エラー メッセージがない場合に表示するメッセージのリソース ID (ストリング テーブル エントリ) を指定します。 0 の場合、メッセージ"エラー メッセージはありません"が表示されます。  
  
### <a name="return-value"></a>戻り値  
 `AfxMessageBox`値以外のメッセージ ボックスを表示するための十分なメモリがない場合は 0 です。 参照してください[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)の戻り値。  
  
### <a name="example"></a>例  
 使用例を次に示します`CException::ReportError`です。 別の例では、例を参照してください。[キャッチ](exception-processing.md#catch)です。  
  
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
 [CObject クラス](cobject-class.md)   
 [階層図](../hierarchy-chart.md)   
 [例外の処理](exception-processing.md)   
 [方法: 独自のカスタム例外クラスを作成します。](http://go.microsoft.com/fwlink/p/?linkid=128045)


