---
title: 'Windows ソケット: データグラム ソケット |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sockets [MFC], datagram
- Windows Sockets [MFC], bi-directional data flow
- datagram sockets [MFC]
- Windows Sockets [MFC], datagram
- sockets [MFC], bi-directional data flow
ms.assetid: bec16a1c-74c0-4ff9-8c18-c2d87897d264
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 30ad7cab43301ae2cb7ebcb1fb4dfa850090955d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383943"
---
# <a name="windows-sockets-datagram-sockets"></a>Windows ソケット : データグラム ソケット
この記事では、データグラム ソケットでは、使用可能な 2 つの Windows ソケット型の 1 つについて説明します。 (他の型が、[ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md))。  
  
 データグラム ソケットでは、ことが保証されないシーケンス処理や重複する双方向データ フローをサポートします。 データグラムも保証がないため信頼性受信に失敗したことができます。 データグラム データが順不同と重複する可能性のある、くる可能性がありますが、レコードは、受信側のサイズが内部制限より小さい場合に限り、データのレコードの境界は保持されます。 シーケンス処理および信頼性の管理を担当しています。 (信頼性はローカル エリア ネットワーク (LAN) で正常である傾向がありますが小さいためにワイド エリア ネットワーク (WAN)、インターネットなど)。  
  
 データグラムは「コネクションレス」、つまり、明示的な接続は確立できません。指定したソケットにデータグラム メッセージを送信して、指定したソケットからメッセージを受信できます。  
  
 データグラム ソケットの例は、システム クロックの同期されているネットワークを保持するアプリケーションです。 これには、少なくとも一部の設定でデータグラム ソケットの追加的な機能を示しています。 大量のネットワーク アドレスにメッセージをブロードキャストします。  
  
 データグラム ソケットでは、データのレコード指向ストリーム ソケットよりも優れています。 データグラム ソケットの詳細については、Windows SDK で使用できる Windows ソケット仕様を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)   
 [Windows ソケット: 予備知識](../mfc/windows-sockets-background.md)

