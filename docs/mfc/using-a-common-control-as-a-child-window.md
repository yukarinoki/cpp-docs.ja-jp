---
title: 子ウィンドウとしてのコモン コントロールの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], using as child windows
- windows [MFC], common controls as
- child windows [MFC], common controls as
- common controls [MFC], child windows
- Windows common controls [MFC], child windows
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
ms.openlocfilehash: 690b48cf50e95265aaf5bdd454e2881b8f5fab3f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655131"
---
# <a name="using-a-common-control-as-a-child-window"></a>子ウィンドウとしてのコモン コントロールの使い方

Windows コモン コントロールのいずれかは、その他のウィンドウの子ウィンドウとして使用できます。 次の手順では、一般的なコントロールを動的に作成し、操作する方法について説明します。

### <a name="to-use-a-common-control-as-a-child-window"></a>子ウィンドウとしてのコモン コントロールを使用するには

1. 関連するクラスまたはハンドラーでは、コントロールを定義します。

1. コントロールのオーバーライドを使用して、 [cwnd::create](../mfc/reference/cwnd-class.md#create) Windows コントロールを作成するメソッド。

1. コントロールが作成された後 (として事前、`OnCreate`ハンドラー場合、コントロールをサブクラス化する)、そのメンバー関数を使用して、コントロールを操作することができます。 ある個々 のコントロールの説明を参照してください。[コントロール](../mfc/controls-mfc.md)メソッドの詳細について。

1. コントロールが完了したらを使用して、[に](../mfc/reference/cwnd-class.md#destroywindow)コントロールを破棄します。

## <a name="see-also"></a>関連項目

[コントロールの作成方法と使い方](../mfc/making-and-using-controls.md)<br/>
[コントロール](../mfc/controls-mfc.md)

