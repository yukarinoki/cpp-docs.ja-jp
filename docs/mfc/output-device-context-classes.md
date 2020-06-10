---
title: 出力 (デバイス コンテキスト) クラス
ms.date: 11/04/2016
f1_keywords:
- vc.classes.output
helpviewer_keywords:
- device contexts [MFC], classes
- screen output classes [MFC]
- printing classes [MFC]
- window drawing classes [MFC]
- painting classes [MFC]
- output classes [MFC]
ms.assetid: 35fd6435-a38e-42c6-a3fa-cd6f39370fc3
ms.openlocfilehash: b15f5034604f9d6b67574288140b79b144692478
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615359"
---
# <a name="output-device-context-classes"></a>出力 (デバイス コンテキスト) クラス

これらのクラスは、Windows で使用可能なさまざまな種類のデバイスコンテキストをカプセル化します。

次のクラスのほとんどは、Windows デバイスコンテキストへのハンドルをカプセル化しています。 デバイスコンテキストは、ディスプレイやプリンターなどのデバイスの描画属性に関する情報を格納する Windows オブジェクトです。 すべての描画呼び出しは、デバイスコンテキストオブジェクトを使用して行われます。 から派生したその他のクラス `CDC` は、Windows メタファイルのサポートなど、特殊なデバイスコンテキスト機能をカプセル化します。

[CDC](reference/cdc-class.md)<br/>
デバイスコンテキストの基本クラス。 ディスプレイ全体にアクセスしたり、プリンターなどの非表示コンテキストにアクセスしたりするために直接使用されます。

[CPaintDC](reference/cpaintdc-class.md)<br/>
Windows のメンバー関数で使用される表示コンテキスト `OnPaint` 。 `BeginPaint`構築時および破棄時に自動的にを呼び出し `EndPaint` ます。

[CClientDC](reference/cclientdc-class.md)<br/>
Windows のクライアント領域の表示コンテキスト。 たとえば、マウスイベントに対してすぐに応答を描画するために使用されます。

[CWindowDC](reference/cwindowdc-class.md)<br/>
クライアント領域と非クライアント領域の両方を含む、ウィンドウ全体の表示コンテキスト。

[CMetaFileDC](reference/cmetafiledc-class.md)<br/>
Windows メタファイルのデバイスコンテキスト。 Windows メタファイルには、イメージを作成するために再生できるグラフィックスデバイスインターフェイス (GDI) コマンドのシーケンスが含まれています。 のメンバー関数に対して行わ `CMetaFileDC` れる呼び出しは、メタファイルに記録されます。

## <a name="related-classes"></a>関連クラス

[CPoint](../atl-mfc-shared/reference/cpoint-class.md)<br/>
座標 (x, y) ペアを保持します。

[CSize](../atl-mfc-shared/reference/csize-class.md)<br/>
距離、相対位置、またはペアの値を保持します。

[CRect](../atl-mfc-shared/reference/crect-class.md)<br/>
四角形の領域の座標を保持します。

[CRgn](reference/crgn-class.md)<br/>
ウィンドウ内で楕円、多角形、または不規則な領域を操作するための GDI 領域をカプセル化します。 クラスのクリッピングメンバー関数と組み合わせて使用され `CDC` ます。

[CRectTracker](reference/crecttracker-class.md)<br/>
四角形オブジェクトのサイズ変更と移動を行うためのユーザーインターフェイスを表示して処理します。

[CColorDialog](reference/ccolordialog-class.md)<br/>
色を選択するための標準のダイアログボックスを提供します。

[CFontDialog](reference/cfontdialog-class.md)<br/>
フォントを選択するための標準のダイアログボックスを提供します。

[CPrintDialog](reference/cprintdialog-class.md)<br/>
には、ファイルを印刷するための標準のダイアログボックスが用意されています。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
