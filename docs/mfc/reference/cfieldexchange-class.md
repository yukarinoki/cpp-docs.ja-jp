---
title: CFieldExchange クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFieldExchange
- AFXDB/CFieldExchange
- AFXDB/CFieldExchange::IsFieldType
- AFXDB/CFieldExchange::SetFieldType
dev_langs:
- C++
helpviewer_keywords:
- CFieldExchange [MFC], IsFieldType
- CFieldExchange [MFC], SetFieldType
ms.assetid: 24c5c0b3-06a6-430e-9b6f-005a2c65e29f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bad68253525fd728b67f2e256c48a3edbf48d720
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
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
|[CFieldExchange::IsFieldType](#isfieldtype)|更新されるフィールドの型の場合は、現在の操作は、0 以外を返しますが適切なします。|  
|[つ](#setfieldtype)|レコード セットのデータ メンバーの種類を指定します: 列またはパラメーター: 次の呼び出しまで RFX 関数に以下のすべての呼び出しによって表される`SetFieldType`です。|  
  
## <a name="remarks"></a>コメント  
 `CFieldExchange` 基本クラスはありません。  
  
 バルク行フェッチを実装するカスタム データ型のデータ エクス チェンジ ルーチンを記述する場合は、このクラスを使用してください。それ以外の場合、していない直接このクラスを使用します。 バルク RFX データ ソースの現在のレコードの対応するフィールドとレコード セット オブジェクトのフィールド データ メンバーのデータを交換します。  
  
> [!NOTE]
>  オープン データベース コネクティビティ (ODBC) クラスではなく、データ アクセス オブジェクト (DAO) クラスで作業している場合は、クラスを使用して[CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md)代わりにします。 詳細については、記事を参照してください。[概要: データベース プログラミング](../../data/data-access-programming-mfc-atl.md)です。  
  
 A`CFieldExchange`オブジェクトを提供するコンテキスト情報を必要なレコード フィールド エクス チェンジまたはバルク レコード フィールド エクスを配置します。 `CFieldExchange` オブジェクトは、バインディング パラメーターのフィールド データ メンバーなど、現在のレコードのフィールドでさまざまなフラグを設定するときに、操作の数をサポートします。 バルク RFX 操作によって定義された型のレコード セット クラスのデータ メンバーに対して実行され、 `enum` **FieldType**で`CFieldExchange`です。 考えられる**FieldType**値は。  
  
- **CFieldExchange::outputColumn**フィールド データ メンバーにします。  
  
- **CFieldExchange::inputParam**または**CFieldExchange::param**の入力パラメーターのデータ メンバーです。  
  
- **CFieldExchange::outputParam**出力パラメーターのデータ メンバーにします。  
  
- **CFieldExchange::inoutParam**入力/出力パラメーター データ メンバーにします。  
  
 クラスのメンバー関数とデータ メンバーの多くは、独自のカスタム RFX ルーチンを記述するために提供されます。 使用して`SetFieldType`頻繁にします。 詳細については、記事を参照してください。[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)と[レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)です。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。 グローバル関数とバルク RFX の詳細については、「[レコード フィールド エクス チェンジ関数](../../mfc/reference/record-field-exchange-functions.md)のこのリファレンス MFC マクロとグローバルのセクションでします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CFieldExchange`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  
  
##  <a name="isfieldtype"></a>  CFieldExchange::IsFieldType  
 RFX 関数を記述する場合は、呼び出す`IsFieldType`特定フィールドまたはパラメーターのデータ メンバー型に現在の操作を実行できるかどうかを決定する、関数の先頭 (、 **CFieldExchange::outputColumn**、 **CFieldExchange::inputParam**、 **CFieldExchange::param**、 **CFieldExchange::outputParam**、または**CFieldExchange::inoutParam**).  
  
```  
BOOL IsFieldType(UINT* pnField);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnField*  
 このパラメーターには、フィールドまたはパラメーターのデータ メンバーの順序番号が返されます。 この数は、データ メンバーの順序、 [CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)または[CRecordset::DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)関数。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、現在のフィールドまたはパラメーターの型に現在の操作を実行することができます。  
  
### <a name="remarks"></a>コメント  
 既存の RFX 関数のモデルに従います。  
  
##  <a name="setfieldtype"></a>  つ  
 呼び出す必要がある`SetFieldType`レコード セット クラスの[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)または[DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)をオーバーライドします。  
  
```  
void SetFieldType(UINT nFieldType);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFieldType`  
 値、 **enum FieldType**で宣言された`CFieldExchange`次のいずれかを指定することができます。  
  
- **CFieldExchange::outputColumn**  
  
- **CFieldExchange::inputParam**  
  
- **CFieldExchange::param**  
  
- **CFieldExchange::outputParam**  
  
- **CFieldExchange::inoutParam**  
  
### <a name="remarks"></a>コメント  
 フィールド データ メンバーを呼び出す必要があります`SetFieldType`のパラメーターを持つ**CFieldExchange::outputColumn**rfx 関数または Bulk RFX 関数を呼び出すと、その後です。 バルク行フェッチを実装していないかどうかは、この ClassWizard 配置`SetFieldType`、フィールド マップのセクションでの呼び出し`DoFieldExchange`です。  
  
 レコード セット クラスをパラメーター化する必要がありますを呼び出した場合`SetFieldType`、もう一度、フィールド マップのセクションの外部続けて rfx 関数呼び出しのすべてのパラメーター データ メンバーのです。 パラメーター データ メンバーの種類ごとにいる必要があります独自`SetFieldType`呼び出します。 次の表は、別の値を渡すことができますを区別`SetFieldType`クラスのパラメーターのデータ メンバーを表す。  
  
|SetFieldType パラメーター値|パラメーター データ メンバーの型|  
|----------------------------------|-----------------------------------|  
|**CFieldExchange::inputParam**|入力パラメーターです。 レコード セットのクエリまたはストアド プロシージャに渡される値。|  
|**CFieldExchange::param**|同じ**CFieldExchange::inputParam**です。|  
|**CFieldExchange::outputParam**|出力パラメーターです。 レコード セットのストアド プロシージャの戻り値。|  
|**CFieldExchange::inoutParam**|入力/出力パラメーターです。 渡されたられ、レコード セットのストアド プロシージャから返される値。|  
  
 一般に、フィールド データ メンバーまたはパラメーター データ メンバーに関連付けられている RFX 関数の呼び出しの各グループの前への呼び出し`SetFieldType`です。 `nFieldType`の各パラメーター`SetFieldType`呼び出しに続く RFX 関数の呼び出しによって表されるデータ メンバーの種類を識別する、`SetFieldType`呼び出します。  
  
 出力パラメーターと入出力パラメーターの処理の詳細については、次を参照してください。、`CRecordset`メンバー関数は、 [FlushResultSet](../../mfc/reference/crecordset-class.md#flushresultset)です。 バルク RFX 関数の詳細については、トピックを参照してください。[レコード フィールド エクス チェンジ関数](../../mfc/reference/record-field-exchange-functions.md)です。 バルク行フェッチの関連情報については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。  
  
### <a name="example"></a>例  
 この例の呼び出しを伴う RFX 関数を複数回呼び出します`SetFieldType`です。 なお`SetFieldType`経由で呼び出され、`pFX`へのポインター、`CFieldExchange`オブジェクト。  
  
 [!code-cpp[NVC_MFCDatabase#33](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRecordset クラス](../../mfc/reference/crecordset-class.md)
