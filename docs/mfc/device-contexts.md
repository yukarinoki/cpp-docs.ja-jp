---
title: デバイス コンテキスト |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OnPrepareDC method [MFC]
- windows [MFC], and device context
- drawing [MFC], device context
- CClientDC class [MFC], and GetDC method [MFC]
- drawing [MFC], in mouse and device contexts
- CDC class [MFC], objects
- device contexts [MFC]
- client areas
- CMetaFileDC class [MFC], and OnPrepareDC method [MFC]
- GDI objects [MFC], device contexts
- graphic objects [MFC], device contexts
- frame windows [MFC], device contexts
- metafiles and device contexts
- EndPaint method [MFC]
- printers [MFC], device contexts
- mouse [MFC], drawing and device contexts
- BeginPaint method, CPaintDC
- CPaintDC class [MFC], device context for painting
- windows [MFC], drawing directly into
- client areas, and device context
- device contexts [MFC], CDC class [MFC]
- user interface [MFC], device contexts
- device-independent drawing
- GetDC method and CClientDC class [MFC]
- CClientDC class [MFC], and ReleaseDC method [MFC]
- ReleaseDC method [MFC]
- device contexts [MFC], about device contexts
- drawing [MFC], directly into windows
- painting and device context
ms.assetid: d0cd51f1-f778-4c7e-bf50-d738d10433c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27203b5b93d69c29df29e64f872efb8e5f1828e1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437646"
---
# <a name="device-contexts"></a>デバイス コンテキスト

デバイス コンテキストは、ディスプレイやプリンターなどのデバイスの描画属性に関する情報を含む Windows データ構造です。 すべての描画呼び出しは、線、図形、およびテキストを描画するための Windows Api をカプセル化されているデバイス コンテキスト オブジェクトを通じて行われます。 デバイス コンテキストでは、Windows でのデバイスに依存しない描画を使用できます。 デバイス コンテキストは、画面、プリンター、または、メタファイルに描画するために使用できます。

[CPaintDC](../mfc/reference/cpaintdc-class.md)オブジェクトが呼び出す、Windows の一般的な表現形式をカプセル化、`BeginPaint`関数は、デバイス コンテキストでの描画後の呼び出し、`EndPaint`関数。 `CPaintDC`コンス トラクター呼び出し`BeginPaint`、およびデストラクター呼び出し`EndPaint`します。 簡略化されたプロセスは、作成する、 [CDC](../mfc/reference/cdc-class.md)オブジェクト、描画、および破棄し、`CDC`オブジェクト。 Framework では、このプロセスでもの多くが自動化されます。 具体的には、`OnDraw`関数に渡されます、`CPaintDC`既に準備 (を使用して`OnPrepareDC`)、単にそこに描画するとします。 フレームワークによって破棄されへの呼び出しから戻ったとき、基になるデバイス コンテキストが Windows にリリースされた、`OnDraw`関数。

[CClientDC](../mfc/reference/cclientdc-class.md)オブジェクトは、ウィンドウのクライアント領域だけを表すデバイス コンテキストの操作をカプセル化します。 `CClientDC`コンス トラクターの呼び出し、`GetDC`関数、およびデストラクターの呼び出し、`ReleaseDC`関数。 [CWindowDC](../mfc/reference/cwindowdc-class.md)オブジェクトを含む、フレーム ウィンドウ全体を表すデバイス コンテキストをカプセル化します。

[CMetaFileDC](../mfc/reference/cmetafiledc-class.md)オブジェクトが Windows メタファイルに描画をカプセル化します。 異なり、`CPaintDC`に渡される`OnDraw`、ここで呼び出す必要がある[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)自分でします。

## <a name="mouse-drawing"></a>マウスによる描画

フレームワーク プログラムでのほとんどの描画- とほとんどのデバイス コンテキスト作業したがって-ビューのでは`OnDraw`メンバー関数。 ただし、他の目的で、デバイス コンテキスト オブジェクトを使用できます。 たとえば、ビューでマウスの動きの追跡のフィードバックを提供する必要がありますを待つことがなく、ビューに直接描画するために`OnDraw`呼び出されます。

このような場合は、使用することができます、 [CClientDC](../mfc/reference/cclientdc-class.md)ビューに直接描画するためにデバイス コンテキスト オブジェクト。

### <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [デバイス コンテキスト (定義)](https://msdn.microsoft.com/library/windows/desktop/dd183553)

- [ビューの描画](../mfc/drawing-in-a-view.md)

- [ビューを経由したユーザー入力の解釈](../mfc/interpreting-user-input-through-a-view.md)

- [直線と曲線](https://msdn.microsoft.com/library/windows/desktop/dd145028)

- [塗りつぶされた図形](https://msdn.microsoft.com/library/windows/desktop/dd162714)

- [フォントとテキスト](/windows/desktop/gdi/fonts-and-text)

- [色](https://msdn.microsoft.com/library/windows/desktop/dd183450)

- [座標空間と変換](https://msdn.microsoft.com/library/windows/desktop/dd183475)

## <a name="see-also"></a>関連項目

[Window オブジェクト](../mfc/window-objects.md)

