---
title: イメージ リストの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
ms.openlocfilehash: 710831ea8ef6b52292ba3e8eb84a69575c6c7508
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226829"
---
# <a name="using-an-image-list"></a>イメージ リストの使い方

イメージリストの一般的な使用方法は、次のパターンに従います。

- [CImageList](../mfc/reference/cimagelist-class.md)オブジェクトを構築し、その[create](../mfc/reference/cimagelist-class.md#create)関数のいずれかのオーバーロードを呼び出して、イメージリストを作成し、それをオブジェクトにアタッチし `CImageList` ます。

- イメージリストの作成時にイメージを追加していない場合は、 [add](../mfc/reference/cimagelist-class.md#add)または[Read](../mfc/reference/cimagelist-class.md#read)メンバー関数を呼び出すことによってイメージの一覧にイメージを追加します。

- イメージリストをコントロールに関連付けるには、そのコントロールの適切なメンバー関数を呼び出すか、イメージリストの[描画](../mfc/reference/cimagelist-class.md#draw)メンバー関数を使用してイメージリストからイメージを描画します。

- イメージリストのドラッグに対する組み込みサポートを使用して、ユーザーがイメージをドラッグできるようにします。

> [!NOTE]
> イメージリストが演算子で作成されている場合は、 **`new`** 操作が完了したら、そのオブジェクトを破棄する必要があり `CImageList` ます。

## <a name="see-also"></a>関連項目

[CImageList の使い方](../mfc/using-cimagelist.md)<br/>
[コントロール](../mfc/controls-mfc.md)
