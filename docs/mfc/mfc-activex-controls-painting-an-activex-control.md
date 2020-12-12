---
description: '詳細については、「MFC ActiveX コントロール: ActiveX コントロールの描画」を参照してください。'
title: 'MFC ActiveX コントロール : ActiveX コントロールの描画'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], painting
- MFC ActiveX controls [MFC], optimizing
ms.assetid: 25fff9c0-4dab-4704-aaae-8dfb1065dee3
ms.openlocfilehash: d9e6fb23deb701e32f1af6ff4bf4d79c7d9df085
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305274"
---
# <a name="mfc-activex-controls-painting-an-activex-control"></a>MFC ActiveX コントロール : ActiveX コントロールの描画

この記事では、ActiveX コントロールの描画プロセスについて説明します。また、描画コードを変更してプロセスを最適化する方法についても説明します。 (前に選択した GDI オブジェクトを個別に復元するコントロールがないようにして、描画を最適化する方法については、「 [コントロールの描画の最適化](optimizing-control-drawing.md) 」を参照してください。 すべてのコントロールが描画された後、コンテナーは元のオブジェクトを自動的に復元できます)。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX を置き換える最新テクノロジの詳細については、「 [Activex コントロール](activex-controls.md)」を参照してください。

この記事の例は、MFC ActiveX コントロールウィザードで既定の設定を使用して作成されたコントロールからのものです。 MFC ActiveX コントロールウィザードを使用してスケルトンコントロールアプリケーションを作成する方法の詳細については、 [Mfc Activex コントロールウィザード](reference/mfc-activex-control-wizard.md)に関する記事を参照してください。

次のトピックが含まれています。

- [描画をサポートするために、コントロールと ActiveX コントロールウィザードによって作成されたコードを描画するための全体的なプロセス](#_core_the_painting_process_of_an_activex_control)

- [描画プロセスを最適化する方法](#_core_optimizing_your_paint_code)

- [方法: メタファイルを使用してコントロールを描画する](#_core_painting_your_control_using_metafiles)

## <a name="the-painting-process-of-an-activex-control"></a><a name="_core_the_painting_process_of_an_activex_control"></a> ActiveX コントロールの描画プロセス

ActiveX コントロールは、最初に表示されるとき、または再描画されるときに、MFC を使用して開発された他のアプリケーションと同様の描画プロセスに従います。重要な違いとして、ActiveX コントロールはアクティブまたは非アクティブの状態になることがあります。

アクティブなコントロールは、子ウィンドウによって ActiveX コントロールコンテナーに表示されます。 他のウィンドウと同様に、WM_PAINT メッセージを受信したときに自身を描画します。 コントロールの基本クラスである [COleControl](reference/colecontrol-class.md)は、このメッセージを関数で処理 `OnPaint` します。 この既定の実装は、 `OnDraw` コントロールの関数を呼び出します。

非アクティブなコントロールは、異なる方法で描画されます。 コントロールが非アクティブになると、ウィンドウは非表示になるか存在しないため、描画メッセージを受信できません。 代わりに、コントロールコンテナーは `OnDraw` コントロールの関数を直接呼び出します。 これは、メンバー関数が呼び出されないという点で、アクティブなコントロールの描画プロセスとは異なり `OnPaint` ます。

前の段落で説明したように、ActiveX コントロールがどのように更新されるかは、コントロールの状態によって異なります。 ただし、フレームワークは、どちらの場合もメンバー関数を呼び出すため、 `OnDraw` このメンバー関数に描画コードの大部分を追加します。

この `OnDraw` メンバー関数は、コントロールの描画を処理します。 コントロールが非アクティブになると、コントロールコンテナーは `OnDraw` を呼び出し、コントロールコンテナーのデバイスコンテキストと、コントロールによって占有される四角形領域の座標を渡します。

フレームワークによってメンバー関数に渡される四角形には、 `OnDraw` コントロールによって占有される領域が含まれます。 コントロールがアクティブな場合、左上隅は (0, 0) で、渡されたデバイスコンテキストは、コントロールを含む子ウィンドウ用です。 コントロールが非アクティブである場合、左上の座標は必ずしも (0, 0) ではなく、渡されたデバイスコンテキストはコントロールを含むコントロールコンテナーを示します。

> [!NOTE]
> 変更が必要になるのは、 `OnDraw` 四角形の左上の位置が (0, 0) であり、に渡された四角形の内部だけであることが重要です `OnDraw` 。 四角形の領域を超えて描画すると、予期しない結果が発生することがあります。

コントロール実装ファイル () の MFC ActiveX コントロールウィザードによって提供される既定の実装。CPP) は、次に示すように、四角形を白のブラシで塗りつぶし、楕円に現在の背景色を設定します。

[!code-cpp[NVC_MFC_AxUI#1](codesnippet/cpp/mfc-activex-controls-painting-an-activex-control_1.cpp)]

> [!NOTE]
> コントロールを描画するときに、 *pdc* パラメーターとして関数に渡されるデバイスコンテキストの状態について、想定しないでください `OnDraw` 。 場合によっては、デバイスコンテキストがコンテナーアプリケーションによって提供され、必ずしも既定の状態に初期化されるとは限りません。 特に、描画コードが依存しているペン、ブラシ、色、フォント、およびその他のリソースを明示的に選択します。

## <a name="optimizing-your-paint-code"></a><a name="_core_optimizing_your_paint_code"></a> 描画コードの最適化

コントロールが正常に描画された後、次の手順は関数を最適化することです `OnDraw` 。

ActiveX コントロールの描画の既定の実装では、コントロール領域全体が描画されます。 これは単純なコントロールには十分ですが、コントロール全体ではなく、更新が必要な部分だけが再描画された場合は、多くの場合、コントロールの再描画が高速になります。

関数は、再 `OnDraw` 描画が必要なコントロールの四角形の領域である *rcinvalid* を渡すことによって、簡単な最適化方法を提供します。 描画プロセスを高速化するために、通常はコントロール領域全体より小さいこの領域を使用します。

## <a name="painting-your-control-using-metafiles"></a><a name="_core_painting_your_control_using_metafiles"></a> メタファイルを使用したコントロールの描画

ほとんどの場合、関数の *pdc* パラメーターは、 `OnDraw` 画面デバイスコンテキスト (DC) を指しています。 ただし、コントロールのイメージを印刷するとき、または印刷プレビューセッション中に、レンダリングのために受信した DC は、"メタファイル DC" と呼ばれる特殊な型になります。 送信された要求をすぐに処理する画面 DC とは異なり、メタファイル DC は後で再生する要求を格納します。 一部のコンテナーアプリケーションでは、デザインモードでメタファイル DC を使用してコントロールイメージを表示することもできます。

メタファイル描画要求は、コンテナーによって、2つのインターフェイス関数 `IViewObject::Draw` (この関数はメタファイル以外の描画にも呼び出すことができます) およびを使用して作成できます。 `IDataObject::GetData` メタファイル DC をパラメーターの1つとして渡すと、MFC フレームワークによって、 [COleControl:: OnDrawMetafile](reference/colecontrol-class.md#ondrawmetafile)が呼び出されます。 これは仮想メンバー関数であるため、特別な処理を実行するには、コントロールクラスのこの関数をオーバーライドします。 既定の動作では、が呼び出さ `COleControl::OnDraw` れます。

コントロールを画面とメタファイルの両方のデバイスコンテキストで描画できるようにするには、画面とメタファイル DC の両方でサポートされているメンバー関数だけを使用する必要があります。 座標系はピクセル単位では測定されない場合があることに注意してください。

の既定の実装は `OnDrawMetafile` コントロールの関数を呼び出すため、を `OnDraw` オーバーライドする場合を除き、メタファイルと画面デバイスコンテキストの両方に適したメンバー関数だけを使用し `OnDrawMetafile` ます。 `CDC`メタファイルと画面デバイスコンテキストの両方で使用できるメンバー関数のサブセットを次に示します。 これらの関数の詳細については、「 *MFC リファレンス*」の「クラス [CDC](reference/cdc-class.md) 」を参照してください。

|Arc|BibBlt|Chord|
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

`CDC`メンバー関数に加えて、メタファイル DC で互換性のある他のいくつかの関数があります。 これには、 [CPalette:: AnimatePalette](reference/cpalette-class.md#animatepalette)、 [CFont:: createfontindirect](reference/cfont-class.md#createfontindirect)、および `CBrush` [CreateBrushIndirect](reference/cbrush-class.md#createbrushindirect)、 [Createdibpattern brush](reference/cbrush-class.md#createdibpatternbrush)、および [createpattern brush](reference/cbrush-class.md#createpatternbrush)の3つのメンバー関数が含まれます。

メタファイルに記録されていない関数は、 [DrawFocusRect](reference/cdc-class.md#drawfocusrect)、 [drawicon](reference/cdc-class.md#drawicon)、 [DrawText](reference/cdc-class.md#drawtext)、 [ExcludeUpdateRgn](reference/cdc-class.md#excludeupdatergn)、 [fillrect](reference/cdc-class.md#fillrect)、 [FrameRect](reference/cdc-class.md#framerect)、 [GrayString](reference/cdc-class.md#graystring)、 [invertrect](reference/cdc-class.md#invertrect)、 [scrolldc](reference/cdc-class.md#scrolldc)、および [TabbedTextOut](reference/cdc-class.md#tabbedtextout)です。 メタファイル DC は実際にはデバイスに関連付けられていないため、メタファイル DC で SetDIBits、GetDIBits、CreateDIBitmap を使用することはできません。 SetDIBitsToDevice と StretchDIBits を、メタファイル DC と共にコピー先として使用できます。 [CreateCompatibleDC](reference/cdc-class.md#createcompatibledc)、 [CreateCompatibleBitmap](reference/cbitmap-class.md#createcompatiblebitmap)、および [CREATEDISCARDABLEBITMAP](reference/cbitmap-class.md#creatediscardablebitmap) は、メタファイル DC では意味がありません。

メタファイル DC を使用するときに考慮するもう1つの点は、座標系がピクセル単位で測定されないことです。 このため、 `OnDraw` *rcbounds* パラメーターでに渡される四角形に合わせて、すべての描画コードを調整する必要があります。 これにより、 *Rcbounds* はコントロールのウィンドウのサイズを表すため、コントロールの外に誤って描画されるのを防ぎます。

コントロールのメタファイルレンダリングを実装したら、テストコンテナーを使用してメタファイルをテストします。 Test Container にアクセスする方法について詳しくは、「 [テスト コンテナーでのプロパティとイベントのテスト](testing-properties-and-events-with-test-container.md) 」をご覧ください。

#### <a name="to-test-the-controls-metafile-using-test-container"></a>テストコンテナーを使用してコントロールのメタファイルをテストするには

1. テストコンテナーの [ **編集** ] メニューで、[ **新しいコントロールの挿入**] をクリックします。

1. [ **新しいコントロールの挿入** ] ボックスで、コントロールを選択し、[ **OK]** をクリックします。

   コントロールがテストコンテナーに表示されます。

1. [ **コントロール** ] メニューの [ **メタファイルの描画**] をクリックします。

   別のウィンドウが表示され、メタファイルが表示されます。 このウィンドウのサイズを変更して、スケーリングがコントロールのメタファイルに与える影響を確認できます。 このウィンドウはいつでも閉じることができます。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)
