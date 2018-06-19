---
title: 例外の処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.exceptions
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a24d78089e468a2020e0ecdb1fba34783965325
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376989"
---
# <a name="exception-processing"></a>例外処理
プログラムを実行するとき、多くの異常な状態と「例外」というエラーが発生する可能性がします。 これらには、メモリ、リソース割り当てのエラー、およびファイルを検索する障害の不足が含まれます。  
  
 Microsoft Foundation Class ライブラリでは、いずれかの C++ の場合、ANSI 標準委員会によって提案された後に密接にモデル化例外処理パターンを使用します。 異常状態に陥る可能性があります関数を呼び出す前に、例外ハンドラーの設定を作成する必要があります。 関数には、異常な状態が発生すると、例外がスローし、例外ハンドラーに制御が渡されます。  
  
 Microsoft Foundation Class ライブラリに含まれているいくつかのマクロは、例外ハンドラーを設定します。 他のグローバル関数の数は、必要に応じて、特殊な例外をスローして、プログラムを終了に役立ちます。 これらのマクロとグローバル関数は、次のカテゴリに分類されます。  
  
- 例外処理マクロは、例外ハンドラーを構成します。  
  
- 関数を Exception-throwing)、特定の種類の例外を生成します。  
  
- 終了関数には、プログラムの終了が発生します。  
  
 例と詳細については、記事を参照してください。[例外](../../mfc/exception-handling-in-mfc.md)です。  
  
### <a name="exception-macros"></a>例外処理マクロ  
  
|||  
|-|-|  
|[再試行してください。](#try)|例外の処理用のコード ブロックを指定します。|  
|[CATCH](#catch)|前述からの例外をキャッチするためのコードのブロックを指定**再試行**ブロックします。|  
|[CATCH_ALL](#catch_all)|上記のすべての例外をキャッチするためのコードのブロックを指定**再試行**ブロックします。|  
|[AND_CATCH](#and_catch)|上記から追加の例外型をキャッチするためのコードのブロックを指定**再試行**ブロックします。|  
|[AND_CATCH_ALL](#and_catch_all)|他のすべての直前に追加の例外の種類をキャッチするためのコードのブロックを指定**再試行**ブロックします。|  
|[END_CATCH](#end_catch)|最後の終了**キャッチ**または`AND_CATCH`コード ブロック。|  
|[END_CATCH_ALL](#end_catch_all)|最後の終了`CATCH_ALL`コード ブロック。|  
|[スローします。](#throw)|指定した例外をスローします。|  
|[THROW_LAST](#throw_last)|[次へ] の外側のハンドラーを現在処理されている例外をスローします。|  
  
### <a name="exception-throwing-functions"></a>例外スロー関数  
  
|||  
|-|-|  
|[AfxThrowArchiveException](#afxthrowarchiveexception)|アーカイブの例外をスローします。|  
|[AfxThrowFileException](#afxthrowfileexception)|ファイルの例外をスローします。|  
|[AfxThrowInvalidArgException](#afxthrowinvalidargexception)|無効な引数の例外をスローします。|
|[AfxThrowMemoryException](#afxthrowmemoryexception)|メモリ不足の例外をスローします。|  
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|サポートしていない例外がスローされます。|  
|[AfxThrowResourceException](#afxthrowresourceexception)|Windows リソースが見つからないの例外をスローします。|  
|[AfxThrowUserException](#afxthrowuserexception)|プログラムのユーザーによる操作で例外をスローします。|  
  
 MFC には、OLE の例外を具体的には 2 つの例外スロー関数が用意されています。  
  
### <a name="ole-exception-functions"></a>OLE 例外関数  
  
|||  
|-|-|  
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|OLE オートメーション関数内で例外をスローします。|  
|[AfxThrowOleException](#afxthrowoleexception)|OLE 例外をスローします。|  
  
 データベース クラスが 2 つの例外クラスを提供するデータベースの例外をサポートする`CDBException`と`CDaoException`、および例外の種類をサポートするためにグローバル関数。  
  
### <a name="dao-exception-functions"></a>DAO 例外関数  
  
|||  
|-|-|  
|[AfxThrowDAOException](#afxthrowdaoexception)|スロー、 [CDaoException](../../mfc/reference/cdaoexception-class.md)独自のコードからです。|  
|[AfxThrowDBException](#afxthrowdbexception)|スロー、 [CDBException](../../mfc/reference/cdbexception-class.md)独自のコードからです。|  
  
 MFC には、次の終了関数が用意されています。  
  
### <a name="termination-functions"></a>終了関数  
  
|||  
|-|-|  
|[AfxAbort](#afxabort)|呼ばれるときに致命的なエラーにアプリケーションを終了するに発生します。|  
  
##  <a name="try"></a>  再試行してください。  
 設定、**再試行**ブロックします。  
  
```   
TRY   
```  
  
### <a name="remarks"></a>コメント  
 A**再試行**ブロックが例外をスローするコードのブロックを指定します。 これらの例外は、次に**キャッチ**と`AND_CATCH`ブロックします。 再帰が許可されている: 例外は、外側に渡される可能性があります**再試行**を無視するかを使用して、ブロック、`THROW_LAST`マクロ。 終了、**再試行**ブロックを`END_CATCH`または`END_CATCH_ALL`マクロです。  
  
 詳細については、記事を参照してください。[例外](../../mfc/exception-handling-in-mfc.md)です。  
  
### <a name="example"></a>例  
 例を参照して[キャッチ](#catch)です。  

### <a name="requirements"></a>要件
ヘッダー: afx.h

##  <a name="catch"></a>  CATCH  
 最初に、上記でスローされた例外の種類をキャッチするコードのブロックを定義**再試行**ブロックします。  
  
```   
CATCH(exception_class, exception_object_pointer_name)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 *exception_class*  
 テストするための例外の種類を指定します。 標準の例外クラスの一覧は、クラスを参照してください。 [CException](../../mfc/reference/cexception-class.md)です。  
  
 *ことは*  
 マクロにより作成される例外オブジェクト ポインターの名前を指定します。 内の例外オブジェクトにアクセスするポインターの名前を使用することができます、**キャッチ**ブロックします。 この変数を宣言します。  
  
### <a name="remarks"></a>コメント  
 例外処理コードは、必要に応じて、例外の特定の原因に関する詳細情報を取得する例外オブジェクトを問い合わせることができます。 呼び出す、`THROW_LAST`処理を外側の例外の次のフレームにシフトするマクロです。 終了、**再試行**ブロックを`END_CATCH`マクロです。  
  
 場合*exception_class*クラス`CException`、すべての例外の種類をキャッチし、します。 使用することができます、[使うため](../../mfc/reference/cobject-class.md#iskindof)メンバー関数を決定する特定の例外がスローされました。 いくつかの種類の例外をキャッチする優れた方法としては、シーケンシャルを使用する`AND_CATCH`ステートメントは、それぞれに異なる例外の種類。  
  
 マクロでは、例外オブジェクトへのポインターが作成されます。 自分で宣言する必要はありません。  
  
> [!NOTE]
>  **キャッチ**ブロックは中かっこで囲んで示して C++ スコープとして定義します。 このスコープで変数を宣言する場合は、そのスコープ内でのみ利用可能です。 これにも当てはまります*ことは*します。  
  
 例外の詳細については、**キャッチ**マクロ、記事を参照して[例外](../../mfc/exception-handling-in-mfc.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCExceptions#26](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]  
  
##  <a name="catch_all"></a>  CATCH_ALL  
 上記でスローされたすべての例外の種類をキャッチするコードのブロックを定義**再試行**ブロックします。  
  
```   
CATCH_ALL(exception_object_pointer_name)   
```  
  
### <a name="parameters"></a>パラメーター  
 *ことは*  
 マクロにより作成される例外オブジェクト ポインターの名前を指定します。 内の例外オブジェクトにアクセスするポインターの名前を使用することができます、`CATCH_ALL`ブロックします。 この変数を宣言します。  
  
### <a name="remarks"></a>コメント  
 例外処理コードは、必要に応じて、例外の特定の原因に関する詳細情報を取得する例外オブジェクトを問い合わせることができます。 呼び出す、`THROW_LAST`処理を外側の例外の次のフレームにシフトするマクロです。 使用する場合`CATCH_ALL`、終了、**再試行**ブロックを`END_CATCH_ALL`マクロです。  
  
> [!NOTE]
>  `CATCH_ALL`ブロックは中かっこで囲んで示して C++ スコープとして定義します。 このスコープで変数を宣言する場合は、そのスコープ内でのみ利用可能です。  
  
 例外の詳細については、記事を参照してください。[例外](../../mfc/exception-handling-in-mfc.md)です。  
  
### <a name="example"></a>例  
 例を参照して[解放](../../mfc/reference/cfile-class.md#abort)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  

##  <a name="and_catch"></a>  AND_CATCH  
 直前に追加の例外型をキャッチするためのコードのブロックを定義**再試行**ブロックします。  
  
```   
AND_CATCH(exception_class, exception_object_pointer_name)   
```  
  
### <a name="parameters"></a>パラメーター  
 *exception_class*  
 テストするための例外の種類を指定します。 標準の例外クラスの一覧は、クラスを参照してください。 [CException](../../mfc/reference/cexception-class.md)です。  
  
 *ことは*  
 マクロにより作成される例外オブジェクトのポインターの名前。 内の例外オブジェクトにアクセスするポインターの名前を使用することができます、`AND_CATCH`ブロックします。 この変数を宣言します。  
  
### <a name="remarks"></a>コメント  
 使用して、**キャッチ**1 つの例外の種類をキャッチする、`AND_CATCH`マクロをキャッチします。 終了、**再試行**ブロックを`END_CATCH`マクロです。  
  
 例外処理コードは、必要に応じて、例外の特定の原因に関する詳細情報を取得する例外オブジェクトを問い合わせることができます。 呼び出す、`THROW_LAST`内でのマクロ、 `AND_CATCH` shift キーを押し、[次へ] の外側の例外フレームを処理するブロックします。 `AND_CATCH` 上記の末尾をマーク**キャッチ**または`AND_CATCH`ブロックします。  
  
> [!NOTE]
>  `AND_CATCH`ブロックは、C++ のスコープ (中かっこで囲んで示して) として定義します。 このスコープ内の変数を宣言する場合は、そのスコープ内でのみアクセスされることに注意してください。 これにも当てはまります、*ことは*変数。  
  
### <a name="example"></a>例  
 例を参照して[キャッチ](#catch)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
##  <a name="and_catch_all"></a>  AND_CATCH_ALL  
 直前に追加の例外型をキャッチするためのコードのブロックを定義**再試行**ブロックします。  
  
```   
AND_CATCH_ALL(exception_object_pointer_name)  
```  
  
### <a name="parameters"></a>パラメーター  
 *ことは*  
 マクロにより作成される例外オブジェクトのポインターの名前。 内の例外オブジェクトにアクセスするポインターの名前を使用することができます、`AND_CATCH_ALL`ブロックします。 この変数を宣言します。  
  
### <a name="remarks"></a>コメント  
 使用して、**キャッチ**1 つの例外の種類をキャッチする、`AND_CATCH_ALL`マクロを他のすべての後続の種類をキャッチします。 使用する場合`AND_CATCH_ALL`、終了、**再試行**ブロックを`END_CATCH_ALL`マクロです。  
  
 例外処理コードは、必要に応じて、例外の特定の原因に関する詳細情報を取得する例外オブジェクトを問い合わせることができます。 呼び出す、`THROW_LAST`内でのマクロ、 `AND_CATCH_ALL` shift キーを押し、[次へ] の外側の例外フレームを処理するブロックします。 `AND_CATCH_ALL` 上記の末尾をマーク**キャッチ**または`AND_CATCH_ALL`ブロックします。  
  
> [!NOTE]
>  `AND_CATCH_ALL`ブロックは、C++ のスコープ (中かっこで囲んで示して) として定義します。 このスコープ内の変数を宣言する場合は、そのスコープ内でのみアクセスされることに注意してください。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="end_catch"></a>  END_CATCH  
 最後の終了をマーク**キャッチ**または`AND_CATCH`ブロックします。  
  
```   
END_CATCH  
```  
  
### <a name="remarks"></a>コメント  
 詳細については、`END_CATCH`マクロ、記事を参照して[例外](../../mfc/exception-handling-in-mfc.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="end_catch_all"></a>  END_CATCH_ALL  
 最後の終了をマーク`CATCH_ALL`または`AND_CATCH_ALL`ブロックします。  
  
```   
END_CATCH_ALL  
```  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="throw"></a>  スロー (MFC)  
 指定された例外をスローします。  
  
```   
THROW(exception_object_pointer) 
```  
  
### <a name="parameters"></a>パラメーター  
 *exception_object_pointer*  
 派生した例外オブジェクトへのポインター`CException`です。  
  
### <a name="remarks"></a>コメント  
 **スロー**割り込みプログラムの実行を関連付けられているコントロールを渡す**キャッチ**でプログラムをブロックします。 提供されていない場合、**キャッチ**コントロールが、エラーを出力メッセージを終了する Microsoft Foundation Class ライブラリ モジュールに渡され、ブロックします。  
  
 詳細については、記事を参照してください。[例外](../../mfc/exception-handling-in-mfc.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="throw_last"></a>  THROW_LAST  
 例外を次にスローバック外部**キャッチ**ブロックします。  
  
```   
THROW_LAST()   
```  
  
### <a name="remarks"></a>コメント  
 このマクロでは、ローカルで作成された例外をスローすることができます。 キャッチした例外をスローしようとする場合はスコープ外に出るは通常され、削除されます。 `THROW_LAST`、[次へ] を正常に渡された例外**キャッチ**ハンドラー。  
  
 詳細については、記事を参照してください。[例外](../../mfc/exception-handling-in-mfc.md)です。  
  
### <a name="example"></a>例  
 例を参照して[解放](../../mfc/reference/cfile-class.md#abort)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="afxthrowarchiveexception"></a>  AfxThrowArchiveException  
 アーカイブの例外をスローします。  
  
```   
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName); 
```  
  
### <a name="parameters"></a>パラメーター  
 `cause`  
 例外の原因を示す整数を指定します。 有効な値の一覧は、次を参照してください。 [CArchiveException::m_cause](../../mfc/reference/carchiveexception-class.md#m_cause)です。  
  
 `lpszArchiveName`  
 名前を含む文字列を指す、 `CArchive` (使用可能な場合)、例外の原因となったオブジェクトです。  
  
### <a name="requirements"></a>要件  
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
 `cause`  
 例外の原因を示す整数を指定します。 有効な値の一覧は、次を参照してください。[については、「](../../mfc/reference/cfileexception-class.md#m_cause)です。  
  
 `lOsError`  
 オペレーティング システムのエラー番号が含まれています (ある場合)、例外の原因を示すです。 エラー コードの一覧については、オペレーティング システムのマニュアルを参照してください。  
  
 `lpszFileName`  
 (該当する場合)、例外の原因となったファイルの名前を含む文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 オペレーティング システム エラー コードに基づく原因を特定するを担当しています。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  

## <a name="afxthrowinvalidargexception"></a>  AfxThrowInvalidArgException
無効な引数の例外をスローします。  
   
### <a name="syntax"></a>構文    
```
void AfxThrowInvalidArgException( );  
```  
   
### <a name="remarks"></a>コメント  
 無効な引数を使用する場合は、この関数が呼び出されます。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
 [CInvalidArgException クラス](cinvalidargexception-class.md)   
 [スローします。](#throw)
  
  
##  <a name="afxthrowmemoryexception"></a>  AfxThrowMemoryException  
 メモリ不足の例外をスローします。  
  
```   
void AfxThrowMemoryException(); 
```  
  
### <a name="remarks"></a>コメント  
 場合、この関数を呼び出す基になるシステム メモリ アロケーターへの呼び出し (など`malloc`と[GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) Windows 関数) は失敗します。 呼び出す必要はありません**新しい**ため**新しい**メモリ割り当てに失敗した場合に自動的にメモリ不足例外がスローされます。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="afxthrownotsupportedexception"></a>  AfxThrowNotSupportedException  
 サポートされていない機能を要求の結果である例外をスローします。  
  
```  
void AfxThrowNotSupportedException(); 
```  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="afxthrowresourceexception"></a>  AfxThrowResourceException  
 リソースの例外をスローします。  
  
```   
void  AfxThrowResourceException(); 
```  
  
### <a name="remarks"></a>コメント  
 この関数は通常、Windows のリソースを読み込むことができないときに呼び出されます。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="afxthrowuserexception"></a>  AfxThrowUserException  
 エンドユーザーの操作を停止する例外をスローします。  
  
```   
void AfxThrowUserException(); 
```  
  
### <a name="remarks"></a>コメント  
 この関数は通常、直後に呼び出される`AfxMessageBox`をユーザーに、エラーが発生しました。  
  
### <a name="requirements"></a>要件  
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
 `wCode`  
 アプリケーションに固有のエラー コード。  
  
 `lpszDescription`  
 エラーの口頭で説明します。  
  
 `nDescriptionID`  
 文章によるエラーの説明のリソース ID です。  
  
 `nHelpID`  
 アプリケーションのヘルプのヘルプ コンテキスト (です。HLP) ファイルです。  
  
### <a name="remarks"></a>コメント  
 駆動アプリケーション (Microsoft Visual Basic または別の OLE オートメーション クライアント アプリケーション) では、この関数に指定された情報を表示できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCExceptions#25](../../mfc/codesnippet/cpp/exception-processing_2.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="afxthrowoleexception"></a>  AfxThrowOleException  
 型のオブジェクトを作成する`COleException`例外をスローします。  
  
``` 
void AFXAPI AfxThrowOleException(SCODE sc);
void AFXAPI AfxThrowOleException(HRESULT hr); 
```  
  
### <a name="parameters"></a>パラメーター  
 `sc`  
 OLE ステータス コードの例外の理由を示します。  
  
 `hr`  
 例外の理由を示す結果コードへのハンドルします。  
  
### <a name="remarks"></a>コメント  
 受け取るバージョンで、`HRESULT`引数に変換結果コード、対応するよう`SCODE`です。 詳細については`HRESULT`と`SCODE`を参照してください[COM エラー コードの構造体](http://msdn.microsoft.com/library/windows/desktop/ms690088)Windows SDK に含まれています。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
  
##  <a name="afxthrowdaoexception"></a>  AfxThrowDaoException  
 型の例外をスローするには、この関数を呼び出す[CDaoException](../../mfc/reference/cdaoexception-class.md)独自のコードからです。  
  
```   
void AFXAPI AfxThrowDaoException(
    int nAfxDaoError = NO_AFX_DAO_ERROR,  
    SCODE scode = S_OK); 
```  
  
### <a name="parameters"></a>パラメーター  
 `nAfxDaoError`  
 DAO の拡張エラー コードを表す整数値、することができます、値の 1 つ下に表示[CDaoException::m_nAfxDaoError](../../mfc/reference/cdaoexception-class.md#m_nafxdaoerror)です。  
  
 *scode*  
 型の DAO から OLE エラー コード`SCODE`です。 詳細については、次を参照してください。 [CDaoException::m_scode](../../mfc/reference/cdaoexception-class.md#m_scode)です。  
  
### <a name="remarks"></a>コメント  
 フレームワークによって呼び出されますも`AfxThrowDaoException`します。 呼び出しでは、パラメーターのいずれかまたは両方を渡すことができます。 たとえばのいずれかが発生する場合、エラーで定義されている**CDaoException::nAfxDaoError**を気にせず、 *scode*パラメーターで有効なコードを渡す、`nAfxDaoError`パラメーターを受け入れると、既定値を*scode*です。  
  
 MFC DAO クラスに関連する例外については、クラスを参照してください。`CDaoException`本書と、アーティクルで[例外: データベースの例外](../../mfc/exceptions-database-exceptions.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdb.h  
  
##  <a name="afxthrowdbexception"></a>  AfxThrowDBException  
 型の例外をスローするには、この関数を呼び出す`CDBException`独自のコードからです。  
  
```  
void AfxThrowDBException(
    RETCODE nRetCode,  
    CDatabase* pdb,  
    HSTMT hstmt);  
```  
  
### <a name="parameters"></a>パラメーター  
 `nRetCode`  
 型の値**RETCODE**例外がスローされる原因となったエラーの種類を定義します。  
  
 `pdb`  
 ポインター、`CDatabase`例外が関連付けられているデータ ソース接続を表すオブジェクト。  
  
 `hstmt`  
 ODBC **HSTMT**例外が関連付けられているステートメント ハンドルを指定するハンドル。  
  
### <a name="remarks"></a>コメント  
 フレームワークによって`AfxThrowDBException`受信すると、ODBC **RETCODE** ODBC API の呼び出しから関数および解釈、 **RETCODE** expectable エラーではなく、例外が発生します。 たとえば、データ アクセス操作ディスクの読み取りエラーのため失敗します。  
  
 については、 **RETCODE** ODBC で定義されている値は、Windows SDK の第 8 章「を取得するステータスおよびエラーについては、」を参照してください。 これらのコードに MFC の拡張機能の概要については、クラスを参照してください。 [CDBException](../../mfc/reference/cdbexception-class.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="afxabort"></a>  AfxAbort  
 MFC によって提供される既定の終了関数。  
  
```   
void  AfxAbort(); 
```  
  
### <a name="remarks"></a>コメント  
 `AfxAbort` 内部的に呼び出されます MFC メンバー関数によってキャッチされない例外は処理できないなどの致命的なエラーがある場合。 呼び出すことができます`AfxAbort`まれな場合は、回復することはできません、致命的なエラーが発生したときにします。  
  
### <a name="example"></a>例  
 例を参照して[キャッチ](#catch)です。  

### <a name="requirements"></a>要件  
  **ヘッダー** afx.h   
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)   
 [CException クラス](../../mfc/reference/cexception-class.md)
