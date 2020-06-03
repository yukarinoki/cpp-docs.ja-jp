---
title: OLE DB リソース プールとサービス
ms.date: 10/29/2018
helpviewer_keywords:
- resource pooling [OLE DB], provider requirements
- OLE DB, resource pooling
- service providers [OLE DB]
- OLE DB services [OLE DB], provider requirements
- OLE DB services [OLE DB]
- OLE DB providers, resource pooling
ms.assetid: 360c36e2-25ae-4caf-8ee7-d4a6b6898f68
ms.openlocfilehash: 67eeffff2bf165a5ccbdbaa546ad5b9ca9a57914
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210029"
---
# <a name="ole-db-resource-pooling-and-services"></a>OLE DB リソース プールとサービス

OLE DB プーリング、または任意の OLE DB サービスで適切に機能するには、プロバイダーがすべてのオブジェクトの集計をサポートしている必要があります。 これは、OLE DB 1.5 以降のプロバイダーの要件です。 サービスを活用することが重要です。 集計をサポートしていないプロバイダーはプールできないため、追加のサービスは提供されません。

プールされるには、プロバイダーがフリースレッドモデルをサポートする必要があります。 リソースプールは、DBPROP_THREADMODEL プロパティに従って、プロバイダーのスレッドモデルを決定します。

データソースが初期化済みの状態である間に変更される可能性のあるグローバルな接続状態がプロバイダーにある場合は、新しい DBPROP_RESETDATASOURCE プロパティをサポートする必要があります。 このプロパティは、接続が再利用される前に呼び出され、次に使用する前に状態をクリーンアップする機会をプロバイダーに与えます。 プロバイダーが接続に関連付けられている状態をクリーンアップできない場合は、プロパティの DBPROPSTATUS_NOTSETTABLE を返すことができ、接続は再利用されません。

リモートデータベースに接続し、その接続が失われる可能性があるかどうかを検出できるプロバイダーは、DBPROP_CONNECTIONSTATUS プロパティをサポートする必要があります。 このプロパティを使用すると、OLE DB サービスは、接続されていない接続を検出し、プールに返されないようにすることができます。

最後に、自動トランザクション参加は、プールが発生するのと同じレベルで実装されていない限り、通常は動作しません。 自動トランザクション登録をサポートするプロバイダーは、DBPROP_INIT_OLEDBSERVICES プロパティを公開し、DBPROPVAL_OS_TXNENLISTMENT が選択解除されている場合に参加を無効にすることで、この参加リストの無効化をサポートする必要があります。

## <a name="see-also"></a>参照

[高度なプロバイダー手法](../../data/oledb/advanced-provider-techniques.md)
