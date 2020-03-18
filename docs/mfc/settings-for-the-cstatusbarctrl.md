---
title: CStatusBarCtrl の設定値
ms.date: 11/04/2016
helpviewer_keywords:
- status bar controls [MFC], settings
- CStatusBarCtrl class [MFC], settings
ms.assetid: adeba0c3-17f3-435c-b140-a57845e9ce49
ms.openlocfilehash: 18c4c780ecf7865d8d648bfa4c54961bbffe7b18
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446389"
---
# <a name="settings-for-the-cstatusbarctrl"></a>CStatusBarCtrl の設定値

[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)ステータスウィンドウの既定の位置は、親ウィンドウの下部に表示されますが、親ウィンドウのクライアント領域の上部に表示されるように CCS_TOP スタイルを指定することもできます。

SBARS_SIZEGRIP スタイルを指定して、`CStatusBarCtrl` ステータスウィンドウの右端にサイズ変更グリップを含めることができます。 サイズ変更グリップは、サイズ変更の境界線に似ています。これは、ユーザーがクリックしてドラッグして親ウィンドウのサイズを変更できる四角形の領域です。

> [!NOTE]
>  CCS_TOP スタイルと SBARS_SIZEGRIP スタイルを組み合わせると、システムによって状態ウィンドウに描画される場合でも、結果のサイズ変更グリップは機能しません。

[ステータス] ウィンドウのウィンドウプロシージャによって、コントロールウィンドウの初期サイズと位置が自動的に設定されます。 幅は、親ウィンドウのクライアント領域と同じです。 高さは、ステータスウィンドウのデバイスコンテキストで現在選択されているフォントのメトリックと、ウィンドウの境界線の幅に基づいています。

ウィンドウプロシージャは、WM_SIZE メッセージを受信するたびに、ステータスウィンドウのサイズを自動的に調整します。 通常、親ウィンドウのサイズが変更されると、親はステータスウィンドウに WM_SIZE メッセージを送信します。

ステータスウィンドウの描画領域の高さの最小値を設定するには、 [Setminheight](../mfc/reference/cstatusbarctrl-class.md#setminheight)を呼び出して最小の高さ (ピクセル単位) を指定します。 描画領域には、ウィンドウの境界線は含まれません。

ステータスウィンドウの境界線の幅を取得するには、 [Getborders](../mfc/reference/cstatusbarctrl-class.md#getborders)を呼び出します。 このメンバー関数には、水平方向の境界線の幅、垂直方向の境界線、および四角形の間の境界線を受け取る、3つの要素から成る配列へのポインターが含まれています。

## <a name="see-also"></a>参照

[CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
