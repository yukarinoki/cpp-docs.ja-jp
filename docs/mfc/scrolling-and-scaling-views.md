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
ms.openlocfilehash: 366f0e2953e5190f80a2877804bff2fc7dbbd520
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372789"
---
# <a name="scrolling-and-scaling-views"></a>ビューのスクロールと拡大/縮小

MFC では、スクロールするビューと、表示するフレーム ウィンドウのサイズに合わせて自動的に拡大/縮小されるビューをサポートしています。 クラス`CScrollView`は両方の種類のビューをサポートします。

スクロールとスケーリングの詳細については *、MFC リファレンス*のクラス[CScrollView](../mfc/reference/cscrollview-class.md)を参照してください。 スクロールの例については[、Scribble サンプル](../overview/visual-cpp-samples.md)を参照してください。

## <a name="what-do-you-want-to-know-more-about"></a>何についてもっと知りたいのですか?

- ビューのスクロール

- ビューのスケーリング

- [座標を表示する](/windows/win32/gdi/window-coordinate-system)

## <a name="scrolling-a-view"></a><a name="_core_scrolling_a_view"></a>ビューのスクロール

多くの場合、ドキュメントのサイズは、ビューが表示できるサイズよりも大きくなります。 これは、ドキュメントのデータが増加したり、ユーザーがビューをフレームに入っているウィンドウを縮小したために発生することがあります。 このような場合、ビューはスクロールをサポートする必要があります。

どのビューも、そのおよびメンバー関数でスクロール`OnHScroll``OnVScroll`バー メッセージを処理できます。 スクロール バーメッセージ処理をこれらの関数で実装して、すべての作業を自分で行うか、または`CScrollView`スクロールを処理するためにクラスを使用できます。

`CScrollView` を実行すると、次の処理が行われます。

- ウィンドウとビューポートのサイズとマッピング モードを管理します。

- スクロール バーのメッセージに応答して自動的にスクロールします。

"ページ" (ユーザーがスクロール バーシャフトをクリックしたとき) と "行" (ユーザーがスクロール バーをクリックしたとき) のスクロール量を指定できます。 これらの値は、ビューの性質に合わせて計画します。 たとえば、グラフィックビューでは 1 ピクセルずつスクロールし、テキストドキュメントの行の高さに基づいてスクロールできます。

## <a name="scaling-a-view"></a><a name="_core_scaling_a_view"></a>ビューのスケーリング

ビューがフレーム ウィンドウのサイズに自動的に合うようにするには、スクロールではなく拡大縮小`CScrollView`に使用します。 論理ビューは、ウィンドウのクライアント領域に正確に合わせて拡大または縮小されます。 拡大縮小ビューにはスクロール バーがありません。

## <a name="see-also"></a>関連項目

[ビューの使用](../mfc/using-views.md)
