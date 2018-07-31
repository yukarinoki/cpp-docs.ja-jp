---
title: 通知のサポート |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- events [C++], notifications in OLE DB
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB provider templates, notifications
- OLE DB providers, notifications
ms.assetid: 76e875fd-2bfd-4e4e-9f43-dbe5a3fa7382
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9fea13ef4a89ee2a1105702db4fe692c12643d2
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337941"
---
# <a name="supporting-notifications"></a>通知のサポート

## <a name="implementing-connection-point-interfaces-on-the-provider-and-consumer"></a>プロバイダーとコンシューマー接続ポイントのインターフェイスを実装します。  
 通知を実装するにはプロバイダー クラスから継承する必要があります[IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)と[IConnectionPointContainer](../../atl/reference/iconnectionpointcontainerimpl-class.md)します。  
  
 `IRowsetNotifyCP` プロバイダーは、サイト接続ポイントのインターフェイスを実装する[IRowsetNotify](https://msdn.microsoft.com/library/ms712959.aspx)します。 `IRowsetNotifyCP` 実装は、接続ポイント上のリスナーに通知する関数をブロードキャスト`IID_IRowsetNotify`の行セットの内容の変更。  
  
 実装し、登録する必要がありますので注意`IRowsetNotify`(シンクとも呼ばれます) を使用して、コンシューマーで[IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)コンシューマーが通知を処理できるようにします。 コンシューマーのコネクション ポイントのインターフェイスを実装する方法の詳細については、次を参照してください。[通知の受信](../../data/oledb/receiving-notifications.md)します。  
  
 さらに、クラスは、次のように、接続ポイント エントリを定義するマップも含める必要があります。  
  
```  
BEGIN_CONNECTION_POINT_MAP  
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)  
END_CONNECTION_POINT_MAP  
```  
  
## <a name="adding-irowsetnotify"></a>IRowsetNotify を追加します。  
 追加する`IRowsetNotify`、追加する必要がある`IConnectionPointContainerImpl<rowset-name>`と`IRowsetNotifyCP<rowset-name>`継承チェーンをします。  
  
 たとえばの継承チェーンをここでは`RUpdateRowset`で[UpdatePV](http://msdn.microsoft.com/c8bed873-223c-4a7d-af55-f90138c6f38f):  
  
> [!NOTE]
>  サンプル コードはここでは記載されているものと異なる場合があります。サンプル コードは、最新のバージョンと見なす必要があります。  
  
```cpp
///////////////////////////////////////////////////////////////////////////  
// class RUpdateRowset (in rowset.h)  
  
class RUpdateRowset :   
public CRowsetImpl< RUpdateRowset, CAgentMan, CUpdateCommand,   
         CAtlArray< CAgentMan, CAtlArray<CAgentMan>>, CSimpleRow,   
         IRowsetScrollImpl< RUpdateRowset, IRowsetScroll >>,  
      public IRowsetUpdateImpl< RUpdateRowset, CAgentMan >,  
      public IConnectionPointContainerImpl<RUpdateRowset>,  
      public IRowsetNotifyCP<RUpdateRowset>  
```  
  
### <a name="setting-com-map-entries"></a>COM マップ エントリの設定  
 また、行セット内の COM マップに、次を追加する必要があります。  
  
```  
COM_INTERFACE_ENTRY(IConnectionPointContainer)  
COM_INTERFACE_ENTRY_IMPL(IConnectionPointContainer)  
```  
  
 これらのマクロ呼び出しは許可`QueryInterface`接続ポイント コンテナー (の基礎`IRowsetNotify`) プロバイダーに要求されたインターフェイスが見つかりません。 接続ポイントを使用する方法の例は、ATL の多角形のサンプルとチュートリアルを参照してください。  
  
### <a name="setting-connection-point-map-entries"></a>コネクション ポイントのマップのエントリの設定  
 コネクション ポイントのマップを追加する必要があります。 ようになります。  
  
```  
BEGIN_CONNECTION_POINT_MAP(rowset-name)  
     CONNECTION_POINT_ENTRY(_uuidof(IRowsetNotify))  
END_CONNECTION_POINT_MAP()  
```  
  
 このコネクション ポイントのマップを使用すると、探しているコンポーネント、`IRowsetNotify`インターフェイスをプロバイダーで検索します。  
  
### <a name="setting-properties"></a>プロパティの設定  
 また、プロバイダーに、次のプロパティを追加する必要があります。 のみをサポートするインターフェイスに基づくプロパティを追加する必要があります。  
  
|プロパティ|サポートします。|  
|--------------|------------------------|  
|`DBPROP_IConnectionPointContainer`|Always|  
|`DBPROP_NOTIFICATIONGRANULARITY`|Always|  
|`DBPROP_NOTIFICATIONPHASES`|Always|  
|`DBPROP_NOTIFYCOLUMNSET`|`IRowsetChange`|  
|`DBPROP_NOTIFYROWDELETE`|`IRowsetChange`|  
|`DBPROP_NOTIFYROWINSERT`|`IRowsetChange`|  
|`DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE`|Always|  
|`DBPROP_NOTIFYROWFIRSTCHANGE`|`IRowsetUpdate`|  
|`DBPROP_NOTIFYROWSETRELEASE`|Always|  
|`DBPROP_NOTIFYROWUNDOCHANGE`|`IRowsetUpdate`|  
|`DBPROP_NOTIFYROWUNDODELETE`|`IRowsetUpdate`|  
|`DBPROP_NOTIFYROWUNDOINSERT`|`IRowsetUpdate`|  
|`DBPROP_NOTIFYROWUPDATE`|`IRowsetUpdate`|  
  
 OLE DB プロバイダー テンプレートでは、通知の実装のほとんどが埋め込まれています。 追加しない場合`IRowsetNotifyCP`継承チェーンをコンパイラはそのため、コードのサイズを小さくすること、コンパイルのストリームからのコードをすべてを削除します。  
  
## <a name="see-also"></a>関連項目  
 [高度なプロバイダー手法](../../data/oledb/advanced-provider-techniques.md)