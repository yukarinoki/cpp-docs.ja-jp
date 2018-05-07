---
title: イメージ リストのイメージの描画 |Microsoft ドキュメント
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
ms.openlocfilehash: 86983506770b9719972170dfbb70b02c8026e108
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="drawing-images-from-an-image-list"></a>イメージ リストのイメージの描画
イメージを描画するには、 [:draw](../mfc/reference/cimagelist-class.md#draw)メンバー関数。 デバイス コンテキスト オブジェクトを描画するイメージを描画するためにデバイス コンテキスト内の場所にイメージのインデックスおよび描画スタイルを示すフラグのセットへのポインターを指定します。  
  
 指定すると、`ILD_TRANSPARENT`スタイル、**描画**マスクされたイメージを描画する 2 段階のプロセスを使用します。 最初を実行する論理、およびイメージのビットとマスクのビットに操作します。 最初の操作の結果とコピー先デバイス コンテキストのバック グラウンド bits での論理 XOR 演算を実行します。 このプロセスは、結果の画像で透明な領域を作成します。つまり、各白のビット マスクの実行が、対応するビットを透明に結果のイメージです。  
  
 純色の背景にマスクされたイメージを描画する前に使用する必要があります、 [SetBkColor](../mfc/reference/cimagelist-class.md#setbkcolor)先と同じ色にイメージ リストの背景色を設定します。 色の設定、画像の透明な領域を作成する必要があるができ、**描画**だけで、コピー先デバイス コンテキストの結果としてパフォーマンスが大幅に増加する画像をコピーします。 イメージを描画するには、指定、`ILD_NORMAL`を呼び出すときにスタイル**描画**です。  
  
 マスクされたイメージ リストの背景色を設定することができます ([CImageList](../mfc/reference/cimagelist-class.md)) ことが、純色の背景で適切に描画するように、いつでもできます。 背景色に設定`CLR_NONE`により既定で透過的に描画されるイメージです。 イメージ リストの背景色を取得するを使用して、 [GetBkColor](../mfc/reference/cimagelist-class.md#getbkcolor)メンバー関数。  
  
 `ILD_BLEND25`と`ILD_BLEND50`スタイル ディザー システム強調表示色を画像。 これらのスタイルは、マスクされたイメージを使用して、ユーザーが選択できるオブジェクトを表す場合に便利です。 たとえば、使用することができます、`ILD_BLEND50`ユーザーに選択されると、イメージを描画するスタイルです。  
  
 移行先デバイス コンテキストを使用して、マスクされていないイメージがコピー、 **SRCCOPY**ラスター オペレーションです。 イメージの色には、デバイス コンテキストの背景色に関係なく同じが表示されます。 指定された描画スタイル**描画**マスクされていないイメージの外観に影響を与えるもありません。  
  
 Draw メンバー関数、別の関数に加えて[もう 1 つ](../mfc/reference/cimagelist-class.md#drawindirect)画像を表示する機能を拡張します。 `DrawIndirect` パラメーターとして受け取り、[された](http://msdn.microsoft.com/library/windows/desktop/bb761395)構造体。 この構造体はラスター オペレーション (ROP) コードの使用を含む、現在のイメージの表示をカスタマイズするためにことができます。 ROP コードの詳細については、次を参照してください。[ラスター オペレーション コード](http://msdn.microsoft.com/library/windows/desktop/dd162892)と[ビットマップ ブラシを](http://msdn.microsoft.com/library/windows/desktop/dd183378)Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [CImageList の使い方](../mfc/using-cimagelist.md)   
 [コントロール](../mfc/controls-mfc.md)

