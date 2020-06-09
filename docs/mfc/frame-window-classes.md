---
title: フレーム ウィンドウ クラス
ms.date: 11/04/2016
helpviewer_keywords:
- frame window classes [MFC], about frame window classes
- frame window classes [MFC]
- windows [MFC], MDI
- document frame windows [MFC], classes
- single document interface (SDI), frame windows
- window classes [MFC], frame
- MFC, frame windows
- MDI [MFC], frame windows
- classes [MFC], window
ms.assetid: c27e43a7-8ad0-4759-b1b7-43f4725f4132
ms.openlocfilehash: ffa5b966ee042120213896dc7ad9d81c048ef928
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625808"
---
# <a name="frame-window-classes"></a>フレーム ウィンドウ クラス

各アプリケーションには、1つの "メインフレームウィンドウ" があります。これは通常、アプリケーション名をキャプションに持つデスクトップウィンドウです。 各ドキュメントには、通常、1つの "ドキュメントフレームウィンドウ" があります。 ドキュメントフレームウィンドウには、ドキュメントのデータを表示する少なくとも1つのビューが含まれています。

## <a name="frame-windows-in-sdi-and-mdi-applications"></a>SDI および MDI アプリケーションのフレームウィンドウ

SDI アプリケーションの場合、クラス[CFrameWnd](reference/cframewnd-class.md)から派生したフレームウィンドウが1つあります。 このウィンドウは、メインフレームウィンドウとドキュメントフレームウィンドウの両方です。 MDI アプリケーションの場合、メインフレームウィンドウは[CMDIFrameWnd](reference/cmdiframewnd-class.md)クラスから派生し、mdi 子ウィンドウであるドキュメントフレームウィンドウは[CMDIChildWnd](reference/cmdichildwnd-class.md)クラスから派生します。

## <a name="use-the-frame-window-class-or-derive-from-it"></a>フレームウィンドウクラスを使用するか、またはそのクラスから派生します。

これらのクラスは、アプリケーションに必要なフレームウィンドウ機能のほとんどを提供します。 通常の状況では、既定で提供される動作と外観がニーズに合っています。 追加の機能が必要な場合は、これらのクラスから派生させます。

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [アプリケーションウィザードによって作成されるフレームウィンドウクラス](frame-window-classes-created-by-the-application-wizard.md)

- [フレームウィンドウスタイル](frame-window-styles-cpp.md)

- [MFC で作成したウィンドウのスタイル変更](changing-the-styles-of-a-window-created-by-mfc.md)

## <a name="see-also"></a>関連項目

[フレーム ウィンドウ](frame-windows.md)
