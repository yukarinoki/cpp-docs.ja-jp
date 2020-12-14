---
description: 詳細については、「SDI と MDI」を参照してください。
title: SDI と MDI
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], SDI applications
- frame windows [MFC], MDI applications
- MFC, windows
- single document interface (SDI) [MFC], applications
- MDI [MFC], vs. SDI
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
ms.openlocfilehash: bfa54db04a657507b4b491ada6e8f08d17c2d1c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217784"
---
# <a name="sdi-and-mdi"></a>SDI と MDI

MFC を使用すると、シングルドキュメントインターフェイス (SDI) アプリケーションとマルチドキュメントインターフェイス (MDI) アプリケーションの両方を簡単に操作できます。

SDI アプリケーションでは、一度に1つの開いているドキュメントフレームウィンドウのみを使用できます。 MDI アプリケーションでは、アプリケーションの同じインスタンスで複数のドキュメントフレームウィンドウを開くことができます。 MDI アプリケーションには、フレームウィンドウ自体である複数の MDI 子ウィンドウを開くことができるウィンドウがあり、それぞれが個別のドキュメントを含んでいます。 アプリケーションによっては、子ウィンドウがグラフウィンドウやスプレッドシートウィンドウなどのさまざまな種類になることがあります。 この場合、メニューバーは、異なる種類の MDI 子ウィンドウがアクティブになると変更される可能性があります。

> [!NOTE]
> Windows 95 以降では、オペレーティングシステムが "ドキュメント中心" のビューを採用しているため、一般的にアプリケーションが SDI になります。

詳細については、「 [ドキュメント、ビュー、およびフレームワーク](../mfc/documents-views-and-the-framework.md)」を参照してください。

## <a name="see-also"></a>関連項目

[クラスを使用して Windows 用のアプリケーションを作成する](../mfc/using-the-classes-to-write-applications-for-windows.md)
