---
description: '詳細情報: Rebar コントロールとバンド'
title: Rebar コントロールとバンド
ms.date: 11/04/2016
helpviewer_keywords:
- rebar controls [MFC], working with bands in
- bands, in rebar controls
ms.assetid: b647e7a5-9ea7-48b1-8e5f-096d104748f0
ms.openlocfilehash: 27ada3633a560ad8b5852b05bdd6330a0936fb99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248568"
---
# <a name="rebar-controls-and-bands"></a>Rebar コントロールとバンド

Rebar コントロールの主な目的は、子ウィンドウ、コモンダイアログコントロール、メニュー、ツールバーなどのコンテナーとして機能することです。 この含有は、"バンド" の概念によってサポートされています。 各 rebar バンドには、グリップバー、ビットマップ、テキストラベル、および子ウィンドウの任意の組み合わせを含めることができます。

クラス `CReBarCtrl` には、特定の rebar バンドに関する情報を取得して操作するために使用できる多数のメンバー関数があります。

- [Getバンド数](../mfc/reference/crebarctrl-class.md#getbandcount) Rebar コントロールの現在のバンド数を取得します。

- [Getバンド情報](../mfc/reference/crebarctrl-class.md#getbandinfo) 指定したバンドの情報を使用して、 **REBARBANDINFO** 構造体を初期化します。 対応する [Setバンド情報](../mfc/reference/crebarctrl-class.md#setbandinfo) メンバー関数があります。

- [Getrect](../mfc/reference/crebarctrl-class.md#getrect) 指定したバンドの外接する四角形を取得します。

- [Getrowcount](../mfc/reference/crebarctrl-class.md#getrowcount) Rebar コントロールのバンド行の数を取得します。

- [Idtoindex](../mfc/reference/crebarctrl-class.md#idtoindex) 指定したバンドのインデックスを取得します。

- [Getバンド境界線](../mfc/reference/crebarctrl-class.md#getbandborders) バンドの境界線を取得します。

操作に加えて、特定の rebar バンドでの操作を可能にするいくつかのメンバー関数が用意されています。

[Insertband](../mfc/reference/crebarctrl-class.md#insertband) と [deleteband](../mfc/reference/crebarctrl-class.md#deleteband) rebar バンドを追加および削除します。 [MinimizeBand](../mfc/reference/crebarctrl-class.md#minimizeband) と [最大化](../mfc/reference/crebarctrl-class.md#maximizeband) が、特定の rebar バンドの現在のサイズに影響します。 [Moveband](../mfc/reference/crebarctrl-class.md#moveband) は、特定の rebar バンドのインデックスを変更します。 [Showband](../mfc/reference/crebarctrl-class.md#showband) は、ユーザーからの rebar バンドを表示または非表示にします。

次の例では、既存の rebar コントロール (*m_wndReBar*) にツールバーバンド (*m_wndToolBar*) を追加する方法を示します。 このバンドは、 `rbi` 構造体を初期化してからメンバー関数を呼び出すことによって記述され `InsertBand` ます。

[!code-cpp[NVC_MFCControlLadenDialog#27](../mfc/codesnippet/cpp/rebar-controls-and-bands_1.cpp)]

## <a name="see-also"></a>関連項目

[CReBarCtrl の使い方](../mfc/using-crebarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
