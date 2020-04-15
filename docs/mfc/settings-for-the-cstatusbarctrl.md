---
title: CStatusBarCtrl の設定値
ms.date: 11/04/2016
helpviewer_keywords:
- status bar controls [MFC], settings
- CStatusBarCtrl class [MFC], settings
ms.assetid: adeba0c3-17f3-435c-b140-a57845e9ce49
ms.openlocfilehash: dd7c68d6721c48f751c04437e43c8770f6ec5736
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365378"
---
# <a name="settings-for-the-cstatusbarctrl"></a>CStatusBarCtrl の設定値

[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)ステータス ウィンドウの既定の位置は親ウィンドウの下部に沿っていますが、CCS_TOPスタイルを指定して、親ウィンドウのクライアント領域の上部に表示されるようにすることができます。

ステータス ウィンドウの右端にサイズ変更グリップを含めるSBARS_SIZEGRIP スタイルを`CStatusBarCtrl`指定できます。 サイズ変更グリップは、サイズ変更の境界線に似ています。これは、ユーザーがクリックしてドラッグして親ウィンドウのサイズを変更できる四角形の領域です。

> [!NOTE]
> CCS_TOPスタイルとSBARS_SIZEGRIPスタイルを組み合わせると、システムがステータスウィンドウに描画しても、サイズ変更グリップは機能しません。

ステータス ウィンドウのウィンドウ プロシージャは、コントロール ウィンドウの初期サイズと位置を自動的に設定します。 幅は、親ウィンドウのクライアント領域と同じです。 高さは、ステータスウィンドウのデバイスコンテキストに現在選択されているフォントのメトリックと、ウィンドウの境界の幅に基づいています。

ウィンドウ プロシージャは、WM_SIZE メッセージを受信するたびに、ステータス ウィンドウのサイズを自動的に調整します。 通常、親ウィンドウのサイズが変更されると、親はWM_SIZEメッセージをステータス ウィンドウに送信します。

ステータス ウィンドウの作図領域の最小の高さを設定するには、最小の高さをピクセル単位で指定する[SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight)を呼び出します。 作図領域には、ウィンドウの境界線は含まれません。

ステータス ウィンドウの境界線の幅を取得するには、 [GetBorders](../mfc/reference/cstatusbarctrl-class.md#getborders)を呼び出します。 このメンバー関数には、水平境界線、垂直境界線、および四角形の境界線を受け取る 3 要素配列へのポインターが含まれます。

## <a name="see-also"></a>関連項目

[CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
