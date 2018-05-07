---
title: 'レコード セット: バルク行フェッチ (ODBC) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- bulk row fetching, implementing
- ODBC recordsets, bulk row fetching
- bulk record field exchange
- bulk row fetching
- bulk RFX functions
- recordsets, bulk row fetching
- DoBulkFieldExchange method
- fetching ODBC records in bulk
- RFX (ODBC), bulk
- rowsets, bulk row fetching
- RFX (ODBC), bulk row fetching
ms.assetid: 20d10fe9-c58a-414a-b675-cdf9aa283e4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8ef8803459edeba98e472a0e7fd07e7f5daf2c4e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-fetching-records-in-bulk-odbc"></a>レコードセット: バルク行フェッチ (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 クラス`CRecordset`複数のレコードできますから取得することを一度に取得する 1 つのレコードではなく、1 回のフェッチ中に、時に、データ ソースは、バルク行フェッチのサポートを提供します。 派生でのみバルク行フェッチを実装する`CRecordset`クラスです。 レコード セット オブジェクトにデータ ソースからデータを転送するプロセスは、バルク レコード フィールド エクス チェンジ (Bulk RFX) と呼ばれます。 バルク行フェッチを使用しない場合、 `CRecordset`-派生クラス、データは、レコード フィールド エクス (チェンジ RFX) 経由で転送します。 詳細については、次を参照してください。[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)です。  
  
 このトピックでは、次の内容について説明します。  
  
-   [CRecordset がサポートするしくみバルク行フェッチ](#_core_how_crecordset_supports_bulk_row_fetching)です。  
  
-   [特別な考慮事項を使用する場合はバルク行フェッチ](#_core_special_considerations)です。  
  
-   [バルク レコード フィールド エクス チェンジの実装方法](#_core_how_to_implement_bulk_record_field_exchange)です。  
  
##  <a name="_core_how_crecordset_supports_bulk_row_fetching"></a> CRecordset がバルク行フェッチをサポートする方法  
 レコード セット オブジェクトを開く前に、行セットのサイズを定義することができます、`SetRowsetSize`メンバー関数。 行セットのサイズは、1 回のフェッチ中に取得するレコードの数を指定します。 バルク行フェッチが実装された場合、既定の行セット サイズは 25 です。 バルク行フェッチが実装されていない場合、行セットのサイズは 1 に固定されたままです。  
  
 行セットのサイズを初期化すると、呼び出し、[開く](../../mfc/reference/crecordset-class.md#open)メンバー関数。 ここで指定する必要があります、`CRecordset::useMultiRowFetch`のオプション、 **dwOptions**バルク行フェッチを実装するパラメーターです。 さらに設定することができます、 **crecordset::userallocmultirowbuffers**オプション。 バルク レコード フィールド エクス機構は、複数の行のフェッチ中に取得されるデータを格納するのに配列を使用します。 これらの記憶域バッファーは、フレームワークによって自動的に割り当てることができるかに手動で割り当てることができます。 指定する、 **crecordset::userallocmultirowbuffers**オプションは、割り当てを行うことを意味します。  
  
 次の表は、メンバー関数によって提供される`CRecordset`バルク行フェッチをサポートするためにします。  
  
|メンバー関数|説明|  
|---------------------|-----------------|  
|[CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)|フェッチ中に発生したエラーを処理する仮想関数。|  
|[DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)|レコード フィールド エクス チェンジの一括を実装します。 自動的に呼び出されます転送を複数行のデータをレコード セット オブジェクトにデータ ソースからです。|  
|[GetRowsetSize](../../mfc/reference/crecordset-class.md#getrowsetsize)|行セットのサイズの現在の設定を取得します。|  
|[GetRowsFetched](../../mfc/reference/crecordset-class.md#getrowsfetched)|行の数が指定されたフェッチ後に実際に取得されたに指示します。 ほとんどの場合、これは、行セット サイズを除いて、不完全な行セットがフェッチされました。|  
|[GetRowStatus](../../mfc/reference/crecordset-class.md#getrowstatus)|行セット内の特定の行のフェッチの状態を返します。|  
|[RefreshRowset](../../mfc/reference/crecordset-class.md#refreshrowset)|行セット内の特定の行の状態とデータを更新します。|  
|[SetRowsetCursorPosition](../../mfc/reference/crecordset-class.md#setrowsetcursorposition)|行セット内の特定の行にカーソルを移動します。|  
|[SetRowsetSize](../../mfc/reference/crecordset-class.md#setrowsetsize)|指定した値を行セット サイズの設定を変更する仮想関数。|  
  
##  <a name="_core_special_considerations"></a> 特別な考慮事項  
 バルク行フェッチはパフォーマンスの向上が、特定の機能の動作は異なります。 バルク行フェッチを実装する前に、次の操作を検討してください。  
  
-   フレームワークが自動的に呼び出し、`DoBulkFieldExchange`レコード セット オブジェクトのデータ ソースからデータを転送するメンバー関数。 ただし、データ ソースに、データは、レコード セットからに転送されません。 呼び出す、 `AddNew`、**編集**、**削除**、または**更新**失敗したアサーション内でメンバー関数の結果。 `CRecordset`現在メカニズムが用意されていないデータの一括行を更新するには、ODBC API 関数を使用して、独自の関数を記述することができます**SQLSetPos**です。 詳細については**SQLSetPos**を参照してください、 *ODBC SDK プログラマ リファレンス*MSDN ドキュメント。  
  
-   メンバー関数は、 `IsDeleted`、 `IsFieldDirty`、 `IsFieldNull`、 `IsFieldNullable`、 `SetFieldDirty`、および`SetFieldNull`バルク行フェッチを実装したレコード セットでは使用できません。 ただし、呼び出す`GetRowStatus`の代わりに`IsDeleted`、および`GetODBCFieldInfo`の代わりに`IsFieldNullable`です。  
  
-   **移動**操作は、行セットによって、レコード セットを再配置します。 たとえば、最初の行セット サイズが 10 の 100 のレコードを持つレコード セットを開くとします。 **開いている**1 行に配置されている現在のレコードに、1 ~ 10 の行をフェッチします。 呼び出し`MoveNext`次の行セット、次の行ではなくをフェッチします。 この行セットは、行 11 ~ 20、現在のレコードに 11 行目に配置されているので構成されます。 なお`MoveNext`と**Move (1)** バルク行フェッチが実装されているときに同じではありません。 **Move (1)** 現在のレコードから 1 行で開始する行セットをフェッチします。 この例では呼び出す **(1) に移動**呼び出した後**開く**2 行目に配置されている現在のレコードに 2 ~ 11、行で構成される行セットをフェッチします。 詳細については、次を参照してください。、[移動](../../mfc/reference/crecordset-class.md#move)メンバー関数。  
  
-   レコード フィールド エクス チェンジとは異なり、ウィザードには、バルク レコード フィールド エクス チェンジがサポートされません。 つまり、フィールド データ メンバーを手動で宣言され、手動でオーバーライドする必要があります`DoBulkFieldExchange`バルク RFX 関数の呼び出しを記述しています。 詳細については、次を参照してください。[レコード フィールド エクス チェンジ関数](../../mfc/reference/record-field-exchange-functions.md)で、*クラス ライブラリ リファレンス*です。  
  
##  <a name="_core_how_to_implement_bulk_record_field_exchange"></a> バルク レコード フィールド エクス チェンジを実装する方法  
 バルク レコード フィールド エクス チェンジは、レコード セット オブジェクトにデータ ソースからのデータの行セットを転送します。 バルク RFX 関数は、このデータを格納する配列だけでなく、行セット内の各データ項目の長さを格納する配列を使用します。 クラスの定義でデータの配列にアクセスするへのポインターとして、フィールド データ メンバーを定義する必要があります。 さらに、長さの配列にアクセスするへのポインターのセットを定義する必要があります。 パラメーター データ メンバーは、ポインターとして宣言してはなりませんバルク レコード フィールド エクス チェンジを使用する場合は、パラメーター データ メンバーを宣言すると、レコード フィールド エクス チェンジの使用時にそれらの宣言と同じです。 次のコードは、単純な例を示しています。  
  
```  
class MultiRowSet : public CRecordset  
{  
public:  
   // Field/Param Data  
      // field data members  
      long* m_rgID;  
      LPSTR m_rgName;  
  
      // pointers for the lengths  
      // of the field data  
      long* m_rgIDLengths;  
      long* m_rgNameLengths;  
  
      // input parameter data member  
      CString m_strNameParam;  
  
   .  
   .  
   .  
}  
```  
  
 これらの記憶域バッファーを手動で割り当てるか、フレームワークによって自動的に割り当てがあります。 手動で割り当てる、する必要がありますを指定する、 **crecordset::userallocmultirowbuffers**のオプション、 **dwOptions**内のパラメーター、**開く**メンバー関数。 行セットのサイズには、少なくともと等しい、配列のサイズを設定することを確認します。 ポインターを初期化する必要があります、フレームワークによって自動的に割り当てがある場合は、 **NULL です。** これは通常、レコード セット オブジェクトのコンス トラクターで行います。  
  
```  
MultiRowSet::MultiRowSet( CDatabase* pDB )  
   : CRecordset( pDB )  
{  
   m_rgID = NULL;  
   m_rgName = NULL;  
   m_rgIDLengths = NULL;  
   m_rgNameLengths = NULL;  
   m_strNameParam = "";  
  
   m_nFields = 2;  
   m_nParams = 1;  
  
   .  
   .  
   .  
}  
```  
  
 最後に、オーバーライドする必要があります、`DoBulkFieldExchange`メンバー関数。 フィールド データ メンバーについて; バルク RFX 関数を呼び出すパラメーター データ メンバー、RFX 関数を呼び出します。 SQL ステートメントまたはストアド プロシージャに渡すことによって、レコード セットを開いた**開く**、レコード セット内の列順序 Bulk rfx 関数の呼び出しを行うときの順序に対応する必要があります同様に、呼び出す、RFX の順序。パラメーターは、SQL ステートメントのパラメーターの順序に対応する必要があります。 またはストアド プロシージャです。  
  
```  
void MultiRowSet::DoBulkFieldExchange( CFieldExchange* pFX )  
{  
   // call the Bulk RFX functions  
   // for field data members  
   pFX->SetFieldType( CFieldExchange::outputColumn );  
   RFX_Long_Bulk( pFX, _T( "[colRecID]" ),  
                  &m_rgID, &m_rgIDLengths );  
   RFX_Text_Bulk( pFX, _T( "[colName]" ),  
                  &m_rgName, &m_rgNameLengths, 30 );  
  
   // call the RFX functions for  
   // for parameter data members  
   pFX->SetFieldType( CFieldExchange::inputParam );  
   RFX_Text( pFX, "NameParam", m_strNameParam );  
}  
```  
  
> [!NOTE]
>  呼び出す必要があります、**閉じる**メンバー関数は、派生する前に`CRecordset`クラスがスコープから外れます。 これにより、フレームワークによって割り当てられたメモリが解放されます。 プログラミングを常に明示的に呼び出す方法をお勧め**閉じる**バルク行フェッチを実装するかどうかに関係なく、します。  
  
 レコード フィールド エクス チェンジ (RFX) の詳細については、次を参照してください。[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。 詳細については、パラメーターを使用して、次を参照してください。[つ](../../mfc/reference/cfieldexchange-class.md#setfieldtype)と[レコード セット: レコード セット (ODBC) のパラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)   
 [CRecordset::m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)   
 [CRecordset::m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)

