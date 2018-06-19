---
title: 'TN029: 分割ウィンドウ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.windows.splitter
dev_langs:
- C++
helpviewer_keywords:
- TN029
- splitter windows [MFC], about splitter windows
ms.assetid: 2c57ce99-2a3c-4eff-9cea-baccb13af075
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ca18f12c5aa1ae767b8921c28e650f3fb69d9942
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384724"
---
# <a name="tn029-splitter-windows"></a>テクニカル ノート 29: 分割ウィンドウ
この注の説明、MFC [CSplitterWnd クラス](../mfc/reference/csplitterwnd-class.md)ウィンドウを分割し、その他のウィンドウのウィンドウのサイズ変更の管理を提供します。  
  
## <a name="splitter-styles"></a>分割線のスタイル  
 A`CSplitterWnd`ウィンドウの分割の 2 つの異なるスタイルをサポートしています。  
  
 「静的分割ウィンドウで」では、分割ウィンドウは、作成時に、ウィンドウを作成します。 ウィンドウの数と順序は変わりません。 分割バーを使用して、別のウィンドウのサイズを変更します。 このスタイルを使用すると、各ウィンドウに別のビュー クラスを表示します。 Visual C グラフィックス エディターと Windows ファイル マネージャーは、この分割線のスタイルを使用するプログラムの例を示します。 このスタイルの分割ウィンドウでは、分割ボックスは使用しません。  
  
 「動的分割ウィンドウで」でその他のウィンドウが作成され、ユーザーの分割と解除分割新しいビューと破棄されます。 この分割は、1 つのビューから始まりし、ユーザーが分割を開始するための分割ボックスを提供します。 分割ウィンドウは、ビューは、1 つの方向に分割されると、新しいビュー オブジェクトを動的に作成します。 この新しいビュー オブジェクトは、新しいウィンドウを表します。 ビューは、キーボード インターフェイスを使用して 2 つの方向に分割される、分割ウィンドウは、3 つの新しいウィンドウの 3 つの新しい表示オブジェクトを作成します。 分割がアクティブな間は、ペイン間の分割バーとして分割ボックスが表示されます。 Windows は、ユーザーには、分割が削除されますが、元表示されるまで残ります分割ウィンドウ自体が破棄されるときに、追加のビュー オブジェクトを破棄します。 Microsoft Excel や Microsoft Word 動的分割線のスタイルを使用するアプリケーションの例に示します。  
  
 分割ウィンドウのいずれかの種類を作成する場合は、スプリッターを管理している行と列の最大数を指定する必要があります。 静的な分割では、すべての行と列を入力するウィンドウを作成します。 動的分割が最初のペインのみを作成するときに、`CSplitterWnd`を作成します。  
  
 静的分割ウィンドウに指定できるウィンドウの最大数は、16 個の列が 16 行です。 推奨される構成は次のとおりです。  
  
-   1 行 x 2 列: 通常と異なるウィンドウ  
  
-   2 行 x 1 列: 通常と異なるウィンドウ  
  
-   2 行 x 2 列: のようなウィンドウを通常  
  
 動的分割ウィンドウに対して指定できるウィンドウの最大数は、2 つの列で 2 行です。 推奨される構成は次のとおりです。  
  
-   1 行 x 2 列: 単票形式のデータ  
  
-   2 行 x 1 列: テキストまたはその他のデータ  
  
-   2 行 x 2 列: 表形式のデータ  
  
## <a name="splitter-examples"></a>分割ウィンドウの例  
 分割ウィンドウは、直接または間接的に、MFC のサンプル プログラム多く使用します。 MFC 標準サンプル[VIEWEX](../visual-cpp-samples.md)静的分割ウィンドウでスプリッターの分割線を配置する方法などのいくつかの使用を示します。  
  
 新しい複数ドキュメント インターフェイス (MDI) 子フレーム ウィンドウ クラスを含む分割ウィンドウを作成する ClassWizard を行うこともできます。 分割ウィンドウの詳細については、次を参照してください。[複数のドキュメント タイプ、ビュー、およびフレーム ウィンドウ](../mfc/multiple-document-types-views-and-frame-windows.md)します。  
  
## <a name="terminology-used-by-implementation"></a>実装で使用される用語集  
 分割ウィンドウに固有の用語の一覧を次に示します。  
  
 `CSplitterWnd`:  
 ペイン分割コントロールと列または行にすべてのペイン間で共有されるスクロール バーを提供するウィンドウです。 0 から始まる番号を持つ行と列を指定する (行は、最初のウィンドウが 0 と列を = = 0) です。  
  
 ウィンドウ:  
 特定のアプリケーション ウィンドウを`CSplitterWnd`を管理します。 ペインがから派生したオブジェクトでは通常、 [CView クラス](../mfc/reference/cview-class.md)、いずれかを指定できますが、 [CWnd](../mfc/reference/cwnd-class.md)適切な子ウィンドウ ID を持つオブジェクト  
  
 使用する、 `CWnd`-派生オブジェクトを渡す、`RUNTIME_CLASS`するオブジェクトの`CreateView`関数を使用していた場合と同様、 `CView`-クラスを派生します。 クラスを使用する必要があります`DECLARE_DYNCREATE`と`IMPLEMENT_DYNCREATE`フレームワークは、実行時に動的な作成を使用するためです。 多くのコードでが`CSplitterWnd`に固有である、`CView`クラス、[使うため](../mfc/reference/cobject-class.md#iskindof)それらのアクションが実行される前に、は常に使用します。  
  
 分割バー:  
 ペインの行と列の間に配置されるコントロールです。 行のサイズまたはウィンドウの列を調整するために使用する可能性があります。  
  
 分割ボックス:  
 動的コントロール`CSplitterWnd`ペインの新しい行または列の作成を行えます。 または、水平スクロール バーの左側に垂直スクロール バーの上部になります。  
  
 スプリッターの積集合。  
 垂直分割バーと水平分割バーの交差部分です。 同時にウィンドウの列や行のサイズを調整するドラッグすることができます。  
  
## <a name="shared-scroll-bars"></a>共有のスクロール バー  
 `CSplitterWnd`クラスには、共有のスクロール バーもサポートしています。 これらのスクロール バー コントロールの子である、`CSplitterWnd`され、分割ウィンドウの各種ウィンドウを共有します。  
  
 たとえば、1 行 x 2 列ウィンドウを指定できます WS_VSCROLL を作成するとき、`CSplitterWnd`です。 Windows では、2 つのペイン間で共有される特殊なスクロール バー コントロールを作成します。  
  
```  
[      ][      ][^]  
[pane00][pane01][|]  
[      ][      ][v]  
```  
  
 ユーザーが、スクロール バーを移動すると`WM_VSCROLL`メッセージは、両方のビューに送信されます。 スクロール バーの位置を設定すると、いずれかのビューとは、共有のスクロール バーが設定されます。  
  
 共有のスクロール バーが同種のビュー オブジェクトで最も便利なことに注意してください。 分割ウィンドウ内のさまざまな種類のビューを混在している場合は、それらのスクロール位置を調整するための特別なコードを記述する必要があります。 どの`CView`-派生クラスを使用する、`CWnd`スクロール バーが存在する場合は、Api を共有のスクロール バーを委任します。 `CScrollView`実装の 1 つの例では、`CView`をサポートするクラスは、スクロール バーを共有します。 クラスから派生していない`CView`、非コントロールのスクロール バーに依存しているクラスまたは標準の Windows 実装を使用するクラス (たとえば、 `CEditView`) の共有のスクロール バーの機能では動作しません`CSplitterWnd`です。  
  
## <a name="minimum-sizes"></a>最小サイズ  
 行ごとには、各行の高さ、および列ごとには、列の最小幅。 この最小値は、ウィンドウは完全な詳細に表示するのには小さすぎるいないことを保証します。  
  
 静的な分割ウィンドウでは、最初の行の最小の高さと列の幅は 0 です。 によって、動的分割ウィンドウの最初の行の最小の高さと列の幅の設定、`sizeMin`のパラメーター、`CSplitterWnd::Create`関数。  
  
 使用してこれらの最小サイズを変更することができます、 [CSplitterWnd::SetRowInfo](../mfc/reference/csplitterwnd-class.md#setrowinfo)と[CSplitterWnd::SetColumnInfo](../mfc/reference/csplitterwnd-class.md#setcolumninfo)関数。  
  
## <a name="actual-vs-ideal-sizes"></a>実際のサイズと理想的なサイズ  
 分割ウィンドウのペインのレイアウトは、それらを含むフレームのサイズによって異なります。 ユーザーがフレームを変更するときに、`CSplitterWnd`位置を変更して、できるだけ効率よくに収まるように、ウィンドウのサイズを変更します。  
  
 ユーザー手動で設定できる行の高さと列の幅またはプログラムを使用して適切なサイズを設定することができます、`CSplitterWnd`クラスです。 実際のサイズは、理想より小さいか大きいできます。 理想的なサイズを表示するための十分なスペースがない場合、または右または分割ウィンドウの下部の空の領域が多すぎるがある場合、Windows は実際のサイズを調整します。  
  
## <a name="custom-controls"></a>カスタム コントロール  
 動作をカスタマイズし、カスタマイズされたインターフェイスを提供する多くの関数をオーバーライドすることができます。 分割ウィンドウのさまざまなグラフィカル要素の外観を提供するこの最初のセットを上書きすることができます。  
  
- `virtual void OnDrawSpltter(CDC* pDC, ESplitType nType, const CRect& rect);`  
  
- `virtual void OnInvertTracker(const CRect& rect);`  
  
 共有のスクロール バー コントロールを作成するには、この関数を呼び出します。 スクロール バーの横にある余分なコントロールを作成するメソッドをオーバーライドすることができます。  
  
- `virtual BOOL CreateScrollBarCtrl(DWORD dwStyle, UINT nID);`  
  
 これらの関数は、動的分割ウィンドウのロジックを実装します。 高度な分割のロジックを提供するようにそれらをオーバーライドできます。  
  
- `virtual void DeleteView(int row, int col);`  
  
- `virtual BOOL SplitRow(int cyBefore);`  
  
- `virtual BOOL SplitColumn(int cxBefore);`  
  
- `virtual void DeleteRow(int rowDelete);`  
  
- `virtual void DeleteColumn(int colDelete);`  
  
## <a name="cview-functionality"></a>CView 機能  
 `CView`クラスに委任する高レベルの次のコマンドを使用して、`CSplitterWnd`実装します。 これらのコマンドは仮想であるため、標準`CView`実装全体を必要としません`CSplitterWnd`にリンクされている実装します。 使用するアプリケーションの`CView`ではなく`CSplitterWnd`、`CSplitterWnd`実装は、アプリケーションにリンクされません。  
  
 `virtual BOOL CanActivateNext(BOOL bPrev = FALSE);`  
 ID_NEXT_PANE または ID_PREV_PANE が現在可能かどうかを確認します。  
  
 `virtual void ActivateNext(BOOL bPrev = FALSE);`  
 「次のペイン」または「前のペイン」コマンドを実行します。  
  
 `virtual BOOL DoKeyboardSplit();`  
 キーボード分割コマンド、通常「ウィンドウの分割」を実行します。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

