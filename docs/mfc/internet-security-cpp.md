---
title: インターネット セキュリティ (C++) |Microsoft Docs
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
ms.openlocfilehash: 3b61df9a17903f50ea922edf9c29eee926063254
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055412"
---
# <a name="internet-security-c"></a>インターネット セキュリティ (C++)

コードの安全性は、開発者とユーザーがインターネット アプリケーションの主要な問題です。 上のリスクがある: 悪意のあるコードが改ざんされていないコードや不明なサイトまたは作成者からのコード。

インターネット向けの開発時のセキュリティに 2 つの基本的な方法は。 1 つ目は「サンド ボックス化します」と呼ばれる この方法でのアプリケーションの特定の Api のセットに制限し、プログラムがユーザーのコンピューター上のデータを破棄でしたファイル I/O などの危険性のあるものから除外します。 2 つ目は、デジタル署名を使用して実装されます。 このアプローチは、インターネット用に"shrinkwrap"と呼ばれます。 コードが検証され、プライベート キーと公開キー テクノロジを使用して署名します。 コードを実行すると、前に、そのデジタル署名を検証して、コードが既知の認証済みのソースからのものとが署名されているため、コードが変更されていないことを確認します。

最初のケースで、アプリケーションが起きなくを実行していないと、アプリケーションの配信元を信頼することを信頼します。 2 番目の場合は、デジタル署名が信頼性を確認に使用されます。 デジタル署名では業界標準を特定し、コードの発行元の詳細を提供するために使用します。 同社のテクノロジは、RSA など、X.509 標準に基づいています。 ブラウザーは、通常ユーザーが元が不明なコードをダウンロードして実行するかどうかに選択を許可します。

## <a name="see-also"></a>関連項目

[MFC インターネット プログラミングの作業](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)

