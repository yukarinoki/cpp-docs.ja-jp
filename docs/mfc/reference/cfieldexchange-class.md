---
title: クラス
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
ms.openlocfilehash: d4b99a4992075072253d4f9b3182a926673bdfd0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373929"
---
# <a name="cfieldexchange-class"></a>クラス

データベース クラスで使うレコード フィールド エクスチェンジ (RFX) ルーチンとバルク レコード フィールド エクスチェンジ (Bulk RFX) ルーチンをサポートします。

## <a name="syntax"></a>構文

```
class CFieldExchange
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[フィールドエクスチェンジ::イズフィールドタイプ](#isfieldtype)|現在の操作が更新されるフィールドの種類に適している場合は、0 以外を返します。|
|[フィールドエクスチェンジ::セットフィールドタイプ](#setfieldtype)|次に RFX 関数を呼び出す場合、次の呼び出しで表されるレコードセット`SetFieldType`データ メンバの型 (列またはパラメータ) を指定します。|

## <a name="remarks"></a>解説

`CFieldExchange`は基本クラスを持っていません。

カスタム データ型のデータ交換ルーチンを記述する場合、またはバルク行フェッチを実装する場合は、このクラスを使用します。それ以外の場合は、このクラスを直接使用しません。 RFX と Bulk RFX は、レコードセット オブジェクトのフィールド データ メンバーと、データ ソースの現在のレコードの対応するフィールドとの間でデータを交換します。

> [!NOTE]
> オープン データベース接続 (ODBC) クラスではなく、データ アクセス オブジェクト (DAO) クラスを使用している場合は、代わりにクラス[CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md)を使用します。 詳細については、記事の[概要: データベース プログラミングを参照してください](../../data/data-access-programming-mfc-atl.md)。

オブジェクト`CFieldExchange`は、レコード フィールドエクスチェンジまたはバルク レコード フィールドエクスチェンジに必要なコンテキスト情報を提供します。 `CFieldExchange`オブジェクトは、パラメータとフィールド データ メンバのバインド、現在のレコードのフィールドに対するさまざまなフラグの設定など、多くの操作をサポートします。 RFX およびバルク RFX 操作は、 の**列挙****型 FieldType**で定義された型`CFieldExchange`のレコードセット クラス データ メンバに対して実行されます。 **フィールドタイプの**値は次のとおりです。

- `CFieldExchange::outputColumn`フィールド データ メンバーの場合。

- `CFieldExchange::inputParam`または`CFieldExchange::param`入力パラメータデータメンバー用。

- `CFieldExchange::outputParam`出力パラメータ データ メンバの場合。

- `CFieldExchange::inoutParam`入力/出力パラメーター のデータ メンバーの場合。

クラスのメンバー関数とデータ メンバーのほとんどは、独自のカスタム RFX ルーチンを記述するために用意されています。 頻繁に`SetFieldType`使用します。 詳細については、「レコード フィールド[エクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)および[レコードセット (ODBC)」を](../../data/odbc/recordset-odbc.md)参照してください。 バルク行フェッチの詳細については、「[レコードセット: レコードを一括でフェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。 RFX およびバルク RFX グローバル関数の詳細については、このリファレンスの「MFC マクロとグローバル[」の「レコード フィールドエクスチェンジ関数](../../mfc/reference/record-field-exchange-functions.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CFieldExchange`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="cfieldexchangeisfieldtype"></a><a name="isfieldtype"></a>フィールドエクスチェンジ::イズフィールドタイプ

独自の RFX 関数を記述する`IsFieldType`場合は、関数の先頭で呼び出し、特定のフィールドまたはパラメーターのデータ メンバーの種類 ( `CFieldExchange::outputColumn`、 `CFieldExchange::inputParam` `CFieldExchange::param`、 `CFieldExchange::outputParam`、 `CFieldExchange::inoutParam`、 、 、 、 ) に対して現在の操作を実行できるかどうかを判断します。

```
BOOL IsFieldType(UINT* pnField);
```

### <a name="parameters"></a>パラメーター

*フィールド*<br/>
このパラメーターには、フィールドまたはパラメーター・データ・メンバーの連続番号が戻されます。 この数値は[、CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)または[CRecordset::DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)関数でのデータ メンバーの順序に対応します。

### <a name="return-value"></a>戻り値

現在のフィールドまたはパラメーターの型に対して現在の操作を実行できる場合は、0 以外の値を指定します。

### <a name="remarks"></a>解説

既存の RFX 関数のモデルに従います。

## <a name="cfieldexchangesetfieldtype"></a><a name="setfieldtype"></a>フィールドエクスチェンジ::セットフィールドタイプ

レコードセット クラスの`SetFieldType` [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)または[ドバルクフィールドエクスチェンジ](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)のオーバーライドで呼び出しが必要です。

```
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>パラメーター

*フィールドタイプ*<br/>
で`CFieldExchange`宣言される`enum FieldType`、 の値は、次のいずれかになります。

- `CFieldExchange::outputColumn`

- `CFieldExchange::inputParam`

- `CFieldExchange::param`

- `CFieldExchange::outputParam`

- `CFieldExchange::inoutParam`

### <a name="remarks"></a>解説

フィールド データ メンバーの場合は`SetFieldType`、パラメーター を`CFieldExchange::outputColumn`指定して呼び出し、その後に RFX 関数または Bulk RFX 関数を呼び出す必要があります。 バルク行フェッチを実装していない場合、ClassWizard は、 のフィールド`SetFieldType`マップ セクションにこの呼び出`DoFieldExchange`しを行います。

レコードセット クラスをパラメーター化する場合は、`SetFieldType`フィールド マップ セクションの外側でもう一度呼び出し、その後にすべてのパラメーター データ メンバーの RFX 呼び出しを行う必要があります。 パラメーター データ メンバーの各型には、`SetFieldType`独自の呼び出しが必要です。 次の表は、クラスのパラメーター データ メンバー`SetFieldType`を表すために渡すことができるさまざまな値を示しています。

|パラメーター値を設定します。|パラメーター データ メンバーの型|
|----------------------------------|-----------------------------------|
|`CFieldExchange::inputParam`|入力パラメーターです。 レコードセットのクエリまたはストアド プロシージャに渡される値。|
|`CFieldExchange::param` | と同`CFieldExchange::inputParam`じです。|
|`CFieldExchange::outputParam`|出力パラメーターです。 レコードセットのストアド プロシージャの戻り値。|
|`CFieldExchange::inoutParam`|入力/出力パラメーター。 レコードセットのストアド プロシージャに渡され、レコードセットから返される値。|

一般に、フィールド データ メンバーまたはパラメーター データ メンバーに関連付けられている RFX 関数呼び出`SetFieldType`しの各グループの前に、 を呼び出す必要があります。 各`SetFieldType`呼び出しの*nFieldType*パラメーターは、呼び出しの後に RFX 関数`SetFieldType`呼び出しによって表されるデータ メンバーの型を識別します。

出力パラメータと入出力パラメータの処理の詳細については、`CRecordset`メンバー関数[FlushResultSet](../../mfc/reference/crecordset-class.md#flushresultset)を参照してください。 RFX 関数とバルク RFX 関数の詳細については、トピック「[レコード フィールド エクスチェンジ関数](../../mfc/reference/record-field-exchange-functions.md)」を参照してください。 バルク行フェッチの関連情報については、「[レコードセット: レコードを一括でフェッチする (ODBC) 」](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)を参照してください。

### <a name="example"></a>例

この例では、RFX 関数への呼び出し`SetFieldType`とそれに伴う 呼び出しを示します。 オブジェクトへの`SetFieldType`ポインタを`pFX`通して呼び出`CFieldExchange`されることに注意してください。

[!code-cpp[NVC_MFCDatabase#33](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/crecordset-class.md)
