---
title: Idbschemarowsetimpl::setrestrictions |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBSchemaRowsetImpl::SetRestrictions
- SetRestrictions
- IDBSchemaRowsetImpl.SetRestrictions
dev_langs:
- C++
helpviewer_keywords:
- SetRestrictions method
ms.assetid: 707d5065-b853-4d38-9b67-3066b4d3b279
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8b6effd432b033941d404c4935cdbad5a2336ac8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="idbschemarowsetimplsetrestrictions"></a>IDBSchemaRowsetImpl::SetRestrictions
特定のスキーマ行セットでサポートする制限を指定します。  
  
## <a name="syntax"></a>構文  
  
```
void SetRestrictions(ULONG cRestrictions,  
  GUID* /* rguidSchema */,  
   ULONG* rgRestrictions);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cRestrictions`  
 [入力] `rgRestrictions` 配列の制限の数および `rguidSchema` 配列の GUID の数。  
  
 `rguidSchema`  
 [入力] 制限をフェッチするスキーマ行セットの GUID の配列。 配列の各要素は、1 つのスキーマ行セットの GUID ( `DBSCHEMA_TABLES`など) を保持します。  
  
 `rgRestrictions`  
 [入力] 設定する制限値の長さ `cRestrictions` の配列。 各要素は、GUID によって識別されるスキーマ行セットの制限に対応します。 スキーマ行セットがプロバイダーによってサポートされていない場合、その要素は 0 に設定されます。 それ以外の場合、 **ULONG** 値は、そのスキーマ行セットでサポートされている制限を表すビット マスクを保持します。 特定のスキーマ行セットに対応する制限の詳細については、スキーマ行セット Guid の表を参照してくださいで[IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx)で、 *OLE DB プログラマーズ リファレンス*windowsSDK。  
  
## <a name="remarks"></a>コメント  
 **IDBSchemaRowset** オブジェクトは `SetRestrictions` を呼び出して、特定のスキーマ行セットでサポートする制限を判断します。SetRestrictions は、アップキャストされたポインターを通じて [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) によって呼び出されます。 制限により、コンシューマーは一致する行だけをフェッチできます (たとえば、テーブル "MyTable" 内のすべての列を検索します)。 制限は省略可能であり、制限がサポートされていない場合 (既定)、常にすべてのデータが返されます。  
  
 このメソッドの既定の実装では、 `rgRestrictions` 配列の要素が 0 に設定されます。 既定以外の制限を設定する場合は、セッション クラスで既定値をオーバーライドします。  
  
 スキーマ行セットのサポートの実装については、「 [スキーマ行セットのサポート](../../data/oledb/supporting-schema-rowsets.md)」を参照してください。  
  
 スキーマ行セットをサポートするプロバイダーの例については、 [UpdatePV](../../visual-cpp-samples.md) サンプルを参照してください。  
  
 スキーマ行セットの詳細については、次を参照してください。 [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx)で、 *OLE DB プログラマーズ リファレンス*Windows SDK に含まれています。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IDBSchemaRowsetImpl クラス](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl クラス メンバー](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)   
 [スキーマ行セットのサポート](../../data/oledb/supporting-schema-rowsets.md)   
 [UpdatePV](../../visual-cpp-samples.md)