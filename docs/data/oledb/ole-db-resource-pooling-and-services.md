---
title: OLE DB リソース プールとサービス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- resource pooling [OLE DB], provider requirements
- OLE DB, resource pooling
- service providers [OLE DB]
- OLE DB services [OLE DB], provider requirements
- OLE DB services [OLE DB]
- OLE DB providers, resource pooling
ms.assetid: 360c36e2-25ae-4caf-8ee7-d4a6b6898f68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ab8c5e5a3e219da7204ef1a1b4942dc70b2f2ad2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ole-db-resource-pooling-and-services"></a>OLE DB リソース プールとサービス
OLE DB のプール、密接に連携または任意の OLE DB サービスを使用するには、プロバイダーは、すべてのオブジェクトの集計をサポートする必要があります。 これは、任意の OLE DB 1.5 またはそれ以降のプロバイダーの要件です。 サービスを利用するために重要です。 集約をサポートしないプロバイダーをプールできないため、追加のサービスが指定されていません。  
  
 プールに追加するには、プロバイダーは、フリー スレッド モデルをサポートする必要があります。 リソース プールによると、プロバイダーのスレッド モデルの決定、 **DBPROP_THREADMODEL**プロパティです。  
  
 プロバイダーにデータ ソースが初期化済みの状態の間に変わる可能性があるグローバル接続の状態がある場合は、サポートすることが、新しい**DBPROP_RESETDATASOURCE**プロパティです。 このプロパティは、接続が再利用され、プロバイダーに、次に使用する前に状態をクリーンアップする機会を与える前に呼び出されます。 返せる場合は、プロバイダーは、接続に関連付けられているいくつかの状態をクリーンアップできません、 **DBPROPSTATUS_NOTSETTABLE**のプロパティと、接続が再利用できません。  
  
 プロバイダー、リモート データベースに接続し、接続が失われる可能性がありますをサポートする必要があるかどうかを検出できますが、 **DBPROP_CONNECTIONSTATUS**プロパティです。 このプロパティは、OLE DB サービス配信不能の接続を検出し、プールに返されませんかどうかを確認する機能を使用します。  
  
 最後に、自動トランザクション参加一般的には機能しませんプールが発生したものと同じレベルで実装されていない限り。 自体自動トランザクション参加をサポートするプロバイダーをサポートして公開することで、この参加リストを無効にする必要があります、 **DBPROP_INIT_OLEDBSERVICES**プロパティと参加を無効にする場合、 **DBPROPVAL_OS_TXNENLISTMENT**選択が解除されます。  
  
## <a name="see-also"></a>関連項目  
 [高度なプロバイダー手法](../../data/oledb/advanced-provider-techniques.md)