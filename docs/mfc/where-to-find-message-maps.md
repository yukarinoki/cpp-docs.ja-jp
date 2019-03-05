---
title: メッセージ マップの所在
ms.date: 11/04/2016
helpviewer_keywords:
- macros, message map
- locating message maps
- message classes [MFC], finding
- message-map macros
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
ms.openlocfilehash: d9b9a50062334822f34047b8e22e67541ccaa952
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57305147"
---
# <a name="where-to-find-message-maps"></a>メッセージ マップの所在

アプリケーション ウィザードを使用して新しいスケルトン アプリケーションを作成するときに、アプリケーション ウィザードの作成コマンド ターゲット クラスごとのメッセージ マップを書き込みます。 これには、派生したアプリケーション、ドキュメント、ビュー、およびフレーム ウィンドウ クラスが含まれます。 特定のメッセージと定義済みのコマンドでは、アプリケーション ウィザードで指定されたエントリが既にあるこれらのメッセージ マップの一部と、いくつか追加するハンドラーの単なるプレース ホルダーです。

クラスのメッセージ マップにあります。クラスの CPP ファイルです。 メッセージと各クラスを処理するコマンドのエントリを追加するのにプロパティ ウィンドウを使用するアプリケーション ウィザードで作成される基本的なメッセージ マップを使用します。 いくつかのエントリを追加した後、通常のメッセージ マップは、次のようになります。

[!code-cpp[NVC_MFCMessageHandling#1](../mfc/codesnippet/cpp/where-to-find-message-maps_1.cpp)]

メッセージ マップは、マクロのコレクションで構成されます。 2 つのマクロ[BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map)と[END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map)、メッセージ マップを角かっこです。 その他のマクロなど`ON_COMMAND`、メッセージ マップのコンテンツを入力します。

> [!NOTE]
>  セミコロンでは、メッセージ マップ マクロは追跡されません。

新しいクラスを作成するクラスの追加ウィザードを使用する場合は、クラスのメッセージ マップを提供します。 または、ソース コード エディターを使用して手動でメッセージ マップを作成することができます。

## <a name="see-also"></a>関連項目

[フレームワークのメッセージ マップ検索方法](../mfc/how-the-framework-searches-message-maps.md)
