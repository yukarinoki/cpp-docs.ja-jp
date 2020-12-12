---
description: '詳細情報: ウィンドウオブジェクト'
title: ウィンドウ オブジェクト
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], window
- Windows window [MFC]
- MFC, windows
- frame windows [MFC], C++ window objects
- window objects [MFC]
- windows [MFC], C++ window objects
- window messages [MFC]
- HWND
- messages [MFC], Windows
- Visual C++, window objects [MFC]
- HWND, window objects [MFC]
ms.assetid: 28b33ce2-af05-4617-9d03-1cb9a02be687
ms.openlocfilehash: 5a7755dfecc8205279785a6452b04c3f8dc429d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214495"
---
# <a name="window-objects"></a>ウィンドウ オブジェクト

MFC は、ウィンドウのハンドルをカプセル [化するため](../mfc/reference/cwnd-class.md) のクラスを提供し `HWND` ます。 `CWnd`オブジェクトは、 `HWND` Windows のウィンドウを表すものの、それを含んでいるとは別の C++ ウィンドウオブジェクトです。 を使用し `CWnd` て独自の子ウィンドウクラスを派生させるか、から派生した多くの MFC クラスの1つを使用し `CWnd` ます。 クラス `CWnd` は、フレームウィンドウ、ダイアログボックス、子ウィンドウ、コントロール、およびツールバーなどのコントロールバーを含む、すべてのウィンドウの基本クラスです。 [C++ ウィンドウオブジェクトと HWND の関係](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)をよく理解していることは、MFC での効果的なプログラミングに不可欠です。

MFC には、windows の既定の機能と管理がいくつか用意されていますが、独自のクラスをから派生させ、 `CWnd` そのメンバー関数を使用して、提供される機能をカスタマイズすることもできます。 子ウィンドウを作成するには、 `CWnd` オブジェクトを構築してその [create](../mfc/reference/cwnd-class.md#create) member 関数を呼び出した後、メンバー関数を使用して子ウィンドウをカスタマイズし `CWnd` ます。 フォームビューやツリービューなど、 [CView](../mfc/reference/cview-class.md)から派生したオブジェクトをフレームウィンドウに埋め込むことができます。 また、 [CSplitterWnd](../mfc/reference/csplitterwnd-class.md)クラスによって提供されるスプリッターペインを使用して、ドキュメントの複数のビューをサポートできます。

クラスから派生した各オブジェクトには `CWnd` 、メッセージマップが含まれています。このマップを使用して、Windows メッセージまたはコマンド id を独自のハンドラーにマップできます。

Windows のプログラミングに関する一般的な文献は、 `CWnd` api をカプセル化するメンバー関数の使用方法を学習するためのリソースです `HWND` 。

## <a name="functions-for-operating-on-a-cwnd"></a>CWnd で動作する関数

`CWnd` およびその [派生ウィンドウクラス](../mfc/derived-window-classes.md) は、コンストラクター、デストラクター、およびメンバー関数を提供して、オブジェクトを初期化し、基になる Windows 構造体を作成して、カプセル化されたにアクセスし `HWND` ます。 `CWnd` には、メッセージの送信、ウィンドウの状態へのアクセス、座標の変換、スクロール、クリップボードへのアクセス、およびその他多くのタスクのための Windows Api をカプセル化するメンバー関数も用意されています。 引数を受け取るほとんどの Windows ウィンドウ管理 Api `HWND` は、のメンバー関数としてカプセル化されてい `CWnd` ます。 関数とそのパラメーターの名前は、メンバー関数に保持され `CWnd` ます。 によってカプセル化された Windows Api の詳細については `CWnd` 、「 [CWnd](../mfc/reference/cwnd-class.md)クラス」を参照してください。

## <a name="cwnd-and-windows-messages"></a>CWnd と Windows のメッセージ

の主な目的の1つ `CWnd` は、WM_PAINT や WM_MOUSEMOVE などの Windows メッセージを処理するためのインターフェイスを提供することです。 のメンバー関数の多く `CWnd` は、標準メッセージのハンドラーであり、識別子で始まる **afx_msg** とプレフィックス "On" で始まります ( `OnPaint` やなど) `OnMouseMove` 。 メッセージの[処理とマッピング](../mfc/message-handling-and-mapping.md)では、メッセージとメッセージの処理について詳しく説明します。 これらの情報は、フレームワークのウィンドウにも同様に適用されます。また、特別な目的で作成した情報も同様です。

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [C++ ウィンドウオブジェクトと HWND の関係](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)

- [ウィンドウ クラスの派生](../mfc/derived-window-classes.md)

- [ウィンドウの作成](../mfc/creating-windows.md)

- [ウィンドウ オブジェクトの破棄](../mfc/destroying-window-objects.md)

- [CWnd を HWND からデタッチする](../mfc/detaching-a-cwnd-from-its-hwnd.md)

- [ウィンドウ オブジェクトの操作](../mfc/working-with-window-objects.md)

- [デバイスコンテキスト](../mfc/device-contexts.md): Windows 描画デバイスに依存しないようにするオブジェクト

- [グラフィックオブジェクト](../mfc/graphic-objects.md): ペン、ブラシ、フォント、ビットマップ、パレット、領域

## <a name="see-also"></a>関連項目

[Windows](../mfc/windows.md)
