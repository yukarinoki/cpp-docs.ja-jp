---
title: ラバー バンド処理とトラッカー |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- trackers [MFC]
- CRectTracker class [MFC], implementing trackers
- OLE objects [MFC], selecting
- rubber banding [MFC]
- WM_LBUTTONDOWN [MFC]
ms.assetid: 0d0fa64c-6418-4baf-ab7f-2d16ca039230
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed6e649309acf86e24c52bf8b50a859d0ac066ad
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428201"
---
# <a name="rubber-banding-and-trackers"></a>ラバー バンド処理とトラッカー

トラッカーで提供されるもう 1 つの機能は、「ラバー バンド」の選択範囲を選択できるアイテムの周囲のサイズ変更の四角形をドラッグして、複数の OLE 項目を選択することが可能です。 マウスの左ボタンを離したときに、ユーザーが選択したリージョン内の項目が選択され、ユーザーが操作することができます。 たとえば、ユーザーは、別のコンテナー アプリケーションに選択範囲をドラッグする可能性があります。

この機能を実装するには、アプリケーションの WM_LBUTTONDOWN ハンドラー関数でいくつかのコードを追加する必要があります。

次のコード サンプルでは、ラバー バンド選択とその他の機能を実装します。

[!code-cpp[NVC_MFCOClient#6](../mfc/codesnippet/cpp/rubber-banding-and-trackers_1.cpp)]

ラバー バンド処理中にトラッカーの元に戻すことの向きを許可する場合を呼び出す必要があります[CRectTracker::TrackRubberBand](../mfc/reference/crecttracker-class.md#trackrubberband) 3 番目のパラメーターを設定して**TRUE**します。 向きを元に戻すことを許可することが原因場合がありますに注意してください。[裏返し](../mfc/reference/crecttracker-class.md#m_rect)反転になります。 これへの呼び出しによって修正できる[CRect::NormalizeRect](../atl-mfc-shared/reference/crect-class.md#normalizerect)します。

詳細については、次を参照してください。[コンテナー クライアント アイテム](../mfc/containers-client-items.md)と[をカスタマイズするドラッグ アンド ドロップ](../mfc/drag-and-drop-customizing.md)します。

## <a name="see-also"></a>関連項目

[トラッカー: OLE アプリケーションでのトラッカーの実装](../mfc/trackers-implementing-trackers-in-your-ole-application.md)<br/>
[CRectTracker クラス](../mfc/reference/crecttracker-class.md)
