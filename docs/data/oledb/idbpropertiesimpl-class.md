---
title: IDBPropertiesImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBPropertiesImpl
- ATL.IDBPropertiesImpl
- ATL.IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl
dev_langs:
- C++
helpviewer_keywords:
- IDBPropertiesImpl class
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3685e6a77e4293ef65b5ee98a0aa326500cfdb2d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="idbpropertiesimpl-class"></a>IDBPropertiesImpl クラス
実装を提供、`IDBProperties`インターフェイスです。  
  
## <a name="syntax"></a>構文

```cpp
template <class T>   
class ATL_NO_VTABLE IDBPropertiesImpl   
   : public IDBProperties, public CUtlProps<T>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IDBPropertiesImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)|データ ソース オブジェクトで現在設定されている初期化プロパティ グループ内のプロパティの値に設定されているデータ ソース、データ ソース情報、および初期化プロパティ グループのプロパティの値を返す、列挙子。|  
|[GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)|プロバイダーでサポートされているすべてのプロパティに関する情報を返します。|  
|[SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)|列挙子のデータ ソースと初期化プロパティ グループのデータ ソース オブジェクトまたは Initialization プロパティ グループのプロパティを設定します。|  
  
## <a name="remarks"></a>コメント  
 [IDBProperties](https://msdn.microsoft.com/en-us/library/ms719607.aspx)はデータ ソース オブジェクトに必要なインターフェイスと列挙子のオプションのインターフェイスです。 ただし、列挙子を公開する場合[IDBInitialize](https://msdn.microsoft.com/en-us/library/ms713706.aspx)、公開している`IDBProperties`です。 `IDBPropertiesImpl` 実装する`IDBProperties`によって定義された静的関数を使用して[BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)