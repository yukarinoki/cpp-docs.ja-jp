---
title: IRowsetChangeImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IRowsetChangeImpl
- IRowsetChangeImpl
- ATL.IRowsetChangeImpl
dev_langs:
- C++
helpviewer_keywords:
- providers, updatable
- updatable providers, immediate update
- IRowsetChangeImpl class
ms.assetid: 1e9fee15-ed9e-4387-af8f-215569beca6c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 11435cd1372147efb14aed78448d889fd60dc5a0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetchangeimpl-class"></a>IRowsetChangeImpl クラス
OLE DB テンプレートの実装、 [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) OLE DB 仕様のインターフェイスです。  
  
## <a name="syntax"></a>構文

```cpp
template <  
   class T,   
   class Storage,   
   class BaseInterface = IRowsetChange,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>>  
class ATL_NO_VTABLE IRowsetChangeImpl : public BaseInterface  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス`IRowsetChangeImpl`です。  
  
 `Storage`  
 ユーザー レコードです。  
  
 `BaseInterface`  
 基本クラス、インターフェイスなど`IRowsetChange`です。  
  
 `RowClass`  
 行ハンドルの記憶域ユニットです。  
  
 `MapClass`  
 すべての行ハンドルの記憶域ユニットでは、プロバイダーによって保持されています。  
  
## <a name="members"></a>メンバー  
  
### <a name="interface-methods-used-with-irowsetchange"></a>インターフェイスのメソッド (IRowsetChange で使用)  
  
|||  
|-|-|  
|[DeleteRows](../../data/oledb/irowsetchangeimpl-deleterows.md)|行セットから行を削除します。|  
|[InsertRow](../../data/oledb/irowsetchangeimpl-insertrow.md)|行セットに行を挿入します。|  
|[SetData](../../data/oledb/irowsetchangeimpl-setdata.md)|1 つまたは複数の列のデータ値を設定します。|  
  
### <a name="implementation-method-callback"></a>実装メソッド (コールバック)  
  
|||  
|-|-|  
|[FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md)|データをそのストアにコミットするためのプロバイダーによってオーバーライドされします。|  
  
## <a name="remarks"></a>コメント  
 このインターフェイスは、データ ストアへの即時の書き込み操作を担当します。 「直接」ことを意味するエンドユーザー (、コンシューマーの使用者) は、変更を行った、ときにそれらの変更はすぐに転送データには格納 (および、元に戻すことはできません)。  
  
 `IRowsetChangeImpl` OLE DB を実装して`IRowsetChange`インターフェイスは、これにより、行を削除して、新しい行を挿入する、既存の行の列の値を更新します。  
  
 OLE DB テンプレートの実装には、すべての基本メソッドがサポートしています (`SetData`、 `InsertRow`、および`DeleteRows`)。  
  
> [!IMPORTANT]
>  プロバイダーを実装する前に、次のドキュメントを読むことを強くお勧めします。  
  
-   [更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)  
  
-   第 6 章、 *OLE DB プログラマーズ リファレンス*  
  
-   参照してください、 `RUpdateRowset` UpdatePV サンプルで使用されます  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)