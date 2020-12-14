---
description: '詳細については、「テクニカルノート 29: Splitter Windows」を参照してください。'
title: 'テクニカル ノート 29: 分割ウィンドウ'
ms.date: 11/04/2016
f1_keywords:
- vc.windows.splitter
helpviewer_keywords:
- TN029
- splitter windows [MFC], about splitter windows
ms.assetid: 2c57ce99-2a3c-4eff-9cea-baccb13af075
ms.openlocfilehash: e1079adf403b64aa47f5aae00aa32f7da702ddcf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215639"
---
# <a name="tn029-splitter-windows"></a>テクニカル ノート 29: 分割ウィンドウ

このメモでは、ウィンドウ分割を提供し、他のペインウィンドウのサイズ変更を管理する MFC [CSplitterWnd クラス](../mfc/reference/csplitterwnd-class.md)について説明します。

## <a name="splitter-styles"></a>スプリッターのスタイル

は、 `CSplitterWnd` 分割ウィンドウの2つの異なるスタイルをサポートしています。

"静的スプリッター" では、分割ウィンドウの作成時にペインが作成されます。 ペインの順序と数が変更されることはありません。 分割バーは、さまざまなペインのサイズを変更するために使用します。 このスタイルを使用して、各ペインに異なるビュークラスを表示できます。 このスプリッタースタイルを使用するプログラムの例として、Visual C++ グラフィックエディターと Windows ファイルマネージャーがあります。 このスタイルのスプリッターウィンドウでは、スプリッターボックスは使用されません。

"動的スプリッター" では、ユーザーが新しいビューを分割および分割解除するときに、追加のペインが作成され、破棄されます。 このスプリッターは、1つのビューから開始し、ユーザーが分割を開始するためのスプリッターボックスを提供します。 分割ウィンドウでは、ビューが一方向に分割されると、新しいビューオブジェクトが動的に作成されます。 この新しいビューオブジェクトは、新しいペインを表します。 キーボードインターフェイスを使用してビューが2方向に分割されている場合は、3つの新しいペイン用に3つの新しいビューオブジェクトが分割ウィンドウによって作成されます。 分割がアクティブになっている間、ウィンドウの間にスプリッターバーとしてスプリッターボックスが表示されます。 ユーザーが分割を解除すると、Windows によって追加のビューオブジェクトが破棄されますが、元のビューは分割ウィンドウ自体が破棄されるまで残ります。 動的スプリッタースタイルを使用するアプリケーションの例として、microsoft Excel と Microsoft Word があります。

どちらの種類の分割ウィンドウを作成する場合でも、スプリッターが管理する行と列の最大数を指定する必要があります。 静的スプリッターでは、すべての行と列を埋めるためのペインが作成されます。 動的スプリッターは、の作成時に最初のペインだけを作成し `CSplitterWnd` ます。

静的スプリッターに指定できるペインの最大数は、16行の列です。 推奨される構成は次のとおりです。

- 1行 x 2 列: 通常は異なるペインがある

- 2行 x 1 列: 通常は異なるペインがある

- 2行 x 2 列: 通常は同様のペインがある

動的スプリッターに指定できるペインの最大数は、2列 (2 行) です。 推奨される構成は次のとおりです。

- 1行 x 2 列: 単票形式データ用

- 2行 x 1 列: テキストまたはその他のデータ用

- 2行 x 2 列: グリッドまたはテーブル指向データ用

## <a name="splitter-examples"></a>スプリッターの例

MFC サンプルプログラムの多くは、スプリッターウィンドウを直接または間接的に使用します。 MFC の一般的なサンプル [VIEWEX](../overview/visual-cpp-samples.md) では、分割線をスプリッターに配置する方法など、静的スプリッターのいくつかの用途を示しています。

また、ClassWizard を使用して、スプリッターウィンドウを含む新しいマルチドキュメントインターフェイス (MDI) 子フレームウィンドウクラスを作成することもできます。 分割ウィンドウの詳細については、「 [複数のドキュメントの種類、ビュー、フレームウィンドウ](../mfc/multiple-document-types-views-and-frame-windows.md)」を参照してください。

## <a name="terminology-used-by-implementation"></a>実装で使用される用語

スプリッターウィンドウに固有の用語の一覧を次に示します。

`CSplitterWnd`: 行または列のすべてのペイン間で共有されるペイン分割コントロールとスクロールバーを提供するウィンドウ。 0から始まる行と列を指定します (最初のペインは row = 0、column = 0)。

ウィンドウ: が管理するアプリケーション固有のウィンドウ。 `CSplitterWnd` 通常、ペインは、 [CView クラス](../mfc/reference/cview-class.md)から派生したオブジェクトですが、適切な子ウィンドウ ID を持つ任意の [CWnd](../mfc/reference/cwnd-class.md) オブジェクトを指定できます。

派生オブジェクトを使用するには、 `CWnd` `CreateView` から派生したクラスを使用する場合と同様に、オブジェクトの RUNTIME_CLASS を関数に渡し `CView` ます。 フレームワークは実行時に動的作成を使用するため、クラスは DECLARE_DYNCREATE と IMPLEMENT_DYNCREATE を使用する必要があります。 クラスに固有のコードは多数あり `CSplitterWnd` `CView` ますが、これらのアクションが実行される前に [CObject:: IsKindOf](../mfc/reference/cobject-class.md#iskindof) が常に使用されます。

分割バー: ペインの行と列の間に配置されるコントロールです。 これは、ペインの行または列のサイズを調整するために使用できます。

スプリッターボックス: 動的なコントロールで、 `CSplitterWnd` 新しい行またはペインの列を作成できます。 垂直スクロールバーの上部または水平スクロールバーの左側にあります。

分割線集合: 垂直分割バーと水平分割バーの交差部分。 ドラッグすると、ペインの行と列のサイズを同時に調整できます。

## <a name="shared-scroll-bars"></a>共有スクロールバー

クラスは、 `CSplitterWnd` 共有スクロールバーもサポートしています。 これらのスクロールバーコントロールはの子であり、 `CSplitterWnd` スプリッターのさまざまなペインで共有されます。

たとえば、1行 x 2 列ウィンドウでは、を作成するときに WS_VSCROLL を指定でき `CSplitterWnd` ます。 Windows によって、2つのペイン間で共有される特殊なスクロールバーコントロールが作成されます。

```
[      ][      ][^]
[pane00][pane01][|]
[      ][      ][v]
```

ユーザーがスクロールバーを移動すると、WM_VSCROLL メッセージが両方のビューに送信されます。 どちらかのビューがスクロールバーの位置を設定すると、共有スクロールバーが設定されます。

共有スクロールバーは、類似したビューオブジェクトで最も役に立ちます。 分割線で異なる種類のビューを混在させる場合、スクロール位置を調整するための特殊なコードを記述することが必要になる場合があります。 `CView`スクロールバーの api を使用する派生クラス `CWnd` は、存在する場合は共有スクロールバーに委任されます。 の `CScrollView` 実装は、 `CView` 共有スクロールバーをサポートするクラスの一例です。 から派生していないクラス `CView` 、非コントロールのスクロールバーに依存するクラス、または標準の Windows 実装を使用するクラス (など) は、 `CEditView` の共有スクロールバー機能では動作しません `CSplitterWnd` 。

## <a name="minimum-sizes"></a>最小サイズ

行ごとに、行の高さの最小値があり、各列には列の幅の最小値があります。 これにより、ペインが小さすぎて完全な詳細情報を表示できなくなります。

静的スプリッターウィンドウでは、行の初期の最小の高さと列の幅が0になります。 動的分割ウィンドウの場合、行の初期の最小の高さと列の幅は、関数の *sizeMin* パラメーターによって設定され `CSplitterWnd::Create` ます。

これらの最小サイズを変更するには、 [CSplitterWnd:: SetRowInfo](../mfc/reference/csplitterwnd-class.md#setrowinfo) 関数と [CSplitterWnd:: SetColumnInfo](../mfc/reference/csplitterwnd-class.md#setcolumninfo) 関数を使用します。

## <a name="actual-vs-ideal-sizes"></a>実際のサイズと理想的なサイズ

スプリッターウィンドウのペインのレイアウトは、分割ウィンドウが含まれているフレームのサイズによって異なります。 ユーザーがコンテナーフレームのサイズを変更すると、では、可能な限り、ウィンドウの位置が変更され、サイズが変更され `CSplitterWnd` ます。

ユーザーは、行の高さと列の幅のサイズを手動で設定できます。また、プログラムはクラスを使用して理想的なサイズを設定でき `CSplitterWnd` ます。 実際のサイズは、最適なサイズより小さくしたり、大きくしたりすることができます。 最適なサイズを表示するのに十分な空き領域がない場合や、スプリッターウィンドウの右側または下部に空き領域が大きくない場合は、ウィンドウによって実際のサイズが調整されます。

## <a name="custom-controls"></a>カスタム コントロール

多くの関数をオーバーライドして、カスタマイズされた動作やカスタマイズされたインターフェイスを提供できます。 この最初のセットを上書きして、スプリッターウィンドウのさまざまなグラフィカルコンポーネントに別の画像を提供することができます。

- `virtual void OnDrawSpltter(CDC* pDC, ESplitType nType, const CRect& rect);`

- `virtual void OnInvertTracker(const CRect& rect);`

この関数を呼び出して、共有スクロールバーコントロールを作成します。 これをオーバーライドして、スクロールバーの横に追加のコントロールを作成できます。

- `virtual BOOL CreateScrollBarCtrl(DWORD dwStyle, UINT nID);`

これらの関数は、動的分割ウィンドウのロジックを実装します。 これらをオーバーライドして、より高度なスプリッターロジックを提供できます。

- `virtual void DeleteView(int row, int col);`

- `virtual BOOL SplitRow(int cyBefore);`

- `virtual BOOL SplitColumn(int cxBefore);`

- `virtual void DeleteRow(int rowDelete);`

- `virtual void DeleteColumn(int colDelete);`

## <a name="cview-functionality"></a>CView の機能

クラスは、 `CView` 次の高レベルのコマンドを使用して実装に委任し `CSplitterWnd` ます。 これらのコマンドは仮想であるため、標準の `CView` 実装では、の実装全体をリンクする必要はありません `CSplitterWnd` 。 を使用するアプリケーションの場合 `CView` `CSplitterWnd` 、 `CSplitterWnd` 実装はアプリケーションとリンクされません。

- `virtual BOOL CanActivateNext(BOOL bPrev = FALSE);`

   ID_NEXT_PANE または ID_PREV_PANE が現在可能かどうかを確認します。

- `virtual void ActivateNext(BOOL bPrev = FALSE);`

   "次のペイン" または "前のペイン" コマンドを実行します。

- `virtual BOOL DoKeyboardSplit();`

   キーボード分割コマンドを実行します。通常は "ウィンドウ分割" です。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
