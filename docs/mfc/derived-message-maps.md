---
title: メッセージ マップの派生
description: MFC メッセージの処理について説明します。
ms.date: 09/23/2020
helpviewer_keywords:
- message handling [MFC], derived message handlers
- messages, routing
- message maps [MFC], derived
- derived message maps
ms.assetid: 21829556-6e64-40c3-8279-fed85d99de77
ms.openlocfilehash: 44c2180e441c91d34350c65bc17a53d1b650607c
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414218"
---
# <a name="derived-message-maps"></a>メッセージ マップの派生

メッセージの処理中に、クラス独自のメッセージマップを確認することは、メッセージマップのストーリーの最後ではありません。 `CMyView`(から派生した) クラス `CView` がメッセージに一致するエントリを持っていない場合はどうなりますか。

`CView`の基本クラス `CMyView` はから派生することに注意してください `CWnd` 。 したがって、はであり、はです `CMyView` *is* `CView` *is* `CWnd` 。 これらの各クラスには、独自のメッセージマップがあります。 次の図は、クラスの階層関係を示していますが、 `CMyView` オブジェクトは、3つのクラスすべての特性を持つ単一のオブジェクトであることに注意してください。

![ビュー階層](../mfc/media/vc38621.gif "ビュー階層") <br/>
ビュー階層

メッセージがクラスのメッセージマップで一致しない場合 `CMyView` 、フレームワークはその直接の基底クラスのメッセージマップも検索します。 `BEGIN_MESSAGE_MAP`メッセージマップの先頭にあるマクロは、次の2つのクラス名を引数として指定します。

[!code-cpp[NVC_MFCMessageHandling#2](codesnippet/cpp/derived-message-maps_1.cpp)]

最初の引数は、メッセージマップが属するクラスの名前を指定します。 2番目の引数は、直接の基底クラスとの接続を提供します。この場合、 `CView` フレームワークはメッセージマップも検索できます。

そのため、基底クラスで提供されるメッセージハンドラーは、派生クラスによって継承されます。 これは、すべてのハンドラーメンバー関数を仮想にすることなく、通常の仮想メンバー関数によく似ています。

どの基本クラスのメッセージマップにもハンドラーが見つからない場合は、メッセージの既定の処理が実行されます。 メッセージがコマンドの場合、フレームワークはそれを次のコマンドターゲットにルーティングします。 標準の Windows メッセージの場合、メッセージは適切な既定のウィンドウプロシージャに渡されます。

メッセージマップの照合速度を向上させるために、フレームワークは、同じメッセージを再び受信する可能性について、最近の一致をキャッシュします。 このような結果の1つとして、フレームワークは未処理のメッセージを非常に効率的に処理します。 また、メッセージマップは、仮想関数を使用する実装よりも領域が効率的です。

## <a name="see-also"></a>関連項目

[フレームワークがメッセージマップを検索する方法](how-the-framework-searches-message-maps.md)
