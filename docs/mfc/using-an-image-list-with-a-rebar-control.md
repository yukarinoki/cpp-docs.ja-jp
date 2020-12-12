---
description: '詳細情報: Rebar コントロールでのイメージリストの使用'
title: Rebar コントロールでのイメージ リストの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], rebar controls
- rebar controls [MFC], image lists
ms.assetid: 1a5836ac-019a-46aa-8741-b35c3376b839
ms.openlocfilehash: ae4aa0259cbe850dbab8ef4bc04277014b39e357
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271799"
---
# <a name="using-an-image-list-with-a-rebar-control"></a>Rebar コントロールでのイメージ リストの使い方

各 rebar バンドには、関連付けられているイメージリストのイメージを含めることができます。 次の手順では、rebar バンドに画像を表示するために必要な手順について詳しく説明します。

### <a name="to-display-images-in-a-rebar-band"></a>Rebar バンドに画像を表示するには

1. 既存のイメージリストへのポインターを渡して [SetImageList](../mfc/reference/crebarctrl-class.md#setimagelist)を呼び出すことによって、rebar コントロールオブジェクトにイメージリストをアタッチします。

1. **REBARBANDINFO** 構造体を変更して、イメージを rebar バンドに割り当てます。

   - [ *Fmask* ] メンバーをに設定し `RBBIM_IMAGE` 、ビットごとの or 演算子を使用して必要に応じて追加のフラグを指定します。

   - 表示するイメージのイメージリストインデックスに *iImage* メンバーを設定します。

1. 必要な情報を使用して、含まれている子ウィンドウのサイズ、テキスト、ハンドルなどの残りのデータメンバーを初期化します。

1. 新しいバンド (イメージを含む) を [Crebarctrl:: InsertBand](../mfc/reference/crebarctrl-class.md#insertband)の呼び出しと共に挿入し、 **REBARBANDINFO** 構造体を渡します。

次の例では、2つのイメージを持つ既存のイメージリストオブジェクトが rebar コントロールオブジェクト () にアタッチされていることを前提としてい `m_wndReBar` ます。 最初のイメージを含む新しい rebar バンド (で定義 `rbi` ) が、の呼び出しで追加され `InsertBand` ます。

[!code-cpp[NVC_MFCControlLadenDialog#28](../mfc/codesnippet/cpp/using-an-image-list-with-a-rebar-control_1.cpp)]

## <a name="see-also"></a>関連項目

[CReBarCtrl の使い方](../mfc/using-crebarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
