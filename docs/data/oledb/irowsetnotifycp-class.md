---
title: IRowsetNotifyCP クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetNotifyCP
dev_langs:
- C++
helpviewer_keywords:
- IRowsetNotifyCP class
ms.assetid: ccef402b-94a0-4c2e-9a13-7e854ef82390
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 19147710ce8965222eed998e1a7ab4baa1e32caf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetnotifycp-class"></a>IRowsetNotifyCP クラス
プロバイダー サイト ポイントの接続インターフェイスを実装する[IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx)です。  
  
## <a name="syntax"></a>構文

```cpp
template <class T, class ReentrantEventSync = CComSharedMutex>  
class IRowsetNotifyCP :   
   public IConnectionPointImpl<  
      T,   
      piid = &__uuidof(IRowsetNotify),   
      CComDynamicUnkArray DynamicUnkArray>,  
   public ReentrantEventSync  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス`IRowsetNotifyCP`です。  
  
 `ReentrantEventSync`  
 再入をサポートする相互排他クラス (既定値は**CComSharedMutex**)。 ミュー テックスは、リソースへの 1 つのスレッド相互に排他的アクセスを許可する同期オブジェクトです。  
  
 `piid`  
 インターフェイス ID のポインター (**IID\***) の**IRowsetNotify**コネクション ポイント インターフェイスです。 既定値は **& __uuidof(IRowsetNotify)** です。  
  
 `DynamicUnkArray`  
 型の配列[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)、これは、動的に割り当てられた配列の**IUnknown**シンク インターフェイスのクライアントへのポインター。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[Fire_OnFieldChange](../../data/oledb/irowsetnotifycp-fire-onfieldchange.md)|列の値に変更をコンシューマーに通知します。|  
|[Fire_OnRowChange](../../data/oledb/irowsetnotifycp-fire-onrowchange.md)|行に影響する変更をコンシューマーに通知します。|  
|[Fire_OnRowsetChange](../../data/oledb/irowsetnotifycp-fire-onrowsetchange.md)|行セット全体に影響する変更をコンシューマーに通知します。|  
  
## <a name="remarks"></a>コメント  
 `IRowsetNotifyCP` 実装は、接続ポイントに対するリスナーに通知する関数をブロードキャスト**IID_IRowsetNotify**行セットの内容を変更します。  
  
 実装し、登録する必要がありますもなお`IRowsetNotify`(とも呼ばれる、「シンク」) を使用して、コンシューマーで[IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)コンシューマーが通知を処理できるようにします。 参照してください[通知の受信](../../data/oledb/receiving-notifications.md)に関するコンシューマーのコネクション ポイントのインターフェイスを実装します。  
  
 通知の実装の詳細については、「通知のサポート」を参照してください[更新可能なプロバイダーを作成する](../../data/oledb/creating-an-updatable-provider.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [通知 (COM)](http://msdn.microsoft.com/library/windows/desktop/ms678433)   
 [BEGIN_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#begin_connection_point_map)   
 [END_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#end_connection_point_map)   
 [CONNECTION_POINT_ENTRY](../../atl/reference/connection-point-macros.md#connection_point_entry)   
 [更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)