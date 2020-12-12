---
description: '詳細情報: 通知のサポート'
title: 通知のサポート
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- events [C++], notifications in OLE DB
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB provider templates, notifications
- OLE DB providers, notifications
ms.assetid: 76e875fd-2bfd-4e4e-9f43-dbe5a3fa7382
ms.openlocfilehash: 3f03ded9b900a8691c256e6cde8eaf1a2f4fb5cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316675"
---
# <a name="supporting-notifications"></a>通知のサポート

## <a name="implementing-connection-point-interfaces-on-the-provider-and-consumer"></a>プロバイダーとコンシューマーでの接続ポイントインターフェイスの実装

通知を実装するには、プロバイダークラスが [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md) および [IConnectionPointContainer](../../atl/reference/iconnectionpointcontainerimpl-class.md)から継承する必要があります。

`IRowsetNotifyCP` 接続ポイントインターフェイス [IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85))のプロバイダーサイトを実装します。 `IRowsetNotifyCP` は、 `IID_IRowsetNotify` 行セットの内容に対する変更のコネクションポイントをリスナーに通知する broadcast 関数を実装します。

`IRowsetNotify`コンシューマーが通知を処理できるように、 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)を使用してコンシューマー (シンクとも呼ばれます) にも実装し、登録する必要があります。 コンシューマーに接続ポイントインターフェイスを実装する方法の詳細については、「 [通知の受信](../../data/oledb/receiving-notifications.md)」を参照してください。

また、次のように、クラスには接続ポイントのエントリを定義するマップが必要です。

```cpp
BEGIN_CONNECTION_POINT_MAP
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)
END_CONNECTION_POINT_MAP
```

## <a name="adding-irowsetnotify"></a>IRowsetNotify の追加

を追加するに `IRowsetNotify` は、 `IConnectionPointContainerImpl<rowset-name>` 継承チェーンにとを追加する必要があり `IRowsetNotifyCP<rowset-name>` ます。

たとえば、UpdatePV のの継承チェーンは次 `RUpdateRowset` の[](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)ようになります。

> [!NOTE]
> サンプル コードは、ここに記載されているものと異なる場合があります。サンプル コードの方を最新バージョンと見なしてください。

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

### <a name="setting-com-map-entries"></a>COM マップエントリの設定

また、行セットの COM マップに次のコードを追加する必要があります。

```cpp
COM_INTERFACE_ENTRY(IConnectionPointContainer)
COM_INTERFACE_ENTRY_IMPL(IConnectionPointContainer)
```

これらのマクロを使用 `QueryInterface` すると、接続ポイントコンテナー (の基礎) を呼び出すこと `IRowsetNotify` で、要求されたインターフェイスをプロバイダーで検索できます。 接続ポイントの使用方法の例については、「ATL POLYGON のサンプルとチュートリアル」を参照してください。

### <a name="setting-connection-point-map-entries"></a>接続ポイントマップエントリの設定

また、接続ポイントマップを追加する必要もあります。 次のようなものになります。

```cpp
BEGIN_CONNECTION_POINT_MAP(rowset-name)
     CONNECTION_POINT_ENTRY(_uuidof(IRowsetNotify))
END_CONNECTION_POINT_MAP()
```

この接続ポイントマップを使用すると、コンポーネントはインターフェイスを検索して `IRowsetNotify` プロバイダーで見つけることができます。

### <a name="setting-properties"></a>プロパティの設定

また、次のプロパティをプロバイダーに追加する必要があります。 必要なのは、サポートするインターフェイスに基づいてプロパティを追加することだけです。

|プロパティ|サポートする場合は追加|
|--------------|------------------------|
|DBPROP_IConnectionPointContainer|常時|
|DBPROP_NOTIFICATIONGRANULARITY|常時|
|DBPROP_NOTIFICATIONPHASES|常時|
|DBPROP_NOTIFYCOLUMNSET|`IRowsetChange`|
|DBPROP_NOTIFYROWDELETE|`IRowsetChange`|
|DBPROP_NOTIFYROWINSERT|`IRowsetChange`|
|DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE|常時|
|DBPROP_NOTIFYROWFIRSTCHANGE|`IRowsetUpdate`|
|DBPROP_NOTIFYROWSETRELEASE|常時|
|DBPROP_NOTIFYROWUNDOCHANGE|`IRowsetUpdate`|
|DBPROP_NOTIFYROWUNDODELETE|`IRowsetUpdate`|
|DBPROP_NOTIFYROWUNDOINSERT|`IRowsetUpdate`|
|DBPROP_NOTIFYROWUPDATE|`IRowsetUpdate`|

通知の実装の大部分は、既に OLE DB プロバイダーテンプレートに埋め込まれています。 継承チェーンに追加しない場合、 `IRowsetNotifyCP` コンパイラはコンパイルストリームからすべてのコードを削除します。これにより、コードサイズが小さくなります。

## <a name="see-also"></a>関連項目

[高度なプロバイダー手法](../../data/oledb/advanced-provider-techniques.md)
