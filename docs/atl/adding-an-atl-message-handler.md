---
description: 詳細については、「ATL メッセージハンドラーの追加」を参照してください。
title: ATL メッセージハンドラーの追加
ms.date: 11/04/2016
helpviewer_keywords:
- message handlers [C++]
- ATL, windows
- message handling [C++], ATL message handler
- windows [C++], ATL
- ATL, message handlers
ms.assetid: cdea38a1-0d9b-4f8d-bbd5-b4f063fb3eeb
ms.openlocfilehash: 263cbcb863ee287c9b3f4650263a3fac33d7ab7b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166344"
---
# <a name="adding-an-atl-message-handler"></a>ATL メッセージハンドラーの追加

コントロールにメッセージハンドラー (Windows メッセージを処理するメンバー関数) を追加するには、まずクラスビューでコントロールを選択します。 次に、[ **プロパティ** ] ウィンドウを開き、[ **メッセージ** ] アイコンを選択し、必要なメッセージの反対にあるボックスのドロップダウンコントロールをクリックします。 これにより、コントロールのヘッダーファイル内のメッセージハンドラーの宣言と、コントロールの .cpp ファイル内のハンドラーのスケルトン実装が追加されます。 また、メッセージマップを追加し、ハンドラーのエントリを追加します。

ATL でメッセージハンドラーを追加することは、メッセージハンドラーを MFC クラスに追加することと似ています。 詳細については [、「MFC メッセージハンドラーの追加](../mfc/reference/adding-an-mfc-message-handler.md) 」を参照してください。

次の条件は、ATL メッセージハンドラーを追加する場合にのみ適用されます。

- メッセージハンドラーは、MFC と同じ名前付け規則に従います。

- 新しいメッセージマップエントリがメインメッセージマップに追加されます。 このウィザードでは、代替のメッセージマップとチェーンは認識されません。

## <a name="see-also"></a>関連項目

[ウィンドウの実装](../atl/implementing-a-window.md)
