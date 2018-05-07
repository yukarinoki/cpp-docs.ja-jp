---
title: HTTP の基礎 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTTP [MFC], return codes
- return codes [MFC]
- HTTP requests [MFC], return codes
ms.assetid: 5b7421bf-42c8-4f3a-8566-8ff5957f58cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56a2692edd9d41f80023e44f4ca8172cba8f9d00
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="http-basics"></a>HTTP の基礎
インターネット アプリケーションを作成するときに多くの場合を確認して HTTP ヘッダーの情報を追加します。 リターン コードは、要求されたイベントの成否を示します。 いくつかの一般的なリターン コードは、次の表に一覧表示されます。  
  
|リターン コード|説明|  
|-----------------|-------------|  
|200|ある URL、伝送に従います。|  
|400|解釈できない要求|  
|404|要求された URL が見つかりません。|  
|405|サーバーが要求されたメソッドをサポートしていません|  
|500|不明なサーバー エラー|  
|503|サービス利用不可|  
  
 HTTP 応答は、次の表に示すようにグループ化されます。  
  
|グループ化|説明|  
|-----------|-------------|  
|200-299|成功|  
|300-399|情報|  
|400-499|要求エラー|  
|500-599|サーバー エラー|  
  
 ハイパー テキスト転送プロトコル (HTTP) は、hypermedia 情報システムのアプリケーション レベル プロトコルです。 HTTP、および Web ブラウザーとサーバーの通信方法の詳細については、ハイパー テキスト転送プロトコル (HTTP) の仕様を参照してください。  
  
 [http://www.w3.org/pub/WWW/Protocols/](http://www.w3.org/pub/www/protocols/)  
  
## <a name="see-also"></a>関連項目  
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)

