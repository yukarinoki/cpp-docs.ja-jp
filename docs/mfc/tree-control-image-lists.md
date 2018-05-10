---
title: ツリーのコントロールのイメージ リスト |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- images [MFC], lists in tree controls
- tree controls [MFC], image lists
- CTreeCtrl class [MFC], image lists
ms.assetid: f560c4f2-20d2-4d28-ac33-4017e65fb0a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef74b656cc85fbdcc29c7965b9398a5cbd2f44e8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="tree-control-image-lists"></a>ツリー コントロールのイメージ リスト
ツリー コントロール内の各項目 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 関連付けられているビットマップ イメージのペアを持つことができます。 項目のラベルの左側にある、画像が表示されます。 項目が選択されているし、項目が選択されていないときに表示されたら、他の 1 つのイメージが表示されます。 たとえば、項目が選択されていないときに、開いているフォルダーを選択すると閉じたフォルダーを表示できます。  
  
 項目のイメージを使用するのには、構築することによってイメージ リストを作成する必要があります、 [CImageList](../mfc/reference/cimagelist-class.md)オブジェクトとを使用して、 [CImageList::Create](../mfc/reference/cimagelist-class.md#create)関連付けられているイメージ リストを作成する関数。 必要なビットマップを一覧に追加し、使用して、リストをツリーのコントロールに関連付ける、 [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist)メンバー関数。 既定は、すべてのアイテムは、両方の選択と選択されていない状態のイメージ リスト内の最初のイメージを表示します。 特定の項目の既定の動作を変更するには、コントロールを使用してツリーに項目を追加するときに、選択したイメージのインデックスを指定することによって、 [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem)メンバー関数。 使用して項目を追加した後、インデックスを変更することができます、 [SetItemImage](../mfc/reference/ctreectrl-class.md#setitemimage)メンバー関数。  
  
 ツリー コントロールのイメージ リストは、オーバーレイのイメージは、項目のイメージ上に重ねて表示するのを含めることもできます。 ツリー コントロール項目の状態のビット 8. ~ 11. に 0 以外の値をオーバーレイ イメージの 1 から始まるインデックスを指定します (0 示します)。 4 ビット、1 から始まるインデックスを使用しているために、オーバーレイ イメージは複数のイメージ リストの最初の 15 の画像にする必要があります。 ツリー コントロール項目の状態の詳細については、次を参照してください。[ツリー コントロール項目の状態の概要](../mfc/tree-control-item-states-overview.md)このトピックで前述しました。  
  
 状態のイメージ リストが指定されている場合、ツリー コントロールには、状態の画像の各項目のアイコンの左側の領域が確保されます。 アプリケーションは、アプリケーションで定義された項目の状態を示すためにオン、オフになってのチェック ボックスなどの状態のイメージを使用できます。 状態のイメージの 1 から始まるインデックスを指定するビット 12 ~ 15 に 0 以外の値 (0 示します)。  
  
 指定して、**番号**値、イメージのインデックスではなく、項目が再描画されるまで、選択または選択されていないイメージを指定することを遅らせることができます。 **番号**ようにツリー コントロールに送信することによって、インデックスのアプリケーションをクエリする指示、 [TVN_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773518)通知メッセージです。  
  
 [GetImageList](../mfc/reference/ctreectrl-class.md#getimagelist)メンバー関数は、ツリー コントロールのイメージ リストのハンドルを取得します。 この関数は、イメージを一覧に追加する必要がある場合に便利です。 イメージ リストの詳細については、次を参照してください[を使用して CImageList](../mfc/using-cimagelist.md)、 [CImageList](../mfc/reference/cimagelist-class.md)で、 *『 MFC リファレンス*、および[イメージ リスト](http://msdn.microsoft.com/library/windows/desktop/bb761389)で、。Windows SDK。  
  
## <a name="see-also"></a>関連項目  
 [CTreeCtrl の使い方](../mfc/using-ctreectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

