---
title: Rebar コントロールの作成
ms.date: 11/04/2016
helpviewer_keywords:
- rebar controls [MFC], creating
- CReBarCtrl class [MFC], creating
ms.assetid: 0a012e08-772b-4f6a-af86-7cb651d11d3e
ms.openlocfilehash: 6828fa3b47eaa1e29579b09611d85cd68702c332
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617124"
---
# <a name="creating-a-rebar-control"></a>Rebar コントロールの作成

親オブジェクトを表示する前に、 [Crebarctrl](reference/crebarctrl-class.md)オブジェクトを作成する必要があります。 これにより、描画の問題の可能性が最小限に抑えられます。

たとえば、フレームウィンドウオブジェクトで使用される rebar コントロールは、通常、ツールバーコントロールの親ウィンドウとして使用されます。 そのため、rebar コントロールの親は、フレームウィンドウオブジェクトです。 フレームウィンドウオブジェクトが親であるため、 `OnCreate` (親の) メンバー関数は rebar コントロールを作成するのに最適な場所です。

オブジェクトを使用するには `CReBarCtrl` 、通常、次の手順を実行します。

### <a name="to-use-a-crebarctrl-object"></a>CReBarCtrl オブジェクトを使用するには

1. [Crebarctrl](reference/crebarctrl-class.md)オブジェクトを構築します。

1. [Create](reference/crebarctrl-class.md#create)を呼び出して Windows rebar コモンコントロールを作成し、必要なスタイルを指定してオブジェクトにアタッチし `CReBarCtrl` ます。

1. [CBitmap:: LoadBitmap](reference/cbitmap-class.md#loadbitmap)を呼び出して、rebar コントロールオブジェクトの背景として使用するビットマップを読み込みます。

1. Rebar コントロールオブジェクトに含まれる子ウィンドウオブジェクト (ツールバー、ダイアログコントロールなど) を作成し、初期化します。

1. 挿入するバンドに関する必要な情報を使用して、 **REBARBANDINFO**構造体を初期化します。

1. [Insertband](reference/crebarctrl-class.md#insertband)を呼び出して、既存の子ウィンドウ (など `m_wndReToolBar` ) を新しい rebar コントロールに挿入します。 既存の rebar コントロールにバンドを挿入する方法の詳細については、「 [Rebar コントロールとバンド](rebar-controls-and-bands.md)」を参照してください。

## <a name="see-also"></a>関連項目

[CReBarCtrl の使い方](using-crebarctrl.md)<br/>
[制限](controls-mfc.md)
