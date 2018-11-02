---
title: ビューのスクロールと拡大/縮小
ms.date: 11/04/2016
helpviewer_keywords:
- message handlers [MFC]
- scaling views [MFC]
- message handling [MFC], scroll bars in view class [MFC]
- scroll bars [MFC], messages
- scrolling views [MFC]
ms.assetid: f98a3421-c336-407e-97ee-dbb2ffd76fbd
ms.openlocfilehash: acef79a89da88773da564fc965a607e2fd5b53f7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626103"
---
# <a name="scrolling-and-scaling-views"></a>ビューのスクロールと拡大/縮小

MFC では、それらを表示するフレーム ウィンドウのサイズが自動的に拡大縮小されるビューまでスクロールし、ビューをサポートしています。 クラス`CScrollView`ビューの両方の種類をサポートしています。

スクロールとスケーリングの詳細については、クラスを参照してください。 [CScrollView](../mfc/reference/cscrollview-class.md)で、 *MFC リファレンス*します。 スクロールの例では、次を参照してください。、 [Scribble サンプル](../visual-cpp-samples.md)します。

## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- ビューのスクロール

- ビューのスケーリング

- [ビューの座標](/windows/desktop/gdi/window-coordinate-system)

##  <a name="_core_scrolling_a_view"></a> ビューのスクロール

頻繁に、ドキュメントのサイズは、そのビューには表示サイズを超えています。 これは、ドキュメントのデータが増加したり、ユーザーは、ビューのフレーム ウィンドウを縮小するために発生する可能性があります。 このような場合は、スクロール ビューをサポートする必要があります。

任意のビューにスクロール バーのメッセージを処理できるその`OnHScroll`と`OnVScroll`メンバー関数。 自分ですべての作業を行って、これらの関数のいずれかの実装スクロール バー メッセージの処理ができるかを使用することができます、`CScrollView`スクロールを処理するクラス。

`CScrollView` では次の処理が行われます。

- ウィンドウと、ビューポートのサイズとマップ モードを管理します。

- スクロール バーのメッセージに対応して自動的にスクロールします

(スクロール バーの矢印で、ユーザーがクリックする) ときの「ページ」(スクロール バーの軸で、ユーザーがクリックする) 場合、「行」のスクロール量指定できます。 これらの値に合わせて、ビューの性質を計画します。 たとえば、1 ピクセルずつグラフィック表示がテキスト ドキュメントで、行の高さに基づく増分をスクロールする可能性があります。

##  <a name="_core_scaling_a_view"></a> ビューのスケーリング

使用することができます、ビュー、フレーム ウィンドウのサイズを自動的に調整する場合は、`CScrollView`スクロールする代わりにスケーリングします。 論理ビューを拡大またはウィンドウのクライアント領域をちょうど収まるように縮小するとします。 スケール ビューのスクロール バーはありません。

## <a name="see-also"></a>関連項目

[ビューの使い方](../mfc/using-views.md)

