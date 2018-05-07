---
title: リスト コントロール スタイルの変更 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- styles [MFC], CListCtrl
- CListCtrl class [MFC], styles
- CListCtrl class [MFC], changing styles
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9d93511ad4f4ca835e09b6eaa3f612f0888e844
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="changing-list-control-styles"></a>リスト コントロール スタイルの変更
リスト コントロールのウィンドウ スタイルを変更することができます ([CListCtrl](../mfc/reference/clistctrl-class.md)) 作成した後、いつでもできます。 ウィンドウ スタイルを変更すると、コントロールを使用してビューの種類を変更します。 たとえば、エクスプ ローラー、エミュレートする可能性があります指定する必要がメニュー項目またはコントロールの異なるビュー間を切り替えるためのツール バー ボタン: アイコン ビューや一覧表示します。  
  
 たとえば、ユーザーは、メニュー項目を選択するときに行うことができるへの呼び出し[GetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633584)コントロールの現在のスタイルを取得し、呼び出す[SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591)スタイルをリセットします。 詳細については、次を参照してください。[リスト ビュー コントロールを使用した](http://msdn.microsoft.com/library/windows/desktop/bb774736)Windows SDK に含まれています。  
  
 使用可能なスタイルは、「[作成](../mfc/reference/clistctrl-class.md#create)です。 スタイル`LVS_ICON`、 `LVS_SMALLICON`、 `LVS_LIST`、および`LVS_REPORT`4 つのリスト コントロールのビューを指定します。  
  
## <a name="extended-styles"></a>拡張スタイル  
 リスト コントロールの標準のスタイルに加え、拡張スタイルと呼ばれる別のセットがあります。 これらのスタイルで説明した[リスト ビューのスタイルの拡張](http://msdn.microsoft.com/library/windows/desktop/bb774732)Windows sdk には、さまざまなリスト コントロールの動作をカスタマイズするための便利な機能を提供します。 特定のスタイル (ホバー時の選択) などの動作を実装する呼び出しを行う[かざして](../mfc/reference/clistctrl-class.md#setextendedstyle)、必要なスタイルします。 次の例では、関数呼び出しを示しています。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#22](../mfc/codesnippet/cpp/changing-list-control-styles_1.cpp)]  
  
> [!NOTE]
>  ホバー時の選択が機能するもが必要か**LVS_EX_ONECLICKACTIVATE**または**させる**オンにします。  
  
## <a name="see-also"></a>関連項目  
 [CListCtrl の使い方](../mfc/using-clistctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

