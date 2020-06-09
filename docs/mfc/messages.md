---
title: メッセージ
ms.date: 11/04/2016
helpviewer_keywords:
- messages, MFC
- messages [MFC]
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
ms.openlocfilehash: f36dab679a2e41910b2445a7dab36f5786081563
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624281"
---
# <a name="messages"></a>メッセージ

`Run`クラスのメンバー関数のメッセージループは、 `CWinApp` さまざまなイベントによって生成されるキューに置かれたメッセージを取得します。 たとえば、ユーザーがマウスをクリックすると、Windows はマウスに関連するいくつかのメッセージを送信します。たとえば、マウスの左ボタンを押したときに、マウスの左ボタンが離されたときに WM_LBUTTONUP WM_LBUTTONDOWN などです。 フレームワークのアプリケーションメッセージループの実装により、メッセージが適切なウィンドウにディスパッチされます。

メッセージの重要なカテゴリについては、「[メッセージのカテゴリ](message-categories.md)」を参照してください。

## <a name="see-also"></a>関連項目

[フレームワークのメッセージとコマンド](messages-and-commands-in-the-framework.md)
