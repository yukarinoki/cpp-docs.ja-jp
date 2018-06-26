---
title: ビューの描画 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- drawing [MFC], in views
- views [MFC], printing
- views [MFC], updating
- printing [MFC], views
- views [MFC], rendering
- printing views [MFC]
- paint messages in view class [MFC]
- device contexts, screen drawings
ms.assetid: e3761db6-0f19-4482-a4cd-ac38ef7c4d3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 866f2e2a3de6708d1be78748ee889272a05352cd
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928500"
---
# <a name="drawing-in-a-view"></a>ビューの描画
ビューは、アプリケーションのほぼすべての描画`OnDraw`メンバー関数は、ビュー クラスでオーバーライドする必要があります。 (例外は、マウスの描画、後ほど[を解釈するユーザー入力ビューを経由した](../mfc/interpreting-user-input-through-a-view.md))。`OnDraw`をオーバーライドします。  
  
1.  ドキュメントの指定したメンバー関数を呼び出すことによってデータを取得します。  
  
2.  フレームワークが渡されるデバイス コンテキスト オブジェクトのメンバー関数を呼び出すことによってデータが表示されます`OnDraw`です。  
  
 ドキュメントのデータは、何らかの方法で変更された、ときに、変更を反映するように、ビューが再描画される必要があります。 通常はユーザーがドキュメントのビューから変更を行ったときに発生します。 この場合、ビューがドキュメントを呼び出す[UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews)に自分自身を更新する、同じドキュメントのすべてのビューを通知するメンバー関数。 `UpdateAllViews` それぞれのビューを呼び出す[OnUpdate](../mfc/reference/cview-class.md#onupdate)メンバー関数。 既定の実装`OnUpdate`ビューのクライアント領域全体を無効にします。 ドキュメントの変更後の部分に割り当てられたクライアント領域の領域のみを無効化するメソッドをオーバーライドすることができます。  
  
 `UpdateAllViews`クラスのメンバー関数`CDocument`と`OnUpdate`クラスのメンバー関数`CView`ドキュメントのどの部分が変更されたを説明する情報を渡すことができます。 この「ヒント」メカニズムでは、ビューの再描画する領域を制限できます。 `OnUpdate` 2 つの「ヒント」引数を受け取ります。 最初、 *lHint*、型の**LPARAM**、必要な場合、2 番目の中に、データの受け渡しすることができます*pHint*、型の`CObject`*、派生した任意のオブジェクトへのポインターを渡すことができます`CObject`です。  
  
 Windows がそれを送信すると表示が無効になったとき、 **WM_PAINT**メッセージ。 ビューの[OnPaint](../mfc/reference/cwnd-class.md#onpaint)ハンドラー関数がクラスのデバイス コンテキスト オブジェクトを作成することで、メッセージに応答[CPaintDC](../mfc/reference/cpaintdc-class.md)呼び出しビューのおよび`OnDraw`メンバー関数。 通常はできません、オーバーライドを書き込む`OnPaint`ハンドラー関数。  
  
 A[デバイス コンテキスト](../mfc/device-contexts.md)ディスプレイまたはプリンターなどのデバイスの描画属性に関する情報を含む Windows データ構造です。 デバイス コンテキスト オブジェクトを通じて、すべての描画呼び出しが行われます。 画面で、描画するため`OnDraw`渡される、`CPaintDC`オブジェクト。 描画する場合、プリンターで、渡された、 [CDC](../mfc/reference/cdc-class.md)オブジェクトの現在のプリンターを設定します。  
  
 ビューで描画するため、コードは最初、ドキュメントへのポインターを取得し、デバイス コンテキストから描画呼び出しを実行します。 以下の単純な`OnDraw`の例は、プロセスを示しています。  
  
 [!code-cpp[NVC_MFCDocView#1](../mfc/codesnippet/cpp/drawing-in-a-view_1.cpp)]  
  
 この例では定義して、`GetData`ドキュメントの派生クラスのメンバーとして機能します。  
  
 例では、中心ビューに、ドキュメントから取得した文字列を出力します。 場合、`OnDraw`呼び出しが画面の描画には、`CDC`に渡されたオブジェクト*pDC*は、`CPaintDC`コンス トラクターは既に呼び出さ`BeginPaint`です。 描画関数への呼び出しは、デバイス コンテキスト ポインターを通じて行われます。 デバイス コンテキストおよび描画呼び出しについては、クラスを参照してください。 [CDC](../mfc/reference/cdc-class.md)で、 *『 MFC リファレンス*と[ウィンドウ オブジェクトの操作](../mfc/working-with-window-objects.md)です。  
  
 記述する方法の例について`OnDraw`を参照してください、 [MFC サンプル](../visual-cpp-samples.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ビューの使い方](../mfc/using-views.md)

