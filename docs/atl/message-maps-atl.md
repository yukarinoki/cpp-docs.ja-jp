---
title: メッセージ マップ (ATL) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- message maps, ATL
- ATL, message handlers
ms.assetid: 9e100400-65c7-4a85-8857-4e6cb6dd7340
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eaef52363ebdd79a1efb1e2e26bce016500cb722
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357259"
---
# <a name="message-maps-atl"></a>メッセージ マップ (ATL)
メッセージ マップは、特定のメッセージ、コマンド、または通知ハンドラー関数を関連付けます。 ATL を使用して、[メッセージ マップ マクロ](../atl/reference/message-map-macros-atl.md)ウィンドウのメッセージ マップを指定することができます。 ウィンドウの手順で`CWindowImpl`、 `CDialogImpl`、および`CContainedWindowT`ウィンドウのメッセージのメッセージ マップにリダイレクトされます。  
  
 [メッセージ ハンドラー関数](../atl/message-handler-functions.md)型の追加の引数を受け入れる`BOOL&`です。 この引数は、メッセージの処理が完了しに設定されているかどうかを示します`TRUE`既定です。 ハンドラー関数引数を設定できる`FALSE`メッセージが処理がないことを表します。 この例では、ATL は引き続きメッセージ マップにハンドラー関数をさらに検索します。 この引数を設定して`FALSE`メッセージに応答してアクションを実行し、既定の処理または別のハンドラー関数がメッセージの処理を終了するようにすることができます。  
  
## <a name="chained-message-maps"></a>チェーンのメッセージ マップ  
 ATL こともできます、チェーン メッセージ マップにメッセージを別のクラスで定義されているメッセージ マップを処理するように指示します。 たとえば、そのクラスにチェーンのすべてのウィンドウの一貫した動作を提供する共通のメッセージを別のクラス処理を実装することができます。 基底クラスまたはクラスのデータ メンバーを連結することができます。  
  
 ATL もサポート動的チェーンできる別のオブジェクトのメッセージ マップにチェーンする実行時にします。 動的な組み合わせを実装する必要がありますの派生クラスから[CDynamicChain](../atl/reference/cdynamicchain-class.md)です。 宣言し、[場合](reference/message-map-macros-atl.md#chain_msg_map_dynamic)メッセージ マップ マクロです。 `CHAIN_MSG_MAP_DYNAMIC` オブジェクトおよび連鎖しているメッセージ マップを識別する一意の番号が必要です。 呼び出すことによってこの一意の値を定義する必要があります`CDynamicChain::SetChainEntry`です。  
  
 クラスの派生元提供メッセージ マップを宣言するクラスをチェーンする[CMessageMap](../atl/reference/cmessagemap-class.md)です。 `CMessageMap` 他のオブジェクトへのメッセージ マップを公開するオブジェクトを許可します。 なお`CWindowImpl`から既に派生`CMessageMap`です。  
  
## <a name="alternate-message-maps"></a>代替のメッセージ マップ  
 最後に、ATL はで宣言された、代替のメッセージ マップをサポートしている、 [ALT_MSG_MAP](reference/message-map-macros-atl.md#alt_msg_map)マクロです。 各代替のメッセージ マップに渡す一意の番号によって識別される`ALT_MSG_MAP`です。 代替のメッセージを使用してマップは、1 つのマップ内の複数のウィンドウのメッセージを処理することができます。 既定では、なお`CWindowImpl`代替メッセージ マップを使用しません。 このサポートを追加するには、上書き、`WindowProc`メソッドで、 `CWindowImpl`-派生クラスと呼び出し`ProcessWindowMessage`メッセージ マップの識別子を使用します。  
  
## <a name="see-also"></a>関連項目  
 [ウィンドウの実装](../atl/implementing-a-window.md)

