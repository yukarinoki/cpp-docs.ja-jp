---
title: 1 つのウィンドウで 1 つ以上のコントロールをホストすることができますか。 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [ATL], hosting multiple
- windows [C++], hosting multiple controls
ms.assetid: 3a967a1a-7e7e-42e3-8eed-f7bde912363f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ceb9444b6371e261115bbf52ef5a249100772d1f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356425"
---
# <a name="can-i-host-more-than-one-control-in-a-single-window"></a>1 つのウィンドウで 1 つ以上のコントロールをホストすることができますか。
単一の ATL ホスト ウィンドウに 2 つ以上のコントロールをホストすることはできません。 各ホスト ウィンドウは、(これにより、メッセージのリフレクションとコントロールごとのアンビエント プロパティを処理するための簡単なメカニズム) 時に正確に 1 つのコントロールを保持するために設計されています。 ただし、1 つのウィンドウで複数のコントロールを表示するユーザーに、必要な場合は、そのウィンドウの子として複数のホスト ウィンドウを作成するだけの簡単なです。  
  
## <a name="see-also"></a>関連項目  
 [コントロール コンテインメントよく寄せられる質問](../atl/atl-control-containment-faq.md)

