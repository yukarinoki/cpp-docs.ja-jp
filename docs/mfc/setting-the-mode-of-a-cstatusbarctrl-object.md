---
title: CStatusBarCtrl オブジェクトのモードの設定
ms.date: 11/04/2016
helpviewer_keywords:
- simple mode and status bar controls
- IsSimple method, using
- SetSimple method [MFC]
- status bar controls [MFC], simple and nonsimple modes
- non-simple mode and status bar controls
- CStatusBarCtrl class [MFC], simple and nonsimple modes
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
ms.openlocfilehash: e09a7bd274c44df2da48bbc007a95802fadd8cf0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365414"
---
# <a name="setting-the-mode-of-a-cstatusbarctrl-object"></a>CStatusBarCtrl オブジェクトのモードの設定

`CStatusBarCtrl`オブジェクトには、単純モードと非単純モードの 2 つのモードがあります。 ほとんどの場合、ステータス バー コントロールには、テキストやアイコンやアイコンと共に、1 つ以上の部分が表示されます。 これは非単純モードと呼ばれます。 このモードの詳細については、「 [CStatusBarCtrl オブジェクトのパーツの初期化](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md)」を参照してください。

ただし、1 行のテキストのみを表示する必要がある場合もあります。 この場合、シンプルモードで十分です。 オブジェクトのモードを`CStatusBarCtrl`単純に変更するには[、SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple)メンバー関数を呼び出します。 ステータス バー コントロールが単純モードになったら、メンバー関数を呼び出`SetText`してテキストを設定し *、nPane*パラメータの値として 255 を渡します。

[IsSimple](../mfc/reference/cstatusbarctrl-class.md#issimple)関数を使用して、`CStatusBarCtrl`オブジェクトがどのモードにあるかを判断できます。

> [!NOTE]
> ステータス バー オブジェクトが単純でないオブジェクトから単純オブジェクトに変更されている場合、またはその逆の場合、ウィンドウは直ちに再描画され、該当する場合は、定義されたパーツが自動的に復元されます。

## <a name="see-also"></a>関連項目

[CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
