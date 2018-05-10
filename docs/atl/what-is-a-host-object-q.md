---
title: ホスト オブジェクトとは何ですか。 (ATL) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- host objects
ms.assetid: 4f8da992-b27e-45e8-b5e0-c8b1dcae4fac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d197f02949f6eaaeee50b428338684135d1db27
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="what-is-a-host-object"></a>ホスト オブジェクトとは何ですか。
ホスト オブジェクトは、ATL で特定のウィンドウに指定された ActiveX コントロール コンテナーを表す COM オブジェクトです。 ホスト オブジェクトはサブクラス コンテナー ウィンドウ コントロールにメッセージを反映したものをようにコントロールで使用するために必要なコンテナー インターフェイスを提供し、公開、 [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md)と[IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md)コントロールの環境を構成できるようにするインターフェイスです。  
  
 ホスト オブジェクトを使用して、コンテナーのアンビエント プロパティを設定することができます。  
  
## <a name="see-also"></a>関連項目  
 [コントロール コンテインメントよく寄せられる質問](../atl/atl-control-containment-faq.md)

