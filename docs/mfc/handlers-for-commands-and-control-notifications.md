---
title: コマンドとコントロール通知のハンドラー |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- commands [MFC], handlers for
- functions [MFC], handler
- handlers [MFC]
- controls [MFC], notifications
- handlers [MFC], control notification [MFC]
- notifications [MFC], handlers for control
- handlers [MFC], command
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bda42393cd55b60ab787665b51957bb2f94c5df3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430081"
---
# <a name="handlers-for-commands-and-control-notifications"></a>コマンドとコントロール通知のハンドラー

コマンドまたはコントロールの通知メッセージの既定のハンドラーはありません。 そのためは、これらの種類のメッセージのハンドラーの名前付け規則によってのみバインドされます。 コマンドまたはコントロールの通知をハンドラーにマップするときに、[プロパティ] ウィンドウは、コマンドの ID またはコントロール通知のコードに基づく名前を提案します。 指定された名前をそのまま使用、変更するか、または置き換えることができます。

規則は、両方のカテゴリ ハンドラーを表すユーザー インターフェイス オブジェクトの名前をお勧めします。 [編集] メニューの切り取りコマンドのハンドラーの名前をそのため

[!code-cpp[NVC_MFCMessageHandling#4](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_1.h)]

として Cut コマンドのコマンド ID は、フレームワークが組み込まれて Cut コマンドは、アプリケーションによくため実装されたため、 **ID_EDIT_CUT**します。 定義済みのすべてのコマンド Id の一覧は、コマ ファイルを参照してください。H. 詳細については、次を参照してください。[標準コマンド](../mfc/standard-commands.md)します。

さらに、規則がのハンドラーを提案、 **BN_CLICKED**名前に「マイ ボタン」というラベルのボタンからの通知メッセージ

[!code-cpp[NVC_MFCMessageHandling#5](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_2.h)]

このコマンドの ID を割り当てることができます**として**のため、これは、アプリケーション固有のユーザー インターフェイス オブジェクトに相当します。

メッセージの両方のカテゴリは、引数を受け取らず、値が返されない。

## <a name="see-also"></a>関連項目

[メッセージ ハンドラー関数の宣言](../mfc/declaring-message-handler-functions.md)
