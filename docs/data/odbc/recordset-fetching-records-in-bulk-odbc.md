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
ms.openlocfilehash: ec4d83481f6335d4c40ffb8f004b617f2ee09c62
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367026"
---
# <a name="recordset-fetching-records-in-bulk-odbc"></a>レコードセット: バルク行フェッチ (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

クラス`CRecordset`は、データ ソースから一度に 1 つのレコードを取得するのではなく、1 回のフェッチ中に複数のレコードを取得できることを意味するバルク行フェッチのサポートを提供します。 バルク行フェッチは、派生`CRecordset`クラスでのみ実装できます。 データ ソースからレコードセット オブジェクトにデータを転送するプロセスは、バルク レコード フィールド エクスチェンジ (Bulk RFX) と呼ばれます。 派生クラスで`CRecordset`バルク行フェッチを使用しない場合、データはレコード フィールド エクスチェンジ (RFX) を介して転送されます。 詳細については、「[レコード フィールド エクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)」を参照してください。

このトピックでは、次の内容について説明します。

- [CRecordset がバルク行フェッチをサポートする方法](#_core_how_crecordset_supports_bulk_row_fetching)。

- [バルク行フェッチを使用する場合の特別な考慮事項](#_core_special_considerations)。

- [バルク レコード フィールド エクスチェンジを実装する方法](#_core_how_to_implement_bulk_record_field_exchange)。

## <a name="how-crecordset-supports-bulk-row-fetching"></a><a name="_core_how_crecordset_supports_bulk_row_fetching"></a>CRecordset がバルク行フェッチをサポートする方法

レコードセット オブジェクトを開く前に、メンバ関数を使用して`SetRowsetSize`行セットのサイズを定義できます。 行セットのサイズは、1 回のフェッチ時に取得するレコード数を指定します。 バルク行フェッチが実装されている場合、デフォルトの行セットサイズは 25 です。 バルク行フェッチが実装されていない場合、行セットのサイズは 1 のままです。

行セットのサイズを初期化したら[、Open](../../mfc/reference/crecordset-class.md#open)メンバー関数を呼び出します。 ここでは、バルク行フェッチ`CRecordset::useMultiRowFetch`を実装するために*dwOptions*パラメータのオプションを指定する必要があります。 さらに、オプションを`CRecordset::userAllocMultiRowBuffers`設定できます。 バルク レコード フィールド交換メカニズムでは、配列を使用して、フェッチ中に取得された複数のデータ行を格納します。 これらのストレージ バッファは、フレームワークによって自動的に割り当てることも、手動で割り当てることもできます。 このオプションを`CRecordset::userAllocMultiRowBuffers`指定すると、割り当てを行います。

次の表は、バルク行フェッチを`CRecordset`サポートするために提供されるメンバー関数の一覧です。

|メンバー関数|説明|
|---------------------|-----------------|
|[行セットエラー](../../mfc/reference/crecordset-class.md#checkrowseterror)|フェッチ中に発生したエラーを処理する仮想関数。|
|[ドバルクフィールドエクスチェンジ](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)|バルク レコード フィールドエクスチェンジを実装します。 データ ソースからレコードセット オブジェクトに複数行のデータを転送するために自動的に呼び出されます。|
|[行セットサイズ](../../mfc/reference/crecordset-class.md#getrowsetsize)|行セットサイズの現在の設定を取得します。|
|[フェッチされた行](../../mfc/reference/crecordset-class.md#getrowsfetched)|特定のフェッチ後に実際に取得された行数を示します。 ほとんどの場合、これは不完全な行セットがフェッチされていない限り、行セットのサイズです。|
|[ゲットローステータス](../../mfc/reference/crecordset-class.md#getrowstatus)|行セット内の特定の行のフェッチ ステータスを返します。|
|[リフレッシュローセット](../../mfc/reference/crecordset-class.md#refreshrowset)|行セット内の特定の行のデータと状態を更新します。|
|[行セットカーソル位置](../../mfc/reference/crecordset-class.md#setrowsetcursorposition)|行セット内の特定の行にカーソルを移動します。|
|[セットローセットサイズ](../../mfc/reference/crecordset-class.md#setrowsetsize)|行セットのサイズの設定を指定した値に変更する仮想関数。|

## <a name="special-considerations"></a><a name="_core_special_considerations"></a>特別な考慮事項

バルク行フェッチはパフォーマンス向上ですが、一部の機能は異なる方法で動作します。 バルク行フェッチを実装する前に、次の点を考慮してください。

- フレームワークは、自動的に`DoBulkFieldExchange`メンバー関数を呼び出して、データ ソースからレコードセット オブジェクトにデータを転送します。 ただし、データはレコードセットからデータ ソースに戻されません。 `AddNew`、 、、`Edit`または`Delete``Update`メンバー関数を呼び出すと、アサーションが失敗します。 現在`CRecordset`のところ、バルク行のデータを更新するメカニズムは提供されていませんが、ODBC API 関数`SQLSetPos`を使用して独自の関数を作成できます。 の詳細については`SQLSetPos`、MSDN ドキュメントの *「ODBC SDK プログラマ リファレンス」* を参照してください。

- メンバ関数`IsDeleted`、 `IsFieldDirty` `IsFieldNull`、 `IsFieldNullable` `SetFieldDirty`、 `SetFieldNull` 、 、 、 および一括行フェッチを実装するレコードセットでは使用できません。 ただし、 の代`GetRowStatus`わりに`IsDeleted`、 の代`GetODBCFieldInfo`わりに 呼`IsFieldNullable`び出すことができます。

- この`Move`操作では、レコードセットを行セットによって再配置します。 たとえば、最初の行セット サイズが 10 のレコードが 100 個あるレコードセットを開くとします。 `Open`は、行 1 から 10 の行をフェッチし、現在のレコードは 1 行目に配置されます。 次の`MoveNext`行ではなく、次の行セットをフェッチする呼び出し。 この行セットは 11 から 20 の行で構成され、現在のレコードは 11 行目に配置されます。 バルク行`MoveNext`フェッチ`Move( 1 )`を実装する場合は、同じではありません。 `Move( 1 )`は、現在のレコードから 1 行を開始する行セットをフェッチします。 この例では、呼`Move( 1 )`び出`Open`し後の呼び出しは、行 2 から 11 から成る行セットを取得し、現在のレコードを行 2 に配置します。 詳細については、[ムーブ](../../mfc/reference/crecordset-class.md#move)メンバー関数を参照してください。

- レコード フィールド交換とは異なり、ウィザードでは一括レコード フィールド交換はサポートされません。 つまり、フィールド データ メンバーを手動で宣言し、Bulk `DoBulkFieldExchange` RFX 関数への呼び出しを記述して手動でオーバーライドする必要があります。 詳細については、『クラス ライブラリ リファレンス』の[「レコード フィールドエクスチェンジ関数](../../mfc/reference/record-field-exchange-functions.md)」を*参照してください*。

## <a name="how-to-implement-bulk-record-field-exchange"></a><a name="_core_how_to_implement_bulk_record_field_exchange"></a>一括レコード フィールド エクスチェンジの実装方法

バルク レコード フィールド エクスチェンジは、データ ソースからレコードセット オブジェクトにデータの行セットを転送します。 Bulk RFX 関数は、配列を使用してこのデータを格納し、配列を使用して行セット内の各データ項目の長さを格納します。 クラス定義では、データの配列にアクセスするためのポインタとしてフィールド データ メンバーを定義する必要があります。 さらに、長さの配列にアクセスするためのポインターのセットを定義する必要があります。 パラメーター データ メンバーは、ポインターとして宣言しないでください。バルク レコード フィールド エクスチェンジを使用する場合にパラメータ データ メンバを宣言することは、レコード フィールドエクスチェンジを使用する場合に宣言するのと同じです。 次のコードは、簡単な例を示しています。

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

これらのストレージ バッファは手動で割り当てることも、フレームワークに割り当てを行うこともできます。 バッファーを自分で割り当てるには、メンバー`CRecordset::userAllocMultiRowBuffers`関数で*dwOptions*パラメーターの`Open`オプションを指定する必要があります。 配列のサイズは、少なくとも行セットのサイズと同じに設定してください。 フレームワークに割り当てを行う場合は、ポインタを NULL に初期化する必要があります。 これは通常、レコードセット オブジェクトのコンストラクタで行われます。

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

最後に、メンバー関数を`DoBulkFieldExchange`オーバーライドする必要があります。 フィールド データ メンバーの場合は、Bulk RFX 関数を呼び出します。パラメータ データ メンバーの場合は、RFX 関数を呼び出します。 レコードセットを開いて SQL ステートメントまたはストアド プロシージャを`Open`に渡す場合、Bulk RFX 呼び出しの順序はレコードセット内の列の順序に対応している必要があります。同様に、パラメータの RFX 呼び出しの順序は、SQL ステートメントまたはストアド プロシージャのパラメータの順序に対応している必要があります。

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
> 派生`CRecordset`クラスがスコープ`Close`外になる前に、メンバー関数を呼び出す必要があります。 これにより、フレームワークによって割り当てられたすべてのメモリが解放されます。 バルク行フェッチを実装しているかどうかに関係なく、常`Close`に明示的に呼び出すことをプログラミングの方法としてお勧めします。

レコード フィールド エクスチェンジ (RFX) の詳細については、「[レコード フィールド エクスチェンジ : RFX の動作」を参照してください](../../data/odbc/record-field-exchange-how-rfx-works.md)。 パラメーターの使用の詳細については[、「CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype)と[レコードセット: レコードセットのパラメーター化 (ODBC)」](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)を参照してください。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット::m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)<br/>
[レコードセット::m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)
