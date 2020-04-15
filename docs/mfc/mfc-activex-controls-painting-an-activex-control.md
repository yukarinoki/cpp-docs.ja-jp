---
title: 'MFC ActiveX コントロール : ActiveX コントロールの描画'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], painting
- MFC ActiveX controls [MFC], optimizing
ms.assetid: 25fff9c0-4dab-4704-aaae-8dfb1065dee3
ms.openlocfilehash: fd98af90e86b6b98a856e633e50c5bf266cc466a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364580"
---
# <a name="mfc-activex-controls-painting-an-activex-control"></a>MFC ActiveX コントロール : ActiveX コントロールの描画

この資料では、ActiveX コントロールの描画プロセスについて説明し、ペイント コードを変更してプロセスを最適化する方法について説明します。 (コントロールを個別に復元しない、描画を最適化する方法については、「[コントロール描画の最適化](../mfc/optimizing-control-drawing.md)」を参照してください。 すべてのコントロールが描画された後、コンテナは自動的に元のオブジェクトを復元できます。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX に取って代わる最新テクノロジの詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

この資料の例は、MFC ActiveX コントロール ウィザードで作成されたコントロールの既定の設定です。 MFC ActiveX コントロール ウィザードを使用してスケルトン コントロール アプリケーションを作成する方法の詳細については[、「MFC ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)」を参照してください。

次のトピックが含まれています。

- [コントロールを描画するための全体的なプロセスと、描画をサポートするために ActiveX コントロール ウィザードによって作成されたコード](#_core_the_painting_process_of_an_activex_control)

- [塗装プロセスを最適化する方法](#_core_optimizing_your_paint_code)

- [メタファイルを使用してコントロールを描画する方法](#_core_painting_your_control_using_metafiles)

## <a name="the-painting-process-of-an-activex-control"></a><a name="_core_the_painting_process_of_an_activex_control"></a>ActiveX コントロールの描画プロセス

ActiveX コントロールが最初に表示されるか再描画されるとき、MFC を使用して開発された他のアプリケーションと同様の描画プロセスに従います。

ActiveX コントロール コンテナーでは、アクティブ なコントロールは子ウィンドウによって表されます。 他のウィンドウと同様に、WM_PAINTメッセージを受信したときに、それ自体を描画する役割があります。 コントロールの基本クラスである[COleControl](../mfc/reference/colecontrol-class.md)は、このメッセージを`OnPaint`その関数で処理します。 この既定の実装では`OnDraw`、コントロールの関数を呼び出します。

非アクティブなコントロールは、別の方法で描画されます。 コントロールが非アクティブの場合、そのウィンドウは非表示または存在しないのいずれかであるため、描画メッセージを受信できません。 代わりに、コントロール コンテナーはコントロール`OnDraw`の関数を直接呼び出します。 これは、`OnPaint`アクティブ コントロールの描画プロセスとは異なり、メンバー関数が呼び出されることはありません。

前の段落で説明したように、ActiveX コントロールの更新方法は、コントロールの状態によって異なります。 ただし、フレームワークはどちらの場合も`OnDraw`メンバー関数を呼び出すため、このメンバー関数に描画コードの大部分を追加します。

メンバー`OnDraw`関数は、コントロールの描画を処理します。 コントロールが非アクティブの場合、コントロール コンテナーは`OnDraw`、コントロール コンテナーのデバイス コンテキストと、コントロールが占有する四角形領域の座標を渡して呼び出します。

フレームワークによってメンバー関数に渡される四`OnDraw`角形には、コントロールが占有する領域が含まれます。 コントロールがアクティブな場合、左上隅は (0, 0) になり、渡されるデバイス コンテキストはコントロールを含む子ウィンドウの場合です。 コントロールが非アクティブの場合、左上の座標は必ずしも (0, 0) ではなく、渡されるデバイス コンテキストはコントロールを含むコントロール コンテナーの座標です。

> [!NOTE]
> 変更`OnDraw`は、四角形の左上の点が (0, 0) に等しく、渡された四角形の内側にのみ描画するように変更することが重要です`OnDraw`。 四角形の領域を超えて描画すると、予期しない結果が生じる可能性があります。

MFC ActiveX コントロール ウィザードがコントロール実装ファイル (.CPP)を示す)は、白いブラシで長方形を描画し、現在の背景色で楕円を塗りつぶします。

[!code-cpp[NVC_MFC_AxUI#1](../mfc/codesnippet/cpp/mfc-activex-controls-painting-an-activex-control_1.cpp)]

> [!NOTE]
> コントロールを描画する場合は、`OnDraw`関数に*pdc*パラメーターとして渡されるデバイス コンテキストの状態について想定しないでください。 デバイス コンテキストはコンテナー アプリケーションによって提供され、必ずしも既定の状態に初期化されるとは限りません。 特に、描画コードが依存するペン、ブラシ、色、フォント、およびその他のリソースを明示的に選択します。

## <a name="optimizing-your-paint-code"></a><a name="_core_optimizing_your_paint_code"></a>ペイントコードの最適化

コントロールが正常に描画されたら、次の手順は関数を`OnDraw`最適化することです。

ActiveX コントロールペイントの既定の実装では、コントロール領域全体が描画されます。 単純なコントロールではこれで十分ですが、多くの場合、コントロール全体ではなく、更新が必要な部分だけを再描画した場合は、コントロールの再描画が高速になります。

この`OnDraw`関数は、再描画が必要なコントロールの四角形領域*である rcInvalid*を渡すことで、簡単に最適化を行うことができます。 この領域は、通常、コントロール領域全体よりも小さい領域を使用して、塗装プロセスを高速化します。

## <a name="painting-your-control-using-metafiles"></a><a name="_core_painting_your_control_using_metafiles"></a>メタファイルを使用したコントロールの描画

ほとんどの場合、関数の*pdc* `OnDraw`パラメーターは、画面デバイス コンテキスト (DC) を指します。 ただし、コントロールのイメージを印刷するとき、または印刷プレビュー セッション中に、レンダリング用に受信した DC は、"メタファイル DC" と呼ばれる特殊な型です。 直ちに送信された要求を処理する画面 DC とは異なり、メタファイル DC は後で再生する要求を格納します。 一部のコンテナー アプリケーションでは、デザイン モードのときに、メタファイル DC を使用してコントロール イメージをレンダリングすることもできます。

メタファイルの描画要求は、コンテナが 2 つのインタフェース関数`IViewObject::Draw`(この関数は非メタファイル描画に対して呼び出すこともできます`IDataObject::GetData`)と を通じて行うことができます。 メタファイル DC がパラメーターの 1 つとして渡されると、MFC フレームワークは[COleControl::OnDrawMetafile](../mfc/reference/colecontrol-class.md#ondrawmetafile)を呼び出します。 これは仮想メンバー関数であるため、コントロール クラスでこの関数をオーバーライドして、特別な処理を行います。 既定の動作では`COleControl::OnDraw`、 が呼び出されます。

コントロールを画面とメタファイルの両方のデバイス コンテキストで描画できるようにするには、画面とメタファイル DC の両方でサポートされているメンバー関数のみを使用する必要があります。 座標系はピクセル単位で測定されない場合があります。

コントロールの`OnDrawMetafile``OnDraw`関数を呼び出す既定の実装では、オーバーライド`OnDrawMetafile`しない限り、メタファイルと画面デバイス コンテキストの両方に適したメンバー関数のみを使用します。 メタファイルと画面デバイス`CDC`コンテキストの両方で使用できるメンバー関数のサブセットを次に示します。 これらの関数の詳細については、「MFC リファレンス」の[クラス CDC](../mfc/reference/cdc-class.md)を*参照してください*。

|Arc|ビブブレット|Chord|
|---------|------------|-----------|
|`Ellipse`|`Escape`|`ExcludeClipRect`|
|`ExtTextOut`|`FloodFill`|`IntersectClipRect`|
|`LineTo`|`MoveTo`|`OffsetClipRgn`|
|`OffsetViewportOrg`|`OffsetWindowOrg`|`PatBlt`|
|`Pie`|`Polygon`|`Polyline`|
|`PolyPolygon`|`RealizePalette`|`RestoreDC`|
|`RoundRect`|`SaveDC`|`ScaleViewportExt`|
|`ScaleWindowExt`|`SelectClipRgn`|`SelectObject`|
|`SelectPalette`|`SetBkColor`|`SetBkMode`|
|`SetMapMode`|`SetMapperFlags`|`SetPixel`|
|`SetPolyFillMode`|`SetROP2`|`SetStretchBltMode`|
|`SetTextColor`|`SetTextJustification`|`SetViewportExt`|
|`SetViewportOrg`|`SetWindowExt`|`SetWindowORg`|
|`StretchBlt`|`TextOut`||

メンバー関数に`CDC`加えて、メタファイル DC で互換性のある関数がいくつかあります。 これには[、CPalette::アニメーションパレット](../mfc/reference/cpalette-class.md#animatepalette)[、Cフォント::フォントインダイレクト](../mfc/reference/cfont-class.md#createfontindirect)`CBrush`の[作成](../mfc/reference/cbrush-class.md#createbrushindirect)、および3つのメンバー関数が含[まれます。](../mfc/reference/cbrush-class.md#createpatternbrush) [CreateDIBPatternBrush](../mfc/reference/cbrush-class.md#createdibpatternbrush)

メタファイルに記録されない関数[ScrollDC](../mfc/reference/cdc-class.md#scrolldc)は、[FillRect](../mfc/reference/cdc-class.md#fillrect)[InvertRect](../mfc/reference/cdc-class.md#invertrect)[次](../mfc/reference/cdc-class.md#drawfocusrect)の例[FrameRect](../mfc/reference/cdc-class.md#framerect)[のとおりです。](../mfc/reference/cdc-class.md#tabbedtextout) [DrawIcon](../mfc/reference/cdc-class.md#drawicon) [DrawText](../mfc/reference/cdc-class.md#drawtext) [ExcludeUpdateRgn](../mfc/reference/cdc-class.md#excludeupdatergn) [GrayString](../mfc/reference/cdc-class.md#graystring) メタファイル DC は実際にはデバイスに関連付けられていないため、メタファイル DC で SetDIBits、GetDIBits、および CreateDIBitmap を使用することはできません。 メタファイル DC を宛先として使用できます。 [メタファイル](../mfc/reference/cdc-class.md#createcompatibledc)DC では、互換性のある DC の作成 、[互換性のあるビットマップ](../mfc/reference/cbitmap-class.md#createcompatiblebitmap)の作成、および[破棄可能なビットマップ](../mfc/reference/cbitmap-class.md#creatediscardablebitmap)は意味がありません。

メタファイル DC を使用する場合に考慮すべきもう 1 つの点は、座標系がピクセル単位で測定されない場合があります。 このため、すべての描画コードは *、rcBounds*パラメーターに渡される四角形に`OnDraw`収まるように調整する必要があります。 *これにより、rcBounds*はコントロールのウィンドウのサイズを表すため、コントロールの外部での誤った描画を防ぐことができます。

コントロールのメタファイルレンダリングを実装したら、テストコンテナを使用してメタファイルをテストします。 Test Container にアクセスする方法について詳しくは、「 [テスト コンテナーでのプロパティとイベントのテスト](../mfc/testing-properties-and-events-with-test-container.md) 」をご覧ください。

#### <a name="to-test-the-controls-metafile-using-test-container"></a>テスト コンテナーを使用してコントロールのメタファイルをテストするには

1. テスト コンテナの **[編集]** メニューの [**新しいコントロールの挿入**] をクリックします。

1. [**新しいコントロールの挿入**] ボックスでコントロールを選択し **、[OK]** をクリックします。

   コントロールはテスト コンテナーに表示されます。

1. [**コントロール**] メニューの [**メタファイルの作成**] をクリックします。

   メタファイルが表示される別のウィンドウが表示されます。 このウィンドウのサイズを変更して、スケーリングがコントロールのメタファイルに与える影響を確認できます。 このウィンドウはいつでも閉じてもらえます。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)
