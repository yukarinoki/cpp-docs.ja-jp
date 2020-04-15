---
title: メッセージ マップの所在
ms.date: 11/04/2016
helpviewer_keywords:
- macros, message map
- locating message maps
- message classes [MFC], finding
- message-map macros
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
ms.openlocfilehash: eec0ae43546e3cc0c08e3178c4808e21fa48686a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360163"
---
# <a name="where-to-find-message-maps"></a>メッセージ マップの所在

アプリケーション ウィザードを使用して新しいスケルトン アプリケーションを作成すると、アプリケーション ウィザードによって作成されるコマンド ターゲット クラスごとにメッセージ マップが書き込まれます。 これには、派生アプリケーション、ドキュメント、ビュー、およびフレーム ウィンドウクラスが含まれます。 これらのメッセージ マップの中には、特定のメッセージや定義済みコマンドに対してアプリケーション ウィザードによって提供されるエントリが既に含まれています。

クラスのメッセージ マップは.クラスの CPP ファイル。 アプリケーション ウィザードで作成される基本的なメッセージ マップを使用して、[クラス ウィザード](reference/mfc-class-wizard.md)を使用して、各クラスで処理するメッセージとコマンドのエントリを追加します。 一部のエントリを追加すると、一般的なメッセージ マップは次のようになります。

[!code-cpp[NVC_MFCMessageHandling#1](../mfc/codesnippet/cpp/where-to-find-message-maps_1.cpp)]

メッセージ マップは、マクロのコレクションで構成されます。 [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map)と[END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map)の 2 つのマクロは、メッセージ マップを囲みます。 などの`ON_COMMAND`他のマクロは、メッセージ マップの内容を入力します。

> [!NOTE]
> メッセージ マップ マクロの後にセミコロンは付かっていません。

クラスの追加ウィザードを使用して新しいクラスを作成すると、クラスのメッセージ マップが表示されます。 または、ソース コード エディターを使用してメッセージ マップを手動で作成することもできます。

## <a name="see-also"></a>関連項目

[フレームワークのメッセージ マップ検索方法](../mfc/how-the-framework-searches-message-maps.md)
