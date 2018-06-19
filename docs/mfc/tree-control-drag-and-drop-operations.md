---
title: ツリーのコントロールのドラッグ アンド ドロップ操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CTreeCtrl class [MFC], drag and drop operations
- drag and drop [MFC], CTreeCtrl
- tree controls [MFC], drag and drop operations
ms.assetid: 3cf78b4c-4579-4fe1-9bc9-c5ab876e4af1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a620c2481b29b80f6d30dd6457716a652f51fd85
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382767"
---
# <a name="tree-control-drag-and-drop-operations"></a>ツリー コントロールのドラッグ アンド ドロップ操作
ツリー コントロール ([CTreeCtrl](../mfc/reference/ctreectrl-class.md))、ユーザーが項目のドラッグを開始すると、通知を送信します。 コントロールが送信、 [TVN_BEGINDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773504) 、ユーザーがマウスの左ボタンを持つ項目のドラッグを始めたときに通知メッセージと[TVN_BEGINRDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773509)ユーザーがのドラッグを始めたときに通知メッセージ右ボタンをクリックします。 ツリー コントロールのツリー コントロールを付けることでこれらの通知を送信されないようにできます、 **TVS_DISABLEDRAGDROP**スタイル。  
  
 呼び出すことによって、ドラッグ操作中に表示するイメージを取得する、 [CreateDragImage](../mfc/reference/ctreectrl-class.md#createdragimage)メンバー関数。 ツリー コントロールでは、ドラッグされている項目のラベルに基づくドラッグ用のビットマップを作成します。 ツリー コントロールのイメージ リストを作成、ビットマップを追加し、されへのポインターを返します、 [CImageList](../mfc/reference/cimagelist-class.md)オブジェクト。  
  
 実際には、項目をドラッグするコードを用意する必要があります。 通常、ドラッグ イメージ リストの関数の機能を使用して、処理、 [WM_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616)と[した](http://msdn.microsoft.com/library/windows/desktop/ms645608)(または[WM_RBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms646243))ドラッグ操作が開始された後に送信されるメッセージ。 イメージ リストの関数の詳細については、次を参照してください。 [CImageList](../mfc/reference/cimagelist-class.md)で、 *『 MFC リファレンス*と[イメージ リスト](http://msdn.microsoft.com/library/windows/desktop/bb761389)Windows SDK にします。 ツリー コントロール項目をドラッグすることの詳細については、次を参照してください。[ツリー ビューの項目のドラッグ](http://msdn.microsoft.com/library/windows/desktop/bb760017)もの、[!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]です。  
  
 ツリー コントロールで項目をドラッグ アンド ドロップ操作の対象になる場合は、ターゲット項目上にマウス カーソルが際に知っておく必要があります。 呼び出すことで調べることができます、 [HitTest](../mfc/reference/ctreectrl-class.md#hittest)メンバー関数。 ポイントし、整数、またはのアドレスを指定する、 [TVHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb773448)マウスのカーソルの現在の座標を格納する構造体。 関数から制御が戻るとき、整数または構造体が含まれていますツリーのコントロールに対する相対的なマウスのカーソルの位置を示すフラグには。 ツリー コントロールのアイテムにカーソルがある場合、構造体には、アイテムを同様のハンドルが含まれています。  
  
 ドラッグ アンド ドロップ操作の対象の項目は呼び出すことによってを指定することができます、 [SetItem](../mfc/reference/ctreectrl-class.md#setitem)状態を設定するメンバー関数、`TVIS_DROPHILITED`値。 この状態にある項目がドラッグ アンド ドロップのターゲットを示すために使用されるスタイルで描画されます。  
  
## <a name="see-also"></a>関連項目  
 [CTreeCtrl の使い方](../mfc/using-ctreectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

