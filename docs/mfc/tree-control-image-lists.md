---
title: ツリー コントロールのイメージ リスト |Microsoft Docs
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
ms.openlocfilehash: 184a68ec29e806b5bb914d8744ff5c1f334db5ea
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203767"
---
# <a name="tree-control-image-lists"></a>ツリー コントロールのイメージ リスト
ツリー コントロール内の各アイテム ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 関連付けられているビットマップ イメージのペアを持つことができます。 項目のラベルの左側にある、画像が表示されます。 項目が選択されているし、項目が選択されていないときに、もう一方が表示されます、1 つのイメージが表示されます。 たとえば、項目が選択されていないときに、開いているフォルダーが選択されているときと閉じたフォルダーを表示可能性があります。  
  
 項目のイメージを使用するには、構築することでイメージ リストを作成する必要があります、 [CImageList](../mfc/reference/cimagelist-class.md)オブジェクトとを使用して、 [CImageList::Create](../mfc/reference/cimagelist-class.md#create)関連付けられているイメージ リストを作成する関数。 必要なビットマップを一覧に追加しを使用して、リストをツリーのコントロールに関連付ける、 [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist)メンバー関数。 既定では、すべての項目は、および非選択状態の両方のイメージ リストの最初のイメージを表示します。 特定の項目の既定の動作を変更するにはツリーのコントロールを使用する項目を追加するときに、選択したイメージのインデックスを指定することによって、 [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem)メンバー関数。 使用して項目を追加した後、インデックスを変更することができます、 [SetItemImage](../mfc/reference/ctreectrl-class.md#setitemimage)メンバー関数。  
  
 ツリー コントロールのイメージ リストは、オーバーレイのイメージは、項目のイメージ上に重ねて表示するのを含めることもできます。 ツリー コントロール項目の状態の 8 ~ 11 ビット単位で 0 以外の値がオーバーレイ画像の 1 から始まるインデックスを指定します (0 を示しますオーバーレイ画像なし)。 4 ビット、1 から始まるインデックスを使用しているために、イメージ リストの最初の 15 のイメージ間でイメージのオーバーレイを引き起こすことがあります。 ツリー コントロール項目の状態の詳細については、次を参照してください。[ツリー コントロール項目の状態の概要](../mfc/tree-control-item-states-overview.md)このトピックで前述しました。  
  
 状態イメージのリストが指定されている場合、ツリー コントロールには、状態の画像の各項目のアイコンの左側の領域が確保されます。 アプリケーションでは、オンとオフのチェック ボックスなどの状態のイメージを使用して、アプリケーション定義の項目の状態を示します。 状態イメージの 1 から始まるインデックスを指定するビット 12 ~ 15 に 0 以外の値 (0 を示します状態の画像なし)。  
  
 指定することによって、**番号**値、イメージのインデックスではなく項目が再描画するまでに、選択または選択されていないイメージを指定することを遅らせることができます。 **番号**指示を送信して、インデックスのアプリケーションをクエリするツリー コントロール、 [TVN_GETDISPINFO](/windows/desktop/Controls/tvn-getdispinfo)通知メッセージ。  
  
 [GetImageList](../mfc/reference/ctreectrl-class.md#getimagelist)メンバー関数は、ツリー コントロールのイメージ リストのハンドルを取得します。 この関数は、イメージを一覧に追加する必要がある場合に便利です。 イメージ リストの詳細については、次を参照してください[を使用して CImageList](../mfc/using-cimagelist.md)、 [CImageList](../mfc/reference/cimagelist-class.md)で、 *MFC リファレンス*、および[イメージ リスト](https://msdn.microsoft.com/library/windows/desktop/bb761389)で、。Windows SDK。  
  
## <a name="see-also"></a>関連項目  
 [CTreeCtrl の使い方](../mfc/using-ctreectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

