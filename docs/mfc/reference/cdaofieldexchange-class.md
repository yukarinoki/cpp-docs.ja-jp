---
title: CDaoFieldExchange クラス |Microsoft ドキュメント
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
ms.openlocfilehash: b4f702f619eb06a11cbbf7ec5be7407d12f7f445
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
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
|[CDaoFieldExchange::IsValidOperation](#isvalidoperation)|更新されるフィールドの型の場合は、現在の操作は、0 以外を返しますが適切なします。|  
|[CDaoFieldExchange::SetFieldType](#setfieldtype)|レコード セットのデータ メンバーの種類を指定します: 列またはパラメーター: 次の呼び出しまで DFX 関数へのすべての後続の呼び出しによって表される`SetFieldType`です。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoFieldExchange::m_nOperation](#m_noperation)|レコード セットの現在の呼び出しによって実行される DFX 操作`DoFieldExchange`メンバー関数。|  
|[CDaoFieldExchange::m_prs](#m_prs)|DFX の操作が実行されているレコード セットへのポインター。|  
  
## <a name="remarks"></a>コメント  
 `CDaoFieldExchange` 基本クラスはありません。  
  
 カスタム データ型のデータ エクス チェンジ ルーチンを記述する場合は、このクラスを使用してください。それ以外の場合、していない直接このクラスを使用します。 DFX のフィールド データ メンバーの間のデータの交換、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトおよびデータ ソースの現在のレコードの対応するフィールドです。 DFX は、データ ソースから、データ ソースに、双方向で交換を管理します。 参照してください[テクニカル ノート 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)については、カスタム DFX ルーチンを記述します。  
  
> [!NOTE]
>  DAO データベース クラスは、MFC データベース クラス ODBC Open Database Connectivity () をベースとは異なります。 DAO データベース クラスの名前では、"CDao"プレフィックスがあります。 DAO クラスで ODBC データ ソースのアクセスすることもできます。 一般に、DAO に基づいて MFC クラスは、ODBC に基づいて MFC クラスよりもより高機能です。 DAO ベースのクラスは、独自のデータベース エンジンを使用して、ODBC ドライバーを介してなどのデータにアクセスできます。 また、DAO を呼び出さずにではなくクラスを使用してテーブルの追加などのデータ定義言語 (DDL) 操作をサポートします。  
  
> [!NOTE]
>  DAO レコード フィールド エクス (チェンジ DFX) は、ODBC ベースの MFC データベース クラスではレコード フィールド エクス (チェンジ RFX) によく似ています ( `CDatabase`、 `CRecordset`)。 RFX を理解している場合は、使いやすい DFX を検索されます。  
  
 A`CDaoFieldExchange`オブジェクトを提供するコンテキスト情報を必要な dao レコード フィールド エクスを実行します。 `CDaoFieldExchange` オブジェクトは、バインディング パラメーターのフィールド データ メンバーなど、現在のレコードのフィールドでさまざまなフラグを設定するときに、操作の数をサポートします。 DFX 操作によって定義された型のレコード セット クラスのデータ メンバーに対して実行され、 `enum` **FieldType**で`CDaoFieldExchange`です。 考えられる**FieldType**値は。  
  
- **CDaoFieldExchange::outputColumn**フィールド データ メンバーにします。  
  
- **CDaoFieldExchange::param**パラメーター データ メンバーにします。  
  
 [IsValidOperation](#isvalidoperation)メンバー関数が、独自のカスタム DFX ルーチンを記述するために用意されています。 使用して[SetFieldType](#setfieldtype)で頻繁に、 [CDaoRecordset::DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange)関数。 DFX のグローバル関数に関する詳細については、「[レコード フィールド エクス チェンジ関数](../../mfc/reference/record-field-exchange-functions.md)です。 独自のデータ型のカスタム DFX ルーチンを記述する方法については、次を参照してください。[テクニカル ノート 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CDaoFieldExchange`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
##  <a name="isvalidoperation"></a>  CDaoFieldExchange::IsValidOperation  
 DFX 関数を記述する場合は、呼び出す`IsValidOperation`、特定のフィールド データ メンバーの種類で現在の操作を実行できるかどうかを決定する、関数の先頭 (、 **CDaoFieldExchange::outputColumn**または**CDaoFieldExchange::param**)。  
  
```  
BOOL IsValidOperation();
```  
  
### <a name="return-value"></a>戻り値  
 現在の操作が更新されるフィールドの型に適切な場合は 0 以外の値。  
  
### <a name="remarks"></a>コメント  
 DFX メカニズムによって実行される操作の一部は、可能なフィールドの種類のいずれかにのみ適用されます。 DFX 関数を既存のモデルに従います。  
  
 カスタム DFX ルーチンの作成方法の詳細については、次を参照してください。[テクニカル ノート 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)です。  
  
##  <a name="m_noperation"></a>  CDaoFieldExchange::m_nOperation  
 上で実行される操作を識別、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) field exchange オブジェクトに関連付けられているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 `CDaoFieldExchange`オブジェクトは、多数のレコード セットの DFX 操作を別のコンテキストを提供します。  
  
> [!NOTE]
>  **PSEUDONULL** MarkForAddNew とな操作を以下で説明されているは、値は Null のフィールドをマークするために使用します。 DAO レコード フィールド エクス機構 (エクス チェンジ DFX) では、この値を使用して、どのフィールドが明示的にマークされて Null を調べます。 **PSEUDONULL**は必要ありません[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)と[COleCurrency](../../mfc/reference/colecurrency-class.md)フィールドです。  
  
 使用できる値**m_nOperation**は。  
  
|操作|説明|  
|---------------|-----------------|  
|**AddToParameterList**|ビルド、**パラメーター** SQL ステートメントの句。|  
|**AddToSelectList**|ビルド、**選択**SQL ステートメントの句。|  
|**BindField**|データベース内のフィールドをアプリケーションでメモリの場所にバインドします。|  
|**BindParam**|レコード セットのクエリのパラメーターの値を設定します。|  
|**フィックス アップ**|フィールドの Null 状態を設定します。|  
|**AllocCache**|レコード セット内の「ダーティ」フィールドを確認するためのキャッシュを割り当てます。|  
|**StoreField**|現在のレコードをキャッシュに保存します。|  
|**LoadField**|レコード セット内のキャッシュされたデータ メンバー変数を復元します。|  
|**FreeCache**|レコード セット内の「ダーティ」フィールドを確認するためのキャッシュを解放します。|  
|`SetFieldNull`|フィールドの状態を Null とする値に設定**PSEUDONULL**です。|  
|**MarkForAddNew**|マークされていない場合、フィールドの「ダーティ」 **PSEUDONULL**です。|  
|**MarkForEdit**|マークのフィールド「ダーティ」キャッシュと一致しない場合。|  
|**SetDirtyField**|フィールド「ダーティ」としてマークされている値の設定|  
|**DumpField**|フィールドの内容 (デバッグのみ) をダンプします。|  
|**MaxDFXOperation**|入力の確認のために使用します。|  
  
##  <a name="m_prs"></a>  CDaoFieldExchange::m_prs  
 ポインターが含まれています、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトに関連付けられている、`CDaoFieldExchange`オブジェクト。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setfieldtype"></a>  CDaoFieldExchange::SetFieldType  
 呼び出す`SetFieldType`で、`CDaoRecordset`クラスの`DoFieldExchange`をオーバーライドします。  
  
```  
void SetFieldType(UINT nFieldType);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFieldType`  
 値、 **enum FieldType**で宣言された`CDaoFieldExchange`、これで、次のいずれかのことができます。  
  
- **CDaoFieldExchange::outputColumn**  
  
- **CDaoFieldExchange::param**  
  
### <a name="remarks"></a>コメント  
 通常、ClassWizard では、この呼び出しを書き込みます。 独自の関数を作成して書き込む、ウィザードを使用しているかどうか、`DoFieldExchange`関数、フィールド マップ外の独自の関数への呼び出しを追加します。 ウィザードを使用しない場合がありますされませんフィールドのマップ。 呼び出しは、クラスの各フィールド データ メンバーのいずれかの DFX 関数への呼び出しの前に、フィールドの型を識別**CDaoFieldExchange::outputColumn**です。  
  
 レコード セット クラスをパラメーター化する場合は、(、フィールド マップ外) のすべてのパラメーター データ メンバーの DFX 呼び出しを追加しを呼び出してこれらの呼び出しの前にする必要があります`SetFieldType`です。 値を渡す**CDaoFieldExchange::param**です。 (代わりに、使用することができます、 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)し、そのパラメーター値を設定します)。  
  
 一般に、フィールド データ メンバーまたはパラメーター データ メンバーに関連付けられている DFX 関数呼び出しの各グループの前への呼び出し`SetFieldType`です。 `nFieldType`の各パラメーター`SetFieldType`呼び出しに続く DFX 関数呼び出しによって表されるデータ メンバーの種類を識別する、`SetFieldType`呼び出します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)
