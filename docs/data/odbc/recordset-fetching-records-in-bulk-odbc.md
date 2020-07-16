---
title: 'レコードセット: バルク行フェッチ (ODBC)'
ms.date: 11/04/2016
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
ms.openlocfilehash: ccdc4668f0c19f63ec86ee9a6d788532eb4d9d38
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "86403713"
---
# <a name="recordset-fetching-records-in-bulk-odbc"></a>レコードセット: バルク行フェッチ (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

クラス `CRecordset` では、バルク行フェッチがサポートされています。つまり、一度に1つのレコードをデータソースから取得するのではなく、1回のフェッチ中に一度に複数のレコードを取得できます。 バルク行フェッチは、派生クラスでのみ実装でき `CRecordset` ます。 データソースからレコードセットオブジェクトにデータを転送するプロセスは、バルクレコードフィールドエクスチェンジ (Bulk RFX) と呼ばれます。 派生クラスでバルク行フェッチを使用していない場合 `CRecordset` 、データはレコードフィールドエクスチェンジ (RFX) を介して転送されることに注意してください。 詳細については、「[レコードフィールドエクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)」を参照してください。

このトピックでは、次の内容について説明します。

- [CRecordset がバルク行フェッチをサポートする方法](#_core_how_crecordset_supports_bulk_row_fetching)。

- [バルク行フェッチを使用する場合の特別な考慮事項](#_core_special_considerations)。

- [バルクレコードフィールドエクスチェンジを実装する方法](#_core_how_to_implement_bulk_record_field_exchange)。

## <a name="how-crecordset-supports-bulk-row-fetching"></a><a name="_core_how_crecordset_supports_bulk_row_fetching"></a>CRecordset がバルク行フェッチをサポートする方法

レコードセットオブジェクトを開く前に、メンバー関数を使用して行セットのサイズを定義でき `SetRowsetSize` ます。 行セットサイズは、1回のフェッチ中に取得するレコード数を指定します。 バルク行フェッチが実装されている場合、既定の行セットサイズは25です。 バルク行フェッチが実装されていない場合、行セットのサイズは1で固定されたままになります。

行セットのサイズを初期化した後、 [Open](../../mfc/reference/crecordset-class.md#open)メンバー関数を呼び出します。 ここでは、 `CRecordset::useMultiRowFetch` *dwOptions*パラメーターのオプションを指定して、バルク行フェッチを実装する必要があります。 また、オプションを設定することもでき `CRecordset::userAllocMultiRowBuffers` ます。 バルクレコードフィールド交換メカニズムは、配列を使用して、フェッチ中に取得された複数行のデータを格納します。 これらのストレージバッファーは、フレームワークによって自動的に割り当てることも、手動で割り当てることもできます。 オプションを指定する `CRecordset::userAllocMultiRowBuffers` と、割り当てが行われることになります。

次の表に、 `CRecordset` バルク行フェッチをサポートするためにによって提供されるメンバー関数を示します。

|メンバー関数|説明|
|---------------------|-----------------|
|[CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)|フェッチ中に発生したすべてのエラーを処理する仮想関数。|
|[DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)|バルクレコードフィールドエクスチェンジを実装します。 データソースから複数行のデータをレコードセットオブジェクトに転送するために、自動的に呼び出されます。|
|[GetRowsetSize](../../mfc/reference/crecordset-class.md#getrowsetsize)|行セットサイズの現在の設定を取得します。|
|[GetRowsFetched](../../mfc/reference/crecordset-class.md#getrowsfetched)|特定のフェッチの後に実際に取得された行の数を示します。 ほとんどの場合、不完全な行セットがフェッチされていない限り、これは行セットのサイズです。|
|[GetRowStatus](../../mfc/reference/crecordset-class.md#getrowstatus)|行セット内の特定の行のフェッチ状態を返します。|
|[RefreshRowset](../../mfc/reference/crecordset-class.md#refreshrowset)|行セット内の特定の行のデータと状態を更新します。|
|[SetRowsetCursorPosition](../../mfc/reference/crecordset-class.md#setrowsetcursorposition)|行セット内の特定の行にカーソルを移動します。|
|[SetRowsetSize](../../mfc/reference/crecordset-class.md#setrowsetsize)|行セットのサイズの設定を指定した値に変更する仮想関数。|

## <a name="special-considerations"></a><a name="_core_special_considerations"></a>特別な考慮事項

バルク行フェッチはパフォーマンスの向上を実現しますが、機能によって動作が異なります。 バルク行フェッチを実装する場合は、次の点を考慮してください。

- フレームワークは、メンバー関数を自動的に呼び出して、 `DoBulkFieldExchange` データソースからレコードセットオブジェクトにデータを転送します。 ただし、データはレコードセットからデータソースに戻されません。 、、、またはの各メンバー関数を呼び出すと、 `AddNew` `Edit` `Delete` `Update` アサーションが失敗します。 `CRecordset`現時点では、データの一括行を更新するためのメカニズムは提供されていませんが、ODBC API 関数を使用して独自の関数を記述することができ `SQLSetPos` ます。 の詳細については `SQLSetPos` 、 [ODBC プログラマーズリファレンス](/sql/odbc/reference/odbc-programmer-s-reference)を参照してください。

- メンバー関数、 `IsDeleted` `IsFieldDirty` 、、 `IsFieldNull` `IsFieldNullable` 、、およびは、 `SetFieldDirty` `SetFieldNull` バルク行フェッチを実装するレコードセットでは使用できません。 ただし、の代わりに、の代わりにを呼び出すことができ `GetRowStatus` `IsDeleted` `GetODBCFieldInfo` `IsFieldNullable` ます。

- 操作は、 `Move` レコードセットを行セットによって再配置します。 たとえば、最初の行セットサイズが10である100レコードを含むレコードセットを開くとします。 `Open`現在のレコードが行1に配置された行1から10をフェッチします。 次の行では `MoveNext` なく、次の行セットをフェッチするの呼び出し。 この行セットは、11 ~ 20 行の行で構成され、現在のレコードは行11に配置されています。 `MoveNext`とは、 `Move( 1 )` バルク行フェッチが実装されている場合には同等ではないことに注意してください。 `Move( 1 )`現在のレコードから1行を開始する行セットをフェッチします。 この例では、を呼び出した後にを呼び出すと、行 2 `Move( 1 )` `Open` から11までの行で構成される行セットがフェッチされ、現在のレコードが行2に配置されます。 詳細については、「メンバーの[移動](../../mfc/reference/crecordset-class.md#move)関数」を参照してください。

- レコードフィールドエクスチェンジとは異なり、これらのウィザードでは、一括レコードフィールドの交換はサポートされていません。 つまり、手動でフィールドデータメンバーを宣言し、 `DoBulkFieldExchange` BULK RFX 関数の呼び出しを作成することによって手動でオーバーライドする必要があります。 詳細については、「*クラスライブラリリファレンス*」の「[レコードフィールドエクスチェンジ関数](../../mfc/reference/record-field-exchange-functions.md)」を参照してください。

## <a name="how-to-implement-bulk-record-field-exchange"></a><a name="_core_how_to_implement_bulk_record_field_exchange"></a>バルクレコードフィールドエクスチェンジを実装する方法

バルクレコードフィールドエクスチェンジは、データの行セットをデータソースからレコードセットオブジェクトに転送します。 Bulk RFX 関数は、配列を使用してこのデータを格納し、各データ項目の長さを行セットに格納する配列を使用します。 クラス定義では、データの配列にアクセスするためのポインターとしてフィールドデータメンバーを定義する必要があります。 さらに、長さの配列にアクセスするためのポインターのセットを定義する必要があります。 パラメーターデータメンバーは、ポインターとして宣言しないでください。一括レコードフィールドエクスチェンジを使用する場合のパラメーターデータメンバーの宣言は、レコードフィールドエクスチェンジを使用する場合と同じです。 次のコードは、簡単な例を示しています。

```cpp
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

これらのストレージバッファーは、手動で割り当てることも、割り当てを行うこともできます。 バッファーを自分で割り当てるには、 `CRecordset::userAllocMultiRowBuffers` メンバー関数で*dwOptions*パラメーターのオプションを指定する必要があり `Open` ます。 配列のサイズは、少なくとも行セットのサイズに設定してください。 フレームワークが割り当てを行うようにするには、ポインターを NULL に初期化する必要があります。 これは通常、レコードセットオブジェクトのコンストラクターで行われます。

```cpp
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

最後に、メンバー関数をオーバーライドする必要があり `DoBulkFieldExchange` ます。 フィールドデータメンバーの場合は、Bulk RFX 関数を呼び出します。パラメーターのデータメンバーについては、RFX 関数を呼び出します。 SQL ステートメントまたはストアドプロシージャをに渡してレコードセットを開いた場合、 `Open` BULK rfx 呼び出しを行う順序は、レコードセット内の列の順序に対応している必要があります。同様に、パラメーターに対する RFX 呼び出しの順序は、sql ステートメントまたはストアドプロシージャのパラメーターの順序に対応している必要があります。

```cpp
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
> `Close`派生クラスがスコープ外に出る前に、メンバー関数を呼び出す必要があり `CRecordset` ます。 これにより、フレームワークによって割り当てられたメモリがすべて解放されます。 `Close`バルク行フェッチを実装したかどうかに関係なく、常にを明示的に呼び出すことをお勧めします。

レコードフィールドエクスチェンジ (RFX) の詳細については、「[レコードフィールドエクスチェンジ: rfx の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。 パラメーターの使用の詳細については、「 [CFieldExchange:: SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) and [Recordset: レコードセットのパラメーター化 (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[CRecordset:: m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)<br/>
[CRecordset:: m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)
