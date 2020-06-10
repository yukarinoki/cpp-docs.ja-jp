---
title: MDI 子ウィンドウの管理
ms.date: 11/19/2018
f1_keywords:
- MDICLIENT
helpviewer_keywords:
- MDI [MFC], child windows
- child windows [MFC], and MDICLIENT window
- MDICLIENT window [MFC]
- windows [MFC], MDI
- frame windows [MFC], MDI child windows
- child windows [MFC]
- MDI [MFC], frame windows
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
ms.openlocfilehash: 6e8e3d0aa51eeea112597485a9221dcba4feda87
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618359"
---
# <a name="managing-mdi-child-windows"></a>MDI 子ウィンドウの管理

MDI メインフレームウィンドウ (アプリケーションごとに1つ) には、MDICLIENT ウィンドウと呼ばれる特殊な子ウィンドウがあります。 MDICLIENT ウィンドウはメインフレームウィンドウのクライアント領域を管理し、それ自体には子ウィンドウがあります。ドキュメントウィンドウは、から派生したもの `CMDIChildWnd` です。 ドキュメントウィンドウはフレームウィンドウ自体 (MDI 子ウィンドウ) であるため、独自の子を持つこともできます。 これらのすべての場合、親ウィンドウは子ウィンドウを管理し、コマンドを転送します。

MDI フレームウィンドウでは、フレームウィンドウは MDICLIENT ウィンドウを管理し、コントロールバーと共に移動します。 MDICLIENT ウィンドウでは、すべての MDI 子フレームウィンドウが管理されます。 次の図は、MDI フレームウィンドウとその MDICLIENT ウィンドウとその子ドキュメントフレームウィンドウの間の関係を示しています。

![MDI フレーム ウィンドウの子ウィンドウ](../mfc/media/vc37gb1.gif "MDI フレーム ウィンドウの子ウィンドウ") <br/>
MDI フレーム ウィンドウと子ウィンドウ

MDI フレームウィンドウは、現在の MDI 子ウィンドウと共に使用することもできます (存在する場合)。 MDI フレームウィンドウは、コマンドメッセージを MDI 子に代行させてから、それ自体を処理しようとします。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ドキュメント フレーム ウィンドウの作成](creating-document-frame-windows.md)

- [フレームウィンドウスタイル](frame-window-styles-cpp.md)

## <a name="see-also"></a>関連項目

[フレームウィンドウの使用](using-frame-windows.md)
