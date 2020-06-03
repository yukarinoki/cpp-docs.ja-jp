---
title: ビューの描画
ms.date: 11/04/2016
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
ms.openlocfilehash: 227c4614bad42706893301c69882c3f40af12e2f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214345"
---
# <a name="drawing-in-a-view"></a>ビューの描画

アプリケーションでのほとんどすべての描画はビューの `OnDraw` メンバー関数で発生し、ビュークラスでオーバーライドする必要があります。 (例外は、「[ビューを使用したユーザー入力の解釈](../mfc/interpreting-user-input-through-a-view.md)」で説明されているように、マウス描画です)。`OnDraw` のオーバーライド:

1. 指定したドキュメントメンバー関数を呼び出すことによって、データを取得します。

1. フレームワークが `OnDraw`に渡すデバイスコンテキストオブジェクトのメンバー関数を呼び出すことによって、データを表示します。

ドキュメントのデータが何らかの方法で変更された場合、その変更を反映するためにビューを再描画する必要があります。 通常、これは、ユーザーがドキュメントのビューを通じて変更を行ったときに発生します。 この場合、ビューはドキュメントの[UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews)メンバー関数を呼び出し、同じドキュメントのすべてのビューに対して自身の更新を通知します。 `UpdateAllViews` は、各ビューの[OnUpdate](../mfc/reference/cview-class.md#onupdate)メンバー関数を呼び出します。 `OnUpdate` の既定の実装では、ビューのクライアント領域全体が無効になります。 これをオーバーライドして、ドキュメントの変更部分にマップされているクライアント領域の領域のみを無効にすることができます。

クラス `CDocument` の `UpdateAllViews` メンバー関数と、クラス `CView` の `OnUpdate` メンバー関数を使用すると、ドキュメントのどの部分が変更されたかを説明する情報を渡すことができます。 この "ヒント" 機構を使用すると、ビューが再描画する必要がある領域を制限できます。 `OnUpdate` は、2つの "ヒント" 引数を受け取ります。 **LPARAM**型の最初の*lhint*は、任意のデータを渡すことができます。一方、型 `CObject`* の2番目の*phint*は、`CObject`から派生した任意のオブジェクトへのポインターを渡すことができます。

ビューが無効になると、Windows によって**WM_PAINT**メッセージが送信されます。 ビューの[OnPaint](../mfc/reference/cwnd-class.md#onpaint)ハンドラー関数は、 [CPaintDC](../mfc/reference/cpaintdc-class.md)クラスのデバイスコンテキストオブジェクトを作成することによってメッセージに応答し、ビューの `OnDraw` メンバー関数を呼び出します。 通常は、オーバーライドする `OnPaint` ハンドラー関数を記述する必要はありません。

[デバイスコンテキスト](../mfc/device-contexts.md)は、ディスプレイやプリンターなどのデバイスの描画属性に関する情報を含む Windows データ構造です。 すべての描画呼び出しは、デバイスコンテキストオブジェクトを使用して行われます。 画面上に描画する場合、`OnDraw` には `CPaintDC` オブジェクトが渡されます。 プリンターで描画する場合は、現在のプリンター用に設定されている[CDC](../mfc/reference/cdc-class.md)オブジェクトが渡されます。

ビューに描画するコードでは、まずドキュメントへのポインターを取得し、次にデバイスコンテキストを使用して描画を呼び出します。 次の簡単な `OnDraw` の例は、このプロセスを示しています。

[!code-cpp[NVC_MFCDocView#1](../mfc/codesnippet/cpp/drawing-in-a-view_1.cpp)]

この例では、派生ドキュメントクラスのメンバーとして `GetData` 関数を定義します。

この例では、ドキュメントから取得した任意の文字列を、ビューの中央に印刷します。 `OnDraw` 呼び出しが画面描画を行う場合、 *pDC*で渡される `CDC` オブジェクトは、そのコンストラクターが既に `BeginPaint`を呼び出した `CPaintDC` です。 描画関数の呼び出しは、デバイスコンテキストポインターを使用して行われます。 デバイスコンテキストと描画呼び出しの詳細については、「 *MFC リファレンス*」の「クラス[CDC](../mfc/reference/cdc-class.md) 」および「[ウィンドウオブジェクトの操作](../mfc/working-with-window-objects.md)」を参照してください。

`OnDraw`の記述方法のその他の例については、 [MFC のサンプル](../overview/visual-cpp-samples.md#mfc-samples)を参照してください。

## <a name="see-also"></a>参照

[ビューの使い方](../mfc/using-views.md)
