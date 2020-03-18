---
title: CFieldExchange クラス
ms.date: 11/04/2016
f1_keywords:
- CFieldExchange
- AFXDB/CFieldExchange
- AFXDB/CFieldExchange::IsFieldType
- AFXDB/CFieldExchange::SetFieldType
helpviewer_keywords:
- CFieldExchange [MFC], IsFieldType
- CFieldExchange [MFC], SetFieldType
ms.assetid: 24c5c0b3-06a6-430e-9b6f-005a2c65e29f
ms.openlocfilehash: e66b3ed16d4f21d46567c37bfaf7929d32f63b8e
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425899"
---
# <a name="cfieldexchange-class"></a>CFieldExchange クラス

データベース クラスで使うレコード フィールド エクスチェンジ (RFX) ルーチンとバルク レコード フィールド エクスチェンジ (Bulk RFX) ルーチンをサポートします。

## <a name="syntax"></a>構文

```
class CFieldExchange
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[CFieldExchange::IsFieldType](#isfieldtype)|現在の操作が更新対象のフィールドの型に適している場合は、0以外の値を返します。|
|[CFieldExchange::SetFieldType](#setfieldtype)|次に `SetFieldType`を呼び出すまで、RFX 関数の後続のすべての呼び出しで表される、レコードセットデータメンバー (列またはパラメーター) の種類を指定します。|

## <a name="remarks"></a>解説

`CFieldExchange` には基底クラスがありません。

カスタムデータ型に対してデータ交換ルーチンを作成する場合、または一括行フェッチを実装する場合は、このクラスを使用します。それ以外の場合、このクラスは直接使用されません。 RFX および Bulk RFX は、レコードセットオブジェクトのフィールドデータメンバーと、データソースの現在のレコードの対応するフィールドとの間でデータを交換します。

> [!NOTE]
>  Open Database Connectivity (ODBC) クラスではなく、データアクセスオブジェクト (DAO) クラスを使用している場合は、代わりにクラス[CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md)を使用します。 詳細については、記事「[概要: データベースプログラミング](../../data/data-access-programming-mfc-atl.md)」を参照してください。

`CFieldExchange` オブジェクトは、レコードフィールドの交換または一括レコードフィールドの交換を行うために必要なコンテキスト情報を提供します。 `CFieldExchange` オブジェクトは、パラメーターとフィールドデータメンバーのバインドや、現在のレコードのフィールドに対するさまざまなフラグの設定など、さまざまな操作をサポートしています。 RFX および Bulk RFX 操作は、`CFieldExchange`の**列挙**型の**FieldType**で定義されている型のレコードセットクラスのデータメンバーに対して実行されます。 使用可能な**FieldType**値は次のとおりです。

- フィールドデータメンバーの `CFieldExchange::outputColumn`。

- 入力パラメーターのデータメンバーの `CFieldExchange::inputParam` または `CFieldExchange::param`。

- 出力パラメーターのデータメンバーの `CFieldExchange::outputParam`。

- 入力/出力パラメーターのデータメンバーの `CFieldExchange::inoutParam`。

クラスのメンバー関数とデータメンバーの大部分は、独自のカスタム RFX ルーチンを記述するために用意されています。 `SetFieldType` は頻繁に使用します。 詳細については、[レコードフィールドエクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)とレコード[セット (ODBC)](../../data/odbc/recordset-odbc.md)に関する記事を参照してください。 バルク行フェッチの詳細については、「レコード[セット: レコードを一括フェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。 RFX および Bulk RFX のグローバル関数の詳細については、このリファレンスの「MFC マクロおよびグローバル変数の[レコードフィールドエクスチェンジ関数](../../mfc/reference/record-field-exchange-functions.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CFieldExchange`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

##  <a name="isfieldtype"></a>CFieldExchange::IsFieldType

独自の RFX 関数を記述する場合は、関数の先頭で `IsFieldType` を呼び出して、特定のフィールドまたはパラメーターのデータメンバーの種類 (`CFieldExchange::outputColumn`、`CFieldExchange::inputParam`、`CFieldExchange::param`、`CFieldExchange::outputParam`、または `CFieldExchange::inoutParam`) で現在の操作を実行できるかどうかを判断します。

```
BOOL IsFieldType(UINT* pnField);
```

### <a name="parameters"></a>パラメーター

*pnField*<br/>
このパラメーターでは、フィールドまたはパラメーターのデータメンバーの連続番号が返されます。 この数値は、 [crecordset::D ofieldexchange](../../mfc/reference/crecordset-class.md#dofieldexchange)または[Crecordset::D obulkfieldexchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)関数のデータメンバーの順序に対応します。

### <a name="return-value"></a>戻り値

現在のフィールドまたはパラメーターの型に対して現在の操作を実行できる場合は0以外の。

### <a name="remarks"></a>解説

既存の RFX 関数のモデルに従います。

##  <a name="setfieldtype"></a>CFieldExchange::SetFieldType

レコードセットクラスの[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)または[DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) override で `SetFieldType` を呼び出す必要があります。

```
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>パラメーター

*nFieldType*<br/>
`CFieldExchange`で宣言された `enum FieldType`の値。次のいずれかを指定できます。

- `CFieldExchange::outputColumn`

- `CFieldExchange::inputParam`

- `CFieldExchange::param`

- `CFieldExchange::outputParam`

- `CFieldExchange::inoutParam`

### <a name="remarks"></a>解説

フィールドデータメンバーの場合は、`CFieldExchange::outputColumn`のパラメーターを指定して `SetFieldType` を呼び出した後、RFX 関数または Bulk RFX 関数を呼び出す必要があります。 バルク行フェッチを実装していない場合、ClassWizard は、この `SetFieldType` の呼び出しを `DoFieldExchange`のフィールドマップセクションに配置します。

レコードセットクラスをパラメーター化する場合は、フィールドマップセクションの外側で `SetFieldType` をもう一度呼び出す必要があります。その後、すべてのパラメーターデータメンバーに対して RFX 呼び出しが行われます。 パラメーターデータメンバーの型にはそれぞれ、独自の `SetFieldType` 呼び出しが必要です。 次の表は、クラスのパラメーターデータメンバーを表すために `SetFieldType` に渡すことができるさまざまな値を区別しています。

|SetFieldType パラメーター値|パラメーターデータメンバーの型|
|----------------------------------|-----------------------------------|
|`CFieldExchange::inputParam`|入力パラメーターです。 レコードセットのクエリまたはストアドプロシージャに渡される値。|
|`CFieldExchange::param` | `CFieldExchange::inputParam`と同じです。|
|`CFieldExchange::outputParam`|出力パラメーターです。 レコードセットのストアドプロシージャの戻り値。|
|`CFieldExchange::inoutParam`|入力/出力パラメーター。 レコードセットのストアドプロシージャに渡されて返される値。|

一般に、フィールドデータメンバーまたはパラメーターデータメンバーに関連付けられている RFX 関数呼び出しの各グループの前に、`SetFieldType`を呼び出す必要があります。 各 `SetFieldType` 呼び出しの*nFieldType*パラメーターは、`SetFieldType` 呼び出しの後にある RFX 関数呼び出しによって表されるデータメンバーの型を識別します。

出力パラメーターと入出力パラメーターの処理の詳細については、「`CRecordset` メンバー関数[Flushresultset](../../mfc/reference/crecordset-class.md#flushresultset)」を参照してください。 RFX 関数と Bulk RFX 関数の詳細については、「[レコードフィールドエクスチェンジ関数](../../mfc/reference/record-field-exchange-functions.md)」を参照してください。 バルク行フェッチの詳細については、「レコード[セット: レコードを一括フェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

### <a name="example"></a>例

この例では、`SetFieldType`への呼び出しを伴う RFX 関数の呼び出しをいくつか示します。 `SetFieldType` は、`CFieldExchange` オブジェクトへの `pFX` ポインターを介して呼び出されることに注意してください。

[!code-cpp[NVC_MFCDatabase#33](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]

## <a name="see-also"></a>参照

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CRecordset クラス](../../mfc/reference/crecordset-class.md)
