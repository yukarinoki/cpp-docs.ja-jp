---
title: ラバー バンド処理とトラッカー
ms.date: 11/04/2016
helpviewer_keywords:
- trackers [MFC]
- CRectTracker class [MFC], implementing trackers
- OLE objects [MFC], selecting
- rubber banding [MFC]
- WM_LBUTTONDOWN [MFC]
ms.assetid: 0d0fa64c-6418-4baf-ab7f-2d16ca039230
ms.openlocfilehash: a6a9c9848e21129d4e6a8ce300e8750b4a0c6126
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281045"
---
# <a name="rubber-banding-and-trackers"></a>ラバー バンド処理とトラッカー

トラッカーで提供されるもう 1 つの機能は、「ラバー バンド」の選択範囲を選択できるアイテムの周囲のサイズ変更の四角形をドラッグして、複数の OLE 項目を選択することが可能です。 マウスの左ボタンを離したときに、ユーザーが選択したリージョン内の項目が選択され、ユーザーが操作することができます。 たとえば、ユーザーは、別のコンテナー アプリケーションに選択範囲をドラッグする可能性があります。

この機能を実装するには、アプリケーションの WM_LBUTTONDOWN ハンドラー関数でいくつかのコードを追加する必要があります。

次のコード サンプルでは、ラバー バンド選択とその他の機能を実装します。

[!code-cpp[NVC_MFCOClient#6](../mfc/codesnippet/cpp/rubber-banding-and-trackers_1.cpp)]

ラバー バンド処理中にトラッカーの元に戻すことの向きを許可する場合を呼び出す必要があります[CRectTracker::TrackRubberBand](../mfc/reference/crecttracker-class.md#trackrubberband) 3 番目のパラメーターを設定して**TRUE**します。 向きを元に戻すことを許可することが原因場合がありますに注意してください。[裏返し](../mfc/reference/crecttracker-class.md#m_rect)反転になります。 これへの呼び出しによって修正できる[CRect::NormalizeRect](../atl-mfc-shared/reference/crect-class.md#normalizerect)します。

詳細については、[コンテナー クライアント アイテム](../mfc/containers-client-items.md)と[をカスタマイズするドラッグ アンド ドロップ](../mfc/drag-and-drop-customizing.md)を参照してください。

## <a name="see-also"></a>関連項目

[トラッカー:OLE アプリケーションでのトラッカーの実装](../mfc/trackers-implementing-trackers-in-your-ole-application.md)<br/>
[CRectTracker クラス](../mfc/reference/crecttracker-class.md)
