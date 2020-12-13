---
description: '詳細については、「Windows ソケット: データグラムソケット」を参照してください。'
title: 'Windows ソケット : データグラム ソケット'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], datagram
- Windows Sockets [MFC], bi-directional data flow
- datagram sockets [MFC]
- Windows Sockets [MFC], datagram
- sockets [MFC], bi-directional data flow
ms.assetid: bec16a1c-74c0-4ff9-8c18-c2d87897d264
ms.openlocfilehash: 8de374d6e96348504d4b1fc126c1607c029cd6c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132978"
---
# <a name="windows-sockets-datagram-sockets"></a>Windows ソケット : データグラム ソケット

この記事では、使用可能な2つの Windows ソケットの種類のうちの1つであるデータグラムソケットについて説明します。 (もう1つの型は [ストリームソケット](../mfc/windows-sockets-stream-sockets.md)です)。

データグラムソケットは、シーケンス処理または重複が保証されていない双方向データフローをサポートします。 また、データグラムも確実に信頼できるとは限りません。失敗する可能性があります。 データグラムデータは、順番どおりに到着しない場合もありますが、レコードが受信側の内部サイズの制限よりも小さい限り、データ内のレコードの境界は保持されます。 ユーザーは、シーケンス処理と信頼性の管理を担当します。 (信頼性は、ローカルエリアネットワーク [LAN] には適していますが、インターネットなどのワイドエリアネットワーク [WAN] では有効ではありません)。

データグラムは "コネクションレス" で、明示的な接続は確立されません。指定したソケットにデータグラムメッセージを送信すると、指定したソケットからメッセージを受信できます。

データグラムソケットの例としては、ネットワーク上のシステムクロックが同期された状態を維持するアプリケーションがあります。 これは、少なくともいくつかの設定 (多数のネットワークアドレスへのメッセージのブロードキャスト) でのデータグラムソケットの追加機能を示しています。

データグラムソケットは、レコード指向データのストリームソケットよりも優れています。 データグラムソケットの詳細については、Windows SDK で使用可能な Windows ソケット仕様を参照してください。

## <a name="see-also"></a>関連項目

[MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)<br/>
[Windows ソケット:背景](../mfc/windows-sockets-background.md)
