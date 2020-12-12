---
description: 詳細については、「メッセージマップの検索場所」を参照してください。
title: メッセージ マップの所在
ms.date: 11/04/2016
helpviewer_keywords:
- macros, message map
- locating message maps
- message classes [MFC], finding
- message-map macros
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
ms.openlocfilehash: 4796d358dd3be5455b22e348fbcc9236d1404ce8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284968"
---
# <a name="where-to-find-message-maps"></a>メッセージ マップの所在

アプリケーションウィザードを使用して新しいスケルトンアプリケーションを作成する場合、アプリケーションウィザードでは、作成したコマンドターゲットクラスごとにメッセージマップが書き込まれます。 これには、派生アプリケーション、ドキュメント、ビュー、フレームウィンドウの各クラスが含まれます。 これらのメッセージマップの中には、特定のメッセージと定義済みコマンドに対してアプリケーションウィザードによって指定されたエントリが既に存在しているものと、追加するハンドラーのプレースホルダーだけが含まれているものがあります。

クラスのメッセージマップは、にあります。クラスの CPP ファイル。 アプリケーションウィザードによって作成される基本的なメッセージマップを操作するには、 [クラスウィザード](reference/mfc-class-wizard.md) を使用して、各クラスが処理するメッセージとコマンドのエントリを追加します。 いくつかのエントリを追加すると、一般的なメッセージマップは次のようになります。

[!code-cpp[NVC_MFCMessageHandling#1](../mfc/codesnippet/cpp/where-to-find-message-maps_1.cpp)]

メッセージマップは、マクロのコレクションで構成されます。 2つのマクロ ( [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) と [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map)) は、メッセージマップをかっこで囲みます。 などの他のマクロは、 `ON_COMMAND` メッセージマップの内容を入力します。

> [!NOTE]
> メッセージマップマクロの後にセミコロンがありません。

クラスの追加ウィザードを使用して新しいクラスを作成すると、クラスのメッセージマップが提供されます。 または、ソースコードエディターを使用して、手動でメッセージマップを作成することもできます。

## <a name="see-also"></a>関連項目

[フレームワークがメッセージマップを検索する方法](../mfc/how-the-framework-searches-message-maps.md)
