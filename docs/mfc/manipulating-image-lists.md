---
description: 詳細については、「イメージリストの操作」を参照してください。
title: イメージ リストの操作
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], manipulating
- lists [MFC], image
- CImageList class [MFC], manipulating
ms.assetid: 043418f8-077e-4dce-b8bb-2b7b0d7b5156
ms.openlocfilehash: dc2b136e1aed5266ea7cc910cf10839f59dfcf00
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281133"
---
# <a name="manipulating-image-lists"></a>イメージ リストの操作

[Replace](reference/cimagelist-class.md#replace)メンバー関数は、イメージリスト ([CImageList](reference/cimagelist-class.md)) 内のイメージを新しいイメージに置き換えます。 この関数は、イメージリストオブジェクト内のイメージの数を動的に増やす必要がある場合にも役立ちます。 [SetImageCount](reference/cimagelist-class.md#setimagecount)関数は、イメージリストに格納されているイメージの数を動的に変更します。 イメージリストのサイズを大きくする場合は、 `Replace` を呼び出して、新しいイメージスロットにイメージを追加します。 イメージリストのサイズを小さくすると、新しいサイズを超えるイメージが解放されます。

[Remove](reference/cimagelist-class.md#remove) member 関数は、イメージリストからイメージを削除します。 [Copy](reference/cimagelist-class.md#copy)メンバー関数は、イメージリスト内のイメージをコピーまたは交換できます。 この関数を使用すると、ソースイメージをコピー先のインデックスにコピーするか、コピー元とコピー先のイメージを入れ替える必要があるかを指定できます。

2つのイメージリストをマージして新しいイメージリストを作成するには、 [create](reference/cimagelist-class.md#create) member 関数の適切なオーバーロードを使用します。 のこのオーバーロードは、 `Create` 既存のイメージリストの最初のイメージをマージし、結果のイメージを新しいイメージリストオブジェクトに格納します。 新しいイメージは、最初のイメージに対して透過的に2番目のイメージを描画することによって作成されます。 新しいイメージのマスクは、既存の2つのイメージのマスクのビットに対して論理 OR 演算を実行した結果です。

これは、すべてのイメージがマージされ、新しいイメージリストオブジェクトに追加されるまで繰り返されます。

[書き込み](reference/cimagelist-class.md#write)メンバー関数を呼び出してイメージ情報をアーカイブに書き込んでから、 [read](reference/cimagelist-class.md#read)メンバー関数を呼び出すことによって、その情報を読み取ることができます。

[Getsafehandle](reference/cimagelist-class.md#getsafehandle)、 [Attach](reference/cimagelist-class.md#attach)、 [Detach](reference/cimagelist-class.md#detach)の各メンバー関数を使用すると、オブジェクトにアタッチされているイメージリストのハンドルを操作できます。また、 `CImageList` [deleteimagelist](reference/cimagelist-class.md#deleteimagelist)メンバー関数は、オブジェクトを破棄せずにイメージリストを削除し `CImageList` ます。

## <a name="see-also"></a>関連項目

[CImageList の使い方](using-cimagelist.md)<br/>
[コントロール](controls-mfc.md)
