---
title: イメージ リストの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
ms.openlocfilehash: 0d9566739a15e5d216eb052a7265313850515648
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366572"
---
# <a name="using-an-image-list"></a>イメージ リストの使い方

イメージ リストの一般的な使用方法は、次のパターンに従います。

- [CImageList](../mfc/reference/cimagelist-class.md)オブジェクトを構築し、その[Create](../mfc/reference/cimagelist-class.md#create)関数のオーバーロードのいずれかを呼び出して、イメージ リストを作成`CImageList`し、オブジェクトにアタッチします。

- イメージ リストの作成時にイメージを追加しなかった場合は[、Add](../mfc/reference/cimagelist-class.md#add)または[Read](../mfc/reference/cimagelist-class.md#read)メンバー関数を呼び出してイメージ リストにイメージを追加します。

- そのコントロールの適切なメンバー関数を呼び出してイメージ リストをコントロールに関連付けるか、イメージ リストの Draw メンバー関数を使用してイメージ リストからイメージを自分で[描画](../mfc/reference/cimagelist-class.md#draw)します。

- イメージ リストの組み込みのドラッグサポートを使用して、ユーザーがイメージをドラッグできるようにする可能性があります。

> [!NOTE]
> **new**演算子を使用してイメージ リストを作成した場合は、`CImageList`オブジェクトを破棄する必要があります。

## <a name="see-also"></a>関連項目

[CImageList の使い方](../mfc/using-cimagelist.md)<br/>
[コントロール](../mfc/controls-mfc.md)
