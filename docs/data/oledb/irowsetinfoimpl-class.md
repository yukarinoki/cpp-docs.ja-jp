---
title: IRowsetInfoImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetInfoImpl
- IRowsetInfoImpl
- ATL::IRowsetInfoImpl
dev_langs:
- C++
helpviewer_keywords:
- IRowsetInfoImpl class
ms.assetid: 9c654155-7727-464e-bd31-143e68391a47
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f9b784dbb13ff39be21ccd353d514dd244d5ae41
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetinfoimpl-class"></a>IRowsetInfoImpl クラス
実装を提供、 [IRowsetInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx)インターフェイスです。  
  
## <a name="syntax"></a>構文

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE IRowsetInfoImpl :   
   public IRowsetInfo,    
   public CUtlProps<PropClass>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IRowsetInfoImpl`です。  
  
 `PropClass`  
 その既定値はユーザー定義プロパティ クラス`T`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/irowsetinfoimpl-getproperties.md)|行セットがサポートされているすべてのプロパティの現在の設定を返します。|  
|[GetReferencedRowset](../../data/oledb/irowsetinfoimpl-getreferencedrowset.md)|ブックマークが適用される行セットにインターフェイス ポインターを返します。|  
|[GetSpecification](../../data/oledb/irowsetinfoimpl-getspecification.md)|この行セットを作成するオブジェクト (コマンドまたはセッション) のインターフェイス ポインターを返します。|  
  
## <a name="remarks"></a>コメント  
 行セットの必須のインターフェイスです。 このクラスを使用して、行セット プロパティを実装して、[プロパティ セット マップ](../../data/oledb/begin-propset-map.md)コマンド クラスで定義されています。 行セット クラスでは、コマンド クラスのプロパティを使用する設定が表示されますが、行セットは、コマンドまたはセッション オブジェクトを作成するとき、実行時のプロパティのコピーで提供されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** altdb.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)