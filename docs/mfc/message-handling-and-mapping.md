---
title: メッセージの処理とのマッピング |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, messages
- message handling [MFC]
- message maps [MFC]
ms.assetid: 62fe2a1b-944c-449d-a0f0-63c11ee0a3cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b8c0fc3b9eec88fc9db9bb4eaff93381d1368368
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444321"
---
# <a name="message-handling-and-mapping"></a>メッセージの処理とマップ

ここでは、MFC フレームワークがメッセージとコマンドの処理方法と、ハンドラー関数への接続方法について説明します。

Windows の従来のプログラムでは、Windows メッセージは、ウィンドウ プロシージャでの大規模な switch ステートメントで処理されます。 代わりに MFC を使用して[メッセージ マップ](../mfc/message-categories.md)ダイレクト メッセージを個別のクラス メンバー関数にマップします。 メッセージ マップは、このため、仮想関数よりも効率的と最適な C++ オブジェクトによって処理されるメッセージを許可するが、アプリケーション、ドキュメント、ビュー、およびなど。 1 つのメッセージまたはメッセージ、コマンドの Id の範囲をマップしたり、コントロール Id。

WM_COMMAND メッセージ-通常、メニューのツールバーのボタン、またはアクセラレータによって生成、メッセージ マップ機構を使用しても。 MFC 標準を定義する[ルーティング](../mfc/command-routing.md)アプリケーション間では、コマンドのメッセージのフレーム ウィンドウ、ビュー、およびプログラムでのアクティブなドキュメントです。 必要がある場合、このルーティングをオーバーライドすることができます。

メッセージ マップは (メニューやツールバーのボタン)、ユーザー インターフェイス オブジェクトを更新する方法を指定することも有効化または無効にすることに合わせて、現在のコンテキスト。

メッセージと Windows でのメッセージ キューの詳細については、次を参照してください。[メッセージとメッセージ キュー](https://msdn.microsoft.com/library/windows/desktop/ms632590) Windows SDK に含まれています。

## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)

- [フレームワークがメッセージ ハンドラーを呼び出す方法](../mfc/how-the-framework-calls-a-handler.md)

- [フレームワークのメッセージ マップ検索方法](../mfc/how-the-framework-searches-message-maps.md)

- [メッセージ ハンドラー関数の宣言](../mfc/declaring-message-handler-functions.md)

- [マップ (関数にメッセージを)](../mfc/reference/mapping-messages-to-functions.md)

- [ステータス バーにコマンド情報を表示する方法](../mfc/how-to-display-command-information-in-the-status-bar.md)

- [ユーザー インターフェイス オブジェクトの動的更新](../mfc/how-to-update-user-interface-objects.md)

- [方法: テンプレート クラスのメッセージ マップを作成する](../mfc/how-to-create-a-message-map-for-a-template-class.md)

## <a name="see-also"></a>関連項目

[概念](../mfc/mfc-concepts.md)<br/>
[MFC の一般的なトピック](../mfc/general-mfc-topics.md)<br/>
[CWnd クラス](../mfc/reference/cwnd-class.md)<br/>
[CCmdTarget クラス](../mfc/reference/ccmdtarget-class.md)
