---
title: スピン ボタンのスタイル
ms.date: 11/04/2016
helpviewer_keywords:
- styles [MFC], CSpinButtonCtrl
- CSpinButtonCtrl class [MFC], styles
- styles [MFC], spin button control
- spin button control, styles
ms.assetid: fb4a7f6f-9182-47be-bccf-0728fdc5332f
ms.openlocfilehash: 73042dbbdc28819ecc736c282599189ee074ce77
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50457110"
---
# <a name="spin-button-styles"></a>スピン ボタンのスタイル

スピン ボタンの設定の多く ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)) スタイルによって制御されます。 使用して、次のスタイルを設定することができます、**プロパティ**ダイアログ エディターのウィンドウ。

- **印刷の向き**垂直または水平方向のいずれか。 矢印ボタンの表示方向を制御します。 関連付けられた UDS_HORZ スタイル。

- **配置**接続されていない、左右のいずれか。 スピン ボタンの場所を制御します。 左と右が連動ウィンドウの横にあるスピン ボタンを配置します。 スピン ボタンを対応するために連動ウィンドウの幅が減少します。 関連付けられた UDS_ALIGNLEFT と UDS_ALIGNRIGHT スタイル。

- **Auto Buddy**スピン ボタンを連動ウィンドウとして Z オーダーの前のウィンドウを自動的に選択します。 ダイアログ テンプレートで、これは、タブ オーダーのスピン ボタンの前に、コントロールです。 関連付けられた UDS_AUTOBUDDY スタイル。

- **設定 Buddy Integer**インクリメントし、現在の位置が変更されると連動ウィンドウのキャプションをデクリメントするには、スピン コントロールします。 関連付けられた UDS_SETBUDDYINT スタイル。

- **Nothousands**も桁は挿入されませんが連動ウィンドウのキャプションの値の区切り記号。 関連付けられた UDS_NOTHOUSANDS スタイル。

    > [!NOTE]
    >  アップダウン コントロールから整数値を取得するダイアログ データ エクス (チェンジ DDX) を使用する場合は、このスタイルを設定します。 `DDX_Text` 埋め込みの桁区切り記号は受け入れられません。

- **ラップ**によって「ラップ」値がインクリメントまたはデクリメント コントロールの範囲外に位置します。 関連付けられた UDS_WRAP スタイル。

- **方向キー** ↑ キーおよび ↓ キーが押されたときに、位置を増減するスピン ボタンします。 関連付けられた UDS_ARROWKEYS スタイル。

## <a name="see-also"></a>関連項目

[CSpinButtonCtrl の使い方](../mfc/using-cspinbuttonctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

