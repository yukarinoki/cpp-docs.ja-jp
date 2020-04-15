---
title: SDI と MDI
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], SDI applications
- frame windows [MFC], MDI applications
- MFC, windows
- single document interface (SDI) [MFC], applications
- MDI [MFC], vs. SDI
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
ms.openlocfilehash: 9730e7baf9589c4b05a60703c619aae2e941bdec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372754"
---
# <a name="sdi-and-mdi"></a>SDI と MDI

MFC では、シングル ドキュメント インターフェイス (SDI) アプリケーションとマルチドキュメント インターフェイス (MDI) アプリケーションの両方を簡単に操作できます。

SDI アプリケーションでは、一度に 1 つの開いているドキュメント フレーム ウィンドウしか許可されません。 MDI アプリケーションでは、複数のドキュメント フレーム ウィンドウをアプリケーションの同じインスタンスで開きます。 MDI アプリケーションには、フレーム ウィンドウ自体である複数の MDI 子ウィンドウを開いて、それぞれ別のドキュメントを含むウィンドウがあります。 一部のアプリケーションでは、子ウィンドウは、グラフ ウィンドウやスプレッドシート ウィンドウなど、さまざまな種類の場合があります。 その場合、異なるタイプの MDI 子ウィンドウがアクティブ化されると、メニュー バーが変更される可能性があります。

> [!NOTE]
> Windows 95 以降では、オペレーティング システムが "ドキュメント中心" ビューを採用しているため、アプリケーションは一般的に SDI です。

詳細については、「[ドキュメント、ビュー、およびフレームワーク](../mfc/documents-views-and-the-framework.md)」を参照してください。

## <a name="see-also"></a>関連項目

[クラスを使用した Windows アプリケーションの作成](../mfc/using-the-classes-to-write-applications-for-windows.md)
