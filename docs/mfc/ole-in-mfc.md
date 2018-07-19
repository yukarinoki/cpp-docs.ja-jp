---
title: MFC の OLE |Microsoft ドキュメント
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
ms.openlocfilehash: ef23f0b7e031c6866b7792bca61c5e4d5bd470da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353629"
---
# <a name="ole-in-mfc"></a>MFC の OLE
これらの記事では、MFC を使用して OLE プログラミングの基礎について説明します。 MFC には、OLE を使用するプログラムを作成する最も簡単な方法が用意されています。  
  
-   OLE ビジュアル編集 (インプレース アクティブ化) を使用します。  
  
-   OLE コンテナーまたはサーバーで作業します。  
  
-   ドラッグ アンド ドロップ機能を実装します。  
  
-   日付と時刻のデータを使用します。  
  
-   MFC の状態データを管理するには、DLL 関数のエントリ ポイント、OLE と COM インターフェイス エントリ ポイント、およびウィンドウ プロシージャ エントリ ポイントを含むモジュールがエクスポートされます。  
  
 使用することも[オートメーション](../mfc/automation.md)です。  
  
> [!NOTE]
>  用語 OLE 表します、リンクと埋め込みに関連付けられているなどテクノロジ OLE コンテナー、OLE サーバーを OLE アイテム、インプレース アクティブ化 (ビジュアル編集)、(トラッカーを)、ドラッグ アンド ドロップ、およびメニューのマージします。 という用語は、ActiveX コントロールなど、コンポーネント オブジェクト モデル (COM) と COM ベースのオブジェクトにアクティブなが適用されます。 OLE オートメーションは、オートメーションと呼ばれるようになりました。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [OLE の背景知識](../mfc/ole-background.md)  
 OLE について説明し、そのしくみについて説明します。  
  
 [アクティベーション](../mfc/activation-cpp.md)  
 OLE 項目の編集でのライセンス認証の役割について説明します。  
  
 [コンテナー](../mfc/containers.md)  
 OLE のコンテナーを使用してへのリンクを提供します。  
  
 [データ オブジェクトとデータ ソース](../mfc/data-objects-and-data-sources-ole.md)  
 使用方法に関するトピックへのリンクを提供、`COleDataObject`と`COleDataSource`クラスです。  
  
 [ドラッグ アンド ドロップ](../mfc/drag-and-drop-ole.md)  
 コピーと ole 貼り付けの使用について説明します。  
  
 [OLE のメニューとリソース](../mfc/menus-and-resources-ole.md)  
 MFC OLE ドキュメント アプリケーションでメニューとリソースの使用について説明します。  
  
 [登録](../mfc/registration.md)  
 サーバーのインストールと初期化について説明します。  
  
 [サーバー](../mfc/servers.md)  
 コンテナー アプリケーションで OLE 項目 (コンポーネント) の使用を作成する方法について説明します。  
  
 [トラッカー](../mfc/trackers.md)  
 に関する情報を提供、 `CRectTracker` OLE クライアント アイテムと対話するユーザーを有効にするためのグラフィカル インターフェイスを提供するクラス。  
  
## <a name="related-sections"></a>関連項目  
 [接続ポイント](../mfc/connection-points.md)  
 接続ポイント (以前は OLE コネクション ポイントと呼ばれます) を実装する方法を説明します。 MFC クラスを使用して`CCmdTarget`と`CConnectionPoint`です。  
  
 [コンテナー/サーバーの COM コンポーネント](../mfc/containers-advanced-features.md)  
 省略可能な高度な機能を既存のコンテナー アプリケーションに組み込むに必要な手順について説明します。  
  
 [コンポーネント オブジェクト モデル](http://msdn.microsoft.com/library/windows/desktop/ms694363)  
 MFC を使わない OLE の使用方法について説明します。  
  
## <a name="see-also"></a>関連項目  
 [概念](../mfc/mfc-concepts.md)

