---
description: '詳細情報: 子ウィンドウとしてのコモンコントロールの使用'
title: 子ウィンドウとしてのコモン コントロールの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], using as child windows
- windows [MFC], common controls as
- child windows [MFC], common controls as
- common controls [MFC], child windows
- Windows common controls [MFC], child windows
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
ms.openlocfilehash: 5a5fda2cbf8d0bf16ccb17f2766b31d24e5c0c67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263557"
---
# <a name="using-a-common-control-as-a-child-window"></a>子ウィンドウとしてのコモン コントロールの使い方

Windows コモンコントロールは、他のウィンドウの子ウィンドウとして使用できます。 次の手順では、コモンコントロールを動的に作成して操作する方法について説明します。

### <a name="to-use-a-common-control-as-a-child-window"></a>コモンコントロールを子ウィンドウとして使用するには

1. 関連するクラスまたはハンドラーでコントロールを定義します。

1. [CWnd:: create](../mfc/reference/cwnd-class.md#create)メソッドのコントロールのオーバーライドを使用して、Windows コントロールを作成します。

1. コントロールが作成された後 ( `OnCreate` コントロールをサブクラス化する場合は、ハンドラーと同じように)、メンバー関数を使用してコントロールを操作できます。 メソッドの詳細については、 [コントロール](../mfc/controls-mfc.md) の各コントロールについての説明を参照してください。

1. コントロールが終了したら、 [CWnd::D estroywindow](../mfc/reference/cwnd-class.md#destroywindow) を使用してコントロールを破棄します。

## <a name="see-also"></a>関連項目

[コントロールの作成と使用](../mfc/making-and-using-controls.md)<br/>
[コントロール](../mfc/controls-mfc.md)
