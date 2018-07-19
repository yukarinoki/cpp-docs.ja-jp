---
title: IDBSchemaRowsetImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBSchemaRowsetImpl
dev_langs:
- C++
helpviewer_keywords:
- IDBSchemaRowsetImpl class
ms.assetid: bd7bf0d7-a1c6-4afa-88e3-cfdbdf560703
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dc9da29bcd49b227596325913d521347b6b0ca0e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33110952"
---
# <a name="idbschemarowsetimpl-class"></a>IDBSchemaRowsetImpl クラス
スキーマ行セットの実装を提供します。  
  
## <a name="syntax"></a>構文

```cpp
template <class SessionClass>  
class ATL_NO_VTABLE IDBSchemaRowsetImpl : public IDBSchemaRowset  
```  
  
#### <a name="parameters"></a>パラメーター  
 `SessionClass`  
 `IDBSchemaRowsetImpl` が継承されるクラス。 通常、このクラスは、ユーザーのセッション クラスです。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md)|スキーマ行セットに対して制限の妥当性をチェックします。|  
|[CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md)|テンプレート パラメーターで指定されたオブジェクトの COM オブジェクトの作成関数を実装します。|  
|[SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)|特定のスキーマ行セットでサポートする制限を指定します。|  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)|スキーマ行セットを返します。|  
|[GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)|[IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)でアクセスできるスキーマ行セットの一覧を返します。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、 [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) インターフェイスと、テンプレート化された作成関数 [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md)を実装します。  
  
 OLE DB はスキーマ行セットを使用して、プロバイダーのデータに関するデータを返します。 このようなデータは、多くの場合、"メタデータ" と呼ばれます。 `DBSCHEMA_TABLES`OLE DB プログラマーズ リファレンス **の「** IDBSchemaRowset **」で説明されているように、既定では、プロバイダーは常に**、 [DBSCHEMA_COLUMNS](https://msdn.microsoft.com/en-us/library/ms713686.aspx) 、および *DBSCHEMA_PROVIDER_TYPES*をサポートする必要があります。 スキーマ行セットはスキーマ マップで指定します。 スキーマ マップ エントリの詳細については、「 [SCHEMA_ENTRY](../../data/oledb/schema-entry.md)」を参照してください。  
  
 ATL オブジェクト ウィザードの OLE DB プロバイダー ウィザードでは、プロジェクトのスキーマ行セットのコードが自動的に生成されます (既定では、ウィザードは、以前説明した必須のスキーマ行セットをサポートしています)。ATL オブジェクト ウィザードでコンシューマーを作成すると、スキーマ行セットで正しいデータがプロバイダーにバインドされます。 正しいメタデータを提供するようにスキーマ行セットを実装していないと、正しいデータがバインドされません。  
  
 プロバイダーでスキーマ行セットをサポートする方法については、「 [スキーマ行セットのサポート](../../data/oledb/supporting-schema-rowsets.md)」を参照してください。  
  
 スキーマ行セットの詳細については、 [OLE DB プログラマーズ リファレンス](https://msdn.microsoft.com/en-us/library/ms712921.aspx) の *スキーマ行セット*に関するセクションを参照してください。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IDBSchemaRowsetImpl クラス メンバー](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)   
 [スキーマ行セットのサポート](../../data/oledb/supporting-schema-rowsets.md)