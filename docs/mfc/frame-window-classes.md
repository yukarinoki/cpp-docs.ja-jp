---
description: 詳細については、「Frame-Window クラス」を参照してください。
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
ms.openlocfilehash: 888fae71bef2dd2e30e10c645e78ab981a30c6af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154956"
---
# <a name="frame-window-classes"></a>フレーム ウィンドウ クラス

各アプリケーションには、1つの "メインフレームウィンドウ" があります。これは通常、アプリケーション名をキャプションに持つデスクトップウィンドウです。 各ドキュメントには、通常、1つの "ドキュメントフレームウィンドウ" があります。 ドキュメントフレームウィンドウには、ドキュメントのデータを表示する少なくとも1つのビューが含まれています。

## <a name="frame-windows-in-sdi-and-mdi-applications"></a>SDI および MDI アプリケーションのフレームウィンドウ

SDI アプリケーションの場合、クラス [CFrameWnd](reference/cframewnd-class.md)から派生したフレームウィンドウが1つあります。 このウィンドウは、メインフレームウィンドウとドキュメントフレームウィンドウの両方です。 MDI アプリケーションの場合、メインフレームウィンドウは [CMDIFrameWnd](reference/cmdiframewnd-class.md)クラスから派生し、mdi 子ウィンドウであるドキュメントフレームウィンドウは [CMDIChildWnd](reference/cmdichildwnd-class.md)クラスから派生します。

## <a name="use-the-frame-window-class-or-derive-from-it"></a>Frame-Window クラスを使用するか、そのクラスから派生します。

これらのクラスは、アプリケーションに必要なフレームウィンドウ機能のほとんどを提供します。 通常の状況では、既定で提供される動作と外観がニーズに合っています。 追加の機能が必要な場合は、これらのクラスから派生させます。

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [アプリケーションウィザードによって作成されるフレームウィンドウクラス](frame-window-classes-created-by-the-application-wizard.md)

- [フレームウィンドウスタイル](frame-window-styles-cpp.md)

- [MFC で作成したウィンドウのスタイル変更](changing-the-styles-of-a-window-created-by-mfc.md)

## <a name="see-also"></a>関連項目

[フレームウィンドウ](frame-windows.md)
