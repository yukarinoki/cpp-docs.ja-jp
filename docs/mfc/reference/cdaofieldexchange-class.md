---
title: クラス
ms.date: 09/17/2019
f1_keywords:
- CDaoFieldExchange
- AFXDAO/CDaoFieldExchange
- AFXDAO/CDaoFieldExchange::IsValidOperation
- AFXDAO/CDaoFieldExchange::SetFieldType
- AFXDAO/CDaoFieldExchange::m_nOperation
- AFXDAO/CDaoFieldExchange::m_prs
helpviewer_keywords:
- CDaoFieldExchange [MFC], IsValidOperation
- CDaoFieldExchange [MFC], SetFieldType
- CDaoFieldExchange [MFC], m_nOperation
- CDaoFieldExchange [MFC], m_prs
ms.assetid: 350a663e-92ff-44ab-ad53-d94efa2e5823
ms.openlocfilehash: 86f12f78338d1c60e3dd13614ccedc2868f28d81
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754721"
---
# <a name="cdaofieldexchange-class"></a>クラス

DAO データベース クラスで使われる DAO レコード フィールド エクスチェンジ (DFX: DAO Record Field eXchange) ルーチンをサポートします。

DAO は Office 2013 を通じてサポートされています。 DAO 3.6 は最終バージョンであり、廃止と見なされます。

## <a name="syntax"></a>構文

```
class CDaoFieldExchange
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[カダフィールドエクスチェンジ::IsValidオペレーション](#isvalidoperation)|現在の操作が更新されるフィールドの種類に適している場合は、0 以外を返します。|
|[セオフィールドエクスチェンジ::セットフィールドタイプ](#setfieldtype)|次に DFX 関数を呼び出す場合、次に呼び出すまで、すべての呼び出`SetFieldType`しで表されるレコードセット データ メンバ (列またはパラメータ) の種類を指定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[カダフィールドエクスチェンジ::m_nOperation](#m_noperation)|レコードセットの`DoFieldExchange`メンバー関数の現在の呼び出しによって実行される DFX 操作。|
|[カダフィールドエクスチェンジ::m_prs](#m_prs)|DFX 操作が実行されるレコードセットへのポインター。|

## <a name="remarks"></a>解説

`CDaoFieldExchange`は基本クラスを持っていません。

カスタム データ型のデータ交換ルーチンを記述する場合は、このクラスを使用します。それ以外の場合は、このクラスを直接使用しません。 DFX は[、CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトのフィールド データ メンバーと、データ ソースの現在のレコードの対応するフィールドとの間でデータを交換します。 DFX は、データ ソースとデータ ソースの両方向の交換を管理します。 カスタム DFX ルーチンの作成については、[テクニカル ノート 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)を参照してください。

> [!NOTE]
> DAO データベース クラスは、オープン データベース接続 (ODBC) に基づく MFC データベース クラスとは異なります。 DAO データベースクラス名には、すべて "CDao" というプレフィックスが付いています。 DAO クラスを使用して ODBC データ ソースにアクセスすることはできます。 一般に、DAO に基づく MFC クラスは、ODBC に基づく MFC クラスよりも優れている。 DAO ベースのクラスは、ODBC ドライバを使用して、独自のデータベース エンジンを介してデータにアクセスできます。 また、DAO を自分で呼び出すのではなく、クラスを使用してテーブルを追加するなど、データ定義言語 (DDL) 操作もサポートしています。

> [!NOTE]
> DAO レコード フィールド エクスチェンジ (DFX) は、ODBC ベースの MFC データベース クラス ( `CDatabase` `CRecordset`、 ) のレコード フィールド エクスチェンジ (RFX) とよく似ています。 RFXを理解すれば、DFXを使いやすいでしょう。

オブジェクト`CDaoFieldExchange`は、DAO レコード フィールドの交換に必要なコンテキスト情報を提供します。 `CDaoFieldExchange`オブジェクトは、パラメータとフィールド データ メンバのバインド、現在のレコードのフィールドに対するさまざまなフラグの設定など、多くの操作をサポートします。 DFX 操作は、 の**列挙型** **FieldType**で定義された型のレコード`CDaoFieldExchange`セット クラス データ メンバに対して実行されます。 **フィールドタイプの**値は次のとおりです。

- `CDaoFieldExchange::outputColumn`フィールド データ メンバーの場合。

- `CDaoFieldExchange::param`パラメーター データ メンバーの場合。

[メンバー](#isvalidoperation)関数は、独自のカスタム DFX ルーチンを記述するために用意されています。 関数では、頻繁に[使用](#setfieldtype):D[フィールド](../../mfc/reference/cdaorecordset-class.md#dofieldexchange)の種類を使用します。 DFX グローバル関数の詳細については、「[レコード フィールド エクスチェンジ関数](../../mfc/reference/record-field-exchange-functions.md)」を参照してください。 独自のデータ型に対するカスタム DFX ルーチンの作成については、[テクニカル ノート 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CDaoFieldExchange`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="cdaofieldexchangeisvalidoperation"></a><a name="isvalidoperation"></a>カダフィールドエクスチェンジ::IsValidオペレーション

独自の DFX 関数を記述する`IsValidOperation`場合は、関数の先頭で呼び出し、特定のフィールド データ メンバー型 (a`CDaoFieldExchange::outputColumn`または`CDaoFieldExchange::param`a) に対して現在の操作を実行できるかどうかを判断します。

```
BOOL IsValidOperation();
```

### <a name="return-value"></a>戻り値

現在の操作が更新されるフィールドの種類に適している場合は、0 以外の値を指定します。

### <a name="remarks"></a>解説

DFX メカニズムによって実行される操作の一部は、可能なフィールドの種類の 1 つにだけ適用されます。 既存の DFX 関数のモデルに従います。

カスタム DFX ルーチンの作成に関する追加情報については、[テクニカル ノート 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)を参照してください。

## <a name="cdaofieldexchangem_noperation"></a><a name="m_noperation"></a>カダフィールドエクスチェンジ::m_nOperation

フィールド エクスチェンジ オブジェクトに関連付けられた[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトに対して実行される操作を識別します。

### <a name="remarks"></a>解説

オブジェクト`CDaoFieldExchange`は、レコードセットに対してさまざまな DFX 操作のコンテキストを提供します。

> [!NOTE]
> 以下の「マークフォーアニュー」および「フィールドNull」操作で説明されている PSEUDONULL 値は、フィールドを Null にマークするために使用される値です。 DAO レコード フィールド エクスチェンジ 機構 (DFX) では、この値を使用して、Null として明示的にマークされたフィールドが決定されます。 フィールドに対[して](../../atl-mfc-shared/reference/coledatetime-class.md)は[疑](../../mfc/reference/colecurrency-class.md)似 NULL は必要ありません。

可能な値`m_nOperation`は次のとおりです。

|Operation|説明|
|---------------|-----------------|
|`AddToParameterList`|SQL ステートメントの**PARAMETERS**句を作成します。|
|`AddToSelectList`|SQL ステートメントの**SELECT**句を作成します。|
|`BindField`|データベース内のフィールドをアプリケーションのメモリ位置にバインドします。|
|`BindParam`|レコードセットのクエリのパラメータ値を設定します。|
|`Fixup`|フィールドの Null ステータスを設定します。|
|`AllocCache`|レコードセット内の "ダーティ" フィールドのチェックに使用するキャッシュを割り当てます。|
|`StoreField`|現在のレコードをキャッシュに保存します。|
|`LoadField`|レコードセット内のキャッシュされたデータ メンバー変数を復元します。|
|`FreeCache`|レコードセット内の "ダーティ" フィールドのチェックに使用されるキャッシュを解放します。|
|`SetFieldNull`|フィールドの状態を Null に設定し、値を PSEUDONULL に設定します。|
|`MarkForAddNew`|PSEUDONULL でない場合は、フィールドに 「ダーティ」のマークを付けます。|
|`MarkForEdit`|キャッシュに一致しない場合は、フィールドに "ダーティ" のマークを付けます。|
|`SetDirtyField`|"ダーティ" としてマークされたフィールド値を設定します。|
|`DumpField`|フィールドの内容をダンプします (デバッグのみ)。|
|`MaxDFXOperation`|入力チェックに使用します。|

## <a name="cdaofieldexchangem_prs"></a><a name="m_prs"></a>カダフィールドエクスチェンジ::m_prs

オブジェクトに関連付けられた[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトへの`CDaoFieldExchange`ポインターを格納します。

### <a name="remarks"></a>解説

## <a name="cdaofieldexchangesetfieldtype"></a><a name="setfieldtype"></a>セオフィールドエクスチェンジ::セットフィールドタイプ

クラス`SetFieldType`の`DoFieldExchange`オーバーライド`CDaoRecordset`を呼び出します。

```cpp
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>パラメーター

*フィールドタイプ*<br/>
で宣言`CDaoFieldExchange`された**列挙型 FieldType**の値は、次のいずれかになります。

- `CDaoFieldExchange::outputColumn`

- `CDaoFieldExchange::param`

### <a name="remarks"></a>解説

通常、ClassWizard は、この呼び出しを書き込みます。 独自の関数を記述し、ウィザードを使用して`DoFieldExchange`関数を記述する場合は、フィールド マップの外部で独自の関数への呼び出しを追加します。 ウィザードを使用しない場合、フィールド マップは存在しません。 呼び出しは、クラスの各フィールド データ メンバーに対して 1 つずつ、DFX 関数を`CDaoFieldExchange::outputColumn`呼び出す前に、フィールドの型を .

レコードセット クラスをパラメーター化する場合は、すべてのパラメータ データ メンバ (フィールド マップ外) に対する DFX 呼び`SetFieldType`出しを追加し、これらの呼び出しの前に を呼び出す必要があります。 値`CDaoFieldExchange::param`を渡します。 (代わりに[、CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)を使用して、そのパラメーター値を設定できます。

一般に、フィールド データ メンバーまたはパラメーター データ メンバーに関連付けられている DFX 関数呼び出`SetFieldType`しの各グループの前に、 を呼び出す必要があります。 各`SetFieldType`呼び出しの*nFieldType*パラメーターは、呼び出しの後に DFX 関数`SetFieldType`呼び出しによって表されるデータ メンバーの型を識別します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/cdaorecordset-class.md)
