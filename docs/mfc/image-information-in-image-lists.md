---
title: イメージ リストのイメージ情報
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], image information in
- image lists [MFC], image information in
ms.assetid: 73c41543-fa91-405d-b15b-0feffa6a72c1
ms.openlocfilehash: c12198c769585763095d22b73d11f7af3c9d6fc0
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624495"
---
# <a name="image-information-in-image-lists"></a>イメージ リストのイメージ情報

[CImageList](reference/cimagelist-class.md)には、イメージリストから情報を取得する多くの関数が含まれています。 [GetImageInfo](reference/cimagelist-class.md#getimageinfo)メンバー関数は、イメージ `IMAGEINFO` ビットマップとマスクビットマップのハンドル、カラープレーンの数とピクセルあたりのビット数、およびイメージビットマップ内のイメージの外接する四角形を含む、1つのイメージに関する情報を構造体に格納します。 この情報を使用して、イメージのビットマップを直接操作できます。

[GetImageCount](reference/cimagelist-class.md#getimagecount)メンバー関数は、イメージリスト内のイメージの数を取得します。

[ExtractIcon](reference/cimagelist-class.md#extracticon)メンバー関数を使用すると、イメージリスト内のイメージとマスクに基づいてアイコンを作成できます。 関数は、新しいアイコンのハンドルを返します。

## <a name="see-also"></a>関連項目

[CImageList の使い方](using-cimagelist.md)<br/>
[制限](controls-mfc.md)
