---
title: CDBException クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDBException
- AFXDB/CDBException
- AFXDB/CDBException::m_nRetCode
- AFXDB/CDBException::m_strError
- AFXDB/CDBException::m_strStateNativeOrigin
dev_langs:
- C++
helpviewer_keywords:
- CDBException [MFC], m_nRetCode
- CDBException [MFC], m_strError
- CDBException [MFC], m_strStateNativeOrigin
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7766b56e75edefda4f40194a5ce18572c8d6d78d
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952249"
---
# <a name="cdbexception-class"></a>CDBException クラス
データベース クラスから発生する例外状態を表現します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDBException : public CException  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDBException::m_nRetCode](#m_nretcode)|コードが含まれる、オープン データベース コネクティビティ (ODBC) 戻り値の型の**RETCODE**です。|  
|[CDBException::m_strError](#m_strerror)|英数字の用語で、エラーを説明する文字列が含まれています。|  
|[CDBException::m_strStateNativeOrigin](#m_strstatenativeorigin)|ODBC が返すエラー コードの観点からエラーを説明する文字列が含まれています。|  
  
## <a name="remarks"></a>Remarks  
 クラスには、例外の原因を確認または例外を説明するテキスト メッセージを表示するに使用できる 2 つのパブリック データ メンバーが含まれています。 `CDBException` オブジェクトが構築し、データベース クラスのメンバー関数によってスローされます。  
  
> [!NOTE]
>  このクラスは、MFC のオープン データベース コネクティビティ (ODBC) クラスの 1 つです。 代わりに、データ アクセス オブジェクト (DAO) のクラスを使用する場合を使用して[CDaoException](../../mfc/reference/cdaoexception-class.md)代わりにします。 DAO クラスの名前では、プレフィックスとして"CDao"があります。 詳細については、記事を参照してください。[概要: データベース プログラミング](../../data/data-access-programming-mfc-atl.md)です。  
  
 例外は、実行時の異常データ ソースなど、プログラムで制御できない状態に関連する場合は、またはネットワーク I/O エラー。 通常、プログラム実行の過程で表示することが期待されたエラーは通常例外考慮されません。  
  
 これらのオブジェクトのスコープ内にアクセスすることができます、**キャッチ**式。 スローすることができますも`CDBException`で独自のコードからのオブジェクト、`AfxThrowDBException`グローバル関数。  
  
 [全般]、またはについての例外処理の詳細については`CDBException`オブジェクト、記事を参照して[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)と[例外: データベースの例外](../../mfc/exceptions-database-exceptions.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDBException`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdb.h  
  
##  <a name="m_nretcode"></a>  CDBException::m_nRetCode  
 型の ODBC エラー コードを含む**RETCODE** ODBC アプリケーション プログラミング インターフェイス (API) 関数によって返されます。  
  
### <a name="remarks"></a>Remarks  
 この型には、ODBC で定義されている SQL プレフィックスが付いたコードとデータベース クラスで定義されている AFX_SQL から始まるコードが含まれています。 `CDBException`、このメンバーには、次の値のいずれかが含まれます。  
  
- **AFX_SQL_ERROR_API_CONFORMANCE**用のドライバー、`CDatabase::OpenEx`または`CDatabase::Open`呼び出しが必要な ODBC API への準拠レベル 1 に準拠していない ( **SQL_OAC_LEVEL1**)。  
  
- **AFX_SQL_ERROR_CONNECT_FAIL**データ ソースに接続できませんでした。 渡されたする、 **NULL** `CDatabase` 、レコード セットのコンス トラクターと接続を作成する後続の試行へのポインターがに基づいて`GetDefaultConnect`できませんでした。  
  
- **AFX_SQL_ERROR_DATA_TRUNCATED**の記憶域を提供するよりも多くのデータを要求します。 指定されたデータ記憶域を増やす方法について`CString`または`CByteArray`データ型を参照してください、`nMaxLength`引数[RFX_Text](record-field-exchange-functions.md#rfx_text)と[RFX_Binary](record-field-exchange-functions.md#rfx_binary)下にある"マクロとグローバル変数です。"  
  
- **AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED**への呼び出し`CRecordset::Open`ダイナセットの要求に失敗しました。 ダイナセットを使う場合は、ドライバーによってサポートされていません。  
  
- **AFX_SQL_ERROR_EMPTY_COLUMN_LIST**テーブルを開こうとした (または、指定した識別できず、プロシージャ呼び出しとしてまたは**選択**ステートメント) レコード フィールド エクス (チェンジ RFX) で識別された列がありません関数呼び出しに、`DoFieldExchange`をオーバーライドします。  
  
- **AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH**での RFX 関数の種類、`DoFieldExchange`オーバーライドは、レコード セット内の列のデータ型と互換性がありません。  
  
- **AFX_SQL_ERROR_ILLEGAL_MODE**と呼ばれる`CRecordset::Update`以前を呼び出さずに`CRecordset::AddNew`または`CRecordset::Edit`です。  
  
- **AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED** ODBC ドライバーがロックをサポートしていないために、更新用のレコードをロックする要求を処理できませんでした。  
  
- **AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED**と呼ばれる`CRecordset::Update`または`Delete`ない一意のキーを持つテーブルの複数のレコードを変更します。  
  
- **AFX_SQL_ERROR_NO_CURRENT_RECORD**を編集または削除されたレコードを削除しようとしました。 削除した後に、新しい現在のレコードをスクロールする必要があります。  
  
- **AFX_SQL_ERROR_NO_POSITIONED_UPDATES**要求、ODBC ドライバーがサポートされていないために、ダイナセットを処理できませんでしたの位置指定更新します。  
  
- **AFX_SQL_ERROR_NO_ROWS_AFFECTED**と呼ばれる`CRecordset::Update`または`Delete`レコードが見つからなくなった、操作が開始されたときに、します。  
  
- **AFX_SQL_ERROR_ODBC_LOAD_FAILED** ODBC を読み込もうとしました。DLL が失敗しました。Windows では、見つかりませんでした。 または、この DLL を読み込むことができませんでした。 このエラーは致命的です。  
  
- **AFX_SQL_ERROR_ODBC_V2_REQUIRED**レベル 2 に準拠した ODBC ドライバーが必要なために、ダイナセットの要求を処理できませんでした。  
  
- **AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY**スクロールしようとすると、ときに、データ ソースは後方スクロールをサポートしていないために失敗しました。  
  
- **AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED**への呼び出し`CRecordset::Open`スナップショットを要求に失敗しました。 ドライバーでは、スナップショットはサポートされていません。 (これにのみ発生時に ODBC カーソル ライブラリ ODBCCURS です。DLL が存在しません。)  
  
- **AFX_SQL_ERROR_SQL_CONFORMANCE**用のドライバー、`CDatabase::OpenEx`または`CDatabase::Open`呼び出しが「最小」の必要な ODBC SQL への準拠レベルに準拠していない (**以上でなければなりません**)。  
  
- **返せない場合**、ODBC ドライバーの合計サイズを指定できませんでした、`CLongBinary`データ値。 グローバル メモリ ブロック可能性がありますいないを事前に割り当てるためにこの操作は失敗します。  
  
- **AFX_SQL_ERROR_RECORDSET_READONLY**読み取り専用レコード セットを更新しようとしています。 または、データ ソースは読み取り専用です。 レコード セットと更新操作ができない、または`CDatabase`に関連付けられたオブジェクト。  
  
- **SQL_ERROR**関数が失敗しました。 ODBC 関数から返されたエラー メッセージ`SQLError`に格納されて、 **m_strError**データ メンバーです。  
  
- **SQL_INVALID_HANDLE**関数に無効な環境ハンドル、接続ハンドル、またはステートメント ハンドルのため失敗しました。 これは、プログラミング エラーを示します。 ODBC 関数から追加情報がない**SQLError**です。  
  
 SQL プレフィックスが付いたコードは、ODBC によって定義されます。 AFX プレフィックスが付いたコードは、AFXDB で定義されます。H に定義してください。  
  
##  <a name="m_strerror"></a>  CDBException::m_strError  
 例外の原因となったエラーを説明する文字列が含まれています。  
  
### <a name="remarks"></a>Remarks  
 文字列は、英数字の用語でエラーを説明します。 詳細な情報と例についてを参照してください。 **m_strStateNativeOrigin**です。  
  
##  <a name="m_strstatenativeorigin"></a>  CDBException::m_strStateNativeOrigin  
 例外の原因となったエラーを説明する文字列が含まれています。  
  
### <a name="remarks"></a>Remarks  
 文字列は、フォーム"の状態: %s、ネイティブ: %ld 元: %s"の順に、形式のコードは記述する値を置き換えなります。  
  
-   **SQLSTATE**で返される、5 文字のエラー コードを含む null で終わる文字列、 *szSqlState* ODBC 関数のパラメーター`SQLError`です。 **SQLSTATE**値は、「付録 A [ODBC エラー コード](https://msdn.microsoft.com/library/ms714687.aspx)で、 *ODBC プログラマ リファレンス*です。 例:"S0022"です。  
  
-   返されたネイティブ エラー コード、データ ソースに固有の*pfNativeError*のパラメーター、`SQLError`関数。 例: 207 です。  
  
-   返されるエラー メッセージ テキスト、*後*のパラメーター、`SQLError`関数。 このメッセージは、いくつかのかっこで囲まれた名前で構成されます。 エラーは、ユーザーにそのソースから渡されたは、各 ODBC コンポーネント (データ ソース、ドライバー、ドライバー マネージャーの) は、独自の名前を追加します。 この情報は、エラーの原因を特定するのに役立ちます。 例: [Microsoft] [ODBC SQL Server Driver] [SQL Server]  
  
 フレームワークは、エラー文字列を解釈し、そのコンポーネントに**m_strStateNativeOrigin**以外の場合は**m_strStateNativeOrigin**情報が含まれますで区切って複数のエラー、エラー改行文字。 フレームワークは、英数字のエラー テキストを**m_strError**です。  
  
 この文字列を構成するために使用するコードの詳細については、次を参照してください。、 [SQLError](https://msdn.microsoft.com/library/ms716312.aspx)で機能、 *ODBC プログラマ リファレンス*です。  
  
### <a name="example"></a>例  
  ODBC: から"状態: S0022、ネイティブ: 207、原点: [Microsoft] [ODBC SQL Server Driver] [SQL Server] の無効な列名 'ColName'"  
  
 **M_strStateNativeOrigin**:"の状態: S0022、ネイティブ: 207、原点: [Microsoft] [ODBC SQL Server Driver] [SQL Server]」  
  
 **M_strError**:「無効な列名 'ColName'」  
  
## <a name="see-also"></a>関連項目  
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDatabase クラス](../../mfc/reference/cdatabase-class.md)   
 [CRecordset クラス](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange クラス](../../mfc/reference/cfieldexchange-class.md)   
 [CRecordset::Update](../../mfc/reference/crecordset-class.md#update)   
 [CRecordset::Delete](../../mfc/reference/crecordset-class.md#delete)   
 [CException クラス](../../mfc/reference/cexception-class.md)
