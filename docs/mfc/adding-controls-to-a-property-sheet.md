---
description: 詳細については、「プロパティシートへのコントロールの追加」を参照してください。
title: プロパティ シートへのコントロールの追加
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
ms.openlocfilehash: e220d08b46f1db7e09ad1f1398731ce7a98f2dc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339076"
---
# <a name="adding-controls-to-a-property-sheet"></a>プロパティ シートへのコントロールの追加

既定では、プロパティシートによって、プロパティページ、タブインデックス、および [OK]、[キャンセル]、および [適用] ボタンのウィンドウ領域が割り当てられます。 (モードレスプロパティシートには、[OK]、[キャンセル]、および [適用] ボタンはありません)。プロパティシートには、他のコントロールを追加できます。 たとえば、[プロパティページ] 領域の右側にプレビューウィンドウを追加すると、外部オブジェクトに適用した場合に現在の設定がどのように表示されるかをユーザーに示すことができます。

ハンドラーの [プロパティシート] ダイアログにコントロールを追加でき `OnCreate` ます。 通常、追加のコントロールに対応するには、[プロパティシート] ダイアログのサイズを拡張する必要があります。 基本クラス **CPropertySheet:: OnCreate** を呼び出した後、 [getwindowrect](reference/cwnd-class.md#getwindowrect) を呼び出して、現在割り当てられているプロパティシートウィンドウの幅と高さを取得し、四角形の寸法を展開し、 [movewindow](reference/cwnd-class.md#movewindow) を呼び出してプロパティシートウィンドウのサイズを変更します。

## <a name="see-also"></a>関連項目

[プロパティシート](property-sheets-mfc.md)<br/>
[CPropertyPage クラス](reference/cpropertypage-class.md)<br/>
[CPropertySheet クラス](reference/cpropertysheet-class.md)
