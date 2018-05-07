---
title: ヘッダーとフッター |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- printing [MFC], multipage documents
- page headers [MFC], printing
- headers [MFC], printing
- footers [MFC], printing
- page footers [MFC], printing
- page headers [MFC]
- printing [MFC], headers and footers
- page footers [MFC]
ms.assetid: b0be9c53-5773-4955-a777-3c15da745128
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c82df1a77cdbf677a6b5e6f84c371da243b9b08d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="headers-and-footers"></a>ヘッダーとフッター
この記事では、印刷ドキュメントにヘッダーとページ フッターを追加する方法について説明します。  
  
 画面のドキュメントを参照するときに、ドキュメントと、ドキュメント内の現在の場所の名前がよく、タイトル バーとステータス バーに表示されます。 ドキュメントの印刷コピーを見るときに、ヘッダーまたはフッターに表示される名前とページ番号にすると便利です。 これは、一般的な方法でも WYSIWYG にどのプログラムが異なる印刷および画面表示の実行方法です。  
  
 [OnPrint](../mfc/reference/cview-class.md#onprint)メンバー関数は、適切な場所に、各ページで呼び出されたため、および画面表示ではなく、印刷にのみこれを呼び出すために、ヘッダーまたはフッターを印刷します。 ヘッダーまたはフッターを印刷する別の関数を定義してから、プリンター デバイス コンテキストを渡す`OnPrint`です。 ウィンドウの原点または呼び出しの前に範囲を調整する必要があります[OnDraw](../mfc/reference/cview-class.md#ondraw)ヘッダーまたはページ フッター、ページの重複部分の本文をしなくても済むようにします。 変更する必要がありますも`OnDraw` ページで、ドキュメントが収まっている量削減できたためです。  
  
 ヘッダーまたはフッターで使用されている領域は、使用するを補正するために 1 つの方法、 **m_rectDraw**のメンバー [CPrintInfo](../mfc/reference/cprintinfo-structure.md)です。 ページを印刷するたびにこのメンバーは、ページの使用可能な領域で初期化されます。 ページの本文を印刷する前に、ヘッダーまたはフッターを印刷する場合に格納されている四角形のサイズを小さくことができます**m_rectDraw**のヘッダーまたはフッターで使用されている領域を考慮します。 `OnPrint`を参照できます**m_rectDraw**量の領域は、印刷ページの本文を調べる。  
  
 ヘッダー、またはから、それ以外に印刷することはできません[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)する前に呼び出されるため、`StartPage`のメンバー関数[CDC](../mfc/reference/cdc-class.md)が呼び出されています。 その時点では、プリンター デバイス コンテキストは、ページの境界であると見なされます。 印刷だけを行うことができます、`OnPrint`メンバー関数。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [マルチページ ドキュメント](../mfc/multipage-documents.md)  
  
-   [印刷用 GDI リソースの割り当てください。](../mfc/allocating-gdi-resources.md)  
  
## <a name="see-also"></a>関連項目  
 [印刷](../mfc/printing.md)

