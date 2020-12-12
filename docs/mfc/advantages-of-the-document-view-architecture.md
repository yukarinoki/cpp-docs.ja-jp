---
description: '詳細情報: ドキュメント/ビューアーキテクチャの利点'
title: Document-View アーキテクチャの利点
ms.date: 11/04/2016
helpviewer_keywords:
- views [MFC], advantages
- document/view architecture [MFC], advantages of
ms.assetid: 0bc27071-e120-4889-939c-ce1e61fb9cb3
ms.openlocfilehash: 54ff7cc0e4717f7f487ece3acee79f39ad7dfa3c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185454"
---
# <a name="advantages-of-the-documentview-architecture"></a>ドキュメント/ビュー アーキテクチャの利点

MFC のドキュメント/ビューアーキテクチャを使用する主な利点は、アーキテクチャが同じドキュメントの複数のビューをサポートしていることです。 (複数のビューが不要で、ドキュメント/ビューの小さなオーバーヘッドがアプリケーションで過剰に発生している場合は、アーキテクチャを避けることができます。 [ドキュメント/ビューアーキテクチャの代替手段](alternatives-to-the-document-view-architecture.md)。

アプリケーションで、ユーザーがスプレッドシート形式またはグラフ形式で数値データを表示できるとします。 ユーザーは、スプレッドシート形式の生データと、データの結果として得られるグラフの両方を同時に表示することができます。 これらの個別のビューは、個別のフレームウィンドウまたは分割ペインで1つのウィンドウに表示されます。 次に、ユーザーがスプレッドシートのデータを編集して、変更がグラフに瞬時に反映されることを想定します。

MFC では、スプレッドシートビューとグラフビューは、CView から派生したさまざまなクラスに基づいています。 どちらのビューも1つのドキュメントオブジェクトに関連付けられます。 ドキュメントには、データが格納されます (または、データベースからデータを取得する場合もあります)。 どちらのビューもドキュメントにアクセスし、そこから取得したデータを表示します。

ユーザーがいずれかのビューを更新すると、そのビューオブジェクトはを呼び出し `CDocument::UpdateAllViews` ます。 この関数はドキュメントのすべてのビューに通知し、各ビューはドキュメントの最新のデータを使用して自身を更新します。 への単一の呼び出しによって `UpdateAllViews` 、異なるビューが同期されます。

このシナリオでは、ビューにデータ自体が格納されている場合は特に、ビューからデータを分離することなくコードを記述することは困難です。 ドキュメント/ビューを使用すると、簡単に行うことができます。 このフレームワークでは、ほとんどの調整が行われます。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ドキュメント/ビューの代替手段](alternatives-to-the-document-view-architecture.md)

- [CDocument](reference/cdocument-class.md)

- [CView](reference/cview-class.md)

- [CDocument:: UpdateAllViews](reference/cdocument-class.md#updateallviews)

- [CView:: GetDocument](reference/cview-class.md#getdocument)

## <a name="see-also"></a>関連項目

[ドキュメント/ビューアーキテクチャ](document-view-architecture.md)
