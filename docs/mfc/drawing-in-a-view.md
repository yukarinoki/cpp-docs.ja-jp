---
description: 詳細については、「ビューでの描画」を参照してください。
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
ms.openlocfilehash: b5d6b33d91f6a71048162078a926c5ad4336d6a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283408"
---
# <a name="drawing-in-a-view"></a>ビューの描画

アプリケーションでのほとんどすべての描画はビューのメンバー関数で行われますが、 `OnDraw` これはビュークラスでオーバーライドする必要があります。 (例外は、「 [ビューを使用したユーザー入力の解釈](interpreting-user-input-through-a-view.md)」で説明されているように、マウス描画です)。 `OnDraw` オーバーライド:

1. 指定したドキュメントメンバー関数を呼び出すことによって、データを取得します。

1. フレームワークによって渡されるデバイスコンテキストオブジェクトのメンバー関数を呼び出すことによって、データを表示し `OnDraw` ます。

ドキュメントのデータが何らかの方法で変更された場合、その変更を反映するためにビューを再描画する必要があります。 通常、これは、ユーザーがドキュメントのビューを通じて変更を行ったときに発生します。 この場合、ビューはドキュメントの [UpdateAllViews](reference/cdocument-class.md#updateallviews) メンバー関数を呼び出し、同じドキュメントのすべてのビューに対して自身の更新を通知します。 `UpdateAllViews` 各ビューの [OnUpdate](reference/cview-class.md#onupdate) メンバー関数を呼び出します。 の既定の実装では `OnUpdate` 、ビューのクライアント領域全体が無効になります。 これをオーバーライドして、ドキュメントの変更部分にマップされているクライアント領域の領域のみを無効にすることができます。

`UpdateAllViews`クラスのメンバー関数 `CDocument` と `OnUpdate` クラスのメンバー関数を `CView` 使用すると、ドキュメントのどの部分が変更されたかを説明する情報を渡すことができます。 この "ヒント" 機構を使用すると、ビューが再描画する必要がある領域を制限できます。 `OnUpdate` 2つの "ヒント" 引数を受け取ります。 **LPARAM** 型の最初の *lhint* は、任意のデータを渡すことができます。一方、型 * の2番目の *phint* では、 `CObject` から派生した任意のオブジェクトへのポインターを渡すことができ `CObject` ます。

ビューが無効になると、Windows によって **WM_PAINT** メッセージが送信されます。 ビューの [OnPaint](reference/cwnd-class.md#onpaint) ハンドラー関数は、 [CPaintDC](reference/cpaintdc-class.md) クラスのデバイスコンテキストオブジェクトを作成することによってメッセージに応答し、ビューのメンバー関数を呼び出し `OnDraw` ます。 通常は、オーバーライドするハンドラー関数を記述する必要はありません `OnPaint` 。

[デバイスコンテキスト](device-contexts.md)は、ディスプレイやプリンターなどのデバイスの描画属性に関する情報を含む Windows データ構造です。 すべての描画呼び出しは、デバイスコンテキストオブジェクトを使用して行われます。 画面上に描画する場合、に `OnDraw` はオブジェクトが渡され `CPaintDC` ます。 プリンターで描画する場合は、現在のプリンター用に設定されている [CDC](reference/cdc-class.md) オブジェクトが渡されます。

ビューに描画するコードでは、まずドキュメントへのポインターを取得し、次にデバイスコンテキストを使用して描画を呼び出します。 次の簡単な例は、この `OnDraw` プロセスを示しています。

[!code-cpp[NVC_MFCDocView#1](codesnippet/cpp/drawing-in-a-view_1.cpp)]

この例では、 `GetData` 派生ドキュメントクラスのメンバーとして関数を定義します。

この例では、ドキュメントから取得した任意の文字列を、ビューの中央に印刷します。 `OnDraw`画面描画の場合、 `CDC` *pDC* で渡されるオブジェクトは、コンストラクターが `CPaintDC` 既にを呼び出しているです `BeginPaint` 。 描画関数の呼び出しは、デバイスコンテキストポインターを使用して行われます。 デバイスコンテキストと描画呼び出しの詳細については、「 *MFC リファレンス*」の「クラス [CDC](reference/cdc-class.md) 」および「[ウィンドウオブジェクトの操作](working-with-window-objects.md)」を参照してください。

その他の記述方法の例につい `OnDraw` ては、 [MFC のサンプル](../overview/visual-cpp-samples.md#mfc-samples)を参照してください。

## <a name="see-also"></a>関連項目

[ビューの使用](using-views.md)
