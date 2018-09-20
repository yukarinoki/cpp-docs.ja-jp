---
title: MFC の OLE |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, OLE and
- OLE items
- OLE applications [MFC], about OLE
- OLE [MFC]
- OLE containers [MFC], about OLE
- applications [OLE], about OLE
- OLE component object model (COM)
ms.assetid: 5193479d-1239-4697-aea4-e82f92c707ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e43484e5f30191c604f43a2280a8deab6eddd93c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434948"
---
# <a name="ole-in-mfc"></a>MFC の OLE

これらの記事では、MFC を使用して OLE プログラミングの基礎について説明します。 MFC には、OLE を使用するプログラムを作成する最も簡単な方法が用意されています。

- OLE ビジュアル編集 (インプレース アクティブ化) を使用します。

- OLE コンテナーまたはサーバーで作業します。

- ドラッグ アンド ドロップ機能を実装します。

- 日付と時刻のデータを使用します。

- MFC の状態データを管理するには、DLL 関数のエントリ ポイント、OLE と COM インターフェイス エントリ ポイント、およびウィンドウ プロシージャ エントリ ポイントを含むモジュールがエクスポートされます。

使用することも[Automation](../mfc/automation.md)します。

> [!NOTE]
>  用語を OLE 表します、リンクと埋め込みに関連付けられているなどテクノロジ OLE コンテナー、OLE サーバー、OLE アイテム、インプレース アクティブ化 (ビジュアル編集)、トラッカー、ドラッグ アンド ドロップ、およびメニューのマージします。 用語など、ActiveX コントロール、コンポーネント オブジェクト モデル (COM) と COM ベースのオブジェクトをアクティブが適用されます。 OLE オートメーションは、Automation と呼ばれるようになりました。

## <a name="in-this-section"></a>このセクションの内容

[OLE の背景知識](../mfc/ole-background.md)<br/>
OLE について説明し、そのしくみについて説明します。

[アクティベーション](../mfc/activation-cpp.md)<br/>
OLE 項目の編集におけるライセンス認証の役割について説明します。

[コンテナー](../mfc/containers.md)<br/>
OLE のコンテナーの使用へのリンクを提供します。

[データ オブジェクトとデータ ソース](../mfc/data-objects-and-data-sources-ole.md)<br/>
使用方法に関するトピックへのリンク、`COleDataObject`と`COleDataSource`クラス。

[ドラッグ アンド ドロップ](../mfc/drag-and-drop-ole.md)<br/>
コピーと貼り付け ole の使用について説明します。

[OLE のメニューとリソース](../mfc/menus-and-resources-ole.md)<br/>
MFC OLE ドキュメント アプリケーションでメニューとリソースの使用について説明します。

[登録](../mfc/registration.md)<br/>
サーバーのインストールと初期化について説明します。

[サーバー](../mfc/servers.md)<br/>
コンテナー アプリケーションで使用するため、OLE 項目 (またはコンポーネント) を作成する方法について説明します。

[トラッカー](../mfc/trackers.md)<br/>
に関する情報を提供、 `CRectTracker` OLE クライアント アイテムと対話するユーザーを有効にするためのグラフィカル インターフェイスを提供するクラス。

## <a name="related-sections"></a>関連項目

[接続ポイント](../mfc/connection-points.md)<br/>
(以前は OLE コネクション ポイントと呼ばれます) の接続ポイントを実装する方法を説明します。 MFC クラスを使用して`CCmdTarget`と`CConnectionPoint`します。

[コンテナー/サーバーの COM コンポーネント](../mfc/containers-advanced-features.md)<br/>
既存のコンテナー アプリケーションに省略可能な高度な機能を組み込むために必要な手順について説明します。

[コンポーネント オブジェクト モデル](/windows/desktop/com/the-component-object-model)<br/>
OLE MFC なしの使用について説明します。

## <a name="see-also"></a>関連項目

[概念](../mfc/mfc-concepts.md)

