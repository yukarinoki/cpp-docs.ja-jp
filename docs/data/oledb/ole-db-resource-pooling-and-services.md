---
title: OLE DB リソース プールとサービス
ms.date: 11/04/2016
helpviewer_keywords:
- resource pooling [OLE DB], provider requirements
- OLE DB, resource pooling
- service providers [OLE DB]
- OLE DB services [OLE DB], provider requirements
- OLE DB services [OLE DB]
- OLE DB providers, resource pooling
ms.assetid: 360c36e2-25ae-4caf-8ee7-d4a6b6898f68
ms.openlocfilehash: 7c57376404b37de95e01be6459b3d57ddcc53fe3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448101"
---
# <a name="ole-db-resource-pooling-and-services"></a>OLE DB リソース プールとサービス

OLE DB のプール、または任意の OLE DB サービスでの作業、プロバイダーは、すべてのオブジェクトの集計をサポートする必要があります。 これは、任意の OLE DB 1.5 または以降のプロバイダーの要件です。 サービスを利用するために重要です。 集約をサポートしないプロバイダーをプールすることはできませんし、その他のサービスは提供されません。

プール、プロバイダーは、フリー スレッド モデルをサポートする必要があります。 リソース プールの決定に従って、プロバイダーのスレッド モデル、`DBPROP_THREADMODEL`プロパティ。

プロバイダーにデータ ソースは、初期化された状態が変わる可能性があるグローバル接続状態がある場合は、サポートすることが、新しい`DBPROP_RESETDATASOURCE`プロパティ。 このプロパティは、接続が再利用され、プロバイダーに、次に使用する前に状態をクリーンアップする機会を与える前に呼び出されます。 返せる場合は、プロバイダー接続に関連付けられているいくつかの状態をクリーンアップできない、`DBPROPSTATUS_NOTSETTABLE`のプロパティと、接続が再利用できません。

プロバイダーをリモート データベースに接続し、接続が失われる可能性がありますをサポートする必要があるかどうかを検出できる、`DBPROP_CONNECTIONSTATUS`プロパティ。 このプロパティは、OLE DB サービスの配信不能の接続を検出し、プールに返されませんかどうかを確認する機能を示します。

最後に、自動トランザクション参加一般的には機能しませんプールが発生したものと同じレベルで実装されていない場合。 この参加リストを公開することで無効にする自体自動トランザクション参加をサポートするプロバイダーがサポートする必要があります、`DBPROP_INIT_OLEDBSERVICES`プロパティと場合、参加を無効にする、`DBPROPVAL_OS_TXNENLISTMENT`の選択を解除します。

## <a name="see-also"></a>関連項目

[高度なプロバイダー手法](../../data/oledb/advanced-provider-techniques.md)