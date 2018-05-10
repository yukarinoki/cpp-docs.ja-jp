---
title: イメージ リストのイメージのドラッグ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CImageList class [MFC], dragging images from
- dragging images from image lists [MFC]
- image lists [MFC], dragging images from
- images [MFC], dragging from image lists
ms.assetid: af691db8-e4f0-4046-b7b9-9acc68d3713d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d54984cdc1dc7897fb4f5d1d9680c6a2b95a787d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="dragging-images-from-an-image-list"></a>イメージ リストのイメージのドラッグ
[CImageList](../mfc/reference/cimagelist-class.md)画面にイメージをドラッグするための関数が含まれています。 ドラッグ関数は、色、およびカーソルの点滅なしスムーズに、イメージを移動します。 マスクとマスク解除の両方のイメージをドラッグすることができます。  
  
 [BeginDrag](../mfc/reference/cimagelist-class.md#begindrag)メンバー関数は、ドラッグ操作を開始します。 パラメーターには、ドラッグするイメージとイメージ内のホット スポットの場所のインデックスが含まれます。 ホット スポットとは、イメージの正確な画面位置として認識するドラッグ関数は、単一のピクセルです。 通常、アプリケーションは、マウス カーソルのホット スポットに一致するように、ホット スポットを設定します。 [DragMove](../mfc/reference/cimagelist-class.md#dragmove)メンバー関数は、新しい場所にイメージを移動します。  
  
 [DragEnter](../mfc/reference/cimagelist-class.md#dragenter)メンバー関数は、ウィンドウ内でドラッグ イメージの初期位置を設定および位置にあるイメージを描画します。 パラメーターには、イメージと、ウィンドウ内の最初の位置の座標を指定する点を描画するためのウィンドウへのポインターが含まれます。 座標は、クライアント領域ではなく、ウィンドウの左上隅を基準としました。 すべてのイメージ ドラッグ関数をパラメーターとしての座標を受け取る同様です。 つまり、座標を指定するときに、境界線、タイトル バー、メニュー バーなどのウィンドウの要素の幅を補正する必要があります。 指定した場合、 **NULL**ウィンドウ ハンドルを呼び出すときに`DragEnter`ドラッグ関数は、デスクトップのウィンドウに関連付けられているデバイス コンテキストでのイメージの描画、および画面の左上隅に対する相対座標は、します。  
  
 `DragEnter` ドラッグ操作中に指定されたウィンドウを他のすべての更新プログラムをロックします。 ドラッグ アンド ドロップ操作のターゲットを強調表示などのドラッグ操作中に描画を実行する必要がある場合を一時的に非表示にするドラッグされているイメージを使用して、[いくつか](../mfc/reference/cimagelist-class.md#dragleave)メンバー関数。 使用することも、 [DragShowNoLock](../mfc/reference/cimagelist-class.md#dragshownolock)メンバー関数。  
  
 呼び出す[EndDrag](../mfc/reference/cimagelist-class.md#enddrag)終了すると、イメージをドラッグします。  
  
 [SetDragCursorImage](../mfc/reference/cimagelist-class.md#setdragcursorimage)メンバー関数は、現在のドラッグ イメージと指定したイメージ (通常はマウス カーソル イメージ) を組み合わせることによって新しいドラッグ イメージを作成します。 ドラッグ関数は、ドラッグ操作中に、新しいイメージを使用するため、Windows を使用する必要があります[ShowCursor](http://msdn.microsoft.com/library/windows/desktop/ms648396)関数を呼び出した後、実際のマウス カーソルを非表示に`SetDragCursorImage`です。 それ以外の場合、システム、ドラッグ操作の期間に対して 2 つのマウス カーソルを表示されます。  
  
 アプリケーションを呼び出すと`BeginDrag`システムが、一時的な内部のイメージ リストを作成し、指定されたコピーは、内部リストに画像をドラッグします。 使用して一時ドラッグ イメージ リストへのポインターを取得することができます、 [GetDragImage](../mfc/reference/cimagelist-class.md#getdragimage)メンバー関数。 関数は、ドラッグの現在の位置とドラッグの位置に対してドラッグ イメージのオフセットを取得します。  
  
## <a name="see-also"></a>関連項目  
 [CImageList の使い方](../mfc/using-cimagelist.md)   
 [コントロール](../mfc/controls-mfc.md)

