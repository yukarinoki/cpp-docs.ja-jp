---
title: 同時実行ランタイムのチュートリアル |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- walkthroughs [Concurrency Runtime]
- Concurrency Runtime, walkthroughs
ms.assetid: 7374c5e9-54eb-44bf-9ed9-5e190cfd290b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 143e9a0bba5aacfd3004bd7b90615692a1cb66bd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433199"
---
# <a name="concurrency-runtime-walkthroughs"></a>同時実行ランタイムのチュートリアル

このセクションでは、シナリオ ベースのトピックでは、多くの同時実行ランタイムの機能を使用する方法を示します。

## <a name="in-this-section"></a>このセクションの内容

[チュートリアル: タスクおよび XML HTTP 要求を使用した接続](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)<br/>
使用する方法を示しています、 [IXMLHTTPRequest2](/previous-versions/windows/desktop/api/msxml6/nn-msxml6-ixmlhttprequest2)と[IXMLHTTPRequest2Callback](/previous-versions/windows/desktop/api/msxml6/nn-msxml6-ixmlhttprequest2callback)ユニバーサル Windows プラットフォーム (UWP) アプリで web サービスに HTTP GET および POST 要求を送信するタスクとのインターフェイス。

[チュートリアル: エージェント ベースのアプリケーションの作成](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)<br/>
基本的なエージェント ベースのアプリケーションを作成する方法について説明します。

[チュートリアル: データフロー エージェントの作成](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)<br/>
制御フローの代わりに、データ フローに基づくエージェント ベースのアプリケーションを作成する方法を示します。

[チュートリアル: イメージ処理ネットワークの作成](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)<br/>
イメージ処理を実行する非同期メッセージ ブロックのネットワークを作成する方法を示します。

[チュートリアル: フューチャの実装](../../parallel/concrt/walkthrough-implementing-futures.md)<br/>
後で使用できる値を非同期的に計算する方法を示します。

[チュートリアル: join を使用したデッドロックの防止](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)<br/>
使用する方法を説明するために食事する哲学者の問題を使用して、 [concurrency::join](../../parallel/concrt/reference/join-class.md)アプリケーションでデッドロックを防止するクラス。

[チュートリアル: ユーザー インターフェイス スレッドからの処理の除去](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)<br/>
マンデルブロ フラクタルを描画する MFC アプリケーションのパフォーマンスを向上させる方法を示します。

[チュートリアル: COM 対応アプリケーションでのコンカレンシー ランタイムの使用](../../parallel/concrt/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application.md)<br/>
コンポーネント オブジェクト モデル (COM) を使用するアプリケーションで同時実行ランタイムを使用する方法を示します。

[チュートリアル: 既存のコードを改変して軽量タスクを使用する](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)<br/>
軽量タスクを使用するスレッドの実行を作成し、Windows API を使用する既存のコードを改変する方法を示します。

[チュートリアル: カスタム メッセージ ブロックの作成](../../parallel/concrt/walkthrough-creating-a-custom-message-block.md)<br/>
優先順位によって受信メッセージを並べるカスタム メッセージ ブロックの型を作成する方法について説明します。

## <a name="related-sections"></a>関連項目

[コンカレンシー ランタイム](../../parallel/concrt/concurrency-runtime.md)<br/>
Visual C の同時実行のプログラミング フレームワークが導入されています。

