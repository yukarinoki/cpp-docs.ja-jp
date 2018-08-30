---
title: イメージ リストのイメージの描画 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CImageList class [MFC], drawing images from
- drawing [MFC], images from image lists
- image lists [MFC], drawing images from
- images [MFC], drawing
ms.assetid: 2f6063fb-1c28-45f8-a333-008c064db11c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f626b0dc4a8177268e72bc01f7d05ca00e326ba
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217828"
---
# <a name="drawing-images-from-an-image-list"></a>イメージ リストのイメージの描画
イメージを描画するために使用して、 [:draw](../mfc/reference/cimagelist-class.md#draw)メンバー関数。 デバイス コンテキスト オブジェクトをイメージを描画するためにデバイス コンテキスト内の場所を描画するイメージのインデックスと描画スタイルを示すフラグのセットへのポインターを指定します。  
  
 指定した場合、 **ILD_TRANSPARENT**スタイル、`Draw`マスクされたイメージを描画するために 2 段階のプロセスを使用します。 最初に、実行、論理- とイメージのビット マスクのビットを操作します。 最初の操作の結果と、コピー先デバイス コンテキストのバック グラウンドの bits の論理 XOR 演算を実行します。 このプロセスは、結果のイメージの透明な領域を作成しますつまり、各白のビット マスクのでは、結果のイメージを透明で、対応するビットが発生します。  
  
 単色の背景にマスクされたイメージを描画する前に使用する必要があります、 [SetBkColor](../mfc/reference/cimagelist-class.md#setbkcolor)メンバー関数は、変換先と同じ色にイメージ リストの背景色を設定します。 画像の透明な領域を作成する必要はありませんし、できるように、色の設定`Draw`単に、コピー先デバイス コンテキストの結果としてパフォーマンスが大幅に増加する画像をコピーします。 イメージを描画するには、指定、**に**を呼び出すときにスタイル設定`Draw`します。  
  
 マスクされたイメージの一覧については、背景色を設定することができます ([CImageList](../mfc/reference/cimagelist-class.md)) いつでもその it は、純色の背景で適切に描画するようにします。 背景色を設定**CLR_NONE**により既定で透過的に描画するイメージ。 イメージ リストの背景色を取得する、 [GetBkColor](../mfc/reference/cimagelist-class.md#getbkcolor)メンバー関数。  
  
 **ILD_BLEND25**と**ILD_BLEND50**スタイル ディザー、イメージ、システムの強調表示色を使用します。 これらのスタイルは、マスクされたイメージを使用して、ユーザーが選択できるオブジェクトを表す場合に便利です。 たとえば、使用することができます、 **ILD_BLEND50**ユーザーが選択するときにイメージの描画スタイル。  
  
 マスクされていないイメージのコピー先デバイス コンテキストを使用する、`SRCCOPY`ラスター オペレーションです。 イメージの色では、デバイス コンテキストの背景色に関係なく同じように表示します。 指定された描画スタイル`Draw`マスクされていないイメージの外観に影響を与えることもありません。  
  
 Draw メンバー関数、別の関数だけでなく[もう 1 つ](../mfc/reference/cimagelist-class.md#drawindirect)イメージをレンダリングする機能を拡張します。 `DrawIndirect` パラメーターとして受け取り、[された](/windows/desktop/api/commctrl/ns-commctrl-_imagelistdrawparams)構造体。 ラスター オペレーション (ROP) コードの使用など、現在のイメージの表示をカスタマイズし、この構造体を使用できます。 ROP コードの詳細については、次を参照してください。[ラスター オペレーション コード](/windows/desktop/gdi/raster-operation-codes)と[ビットマップ ブラシとして](/windows/desktop/gdi/bitmaps-as-brushes)Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [Cimagelist の使い方](../mfc/using-cimagelist.md)   
 [コントロール](../mfc/controls-mfc.md)

