---
title: 通知のサポート |Microsoft ドキュメント
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
ms.openlocfilehash: f750346b0fdd8821800b012b3cdff7acc12f7897
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="supporting-notifications"></a>通知のサポート
## <a name="implementing-connection-point-interfaces-on-the-provider-and-consumer"></a>プロバイダーおよびコンシューマー接続ポイントのインターフェイスを実装します。  
 通知を実装するプロバイダー クラスを継承する必要があります[IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)と[IConnectionPointContainer](../../atl/reference/iconnectionpointcontainerimpl-class.md)です。  
  
 `IRowsetNotifyCP` プロバイダー サイト ポイントの接続インターフェイスを実装する[IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx)です。 `IRowsetNotifyCP` 実装は、接続ポイントに対するリスナーに通知する関数をブロードキャスト**IID_IRowsetNotify**行セットの内容を変更します。  
  
 実装し、登録する必要がありますもなお`IRowsetNotify`(シンクとも呼ばれます) を使用して、コンシューマーで[IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)コンシューマーが通知を処理できるようにします。 コンシューマーのコネクション ポイントのインターフェイスを実装する方法の詳細については、次を参照してください。[通知の受信](../../data/oledb/receiving-notifications.md)です。  
  
 さらに、クラスには、次のように、接続ポイントのエントリを定義するマップする必要がありますも含まれます。  
  
```  
BEGIN_CONNECTION_POINT_MAP  
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)  
END_CONNECTION_POINT_MAP  
```  
  
## <a name="adding-irowsetnotify"></a>IRowsetNotify を追加します。  
 追加する`IRowsetNotify`、追加する必要があります`IConnectionPointContainerImpl<rowset-name>`と`IRowsetNotifyCP<rowset-name>`継承チェーンをします。  
  
 たとえばの継承チェーンをここでは`RUpdateRowset`で[UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f):  
  
> [!NOTE]
>  サンプル コードがここでは記載されている内容と異なる場合があります。サンプル コードは、最新のバージョンと見なす必要があります。  
  
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
  
### <a name="setting-com-map-entries"></a>COM マップ エントリを設定  
 次のエントリを行セットの COM マップに追加する必要があります。  
  
```  
COM_INTERFACE_ENTRY(IConnectionPointContainer)  
COM_INTERFACE_ENTRY_IMPL(IConnectionPointContainer)  
```  
  
 これらのマクロを使用して、呼び出すように`QueryInterface`接続ポイント コンテナーの (の基礎`IRowsetNotify`) プロバイダーに要求されたインターフェイスが見つかりません。 接続ポイントを使用する方法の例は、ATL の多角形のサンプルとチュートリアルを参照してください。  
  
### <a name="setting-connection-point-map-entries"></a>コネクション ポイントのマップのエントリを設定  
 また、接続ポイントのマップを追加する必要があります。 ように表示する必要があります。  
  
```  
BEGIN_CONNECTION_POINT_MAP(rowset-name)  
     CONNECTION_POINT_ENTRY(_uuidof(IRowsetNotify))  
END_CONNECTION_POINT_MAP()  
```  
  
 この接続ポイントのマップにより、コンポーネントを探して、`IRowsetNotify`プロバイダーで検索するインターフェイスです。  
  
### <a name="setting-properties"></a>プロパティの設定  
 また、プロバイダーに、次のプロパティを追加する必要があります。 のみをサポートするインターフェイスに基づくプロパティを追加する必要があります。  
  
|プロパティ|サポートします。|  
|--------------|------------------------|  
|**DBPROP_IConnectionPointContainer**|Always|  
|**DBPROP_NOTIFICATIONGRANULARITY**|Always|  
|**DBPROP_NOTIFICATIONPHASES**|Always|  
|**DBPROP_NOTIFYCOLUMNSET**|`IRowsetChange`|  
|**DBPROP_NOTIFYROWDELETE**|`IRowsetChange`|  
|**DBPROP_NOTIFYROWINSERT**|`IRowsetChange`|  
|**DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE**|Always|  
|**DBPROP_NOTIFYROWFIRSTCHANGE**|`IRowsetUpdate`|  
|**DBPROP_NOTIFYROWSETRELEASE**|Always|  
|**DBPROP_NOTIFYROWUNDOCHANGE**|`IRowsetUpdate`|  
|**DBPROP_NOTIFYROWUNDODELETE**|`IRowsetUpdate`|  
|**DBPROP_NOTIFYROWUNDOINSERT**|`IRowsetUpdate`|  
|**DBPROP_NOTIFYROWUPDATE**|`IRowsetUpdate`|  
  
 通知の実装の大部分は、OLE DB プロバイダー テンプレートに既に埋め込まれます。 追加しない場合`IRowsetNotifyCP`継承チェーンをコンパイラがそのため、コード サイズを小さくすることをコンパイル ストリームからのコードをすべてを削除します。  
  
## <a name="see-also"></a>関連項目  
 [高度なプロバイダー手法](../../data/oledb/advanced-provider-techniques.md)