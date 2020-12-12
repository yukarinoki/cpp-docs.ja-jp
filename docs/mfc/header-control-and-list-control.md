---
description: 詳細については、「ヘッダーコントロールとリストコントロール」を参照してください。
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
ms.openlocfilehash: d2301f82a76516a008de0a72e1c9288580b8f545
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325920"
---
# <a name="header-control-and-list-control"></a>ヘッダー コントロールおよびリスト コントロール

ほとんどの場合は、 [CListCtrl](reference/clistctrl-class.md) オブジェクトまたは [CListView](reference/clistview-class.md) オブジェクトに埋め込まれているヘッダーコントロールを使用します。 ただし、 [CView](reference/cview-class.md)によって派生したオブジェクトでデータを操作したり、列または行に並べたりするなど、別のヘッダーコントロールオブジェクトが望ましい場合もあります。 このような場合は、埋め込みヘッダーコントロールの外観と既定の動作をより詳細に制御する必要があります。

一般的な既定の動作を提供するヘッダーコントロールが必要な場合は、代わりに [CListCtrl](reference/clistctrl-class.md) または [CListView](reference/clistview-class.md) を使用することをお勧めします。 `CListCtrl`リストビューのコモンコントロールに埋め込まれている既定のヘッダーコントロールの機能が必要な場合は、を使用します。 ビューオブジェクトに埋め込まれた既定のヘッダーコントロールの機能が必要な場合は、 [CListView](reference/clistview-class.md) を使用します。

> [!NOTE]
> リストビューコントロールが **LVS_REPORT** スタイルを使用して作成されている場合、これらのコントロールには組み込みのヘッダーコントロールのみが含まれます。

ほとんどの場合、埋め込みヘッダーコントロールの外観は、含まれているリストビューコントロールのスタイルを変更することによって変更できます。 また、ヘッダーコントロールに関する情報は、親リストビューコントロールのメンバー関数を通じて取得することもできます。 ただし、埋め込みヘッダーコントロールの属性とスタイルを完全に制御し、アクセスできるようにするには、ヘッダーコントロールオブジェクトへのポインターを取得することをお勧めします。

埋め込みヘッダーコントロールオブジェクトに `CListCtrl` は、またはの `CListView` 各クラスのメンバー関数への呼び出しを使用してアクセスでき `GetHeaderCtrl` ます。 その例を次のコードに示します。

[!code-cpp[NVC_MFCControlLadenDialog#14](codesnippet/cpp/header-control-and-list-control_1.cpp)]

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ヘッダー コントロールでのイメージ リストの使用](using-image-lists-with-header-controls.md)

## <a name="see-also"></a>関連項目

[CHeaderCtrl の使い方](using-cheaderctrl.md)<br/>
[コントロール](controls-mfc.md)
