---
title: Idbschemarowsetimpl::checkrestrictions |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CheckRestrictions
- IDBSchemaRowsetImpl::CheckRestrictions
- IDBSchemaRowsetImpl.CheckRestrictions
dev_langs:
- C++
helpviewer_keywords:
- CheckRestrictions method
ms.assetid: 3c9d77d2-0e4b-48fa-80db-d735da19f1cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c951c892a2e6d875fb1085b1d3208d43938347c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="idbschemarowsetimplcheckrestrictions"></a>IDBSchemaRowsetImpl::CheckRestrictions
スキーマ行セットに対して制限の妥当性をチェックします。  
  
## <a name="syntax"></a>構文  
  
```
HRESULT CheckRestrictions(REFGUID rguidSchema,  
   ULONG cRestrictions,  const VARIANT rgRestrictions[]);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `rguidSchema`  
 [入力] 要求するスキーマ行セット GUID ( `DBSCHEMA_TABLES`など) への参照。  
  
 `cRestrictions`  
 [入力] コンシューマーがスキーマ行セットに渡した制限の数。  
  
 `rgRestrictions`  
 [入力] 設定する制限値の長さ *cRestrictions* の配列。 詳細については、 `rgRestrictions` SetRestrictions [の](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)パラメーターの説明を参照してください。  
  
## <a name="remarks"></a>コメント  
 `CheckRestrictions` を使用して、スキーマ行セットに対して制限の妥当性をチェックします。 CheckRestrictions は、 `DBSCHEMA_TABLES`、 **DBSCHEMA_COLUMNS**、および **DBSCHEMA_PROVIDER_TYPES** の各スキーマ行セットの制限をチェックします。 これを呼び出して、コンシューマーの **IDBSchemaRowset::GetRowset** 呼び出しが正しいかどうかを判断してください。 上記以外のスキーマ行セットをサポートする場合は、このタスクを実行する独自の関数を作成する必要があります。  
  
 `CheckRestrictions` は、コンシューマーが、プロバイダーによってサポートされている正しい制限および制限の種類 (文字列の場合は [など) を持つ](../../data/oledb/idbschemarowsetimpl-getrowset.md) GetRowset `VT_BSTR` を呼び出しているかどうかを判断します。 また、正しい制限数がサポートされているかどうかも判断します。 `CheckRestrictions` は、既定で [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) 呼び出しを通じて、任意の行セットについてプロバイダーがサポートしている制限の種類を確認します。 次に、コンシューマーが呼び出した制限とプロバイダーがサポートしている制限を比較することで、処理は成功または失敗します。  
  
 スキーマ行セットの詳細については、次を参照してください。 [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx)で、 *OLE DB プログラマーズ リファレンス*Windows SDK に含まれています。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IDBSchemaRowsetImpl クラス](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl クラス メンバー](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)