---
title: 'コンテナー: クライアント アイテム |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE containers [MFC], client items
- client items and OLE containers
ms.assetid: 231528b5-0744-4f83-8897-083bf55ed087
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ae9a37aaeb9df3241cf48d3fc62db046682a7a1b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387069"
---
# <a name="containers-client-items"></a>コンテナー : クライアント アイテム

この記事では、クライアント アイテムについて説明し、そのクライアント アイテムをアプリケーションのクラスから派生させてください。

クライアント アイテムとは別のアプリケーションに含まれているかによって OLE コンテナー アプリケーションのドキュメント参照に属しているデータ項目です。 データは、ドキュメント内に含まれるクライアント アイテムが埋め込まれます。コンテナーのドキュメントで参照されている別の場所にデータが保存されているものがリンクされます。

OLE アプリケーションでドキュメント クラスは、クラスから派生[COleDocument](../mfc/reference/coledocument-class.md)からではなく`CDocument`します。 `COleDocument`クラスから継承`CDocument`する MFC アプリケーションの基にドキュメント/ビュー アーキテクチャを使用するために必要なすべての機能です。 `COleDocument` コレクションとしてドキュメントを処理するインターフェイスも定義`CDocItem`オブジェクト。 いくつか`COleDocument`の追加、取得、およびそのコレクションの要素を削除するためのメンバー関数が用意されています。

すべてのコンテナー アプリケーションを少なくとも 1 つのクラスから派生させてください`COleClientItem`します。 このクラスのオブジェクトは、埋め込みまたはリンク、OLE ドキュメント内の項目を表します。 ドキュメントから削除される場合を除き、これらのオブジェクトは、それらが格納されたドキュメントの有効期間存在します。

`CDocItem` 基本クラスは、`COleClientItem`と`COleServerItem`します。 これらの 2 つから派生したクラスのオブジェクトは、それぞれ OLE アイテムと、クライアントとサーバー アプリケーション間の仲介役として機能します。 新しい OLE 項目は、ドキュメントに追加されるたびに、MFC フレームワークは、クライアント アプリケーションの新しいオブジェクトを追加します`COleClientItem`-クラスを派生クラスのドキュメントのコレクションから`CDocItem`オブジェクト。

## <a name="see-also"></a>関連項目

[コンテナー](../mfc/containers.md)<br/>
[コンテナー: 複合ファイル](../mfc/containers-compound-files.md)<br/>
[コンテナー: ユーザー インターフェイスの問題](../mfc/containers-user-interface-issues.md)<br/>
[コンテナー: 高度な機能](../mfc/containers-advanced-features.md)<br/>
[COleClientItem クラス](../mfc/reference/coleclientitem-class.md)<br/>
[COleServerItem クラス](../mfc/reference/coleserveritem-class.md)
