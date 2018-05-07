---
title: オブジェクトの 1 つのステージと 2 段階の作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], creating graphic objects
- object creation [MFC], graphic objects
- objects [MFC], graphic objects
- one-stage and two-stage construction of objects [MFC]
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c53f99932887acad4d2eab5c15ed73b66b359fd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="one-stage-and-two-stage-construction-of-objects"></a>1 段階でのオブジェクトの構築と 2 段階でのオブジェクトの構築
ブラシ、ペンなどのグラフィック オブジェクトを作成するための 2 つの手法のいずれかがあります。  
  
-   *1 つのステージ構築*: コンス トラクターと、コンス トラクターを持つすべての 1 つのステージでは、オブジェクトを初期化します。  
  
-   *2 段階の構築*: 構築と 2 つの独立した段階でオブジェクトを初期化します。 コンス トラクターは、オブジェクトを作成し、初期化関数では、それを初期化します。  
  
 2 段階で構築する方が安全です。 1 つのステージの構築で不適切な引数を指定するか、メモリの割り当てが失敗した場合、コンス トラクターによって例外がスローする可能性があります。 エラーを確認する必要が、2 段階の構築でその問題を回避できます。 どちらの場合は、同じプロセスには、オブジェクトを破棄します。  
  
> [!NOTE]
>  これらの手法は、いないグラフィック オブジェクトだけで、あらゆるオブジェクトの作成に適用されます。  
  
## <a name="example-of-both-construction-techniques"></a>両方の構築方法の例  
 次の簡単な例は、どちらのペン オブジェクトを構築する方法を示しています。  
  
 [!code-cpp[NVC_MFCDocViewSDI#6](../mfc/codesnippet/cpp/one-stage-and-two-stage-construction-of-objects_1.cpp)]  
  
### <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [グラフィック オブジェクト](../mfc/graphic-objects.md)  
  
-   [グラフィック オブジェクトをデバイス コンテキストに選択します。](../mfc/selecting-a-graphic-object-into-a-device-context.md)  
  
-   [デバイス コンテキスト](../mfc/device-contexts.md)  
  
-   [ビューの描画](../mfc/drawing-in-a-view.md)  
  
## <a name="see-also"></a>関連項目  
 [グラフィック オブジェクト](../mfc/graphic-objects.md)

