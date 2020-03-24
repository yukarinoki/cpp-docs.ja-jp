---
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
ms.openlocfilehash: d29f84a0a5b33d55c0a04a4c758050cf9746f72a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209553"
---
# <a name="supporting-notifications"></a>通知のサポート

## <a name="implementing-connection-point-interfaces-on-the-provider-and-consumer"></a>プロバイダーとコンシューマーでの接続ポイントインターフェイスの実装

通知を実装するには、プロバイダークラスが[IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)および[IConnectionPointContainer](../../atl/reference/iconnectionpointcontainerimpl-class.md)から継承する必要があります。

`IRowsetNotifyCP` は、接続ポイントインターフェイス[IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85))のプロバイダーサイトを実装します。 `IRowsetNotifyCP` は、行セットの内容に対する変更 `IID_IRowsetNotify` 接続ポイントでリスナーをアドバイズするように、ブロードキャスト関数を実装します。

また、 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)を使用してコンシューマー (シンクとも呼ばれます) に `IRowsetNotify` を実装して登録し、コンシューマーが通知を処理できるようにする必要があります。 コンシューマーに接続ポイントインターフェイスを実装する方法の詳細については、「[通知の受信](../../data/oledb/receiving-notifications.md)」を参照してください。

また、次のように、クラスには接続ポイントのエントリを定義するマップが必要です。

```cpp
BEGIN_CONNECTION_POINT_MAP
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)
END_CONNECTION_POINT_MAP
```

## <a name="adding-irowsetnotify"></a>IRowsetNotify の追加

`IRowsetNotify`を追加するには、継承チェーンに `IConnectionPointContainerImpl<rowset-name>` と `IRowsetNotifyCP<rowset-name>` を追加する必要があります。

たとえば、 [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)の `RUpdateRowset` の継承チェーンは次のようになります。

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

これらのマクロを使用すると、接続ポイントコンテナー (`IRowsetNotify`の基礎) に対して `QueryInterface` を呼び出すと、要求されたインターフェイスをプロバイダーで見つけることができます。 接続ポイントの使用方法の例については、「ATL POLYGON のサンプルとチュートリアル」を参照してください。

### <a name="setting-connection-point-map-entries"></a>接続ポイントマップエントリの設定

また、接続ポイントマップを追加する必要もあります。 次のようになります。

```cpp
BEGIN_CONNECTION_POINT_MAP(rowset-name)
     CONNECTION_POINT_ENTRY(_uuidof(IRowsetNotify))
END_CONNECTION_POINT_MAP()
```

この接続ポイントマップを使用すると、コンポーネントが `IRowsetNotify` インターフェイスを探してプロバイダーで検索できるようになります。

### <a name="setting-properties"></a>プロパティの設定

また、次のプロパティをプロバイダーに追加する必要があります。 必要なのは、サポートするインターフェイスに基づいてプロパティを追加することだけです。

|プロパティ|サポートする場合は追加|
|--------------|------------------------|
|DBPROP_IConnectionPointContainer|Always (常に)|
|DBPROP_NOTIFICATIONGRANULARITY|Always (常に)|
|DBPROP_NOTIFICATIONPHASES|Always (常に)|
|DBPROP_NOTIFYCOLUMNSET|`IRowsetChange`|
|DBPROP_NOTIFYROWDELETE|`IRowsetChange`|
|DBPROP_NOTIFYROWINSERT|`IRowsetChange`|
|DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE|Always (常に)|
|DBPROP_NOTIFYROWFIRSTCHANGE|`IRowsetUpdate`|
|DBPROP_NOTIFYROWSETRELEASE|Always (常に)|
|DBPROP_NOTIFYROWUNDOCHANGE|`IRowsetUpdate`|
|DBPROP_NOTIFYROWUNDODELETE|`IRowsetUpdate`|
|DBPROP_NOTIFYROWUNDOINSERT|`IRowsetUpdate`|
|DBPROP_NOTIFYROWUPDATE|`IRowsetUpdate`|

通知の実装の大部分は、既に OLE DB プロバイダーテンプレートに埋め込まれています。 継承チェーンに `IRowsetNotifyCP` を追加しない場合、コンパイラはコンパイルストリームからすべてのコードを削除するため、コードサイズが小さくなります。

## <a name="see-also"></a>参照

[高度なプロバイダー手法](../../data/oledb/advanced-provider-techniques.md)
