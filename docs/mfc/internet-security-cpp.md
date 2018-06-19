---
title: インターネット セキュリティ (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- code signing [MFC], Internet security
- sandboxing [MFC]
- digital signatures [MFC], Internet security
- code signing [MFC]
- Web application security [MFC]
- code access security [MFC], Internet security considerations
- security [MFC]
- security [MFC], Internet
- Internet applications [MFC], security
- Web application security [MFC], Internet security approaches
ms.assetid: bf0da697-81bc-41f0-83fa-d7f82ed83df8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4454eceae2cc5f2e6b46510fe95889c664a568a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348852"
---
# <a name="internet-security-c"></a>インターネット セキュリティ (C++)
コードの安全性は、開発者とユーザーからインターネット アプリケーションの主要な問題です。 上のリスクが: 悪意のあるコードが改ざんされて、コード、不明なサイトまたは作成者からコード。  
  
 インターネット向けの開発時のセキュリティに 2 つの基本的な方法は。 1 つ目は「サンド ボックス化されます」と呼ばれる この方法では、アプリケーションが特定の Api のセットに制限し、プログラムがユーザーのコンピューター上のデータを破棄でしたファイル I/O などの危険性のあるものから除外します。 2 つ目は、デジタル署名を使用して実装されます。 このアプローチは、インターネットでの「開封」と呼びます。 コードでは、検証し、プライベート キーと公開キー テクノロジを使用して署名します。 コードの実行前に、コードが、不明な認証ソースからであると、署名されているため、コードが変更されていないことを確認するデジタル署名が確認されます。  
  
 最初のケースでは、アプリケーションには、コマンドに影響はしないし、アプリケーションの発行元を信頼することを信頼します。 2 番目の信頼性を検証するデジタル署名を使用します。 デジタル署名では、業界標準を識別し、コードのパブリッシャーに関する情報を提供するために使用します。 そのテクノロジは、RSA など、X.509 標準に基づいています。 ブラウザーでは、ユーザーが選択元が不明なコードをダウンロードして実行するかどうかは通常許可します。  
  
  
## <a name="see-also"></a>関連項目  
 [MFC インターネット プログラミングの作業](../mfc/mfc-internet-programming-tasks.md)   
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)

