---
title: CDaoException クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoException
- AFXDAO/CDaoException
- AFXDAO/CDaoException::CDaoException
- AFXDAO/CDaoException::GetErrorCount
- AFXDAO/CDaoException::GetErrorInfo
- AFXDAO/CDaoException::m_nAfxDaoError
- AFXDAO/CDaoException::m_pErrorInfo
- AFXDAO/CDaoException::m_scode
dev_langs:
- C++
helpviewer_keywords:
- CDaoException [MFC], CDaoException
- CDaoException [MFC], GetErrorCount
- CDaoException [MFC], GetErrorInfo
- CDaoException [MFC], m_nAfxDaoError
- CDaoException [MFC], m_pErrorInfo
- CDaoException [MFC], m_scode
ms.assetid: b2b01fa9-7ce2-42a1-842e-40f13dc50da4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4531d63ff7047881f20368cbeaf8e5de4136bb9f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369217"
---
# <a name="cdaoexception-class"></a>CDaoException クラス
データ アクセス オブジェクト (DAO: Data Accsess Object) を基にした MFC データベース クラスから発生する例外条件を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDaoException : public CException  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoException::CDaoException](#cdaoexception)|`CDaoException` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[あります。](#geterrorcount)|データベース エンジンのエラーのコレクション内のエラーの数を返します。|  
|[CDaoException::GetErrorInfo](#geterrorinfo)|Errors コレクションで特定のエラー オブジェクトに関するエラー情報を返します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoException::m_nAfxDaoError](#m_nafxdaoerror)|MFC DAO クラスで、エラーの拡張エラー コードが含まれています。|  
|[CDaoException::m_pErrorInfo](#m_perrorinfo)|ポインター、 [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) DAO エラーの 1 つのオブジェクトに関する情報を含むオブジェクト。|  
|[CDaoException::m_scode](#m_scode)|[SCODE](#m_scode)エラーに関連付けられている値。|  
  
## <a name="remarks"></a>コメント  
 クラスには、例外の原因を調べて使用できるパブリック データ メンバーが含まれています。 `CDaoException` オブジェクトが構築し、DAO データベース クラスのメンバー関数によってスローされます。  
  
> [!NOTE]
>  DAO データベース クラスは、MFC データベース クラス ODBC Open Database Connectivity () をベースとは異なります。 DAO データベース クラスの名前では、"CDao"プレフィックスがあります。 DAO クラスで ODBC データ ソースのアクセスすることもできます。 一般に、DAO に基づいて MFC クラスは ODBC; に基づいて MFC クラスよりもより高機能ですDAO ベースのクラスは、独自のデータベース エンジンを使用して、ODBC ドライバーを介してなどのデータにアクセスできます。 DAO ベースのクラスには、DAO を直接呼び出すことがなく、クラスを使用してテーブルの追加などのデータ定義言語 (DDL) 操作もサポートします。 ODBC クラスによってスローされる例外については、次を参照してください。 [CDBException](../../mfc/reference/cdbexception-class.md)です。  
  
 スコープ内の例外オブジェクトにアクセスすることができます、[キャッチ](../../mfc/reference/exception-processing.md#catch)式。 スローすることができますも`CDaoException`で独自のコードからのオブジェクト、 [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception)グローバル関数。  
  
 MFC では、DAO のすべてのエラーが型の例外で表される`CDaoException`です。 この型の例外をキャッチする場合に行うこともできます`CDaoException`データベース エンジンのエラー コレクションに格納されている DAO エラー オブジェクトから情報を取得するメンバー関数。 各エラーが発生すると、1 つ以上のエラー オブジェクトがエラー コレクションに配置されます。 (通常、コレクションには、1 つだけのエラー オブジェクトが含まれています。 複数のエラー オブジェクトを取得する可能性が高くなりますが、ODBC データ ソースを使用している場合)DAO の別の操作は、エラーを生成するとき、エラーのコレクションをクリアし、エラー コレクションに新しいエラー オブジェクトを配置します。 エラーを生成しない DAO 操作はエラー コレクションに影響を与えるありません。  
  
 DAO エラー コード、DAOERR ファイルを参照してください。H. 関連情報については、「トラップできるデータ アクセス エラー」DAO ヘルプのトピックを参照してください。  
  
 [全般]、またはについての例外処理の詳細については`CDaoException`オブジェクト、記事を参照して[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)と[例外: データベースの例外](../../mfc/exceptions-database-exceptions.md)です。 2 番目の記事には、例外処理、DAO を示したサンプル コードが含まれています。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDaoException`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
##  <a name="cdaoexception"></a>  CDaoException::CDaoException  
 `CDaoException` オブジェクトを構築します。  
  
```  
CDaoException();
```  
  
### <a name="remarks"></a>コメント  
 通常は、フレームワークは、そのコードによって例外がスローされる例外オブジェクトを作成します。 頻度の低い例外オブジェクトを明示的に作成する必要があります。 スローする場合、`CDaoException`独自のコードからグローバル関数を呼び出し[AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception)です。  
  
 ただし、MFC クラスをカプセル化する DAO インターフェイス ポインターを使用して DAO の直接呼び出しを行う場合、例外オブジェクトを明示的に作成することができます。 その場合は、DAO からエラー情報を取得する必要があります。 ワークスペースのデータベース コレクションに DAODatabases インターフェイスを使用して、DAO メソッドを呼び出すと、DAO でのエラーが発生したとします。  
  
##### <a name="to-retrieve-the-dao-error-information"></a>DAO エラー情報を取得するには  
  
1.  `CDaoException` オブジェクトを構築します。  
  
2.  例外オブジェクトの[GetErrorCount](#geterrorcount)メンバー関数は、データベース エンジンのエラーのコレクション内のエラー オブジェクトの数を調べることです。 (通常 1 つだけ、ODBC データ ソースを使用している場合を除き、します)。  
  
3.  例外オブジェクトの[GetErrorInfo](#geterrorinfo)例外オブジェクトを使用して、コレクション内のインデックスを使用して、一度に 1 つの特定のエラー オブジェクトを取得します。 例外オブジェクトの 1 つの DAO エラー オブジェクト用にプロキシとして考えます。  
  
4.  現在の確認[CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md)構造体`GetErrorInfo`内を返します、 [m_pErrorInfo](#m_perrorinfo)データ メンバーです。 そのメンバーは、DAO エラーに関する情報を提供します。  
  
5.  ODBC データ ソースの場合は、手順 3. および 4. より多くのエラー オブジェクトは、必要に応じてを繰り返します。  
  
6.  ヒープ上の例外オブジェクトを構築する場合にそれを削除、**削除**演算子が完了したときにします。  
  
 については、MFC DAO クラスでのエラー処理の詳細については、「[例外: データベースの例外](../../mfc/exceptions-database-exceptions.md)です。  
  
##  <a name="geterrorcount"></a>  あります。  
 DAO データベース エンジンのエラーのコレクションのオブジェクトのエラーの数を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetErrorCount();
```  
  
### <a name="return-value"></a>戻り値  
 DAO データベース エンジンのエラーのコレクションのオブジェクトのエラーの数。  
  
### <a name="remarks"></a>コメント  
 この情報はそれぞれ、1 つまたは複数 DAO エラー内のオブジェクトのコレクションを取得するエラーのコレクションをループに役立ちます。 インデックスまたは DAO エラー番号で、エラー オブジェクトを取得する、 [GetErrorInfo](#geterrorinfo)メンバー関数。  
  
> [!NOTE]
>  通常 1 つだけエラーにオブジェクトがエラー コレクションです。 ODBC データ ソースで作業している場合があります 1 つ以上。  
  
##  <a name="geterrorinfo"></a>  CDaoException::GetErrorInfo  
 Errors コレクションで特定のエラー オブジェクトに関するエラー情報を返します。  
  
```  
void GetErrorInfo(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 インデックスで検索する場合、データベース エンジンのエラー コレクションにエラー情報のインデックス。  
  
### <a name="remarks"></a>コメント  
 次の種類の例外に関する情報を取得するには、このメンバー関数を呼び出します。  
  
-   エラー コード  
  
-   ソース  
  
-   説明  
  
-   ヘルプ ファイル  
  
-   ヘルプ コンテキスト  
  
 `GetErrorInfo` 例外オブジェクトの情報を格納`m_pErrorInfo`データ メンバーです。 返される情報の簡単な説明を参照してください。 [m_pErrorInfo](#m_perrorinfo)です。 型の例外をキャッチする場合`CDaoException`、MFC によってスローされた、`m_pErrorInfo`メンバーが既に入力されます。 DAO を直接呼び出す場合は、呼び出す必要がありますは例外オブジェクトの`GetErrorInfo`メンバー関数は、入力を自分で`m_pErrorInfo`です。 詳細については、次を参照してください。、 [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md)構造体。  
  
 DAO 例外、およびコード例については、記事を参照してください。[例外: データベースの例外](../../mfc/exceptions-database-exceptions.md)です。  
  
##  <a name="m_nafxdaoerror"></a>  CDaoException::m_nAfxDaoError  
 MFC 拡張エラー コードが含まれています。  
  
### <a name="remarks"></a>コメント  
 このコードは、MFC DAO クラスの特定のコンポーネントが下がの場合で提供されます。  
  
 指定できる値は次のとおりです。  
  
- **NO_AFX_DAO_ERROR**最新の操作は、MFC の拡張エラーになりませんでした。 ただし、操作でしたによって生成された DAO または OLE から他のエラーを確認する必要がありますので[m_pErrorInfo](#m_perrorinfo)と場合によっては[m_scode](#m_scode)です。  
  
- **AFX_DAO_ERROR_ENGINE_INITIALIZATION** MFC は、Microsoft Jet データベース エンジンを初期化できませんでした。 OLE は初期化に失敗した可能性があります。 またはそれが解除された可能性が DAO データベース エンジン オブジェクトのインスタンスを作成することです。 これらの問題は、通常、DAO または OLE のいずれかの不適切なインストールを推奨します。  
  
- **AFX_DAO_ERROR_DFX_BIND** DAO レコード フィールド エクス (チェンジ DFX) 関数の呼び出しで使用するアドレスが存在しないか無効です (アドレスがデータ バインドには使用されません)。 DFX 呼び出しに無効なアドレスを渡された可能性があります。 またはアドレスが無効になった DFX 操作します。  
  
- **AFX_DAO_ERROR_OBJECT_NOT_OPEN**クエリ定義または開いている状態ではないテーブル定義オブジェクトに基づくレコード セットを開こうとしました。  
  
##  <a name="m_perrorinfo"></a>  CDaoException::m_pErrorInfo  
 ポインターが含まれています、`CDaoErrorInfo`最後に呼び出すことによって取得する DAO エラー オブジェクト情報を提供する構造体[GetErrorInfo](#geterrorinfo)です。  
  
### <a name="remarks"></a>コメント  
 このオブジェクトには、次の情報が含まれています。  
  
|CDaoErrorInfo メンバー|情報|説明|  
|--------------------------|-----------------|-------------|  
|**m_lErrorCode**|エラー コード|DAO エラー コード|  
|`m_strSource`|ソース|最初に発生したエラーをオブジェクトまたはアプリケーションの名前|  
|`m_strDescription`|説明|エラーに関連付けられているわかりやすい文字列|  
|`m_strHelpFile`|ヘルプ ファイル|ユーザーが、問題に関する情報を取得できる、Windows のヘルプ ファイルへのパス|  
|**m_lHelpContext**|ヘルプ コンテキスト|DAO のヘルプ ファイルのトピックのコンテキスト ID|  
  
 含まれる情報の詳細について、`CDaoErrorInfo`オブジェクトを参照してください、 [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md)構造体。  
  
##  <a name="m_scode"></a>  CDaoException::m_scode  
 型の値を含む`SCODE`エラーを説明します。  
  
### <a name="remarks"></a>コメント  
 これは、OLE コードです。 ほとんどの場合、MFC または DAO エラーの詳細については、他の使用可能なため、この値を使用する必要があります頻度の低い`CDaoException`データ メンバーです。  
  
 については`SCODE`、トピックを参照して[構造体の OLE エラー コード](http://msdn.microsoft.com/library/windows/desktop/ms690088)Windows SDK に含まれています。 `SCODE`データ型にマップ、`HRESULT`データ型。  
  
## <a name="see-also"></a>関連項目  
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CException クラス](../../mfc/reference/cexception-class.md)
