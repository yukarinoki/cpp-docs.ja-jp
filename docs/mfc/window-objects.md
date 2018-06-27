---
title: ウィンドウ オブジェクト |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f040978c898dae3bfd4ca21c2cf9886fde9b5238
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951280"
---
# <a name="window-objects"></a>ウィンドウ オブジェクト
MFC クラスを提供する[CWnd](../mfc/reference/cwnd-class.md)をカプセル化する、`HWND`ウィンドウのハンドル。 `CWnd`オブジェクトが C++ ウィンドウ オブジェクト、別個のもの、`HWND`を表す Windows ウィンドウが、それを含むです。 使用して`CWnd`子ウィンドウを派生するクラス、または多数の MFC クラスのいずれかから派生した`CWnd`です。 クラス`CWnd`フレーム ウィンドウ、ダイアログ ボックス、子ウィンドウ、コントロール、およびツールバーなどのコントロール バーを含む、すべての windows の基本クラスです。 よく理解[C++ ウィンドウ オブジェクトと HWND の関係](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)MFC で効果的なプログラミングは特に重要です。  
  
 MFC には、一部の既定の機能と、windows の管理が用意されていますが、独自のクラスから派生できます`CWnd`し、メンバー関数を使用して、提供されている機能をカスタマイズします。 構築することによって、子ウィンドウを作成できる、`CWnd`オブジェクトと呼び出し元の[作成](../mfc/reference/cwnd-class.md#create)メンバー関数は、次を使用して子ウィンドウをカスタマイズ`CWnd`メンバー関数。 派生したオブジェクトを埋め込むことができます[CView](../mfc/reference/cview-class.md)、フォーム ビューなどのフレーム ウィンドウのツリー ビューです。 クラスで提供される分割ペインを使用してドキュメントの複数のビューをサポートできると[CSplitterWnd](../mfc/reference/csplitterwnd-class.md)です。  
  
 クラスから派生した各オブジェクト`CWnd`メッセージ マップ使用する Windows メッセージのマッピングまたはコマンドのハンドラーを独自に Id にはが含まれています。  
  
 Windows が使用する方法を学習するための適切なリソースをプログラミングで一般的な資料、`CWnd`をカプセル化するメンバー関数、 `HWND` Api です。  
  
## <a name="functions-for-operating-on-a-cwnd"></a>CWnd に対する操作のための関数  
 `CWnd` その[ウィンドウ クラスを派生](../mfc/derived-window-classes.md)コンス トラクター、デストラクター、およびメンバー関数、オブジェクトを初期化するために、基になる Windows 構造体を作成し、カプセル化されたアクセスを提供`HWND`です。 `CWnd` 座標の変換、更新、ウィンドウの状態へのアクセス、メッセージを送信するための Windows Api をカプセル化するメンバー関数も用意されてスクロール、クリップボード、およびその他の多くのタスクへのアクセスします。 実行するほとんどの Windows ウィンドウ管理 Api、`HWND`引数がのメンバー関数としてカプセル化された`CWnd`です。 関数およびそのパラメーターの名前が保持、`CWnd`メンバー関数。 によってカプセル化された Windows Api の詳細について`CWnd`、クラスを参照して[CWnd](../mfc/reference/cwnd-class.md)です。  
  
## <a name="cwnd-and-windows-messages"></a>CWnd と Windows メッセージ  
 主な目的は、のいずれかの`CWnd`WM_PAINT か WM_MOUSEMOVE などの Windows メッセージを処理するためのインターフェイスを提供することです。 メンバー関数の多くは`CWnd`標準のメッセージのハンドラーは、— 識別子で始まる**afx_msg**と、「で、」プレフィックスなど`OnPaint`と`OnMouseMove`です。 [メッセージの処理とマップ](../mfc/message-handling-and-mapping.md)メッセージおよびメッセージ処理の詳細について説明します。 情報は、フレームワークのウィンドウとの特別な目的で作成したものに平等に適用されます。  
  
### <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [C++ ウィンドウ オブジェクトと HWND の関係](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)  
  
-   [ウィンドウ クラスの派生](../mfc/derived-window-classes.md)  
  
-   [ウィンドウの作成](../mfc/creating-windows.md)  
  
-   [ウィンドウ オブジェクトの破棄](../mfc/destroying-window-objects.md)  
  
-   [CWnd と HWND の分離](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
-   [ウィンドウ オブジェクトの操作](../mfc/working-with-window-objects.md)  
  
-   [デバイス コンテキスト](../mfc/device-contexts.md): Windows でのデバイスを描画を独立して構成するオブジェクト  
  
-   [グラフィック オブジェクト](../mfc/graphic-objects.md): ペン、ブラシ、フォント、ビットマップ、パレット、領域  
  
## <a name="see-also"></a>関連項目  
 [Windows](../mfc/windows.md)

