---
description: '詳細情報: CWnd オブジェクトを初期化するタイミング'
title: CWnd オブジェクトの初期化のタイミング
ms.date: 11/04/2016
helpviewer_keywords:
- window objects [MFC], when to initialize CWnd
- initializing CWnd objects [MFC]
- initializing objects [MFC], CWnd
- CWnd objects [MFC], when HWND is attached
- HWND, when attached to CWnd object
- CWnd objects [MFC], when to initialize
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
ms.openlocfilehash: 89d40b826507574fddd41364ac6cecc526663519
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142767"
---
# <a name="when-to-initialize-cwnd-objects"></a>CWnd オブジェクトの初期化のタイミング

独自の子ウィンドウを作成したり、の派生オブジェクトのコンストラクターで任意の Windows API 関数を呼び出したりすることはできません `CWnd` 。 これは、 `HWND` オブジェクトのが `CWnd` まだ作成されていないためです。 子ウィンドウの追加など、ほとんどの Windows 固有の初期化は、 [OnCreate](../mfc/reference/cwnd-class.md#oncreate) メッセージハンドラーで実行する必要があります。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ドキュメント フレーム ウィンドウの作成](../mfc/creating-document-frame-windows.md)

- [ドキュメント/ビューの作成](../mfc/document-view-creation.md)

## <a name="see-also"></a>関連項目

[フレームウィンドウの使用](../mfc/using-frame-windows.md)
