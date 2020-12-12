---
description: '詳細情報: CFieldExchange クラス'
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
ms.openlocfilehash: 128b2a7baf6fff923393f3105e27f1e85657bdde
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184557"
---
# <a name="cfieldexchange-class"></a>CFieldExchange クラス

データベース クラスで使うレコード フィールド エクスチェンジ (RFX) ルーチンとバルク レコード フィールド エクスチェンジ (Bulk RFX) ルーチンをサポートします。

## <a name="syntax"></a>構文

```
class CFieldExchange
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CFieldExchange::IsFieldType](#isfieldtype)|現在の操作が更新対象のフィールドの型に適している場合は、0以外の値を返します。|
|[CFieldExchange::SetFieldType](#setfieldtype)|次にが呼び出されるまで、RFX 関数の後続のすべての呼び出しで表される、レコードセットデータメンバー (列またはパラメーター) の種類を指定し `SetFieldType` ます。|

## <a name="remarks"></a>解説

`CFieldExchange` に基底クラスがありません。

カスタムデータ型に対してデータ交換ルーチンを作成する場合、または一括行フェッチを実装する場合は、このクラスを使用します。それ以外の場合、このクラスは直接使用されません。 RFX および Bulk RFX は、レコードセットオブジェクトのフィールドデータメンバーと、データソースの現在のレコードの対応するフィールドとの間でデータを交換します。

> [!NOTE]
> Open Database Connectivity (ODBC) クラスではなく、データアクセスオブジェクト (DAO) クラスを使用している場合は、代わりにクラス [CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md) を使用します。 詳細については、記事「 [概要: データベースプログラミング](../../data/data-access-programming-mfc-atl.md)」を参照してください。

オブジェクトは、 `CFieldExchange` レコードフィールドの交換または一括レコードフィールドの交換を行うために必要なコンテキスト情報を提供します。 `CFieldExchange` オブジェクトは、パラメーターやフィールドデータメンバーのバインド、現在のレコードのフィールドに対するさまざまなフラグの設定など、さまざまな操作をサポートしています。 RFX および Bulk RFX 操作は、の FieldType で定義されている型のレコードセットクラスのデータメンバーに対して実行され **`enum`**  `CFieldExchange` ます。 使用可能な **FieldType** 値は次のとおりです。

- `CFieldExchange::outputColumn` フィールドデータメンバーの場合。

- `CFieldExchange::inputParam``CFieldExchange::param`入力パラメーターのデータメンバーの場合は。

- `CFieldExchange::outputParam` 出力パラメーターのデータメンバーの場合。

- `CFieldExchange::inoutParam` 入力/出力パラメーターのデータメンバーの場合。

クラスのメンバー関数とデータメンバーの大部分は、独自のカスタム RFX ルーチンを記述するために用意されています。 頻繁に使用 `SetFieldType` します。 詳細については、 [レコードフィールドエクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md) とレコード [セット (ODBC)](../../data/odbc/recordset-odbc.md)に関する記事を参照してください。 バルク行フェッチの詳細については、「レコード [セット: レコードを一括フェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。 RFX および Bulk RFX のグローバル関数の詳細については、このリファレンスの「MFC マクロおよびグローバル変数の [レコードフィールドエクスチェンジ関数](../../mfc/reference/record-field-exchange-functions.md) 」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CFieldExchange`

## <a name="requirements"></a>要件

**ヘッダー:** afxdb.h

## <a name="cfieldexchangeisfieldtype"></a><a name="isfieldtype"></a> CFieldExchange::IsFieldType

独自の RFX 関数を記述する場合は、 `IsFieldType` 関数の先頭でを呼び出して、現在の操作を特定のフィールドまたはパラメーターのデータメンバー型 (、、、、 `CFieldExchange::outputColumn` `CFieldExchange::inputParam` `CFieldExchange::param` `CFieldExchange::outputParam` または `CFieldExchange::inoutParam` ) に対して実行できるかどうかを判断します。

```
BOOL IsFieldType(UINT* pnField);
```

### <a name="parameters"></a>パラメーター

*pnField*<br/>
このパラメーターでは、フィールドまたはパラメーターのデータメンバーの連続番号が返されます。 この数値は、 [crecordset::D ofieldexchange](../../mfc/reference/crecordset-class.md#dofieldexchange) または [Crecordset::D obulkfieldexchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) 関数のデータメンバーの順序に対応します。

### <a name="return-value"></a>戻り値

現在のフィールドまたはパラメーターの型に対して現在の操作を実行できる場合は0以外の。

### <a name="remarks"></a>解説

既存の RFX 関数のモデルに従います。

## <a name="cfieldexchangesetfieldtype"></a><a name="setfieldtype"></a> CFieldExchange::SetFieldType

`SetFieldType`レコードセットクラスの[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)または[DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) override でを呼び出す必要があります。

```cpp
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>パラメーター

*nFieldType*<br/>
`enum FieldType`で宣言されたの値 `CFieldExchange` 。次のいずれかを指定できます。

- `CFieldExchange::outputColumn`

- `CFieldExchange::inputParam`

- `CFieldExchange::param`

- `CFieldExchange::outputParam`

- `CFieldExchange::inoutParam`

### <a name="remarks"></a>解説

フィールドデータメンバーの場合は、のパラメーターを指定してを呼び出す必要があり `SetFieldType` `CFieldExchange::outputColumn` ます。その後、RFX 関数または Bulk rfx 関数を呼び出します。 バルク行フェッチを実装していない場合、ClassWizard は `SetFieldType` のフィールドマップセクションにこの呼び出しを配置し `DoFieldExchange` ます。

レコードセットクラスをパラメーター化する場合は、 `SetFieldType` 任意のフィールドマップセクションの外部でを再度呼び出す必要があります。その後、すべてのパラメーターデータメンバーに対して RFX 呼び出しが行われます。 パラメーターデータメンバーの型にはそれぞれ、独自の呼び出しが必要 `SetFieldType` です。 次の表は、 `SetFieldType` クラスのパラメーターデータメンバーを表すために渡すことができるさまざまな値を区別しています。

|SetFieldType パラメーター値|パラメーターデータメンバーの型|
|----------------------------------|-----------------------------------|
|`CFieldExchange::inputParam`|入力パラメーターです。 レコードセットのクエリまたはストアドプロシージャに渡される値。|
|`CFieldExchange::param` | と同じ `CFieldExchange::inputParam` です。|
|`CFieldExchange::outputParam`|出力パラメーターです。 レコードセットのストアドプロシージャの戻り値。|
|`CFieldExchange::inoutParam`|入力/出力パラメーター。 レコードセットのストアドプロシージャに渡されて返される値。|

一般に、フィールドデータメンバーまたはパラメーターデータメンバーに関連付けられている RFX 関数呼び出しの各グループの前に、を呼び出す必要があり `SetFieldType` ます。 各呼び出しの *nFieldType* パラメーターは、 `SetFieldType` 呼び出しの後にある RFX 関数呼び出しによって表されるデータメンバーの型を識別し `SetFieldType` ます。

出力パラメーターと入出力パラメーターの処理の詳細については、「 `CRecordset` メンバー関数 [flushresultset](../../mfc/reference/crecordset-class.md#flushresultset)」を参照してください。 RFX 関数と Bulk RFX 関数の詳細については、「 [レコードフィールドエクスチェンジ関数](../../mfc/reference/record-field-exchange-functions.md)」を参照してください。 バルク行フェッチの詳細については、「レコード [セット: レコードを一括フェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

### <a name="example"></a>例

この例では、への呼び出しを伴う RFX 関数のいくつかの呼び出しを示し `SetFieldType` ます。 は、 `SetFieldType` オブジェクトへのポインターを介して呼び出されることに注意して `pFX` `CFieldExchange` ください。

[!code-cpp[NVC_MFCDatabase#33](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CRecordset クラス](../../mfc/reference/crecordset-class.md)
