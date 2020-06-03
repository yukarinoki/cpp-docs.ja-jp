---
title: MFC の OLE
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, OLE and
- OLE items
- OLE applications [MFC], about OLE
- OLE [MFC]
- OLE containers [MFC], about OLE
- applications [OLE], about OLE
- OLE component object model (COM)
ms.assetid: 5193479d-1239-4697-aea4-e82f92c707ab
ms.openlocfilehash: 2594531df63bcd62cdaec44fbc3668ea68990922
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366899"
---
# <a name="ole-in-mfc"></a>MFC の OLE

これらの記事では、MFC を使用した OLE プログラミングの基礎について説明します。 MFC には、OLE を使用するプログラムを簡単に記述する方法が用意されています。

- OLE ビジュアル編集 (インプレース アクティブ化) を使用する。

- OLE コンテナまたはサーバーとして動作する。

- ドラッグ アンド ドロップ機能を実装します。

- 日付と時刻のデータを操作します。

- エクスポートされた DLL 関数エントリ ポイント、OLE/COM インターフェイス エントリ ポイント、ウィンドウ プロシージャ エントリ ポイントなど、MFC モジュールの状態データを管理します。

[オートメーション](../mfc/automation.md)を使用することもできます。

> [!NOTE]
> OLE という用語は、OLE コンテナー、OLE サーバー、OLE アイテム、埋め込み場所でのアクティブ化 (またはビジュアル編集)、トラッカー、ドラッグ アンド ドロップ、メニューのマージなど、リンクと埋め込みに関連するテクノロジを表します。 Active という用語は、コンポーネント オブジェクト モデル (COM) および ActiveX コントロールなどの COM ベースのオブジェクトに適用されます。 OLE オートメーションはオートメーションと呼ばれるようになりました。

## <a name="in-this-section"></a>このセクションの内容

[OLE の背景知識](../mfc/ole-background.md)<br/>
OLE について説明し、そのしくみに関する概念的な情報を提供します。

[アクティブ化](../mfc/activation-cpp.md)<br/>
OLE アイテムを編集する際のアクティブ化の役割について説明します。

[Containers](../mfc/containers.md)<br/>
OLE でのコンテナーの使用へのリンクを提供します。

[データ オブジェクトとデータ ソース](../mfc/data-objects-and-data-sources-ole.md)<br/>
クラスおよび クラスの使用方法について説明する`COleDataObject`トピック`COleDataSource`へのリンクを提供します。

[ドラッグ アンド ドロップ](../mfc/drag-and-drop-ole.md)<br/>
OLE を使用したコピーと貼り付けの使用について説明します。

[OLE メニューとリソース](../mfc/menus-and-resources-ole.md)<br/>
MFC OLE ドキュメント アプリケーションでのメニューとリソースの使用方法について説明します。

[登録](../mfc/registration.md)<br/>
サーバーのインストールと初期化について説明します。

[サーバー](../mfc/servers.md)<br/>
コンテナー アプリケーションで使用する OLE アイテム (複数のコンポーネント) を作成する方法について説明します。

[トラッカー](../mfc/trackers.md)<br/>
ユーザーが OLE`CRectTracker`クライアントアイテムを操作できるようにするグラフィカル インターフェイスを提供するクラスについて説明します。

## <a name="related-sections"></a>関連項目

[接続ポイント](../mfc/connection-points.md)<br/>
MFC クラス`CCmdTarget`と`CConnectionPoint`を使用してコネクション ポイント (以前は OLE コネクション ポイント) を実装する方法について説明します。

[コンテナ/サーバー COM コンポーネント](../mfc/containers-advanced-features.md)<br/>
オプションの高度な機能を既存のコンテナー アプリケーションに組み込むために必要な手順について説明します。

[コンポーネント オブジェクト モデル](/windows/win32/com/the-component-object-model)<br/>
MFC を使用しない OLE の使用方法について説明します。

## <a name="see-also"></a>関連項目

[概念](../mfc/mfc-concepts.md)
