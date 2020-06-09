---
title: フレーム ウィンドウ スタイル (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- window styles [MFC]
- PreCreateWindow method, setting window styles
- windows [MFC], MFC
- frame windows [MFC], styles
- MFC, frame windows
- styles [MFC], windows
ms.assetid: fc5058c1-eec8-48d8-9f76-3fc01cfa53f7
ms.openlocfilehash: 3c22944537370a44aee1af1cf71281264ed4969b
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626454"
---
# <a name="frame-window-styles-c"></a>フレーム ウィンドウ スタイル (C++)

フレームワークを使用して取得したフレームウィンドウは、ほとんどのプログラムに適していますが、高度な関数[PreCreateWindow](reference/cwnd-class.md#precreatewindow)と MFC グローバル関数[AfxRegisterWndClass](reference/application-information-and-management.md#afxregisterwndclass)を使用すると、さらに柔軟性が得られます。 `PreCreateWindow`はのメンバー関数です `CWnd` 。

**WS_HSCROLL**と**WS_VSCROLL**のスタイルをメインフレームウィンドウに適用した場合、ユーザーは**MDICLIENT**ウィンドウに適用されるので、ユーザーは**MDICLIENT**領域をスクロールできます。

ウィンドウの**FWS_ADDTOTITLE**スタイルビットが設定されている場合 (既定では)、ビューのドキュメント名に基づいて、ウィンドウのタイトルバーに表示するタイトルがフレームウィンドウに示されます。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- Mdi 子ウィンドウの管理 (mdi 子ウィンドウを含む mdi フレーム内のウィンドウ[) (MDICLIENT)](managing-mdi-child-windows.md)

- [MFC で作成したウィンドウのスタイル変更](changing-the-styles-of-a-window-created-by-mfc.md)

- [ウィンドウスタイル](reference/styles-used-by-mfc.md#window-styles)

## <a name="see-also"></a>関連項目

[フレーム ウィンドウ](frame-windows.md)
