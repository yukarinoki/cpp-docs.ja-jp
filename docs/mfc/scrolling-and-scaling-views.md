---
title: スクロールとビューをスケール |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handlers [MFC]
- scaling views [MFC]
- message handling [MFC], scroll bars in view class [MFC]
- scroll bars [MFC], messages
- scrolling views [MFC]
ms.assetid: f98a3421-c336-407e-97ee-dbb2ffd76fbd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9758c63562a19d6b9e458fd434108a92bbc8576
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="scrolling-and-scaling-views"></a>ビューのスクロールと拡大/縮小
MFC には、それらを表示するフレーム ウィンドウのサイズが自動的に拡大縮小されるまでスクロールし、表示するビューがサポートしています。 クラス`CScrollView`ビューの両方の種類をサポートしています。  
  
 スクロールと拡大/縮小の詳細については、クラスを参照してください。 [CScrollView](../mfc/reference/cscrollview-class.md)で、 *『 MFC リファレンス*です。 スクロールの例では、次を参照してください。、 [Scribble サンプル](../visual-cpp-samples.md)です。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   ビューのスクロール  
  
-   ビューを拡大/縮小  
  
-   [ビューの座標](http://msdn.microsoft.com/library/windows/desktop/dd145205)  
  
##  <a name="_core_scrolling_a_view"></a> ビューのスクロール  
 多くの場合、ドキュメントのサイズは、そのビューには表示サイズを超えています。 これは、ドキュメントのデータが増加したり、ユーザー ビューをフレーム ウィンドウを縮小するために発生する可能性があります。 このような場合は、ビューが、スクロールをサポートする必要があります。  
  
 任意のビューにスクロール バーのメッセージを処理できる、`OnHScroll`と`OnVScroll`メンバー関数。 これらの関数のいずれかの実装スクロール バー メッセージの処理、自分ですべての作業を行うことも使用することができます、`CScrollView`スクロールを処理するクラス。  
  
 `CScrollView` では次の処理が行われます。  
  
-   ウィンドウとビューポートのサイズとのマッピング モードを管理します。  
  
-   スクロール バーのメッセージに応答に自動的にスクロール  
  
 (スクロール バーの矢印で、ユーザーがクリックする) ときに「ページ」(ユーザーがスクロール バーの軸で) と「行」のスクロールする作業がどの程度指定できます。 これらの値に合わせて、ビューの性質を計画します。 たとえば、テキスト ドキュメントで、行の高さに基づく増分では 1 ピクセルずつグラフィック ビューにスクロールすることができます。  
  
##  <a name="_core_scaling_a_view"></a> ビューを拡大/縮小  
 使用することができます、ビュー、フレーム ウィンドウのサイズを自動的に調整する場合は、`CScrollView`スクロールの代わりに拡張するためです。 論理ビューに拡大または縮小、ウィンドウのクライアント領域を正確に適合します。 スケール調節されたビューには、スクロール バーはありません。  
  
## <a name="see-also"></a>関連項目  
 [ビューの使い方](../mfc/using-views.md)

