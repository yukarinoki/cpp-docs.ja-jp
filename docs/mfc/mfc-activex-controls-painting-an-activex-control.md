---
title: 'MFC ActiveX コントロール: ActiveX コントロールの描画 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], painting
- MFC ActiveX controls [MFC], optimizing
ms.assetid: 25fff9c0-4dab-4704-aaae-8dfb1065dee3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f7026dd5ffaab04eb445ae68449127e65c772394
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-activex-controls-painting-an-activex-control"></a>MFC ActiveX コントロール : ActiveX コントロールの描画
この記事では、ActiveX コントロールの描画プロセスとプロセスを最適化する描画コードを変更する方法について説明します。 (を参照してください[コントロールの描画の最適化](../mfc/optimizing-control-drawing.md)ないコントロールを個別に描画を最適化する方法の手法が以前に選択した GDI オブジェクトを復元します。 すべてのコントロールの描画されたが、コンテナーが自動的に復元元のオブジェクトです。)  
  
 この記事の例では、既定の設定では、MFC ActiveX コントロール ウィザードによって作成されたコントロールです。 MFC ActiveX コントロール ウィザードを使用してアプリケーションのスケルトンのコントロールを作成する方法の詳細については、記事を参照してください。 [MFC ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)です。  
  
 次のトピックが含まれます。  
  
-   [描画するため、全体的なプロセス、コントロールとコードによって作成された描画をサポートするために、ActiveX コントロール ウィザード](#_core_the_painting_process_of_an_activex_control)  
  
-   [描画プロセスを最適化する方法](#_core_optimizing_your_paint_code)  
  
-   [メタファイルを使ってコントロールを描画する方法](#_core_painting_your_control_using_metafiles)  
  
##  <a name="_core_the_painting_process_of_an_activex_control"></a> ActiveX コントロールの描画プロセス  
 1 つの重要な違いと、MFC を使用して開発された他のアプリケーションのような描画プロセスに従うと ActiveX コントロールが最初に表示されますが再描画される、: ActiveX コントロールがアクティブまたは非アクティブな状態にすることができます。  
  
 アクティブなコントロールは、子ウィンドウで ActiveX コントロール コンテナーで表されます。 他のウィンドウと同様に、それ自体を描画時に、`WM_PAINT`メッセージを受信します。 コントロールの基底クラス、 [COleControl](../mfc/reference/colecontrol-class.md)でメッセージを処理、`OnPaint`関数。 この既定の実装を呼び出す、`OnDraw`コントロールの関数。  
  
 非アクティブなコントロールの描画方法が異なります。 コントロールがアクティブでない場合は、そのウィンドウは非表示、または存在しない場合は、描画メッセージを受け取ることができません。 コントロールのコンテナーを直接呼び出す代わりに、`OnDraw`コントロールの機能です。 これで、アクティブなコントロールの描画のプロセスとは異なります、`OnPaint`メンバー関数が呼び出されることはありません。  
  
 前の段落で説明した、ようは ActiveX コントロールを更新する方法、コントロールの状態に依存します。 ただし、フレームワークが呼び出すため、`OnDraw`メンバー関数は、どちらの場合では、このメンバー関数で描画コードの大部分を追加します。  
  
 `OnDraw`メンバー関数は、コントロールの描画を処理します。 コントロールがアクティブでないときに、コントロール コンテナーを呼び出す`OnDraw`、コントロール コンテナーのデバイス コンテキストと、コントロールで占有される四角形の領域の座標。  
  
 フレームワークによって渡された、四角形、`OnDraw`メンバー関数には、コントロールで占有される領域が含まれています。 左上隅には、コントロールがアクティブである場合 (0, 0) として、コントロールを含む子ウィンドウを渡されたデバイス コンテキスト。 コントロールがアクティブでない場合、左上隅の座標が必ずしも (0, 0) であり、渡されたデバイス コンテキストのコントロールを含むコントロールのコンテナーです。  
  
> [!NOTE]
>  重要ですへの変更`OnDraw`四角形の左上の点に等しくなるに依存しない (0, 0) に渡される四角形の内部でのみを描画することと`OnDraw`です。 予期しない結果は、四角形の領域外に描画する場合に発生することができます。  
  
 MFC ActiveX コントロール ウィザード、コントロール実装ファイル内で提供される既定の実装 (です。CPP) を示す以下、白のブラシを含む四角形を描画し、省略記号を現在の背景色で塗りつぶします。  
  
 [!code-cpp[NVC_MFC_AxUI#1](../mfc/codesnippet/cpp/mfc-activex-controls-painting-an-activex-control_1.cpp)]  
  
> [!NOTE]
>  コントロールを描画する必要がありますいないとして渡されるデバイス コンテキストの状態に関する前提条件、 *pdc*パラメーターを`OnDraw`関数。 場合によってはデバイス コンテキストでは、コンテナー アプリケーションによって提供され、既定の状態には必ずしも初期化されません。 ペン、ブラシ、色、フォント、および描画コードが依存するその他のリソースを明示的に選択具体的には、します。  
  
##  <a name="_core_optimizing_your_paint_code"></a> 描画コードの最適化  
 次の手順を最適化するためには、コントロールが自身を正常に描画は、後に、`OnDraw`関数。  
  
 ActiveX コントロールの描画の既定の実装では、コントロール全体の領域を描画します。 これは単純なコントロールは、のための十分なが多くの場合、コントロールを再描画するは高速更新が必要な部分が再描画される、コントロール全体ではなくだけの場合。  
  
 `OnDraw`関数を渡すことによって最適化の簡単な方法を提供する`rcInvalid`、再描画が必要なコントロールの四角形の領域。 描画プロセスを高速化に通常領域よりも小さければ、コントロール全体、この領域を使用します。  
  
##  <a name="_core_painting_your_control_using_metafiles"></a> メタファイルを使用して、コントロールの描画  
 ほとんどの場合、`pdc`パラメーターを`OnDraw`関数が画面デバイス コンテキスト (DC) を指します。 、または印刷プレビュー セッション中に、コントロールのイメージを印刷する場合に表示するために受信した DC が「メタファイル DC」と呼ばれる特殊な種類です。 送信された要求をすぐに処理するには、画面、DC とは異なりは、メタファイル DC は、後で再生するための要求を格納します。 コンテナー アプリケーションによっては、メタファイル デザイン モードでの DC を使用してコントロールのイメージをレンダリングすることもできます。  
  
 要求を描画するメタファイル使用できる 2 つのインターフェイス関数を使用して、コンテナー: **IViewObject::Draw** (この関数できますも呼び出される非メタファイルの描画の) と**IDataObject::GetData**です。 MFC フレームワークへの呼び出しは、DC は、パラメーターの 1 つとして渡されるメタファイル、ときに[COleControl::OnDrawMetafile](../mfc/reference/colecontrol-class.md#ondrawmetafile)です。 これは、仮想メンバー関数であるため、特別な処理を実行するコントロール クラスのこの関数をオーバーライドします。 既定の動作`COleControl::OnDraw`です。  
  
 画面とメタファイルの両方のデバイス コンテキストで、コントロールに描画できるようにするには、画面とメタファイル DC の両方でサポートされているメンバー関数のみを使用する必要があります。 座標系をピクセル単位で計測いない可能性がありますに注意してください。  
  
 の既定の実装`OnDrawMetafile`コントロールの呼び出し`OnDraw`関数、上書きしない限り、メタファイルと、画面のデバイス コンテキストの両方に適しているメンバー関数のみを使用して`OnDrawMetafile`です。 次の一覧のサブセット`CDC`メタファイルと画面デバイス コンテキストの両方で使用できるメンバー関数。 これらの関数の詳細については、クラスを参照してください。 [CDC](../mfc/reference/cdc-class.md)で、 *『 MFC リファレンス*です。  
  
|円弧|BibBlt|弦|  
|---------|------------|-----------|  
|**楕円**|**Escape**|`ExcludeClipRect`|  
|`ExtTextOut`|`FloodFill`|`IntersectClipRect`|  
|`LineTo`|`MoveTo`|`OffsetClipRgn`|  
|`OffsetViewportOrg`|`OffsetWindowOrg`|`PatBlt`|  
|`Pie`|**多角形**|`Polyline`|  
|`PolyPolygon`|`RealizePalette`|`RestoreDC`|  
|`RoundRect`|`SaveDC`|`ScaleViewportExt`|  
|`ScaleWindowExt`|`SelectClipRgn`|`SelectObject`|  
|`SelectPalette`|`SetBkColor`|`SetBkMode`|  
|`SetMapMode`|`SetMapperFlags`|`SetPixel`|  
|`SetPolyFillMode`|`SetROP2`|`SetStretchBltMode`|  
|`SetTextColor`|`SetTextJustification`|`SetViewportExt`|  
|`SetViewportOrg`|`SetWindowExt`|`SetWindowORg`|  
|`StretchBlt`|`TextOut`||  
  
 加え`CDC`メンバー関数の場合、メタファイル DC に互換性のある他のいくつかの関数があります。 これらを含める[CPalette::AnimatePalette](../mfc/reference/cpalette-class.md#animatepalette)、 [CFont::CreateFontIndirect](../mfc/reference/cfont-class.md#createfontindirect)、および 3 つのメンバー関数の`CBrush`: [CreateBrushIndirect](../mfc/reference/cbrush-class.md#createbrushindirect)、 [構築](../mfc/reference/cbrush-class.md#createdibpatternbrush)、および[とき](../mfc/reference/cbrush-class.md#createpatternbrush)です。  
  
 関数は、メタファイルは記録されません[消去](../mfc/reference/cdc-class.md#drawfocusrect)、 [DrawIcon](../mfc/reference/cdc-class.md#drawicon)、 [DrawText](../mfc/reference/cdc-class.md#drawtext)、 [ExcludeUpdateRgn](../mfc/reference/cdc-class.md#excludeupdatergn)、 [。FillRect](../mfc/reference/cdc-class.md#fillrect)、 [FrameRect](../mfc/reference/cdc-class.md#framerect)、[とき](../mfc/reference/cdc-class.md#graystring)、 [InvertRect](../mfc/reference/cdc-class.md#invertrect)、 [ScrollDC](../mfc/reference/cdc-class.md#scrolldc)、および[TabbedTextOut](../mfc/reference/cdc-class.md#tabbedtextout)です。 メタファイル DC には実際には、デバイスに関連付けられていないためには、メタファイル DC を SetDIBits、GetDIBits、および CreateDIBitmap を使用できません。 エクスポート先として、SetDIBitsToDevice と StretchDIBits をメタファイル DC を使用できます。 [CreateCompatibleDC](../mfc/reference/cdc-class.md#createcompatibledc)、[ビットマップ](../mfc/reference/cbitmap-class.md#createcompatiblebitmap)、および[CreateDiscardableBitmap](../mfc/reference/cbitmap-class.md#creatediscardablebitmap)メタファイル DC で意味がありません。  
  
 メタファイル DC を使用する際に考慮する別のポイントは、座標系をピクセル単位で計測いない可能性があります。 この理由により、四角形に収まるように、描画コードを調整する必要がありますすべてに渡されます`OnDraw`で、`rcBounds`パラメーター。 これにより、コントロール外の描画、ため`rcBounds`コントロールのウィンドウのサイズを表します。  
  
 コントロールのレンダリングをメタファイルを実装した後は、テスト コンテナーを使用して、メタファイルをテストします。 Test Container にアクセスする方法について詳しくは、「 [テスト コンテナーでのプロパティとイベントのテスト](../mfc/testing-properties-and-events-with-test-container.md) 」をご覧ください。  
  
#### <a name="to-test-the-controls-metafile-using-test-container"></a>テスト コンテナーを使用して、コントロールのメタファイルをテストするには  
  
1.  テスト コンテナーの **[編集]** メニューのをクリックして**新しいコントロールを挿入**です。  
  
2.  **新しいコントロールを挿入**ボックス コントロールを選択し、をクリックして**OK**です。  
  
     コントロールは、テスト コンテナーに表示されます。  
  
3.  **コントロール** メニューのをクリックして**を描画するメタファイル**です。  
  
     メタファイルを表示する別のウィンドウが表示されます。 スケーリングがコントロールのメタファイルに与える影響を確認するには、このウィンドウのサイズを変更することができます。 このウィンドウは、いつでも閉じることができます。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

