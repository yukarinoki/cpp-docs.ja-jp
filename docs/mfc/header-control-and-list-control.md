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
ms.openlocfilehash: 53dd6f1a7878d82a7f7ac48dd7082d791323941b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370473"
---
# <a name="header-control-and-list-control"></a>ヘッダー コントロールおよびリスト コントロール

ほとんどの場合[、CListCtrl](../mfc/reference/clistctrl-class.md)または[CListView](../mfc/reference/clistview-class.md)オブジェクトに埋め込まれているヘッダー コントロールを使用します。 ただし[、CView](../mfc/reference/cview-class.md)派生オブジェクト内の列または行に配置されたデータの操作など、個別のヘッダー制御オブジェクトが望ましい場合があります。 このような場合は、埋め込みヘッダー コントロールの外観と既定の動作をより大きく制御する必要があります。

ヘッダー コントロールで標準の既定の動作を提供する一般的な場合は、代わりに[CListCtrl](../mfc/reference/clistctrl-class.md)または[CListView](../mfc/reference/clistview-class.md)を使用する必要があります。 既定`CListCtrl`のヘッダー コントロールの機能が、リスト ビューコモン コントロールに埋め込まれる場合に使用します。 既定のヘッダー コントロールの機能がビュー オブジェクトに埋め込まれる場合は[、CListView](../mfc/reference/clistview-class.md)を使用します。

> [!NOTE]
> これらのコントロールには、リスト ビュー コントロールが**LVS_REPORT**スタイルを使用して作成される場合にのみ、組み込みのヘッダー コントロールが含まれます。

ほとんどの場合、埋め込みヘッダー コントロールの外観は、含まれているリスト ビュー コントロールのスタイルを変更することで変更できます。 さらに、ヘッダー コントロールに関する情報は、親リスト ビュー コントロールのメンバー関数を通じて取得できます。 ただし、埋め込みヘッダー コントロールの属性とスタイルへの完全な制御とアクセスの場合は、ヘッダー コントロール オブジェクトへのポインターを取得することをお勧めします。

埋め込みヘッダー コントロール オブジェクトは`CListCtrl`、`CListView`それぞれのクラスの`GetHeaderCtrl`メンバー関数を呼び出して、または呼び出しを使用してアクセスできます。 次のコードはこれを示しています。

[!code-cpp[NVC_MFCControlLadenDialog#14](../mfc/codesnippet/cpp/header-control-and-list-control_1.cpp)]

## <a name="what-do-you-want-to-know-more-about"></a>何についてもっと知りたいのですか?

- [ヘッダー コントロールでのイメージ リストの使用](../mfc/using-image-lists-with-header-controls.md)

## <a name="see-also"></a>関連項目

[CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
