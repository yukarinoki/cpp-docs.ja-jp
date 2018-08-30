---
title: イメージ リストのイメージのドラッグ |Microsoft Docs
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
ms.openlocfilehash: 9679fe46712220cd38cfb43c57b2f3c81deafde4
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213680"
---
# <a name="dragging-images-from-an-image-list"></a>イメージ リストのイメージのドラッグ
[CImageList](../mfc/reference/cimagelist-class.md)画面にイメージをドラッグする機能が含まれます。 ドラッグ関数は、色、およびカーソルの点滅なし円滑にイメージを移動します。 マスクとマスク解除の両方のイメージをドラッグすることができます。  
  
 [BeginDrag](../mfc/reference/cimagelist-class.md#begindrag)メンバー関数は、ドラッグ操作を開始します。 パラメーターには、イメージをドラッグして、イメージ内のホット スポットの場所のインデックスが含まれます。 ホット スポットとは、ドラッグの関数のイメージの正確な画面位置として認識する 1 つのピクセルです。 通常、アプリケーションは、マウス カーソルのホット スポットに一致するように、ホット スポットを設定します。 [DragMove](../mfc/reference/cimagelist-class.md#dragmove)メンバー関数がイメージを新しい場所に移動します。  
  
 [DragEnter](../mfc/reference/cimagelist-class.md#dragenter)メンバー関数は、ウィンドウ内のドラッグ イメージの初期位置を設定し、位置にあるイメージを描画します。 パラメーターには、イメージと、ウィンドウ内の最初の位置の座標を指定する点を描画するためのウィンドウへのポインターが含まれます。 座標は、クライアント領域ではなく、ウィンドウの左上隅に対して相対的です。 すべての座標をパラメーターとして取るイメージ ドラッグ関数も同様です。 つまり、座標を指定するときに、境界線、タイトル バー、メニュー バーなどのウィンドウの要素の幅を補正する必要があります。 指定した場合、 **NULL**を呼び出すときにウィンドウ ハンドル`DragEnter`ドラッグ関数は、デスクトップのウィンドウに関連付けられているデバイス コンテキストでのイメージの描画、および、座標は画面の左上隅を基準とします。  
  
 `DragEnter` ドラッグ操作中に指定されたウィンドウにその他のすべての更新プログラムをロックします。 使用して、ドラッグしたイメージを一時的に非、ドラッグ アンド ドロップ操作のターゲットを強調表示などのドラッグ操作中に描画を実行する必要がある場合、 [DragLeave](../mfc/reference/cimagelist-class.md#dragleave)メンバー関数。 使用することも、 [DragShowNoLock](../mfc/reference/cimagelist-class.md#dragshownolock)メンバー関数。  
  
 呼び出す[EndDrag](../mfc/reference/cimagelist-class.md#enddrag)完了したら、イメージをドラッグします。  
  
 [SetDragCursorImage](../mfc/reference/cimagelist-class.md#setdragcursorimage)メンバー関数は、現在のドラッグ イメージと指定したイメージ (通常はマウス カーソル イメージ) を組み合わせることによって新しいドラッグ イメージを作成します。 ドラッグの関数は、ドラッグ操作中に、新しいイメージを使用するため、Windows を使用する必要があります[ShowCursor](/windows/desktop/api/winuser/nf-winuser-showcursor)関数を呼び出した後、実際のマウス カーソルを非表示に`SetDragCursorImage`します。 それ以外の場合、システムがドラッグ操作中にマウス カーソルが 2 つあります。  
  
 アプリケーションを呼び出すと`BeginDrag`システムは、一時的な内部のイメージ リストを作成および指定したコピーは、内部リストに画像をドラッグします。 使用して一時のドラッグ イメージ リストへのポインターを取得することができます、 [GetDragImage](../mfc/reference/cimagelist-class.md#getdragimage)メンバー関数。 関数は、また、ドラッグの現在の位置とドラッグの位置を基準としてドラッグ イメージのオフセットを取得します。  
  
## <a name="see-also"></a>関連項目  
 [Cimagelist の使い方](../mfc/using-cimagelist.md)   
 [コントロール](../mfc/controls-mfc.md)

