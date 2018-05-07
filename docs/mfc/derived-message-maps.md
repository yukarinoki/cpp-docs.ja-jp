---
title: メッセージ マップの派生 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handling [MFC], derived message handlers
- messages, routing
- message maps [MFC], derived
- derived message maps
ms.assetid: 21829556-6e64-40c3-8279-fed85d99de77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e780d411e62d1347d8286f86b45df864b0fcdb3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="derived-message-maps"></a>メッセージ マップの派生
メッセージの処理、クラスのメッセージを確認中には、マップと、メッセージ マップのストーリーの終わりではありません。 場合の対処クラス`CMyView`(から派生した`CView`) メッセージに対応するエントリがありません  
  
 注意してください`CView`の基本クラス`CMyView`からさらに派生した`CWnd`です。 したがって`CMyView`*は*、`CView`と*は*、`CWnd`です。 これらの各クラスが、独自のメッセージ マップです。 「A 階層の表示」以下では、クラスの階層関係を示しています。 図に留意する、`CMyView`オブジェクトが 3 つすべてのクラスの特性を持つ 1 つのオブジェクト。  
  
 ![ビュー階層](../mfc/media/vc38621.gif "vc38621")  
階層の表示  
  
 クラスのメッセージを照合できない場合は`CMyView`のフレームワークのメッセージ マップも、直接基底クラスのメッセージ マップを検索します。 `BEGIN_MESSAGE_MAP`メッセージ マップの開始時にマクロがその引数として 2 つのクラス名を指定します。  
  
 [!code-cpp[NVC_MFCMessageHandling#2](../mfc/codesnippet/cpp/derived-message-maps_1.cpp)]  
  
 最初の引数は、メッセージ マップが所属するクラスを名前します。 2 番目の引数は、直接の基本クラスとの接続を提供 —`CView`ここで、フレームワークでは、メッセージ マップをすぎる検索できるようにします。  
  
 派生クラスによって継承基底クラスで提供されるメッセージ ハンドラー。 これは、仮想ハンドラーのすべてのメンバー関数を作成することがなく通常の仮想メンバー関数とよく似ています。  
  
 基底クラスのメッセージ マップのいずれかでハンドラーが見つからない場合は、メッセージの既定の処理が実行されます。 メッセージがコマンドの場合は、次のコマンド ターゲットにルーティング フレームワークです。 標準 Windows メッセージである場合は、メッセージが適切な既定のウィンドウ プロシージャに渡されます。  
  
 メッセージ マップに一致する高速化するには、フレームワークは、同じメッセージをもう一度受信はこと、その確率で最近使用した一致をキャッシュします。 この結果は、未処理メッセージを効率よく framework プロセスです。 メッセージ マップは、また領域 - より効率的仮想関数を使用する実装です。  
  
## <a name="see-also"></a>関連項目  
 [フレームワークのメッセージ マップ検索方法](../mfc/how-the-framework-searches-message-maps.md)

