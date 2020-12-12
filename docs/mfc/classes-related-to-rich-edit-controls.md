---
description: 詳細については、「リッチエディットコントロールに関連するクラス」を参照してください。
title: リッチ エディット コントロールに関連するクラス
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC], and CRichEditItem
- CRichEditCtrl class [MFC], related classes
- CRichEditDoc class [MFC], Rich Edit controls
- rich edit controls [MFC], classes related to
- classes [MFC], related to rich edit controls
- rich edit controls [MFC], and CRichEditView
- CRichEditCtrlItem class and CRichEditCtrl
- rich edit controls [MFC], and CRichEditDoc
- CRichEditView class [MFC], and CRichEditCtrl
ms.assetid: 4b31c2cc-6ea1-4146-b7c5-b0b5b419f14d
ms.openlocfilehash: b44c5a874c7f48c132f31483bf5ee73eafbe4da5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176679"
---
# <a name="classes-related-to-rich-edit-controls"></a>リッチ エディット コントロールに関連するクラス

[CRichEditView](reference/cricheditview-class.md)、 [CRichEditDoc](reference/cricheditdoc-class.md)、および[CRichEditCntrItem](reference/cricheditcntritem-class.md)クラスは、MFC のドキュメント/ビューアーキテクチャのコンテキスト内で、リッチエディットコントロール ([CRichEditCtrl](reference/cricheditctrl-class.md)) の機能を提供します。 `CRichEditView` テキストのテキストと書式設定の特性を維持します。 `CRichEditDoc` ビュー内の OLE クライアントアイテムの一覧を保持します。 `CRichEditCntrItem` OLE クライアントアイテムへのコンテナー側のアクセスを提供します。 の内容を変更するには `CRichEditView` 、 [CRichEditView:: GetRichEditCtrl](reference/cricheditview-class.md#getricheditctrl) を使用して、基になるリッチエディットコントロールにアクセスします。

## <a name="see-also"></a>関連項目

[CRichEditCtrl の使い方](using-cricheditctrl.md)<br/>
[コントロール](controls-mfc.md)
