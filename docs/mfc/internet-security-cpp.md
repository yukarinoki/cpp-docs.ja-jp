---
description: '詳細情報: インターネットセキュリティ (C++)'
title: インターネット セキュリティ (C++)
ms.date: 11/04/2016
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
ms.openlocfilehash: 870695abc89ba022a333829ec974d2f1e9147a53
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335848"
---
# <a name="internet-security-c"></a>インターネット セキュリティ (C++)

コードセーフは、開発者やインターネットアプリケーションのユーザーにとって大きな問題です。 リスクには、悪意のあるコード、改ざんされたコード、不明なサイトや作成者からのコードなどがあります。

インターネット用に開発する場合、セキュリティには2つの基本的な方法があります。 1つ目は "サンドボックス" と呼ばれます。 この方法では、アプリケーションは特定の Api セットに限定され、プログラムがユーザーのコンピューター上のデータを破壊する可能性のあるファイル i/o などの危険なものから除外されます。 2つ目は、デジタル署名を使用して実装されます。 この方法は、インターネットでは "shrinkwrap" と呼ばれています。 コードは、秘密キー/公開キーテクノロジを使用して検証および署名されます。 コードを実行する前に、そのデジタル署名を検証して、コードが既知の認証済みソースからのものであること、およびコードが署名されてから変更されていないことを確認します。

最初のケースでは、アプリケーションが害を及ぼすことはなく、アプリケーションの発行元を信頼することになります。 2つ目の方法では、デジタル署名を使用して信頼性を確認します。 デジタル署名は、コードの発行元に関する詳細を特定して提供するために使用される業界標準です。 このテクノロジは、RSA や x.509 などの標準に基づいています。 通常、ブラウザーでは、不明な配信元のコードをダウンロードして実行するかどうかをユーザーが選択できます。

## <a name="see-also"></a>関連項目

[MFC インターネットプログラミングタスク](mfc-internet-programming-tasks.md)<br/>
[MFC インターネットプログラミングの基礎](mfc-internet-programming-basics.md)
