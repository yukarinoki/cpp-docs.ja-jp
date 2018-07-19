---
title: CDaoFieldExchange クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoFieldExchange
- AFXDAO/CDaoFieldExchange
- AFXDAO/CDaoFieldExchange::IsValidOperation
- AFXDAO/CDaoFieldExchange::SetFieldType
- AFXDAO/CDaoFieldExchange::m_nOperation
- AFXDAO/CDaoFieldExchange::m_prs
dev_langs:
- C++
helpviewer_keywords:
- CDaoFieldExchange [MFC], IsValidOperation
- CDaoFieldExchange [MFC], SetFieldType
- CDaoFieldExchange [MFC], m_nOperation
- CDaoFieldExchange [MFC], m_prs
ms.assetid: 350a663e-92ff-44ab-ad53-d94efa2e5823
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9f5f4de25c0ed4643f93626f92a83942c70dfce5
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337841"
---
# <a name="cdaofieldexchange-class"></a>CDaoFieldExchange クラス
DAO データベース クラスで使われる DAO レコード フィールド エクスチェンジ (DFX: DAO Record Field eXchange) ルーチンをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CDaoFieldExchange  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoFieldExchange::IsValidOperation](#isvalidoperation)|現在の操作がある場合、0 以外の値を返します。 適切な更新されるフィールドの型。|  
|[CDaoFieldExchange::SetFieldType](#setfieldtype)|レコード セットのデータ メンバーの種類を指定します: 列またはパラメーター: 次回の呼び出しまで DFX 関数へのすべての後続の呼び出しによって表される`SetFieldType`します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoFieldExchange::m_nOperation](#m_noperation)|レコード セットの現在の呼び出しによって実行される DFX 操作`DoFieldExchange`メンバー関数。|  
|[CDaoFieldExchange::m_prs](#m_prs)|DFX 操作が実行されているレコード セットへのポインター。|  
  
## <a name="remarks"></a>Remarks  
 `CDaoFieldExchange` 基本クラスはありません。  
  
 このクラスを使用して、カスタム データ型のデータ エクス チェンジ ルーチンを記述する場合それ以外の場合、直接使用しないこのクラス。 DFX のフィールド データ メンバーの間でデータの交換、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトとデータ ソースの現在のレコードの対応するフィールド。 DFX は、データ ソースから、データ ソースには、両方向で exchange を管理します。 参照してください[テクニカル ノート 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)用カスタム DFX ルーチンを記述する方法について。  
  
> [!NOTE]
>  DAO データベース クラスは、ベースの開いているデータベースの接続 (ODBC) で MFC データベース クラスとは異なります。 DAO データベース クラスの名前には、"CDao"プレフィックスが付いています。 DAO クラスで ODBC データ ソースのアクセスできます。 一般に、DAO に基づいて MFC クラスは、ODBC に基づいて、MFC クラスよりもより高機能なは。 DAO ベースのクラスは、独自のデータベース エンジンを使用して、ODBC ドライバーを含む、データにアクセスできます。 また、DAO を自分で呼び出すのではなくクラスを使用してテーブルの追加などのデータ定義言語 (DDL) 操作をサポートします。  
  
> [!NOTE]
>  DAO レコード フィールド エクス (チェンジ DFX) は、ODBC ベースの MFC データベース クラスではレコード フィールド エクス (チェンジ RFX) によく似ています ( `CDatabase`、 `CRecordset`)。 RFX を理解している場合は、使いやすい DFX を検索されます。  
  
 A`CDaoFieldExchange`コンテキスト情報に必要な dao レコード フィールド エクス行われるようにオブジェクトを提供します。 `CDaoFieldExchange` オブジェクトは、多くの操作、バインド パラメーター、フィールド データ メンバーなど、現在のレコードのフィールドでさまざまなフラグの設定をサポートします。 DFX 操作によって定義された型のレコード セット クラスのデータ メンバーに対して実行される、 **enum** **FieldType**で`CDaoFieldExchange`します。 考えられる**FieldType**値は。  
  
- `CDaoFieldExchange::outputColumn` フィールド データ メンバーにします。  
  
- `CDaoFieldExchange::param` パラメーターのデータ メンバーにします。  
  
 [IsValidOperation](#isvalidoperation)メンバー関数は、独自のカスタム DFX ルーチンの用意されています。 使用する[SetFieldType](#setfieldtype)で頻繁に、 [CDaoRecordset::DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange)関数。 詳細については、DFX のグローバル関数は、次を参照してください。[レコード フィールド エクス チェンジ関数](../../mfc/reference/record-field-exchange-functions.md)します。 独自のデータ型用カスタム DFX ルーチンを記述する方法の詳細については、次を参照してください。[テクニカル ノート 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CDaoFieldExchange`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdao.h  
  
##  <a name="isvalidoperation"></a>  CDaoFieldExchange::IsValidOperation  
 DFX 関数を記述する場合は、呼び出す`IsValidOperation`特定のフィールド データ メンバーの種類で現在の操作を実行できるかどうかを判断する関数の先頭 (、`CDaoFieldExchange::outputColumn`または`CDaoFieldExchange::param`)。  
  
```  
BOOL IsValidOperation();
```  
  
### <a name="return-value"></a>戻り値  
 現在の操作が更新されるフィールドの型の適切な場合は 0 以外の値。  
  
### <a name="remarks"></a>Remarks  
 DFX メカニズムによって実行された操作の一部は、可能なフィールドの種類のいずれかにのみ適用されます。 DFX 関数を既存のモデルに従います。  
  
 カスタム DFX ルーチンを記述する方法の詳細については、次を参照してください。[テクニカル ノート 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)します。  
  
##  <a name="m_noperation"></a>  CDaoFieldExchange::m_nOperation  
 実行する操作を識別、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)フィールド exchange オブジェクトに関連付けられているオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 `CDaoFieldExchange`オブジェクトは、多数のレコード セットの DFX 操作を別のコンテキストを提供します。  
  
> [!NOTE]
>  PSEUDONULL MarkForAddNew とな操作を以下で説明されている値は、Null のフィールドをマークするために使用値です。 DAO レコード フィールド エクス機構 (DFX) では、この値を使用して、どのフィールドが明示的にマークされて Null を調べます。 PSEUDONULL は必要ありません[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)と[COleCurrency](../../mfc/reference/colecurrency-class.md)フィールド。  
  
 使用可能な値の`m_nOperation`は。  
  
|操作|説明|  
|---------------|-----------------|  
|`AddToParameterList`|ビルド、**パラメーター** SQL ステートメントの句。|  
|`AddToSelectList`|ビルド、**選択**SQL ステートメントの句。|  
|`BindField`|アプリケーション内のメモリ位置に、データベース内のフィールドをバインドします。|  
|`BindParam`|レコード セットのクエリのパラメーターの値を設定します。|  
|`Fixup`|フィールドの Null 状態を設定します。|  
|`AllocCache`|レコード セットの「ダーティ」フィールドを確認するためのキャッシュを割り当てます。|  
|`StoreField`|現在のレコードをキャッシュに保存します。|  
|`LoadField`|レコード セット内のキャッシュされたデータ メンバー変数を復元します。|  
|`FreeCache`|レコード セットの「ダーティ」フィールドを確認するためのキャッシュを解放します。|  
|`SetFieldNull`|フィールドのステータスを Null と PSEUDONULL を値に設定します。|  
|`MarkForAddNew`|記号フィールド「ダーティ」PSEUDONULL しない場合。|  
|`MarkForEdit`|キャッシュと一致しない場合はフィールドは「ダーティ」のマークされます。|  
|`SetDirtyField`|フィールド「ダーティ」としてマークされている値の設定|  
|`DumpField`|(デバッグのみ) のフィールドの内容をダンプします。|  
|`MaxDFXOperation`|入力チェックに使用されます。|  
  
##  <a name="m_prs"></a>  CDaoFieldExchange::m_prs  
 ポインターが含まれています、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトに関連付けられている、`CDaoFieldExchange`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setfieldtype"></a>  CDaoFieldExchange::SetFieldType  
 呼び出す`SetFieldType`で、`CDaoRecordset`クラスの`DoFieldExchange`をオーバーライドします。  
  
```  
void SetFieldType(UINT nFieldType);
```  
  
### <a name="parameters"></a>パラメーター  
 *nFieldType*  
 値、 **enum FieldType**で宣言された`CDaoFieldExchange`、次のいずれかとなることができます。  
  
- `CDaoFieldExchange::outputColumn`  
  
- `CDaoFieldExchange::param`  
  
### <a name="remarks"></a>Remarks  
 通常、ClassWizard では、この呼び出しを書き込みます。 独自の関数を作成して書き込む、ウィザードを使用しているかどうか、`DoFieldExchange`関数は、フィールド マップの外部の独自の関数の呼び出しを追加します。 ウィザードを使用しない場合がありますされませんフィールド マップ。 呼び出しは、クラスの各フィールドのデータ メンバーのいずれかの DFX 関数への呼び出しの前に、フィールドの型を識別する`CDaoFieldExchange::outputColumn`します。  
  
 レコード セット クラスをパラメーター化する場合は、すべてのパラメーター データ メンバー (フィールド マップの) 外の DFX 呼び出しを追加しへの呼び出しでこれらの呼び出しの前にする必要があります`SetFieldType`します。 値を渡す`CDaoFieldExchange::param`します。 (代わりに、使用することができます、 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)し、そのパラメーターの値を設定します)。  
  
 一般に、フィールド データ メンバーまたはパラメーターのデータ メンバーに関連付けられた DFX 関数呼び出しの各グループへの呼び出し前が必要`SetFieldType`します。 *NFieldType*の各パラメーター`SetFieldType`呼び出しに続く DFX 関数の呼び出しによって表されるデータ メンバーの種類を識別する、`SetFieldType`呼び出します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)
