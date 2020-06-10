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
ms.openlocfilehash: 529b6d0eaedaee200da547ef9ed980aab51ea233
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622170"
---
# <a name="ole-in-mfc"></a>MFC の OLE

これらの記事では、MFC を使用した OLE プログラミングの基礎について説明します。 MFC には、OLE を使用するプログラムを記述する最も簡単な方法が用意されています。

- OLE ビジュアル編集を使用する場合 (インプレースアクティブ化)。

- OLE コンテナーまたはサーバーとして機能します。

- ドラッグアンドドロップ機能を実装します。

- 日付と時刻のデータを使用する場合。

- エクスポートされた DLL 関数のエントリポイント、OLE/COM インターフェイスのエントリポイント、ウィンドウプロシージャのエントリポイントなど、MFC モジュールの状態データを管理する。

[オートメーション](automation.md)を使用することもできます。

> [!NOTE]
> Ole という用語は、OLE コンテナー、OLE サーバー、OLE アイテム、埋め込み先ライセンス認証 (またはビジュアル編集)、トラッカー、ドラッグアンドドロップ、メニューのマージなど、リンクと埋め込みに関連するテクノロジを意味します。 アクティブという用語は、ActiveX コントロールなどのコンポーネントオブジェクトモデル (COM) と COM ベースのオブジェクトに適用されます。 OLE オートメーションがオートメーションと呼ばれるようになりました。

## <a name="in-this-section"></a>このセクションの内容

[OLE の背景知識](ole-background.md)<br/>
OLE について説明し、そのしくみについての概念を説明します。

[アクティブ化](activation-cpp.md)<br/>
OLE 項目の編集時のアクティブ化の役割について説明します。

[Containers](containers.md)<br/>
OLE でコンテナーを使用するためのリンクを示します。

[データオブジェクトとデータソース](data-objects-and-data-sources-ole.md)<br/>
クラスおよびクラスの使用について説明したトピックへのリンクを示し `COleDataObject` `COleDataSource` ます。

[ドラッグアンドドロップ](drag-and-drop-ole.md)<br/>
OLE でのコピーと貼り付けの使用方法について説明します。

[OLE のメニューとリソース](menus-and-resources-ole.md)<br/>
MFC OLE ドキュメントアプリケーションでのメニューとリソースの使用について説明します。

[登録](registration.md)<br/>
サーバーのインストールと初期化について説明します。

[サーバー](servers.md)<br/>
コンテナーアプリケーションで使用する OLE 項目 (またはコンポーネント) を作成する方法について説明します。

[トラッカー](trackers.md)<br/>
`CRectTracker`ユーザーが OLE クライアントアイテムと対話できるようにするためのグラフィカルインターフェイスを提供するクラスについて説明します。

## <a name="related-sections"></a>関連項目

[接続ポイント](connection-points.md)<br/>
MFC クラスおよびを使用して、接続ポイント (旧称 OLE connection points) を実装する方法について説明し `CCmdTarget` `CConnectionPoint` ます。

[コンテナー/サーバー COM コンポーネント](containers-advanced-features.md)<br/>
既存のコンテナーアプリケーションにオプションの高度な機能を組み込むために必要な手順について説明します。

[コンポーネント オブジェクト モデル](/windows/win32/com/the-component-object-model)<br/>
MFC を使用しない OLE の使用について説明します。

## <a name="see-also"></a>関連項目

[概念](mfc-concepts.md)
