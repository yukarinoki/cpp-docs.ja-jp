---
description: '詳細情報: デバイスコンテキスト'
title: デバイス コンテキスト
ms.date: 11/04/2016
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
ms.openlocfilehash: 725387ad3aa3f099c72c82aecd14d89bad7168bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261594"
---
# <a name="device-contexts"></a>デバイス コンテキスト

デバイスコンテキストは、ディスプレイやプリンターなどのデバイスの描画属性に関する情報を含む Windows データ構造です。 すべての描画呼び出しはデバイスコンテキストオブジェクトを使用して行われます。これにより、線、図形、テキストを描画するための Windows Api がカプセル化されます。 デバイスコンテキストでは、Windows でデバイスに依存しない描画を実行できます。 デバイスコンテキストは、画面、プリンター、またはメタファイルに描画するために使用できます。

[CPaintDC](reference/cpaintdc-class.md) オブジェクトは、Windows の共通表現をカプセル化し、関数を呼び出した `BeginPaint` 後、デバイスコンテキストで描画した後、関数を呼び出し `EndPaint` ます。 コンストラクターはを `CPaintDC` 呼び出し `BeginPaint` 、デストラクターはを呼び出し `EndPaint` ます。 簡略化されたプロセスは、 [CDC](reference/cdc-class.md) オブジェクトを作成して描画し、オブジェクトを破棄することです `CDC` 。 フレームワークでは、このプロセスの多くが自動化されています。 特に、 `OnDraw` 関数には既に準備された (経由で) が渡され、 `CPaintDC` `OnPrepareDC` それに単に描画するだけです。 これはフレームワークによって破棄され、基になるデバイスコンテキストは、関数の呼び出しから戻った時点で Windows に解放され `OnDraw` ます。

[Cclientdc](reference/cclientdc-class.md) オブジェクトは、ウィンドウのクライアント領域のみを表すデバイスコンテキストの操作をカプセル化します。 `CClientDC`コンストラクターは関数を呼び出し、 `GetDC` デストラクターは関数を呼び出し `ReleaseDC` ます。 [CWindowDC](reference/cwindowdc-class.md) オブジェクトは、フレームを含む、ウィンドウ全体を表すデバイスコンテキストをカプセル化します。

[CMetaFileDC](reference/cmetafiledc-class.md) オブジェクトは、描画を Windows メタファイルにカプセル化します。 に渡されるとは対照的に `CPaintDC` `OnDraw` 、この場合は自分で [OnPrepareDC](reference/cview-class.md#onpreparedc) を呼び出す必要があります。

## <a name="mouse-drawing"></a>マウスの描画

フレームワークプログラムにおけるほとんどの描画 (つまり、ほとんどのデバイスコンテキストの作業) は、ビューのメンバー関数で実行され `OnDraw` ます。 ただし、他の目的でデバイスコンテキストオブジェクトを使用することもできます。 たとえば、ビューでのマウスの動きに関するフィードバックを追跡するには、が呼び出されるのを待たずに、ビューに直接描画する必要があり `OnDraw` ます。

このような場合は、 [Cclientdc](reference/cclientdc-class.md) デバイスコンテキストオブジェクトを使用して、ビューに直接描画できます。

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [デバイスコンテキスト (定義)](/windows/win32/gdi/device-contexts)

- [描画 (ビューで)](drawing-in-a-view.md)

- [ビューを使用したユーザー入力の解釈](interpreting-user-input-through-a-view.md)

- [線と曲線](/windows/win32/gdi/lines-and-curves)

- [図形の塗りつぶし](/windows/win32/gdi/filled-shapes)

- [フォントとテキスト](/windows/win32/gdi/fonts-and-text)

- [色](/windows/win32/gdi/colors)

- [座標空間と変換](/windows/win32/gdi/coordinate-spaces-and-transformations)

## <a name="see-also"></a>関連項目

[ウィンドウオブジェクト](window-objects.md)
