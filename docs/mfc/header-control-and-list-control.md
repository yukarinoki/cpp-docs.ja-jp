---
title: ヘッダー コントロールおよびリスト コントロール
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], with CHeaderCtrl
- CListCtrl class [MFC], header controls
- CHeaderCtrl class [MFC], with CListCtrl
- controls [MFC], header
- header controls [MFC]
- header controls [MFC], list controls used with
ms.assetid: b20194b1-1a6b-4e2f-b890-1b3cca6650bc
ms.openlocfilehash: 5e1c5f338ea8626969d426af3ae2b51e8bdc62fa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50526817"
---
# <a name="header-control-and-list-control"></a>ヘッダー コントロールおよびリスト コントロール

ほとんどの場合に埋め込まれているヘッダー コントロールを使用して、 [CListCtrl](../mfc/reference/clistctrl-class.md)または[CListView](../mfc/reference/clistview-class.md)オブジェクト。 ただし、別のヘッダー コントロール オブジェクトが行または列内に配置されたデータの操作などの望ましい場合があります、 [CView](../mfc/reference/cview-class.md)の派生オブジェクト。 このような場合は、埋め込みヘッダー コントロールの既定の動作と外観をより細かく制御する必要があります。

ヘッダー コントロールを標準を提供する多くの場合、既定の動作を使用する場合は、 [CListCtrl](../mfc/reference/clistctrl-class.md)または[CListView](../mfc/reference/clistview-class.md)代わりにします。 使用`CListCtrl`リスト ビュー コモン コントロールに埋め込まれている既定のヘッダー コントロールの機能を使用する場合。 使用[CListView](../mfc/reference/clistview-class.md)ビュー オブジェクトに埋め込まれている既定のヘッダー コントロールの機能を使用する場合。

> [!NOTE]
>  これらのコントロールを使用して、リスト ビュー コントロールが作成された場合のみ、組み込みのヘッダー コントロールを含む、 **LVS_REPORT**スタイル。

ほとんどの場合、埋め込みヘッダー コントロールの外観を含むリスト ビュー コントロールのスタイルを変更することで変更できます。 さらに、親のリスト ビュー コントロールのメンバー関数を使用して、ヘッダー コントロールに関する情報を取得できます。 ただし、完全に制御、および属性と埋め込みヘッダー コントロールのスタイルへのアクセスは、ヘッダー コントロールのオブジェクトへのポインターを取得することをお勧めします。

埋め込みのヘッダー コントロール オブジェクトは、いずれかからアクセスできる`CListCtrl`または`CListView`それぞれのクラスを呼び出して`GetHeaderCtrl`メンバー関数。 次のコードでは、これを示しています。

[!code-cpp[NVC_MFCControlLadenDialog#14](../mfc/codesnippet/cpp/header-control-and-list-control_1.cpp)]

## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [ヘッダー コントロールでリストのイメージを使用して](../mfc/using-image-lists-with-header-controls.md)

## <a name="see-also"></a>関連項目

[CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

