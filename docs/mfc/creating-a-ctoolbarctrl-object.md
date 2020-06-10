---
title: CToolBarCtrl オブジェクトの作成
ms.date: 11/04/2016
helpviewer_keywords:
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: a4f6bf0c-0195-4dbf-a09e-aee503e19dc3
ms.openlocfilehash: 2627f9aaceeab7760e15b23435233e124c5ea6f0
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619000"
---
# <a name="creating-a-ctoolbarctrl-object"></a>CToolBarCtrl オブジェクトの作成

[CToolBarCtrl](reference/ctoolbarctrl-class.md)オブジェクトにはいくつかの内部データ構造が含まれています。これは、ボタンイメージビットマップのリスト、ボタンラベル文字列のリスト、および構造体のリストで、 `TBBUTTON` イメージや文字列をボタンの位置、スタイル、状態、およびコマンド ID に関連付けます。 これらのデータ構造体の各要素は、0から始まるインデックスによって参照されます。 オブジェクトを使用する前に `CToolBarCtrl` 、これらのデータ構造を設定する必要があります。 データ構造の一覧については、「Windows SDK の[ツールバーコントロール](controls-mfc.md)」を参照してください。 文字列のリストは、ボタンラベルに対してのみ使用できます。ツールバーから文字列を取得することはできません。

オブジェクトを使用するには `CToolBarCtrl` 、通常、次の手順を実行します。

### <a name="to-use-a-ctoolbarctrl-object"></a>CToolBarCtrl オブジェクトを使用するには

1. [CToolBarCtrl](reference/ctoolbarctrl-class.md)オブジェクトを構築します。

1. [Create](reference/ctoolbarctrl-class.md#create)を呼び出して、Windows ツールバーコモンコントロールを作成し、オブジェクトにアタッチし `CToolBarCtrl` ます。 ボタンにビットマップイメージが必要な場合は、 [AddBitmap](reference/ctoolbarctrl-class.md#addbitmap)を呼び出して、ボタンのビットマップをツールバーに追加します。 ボタンに文字列ラベルが必要な場合は、 [Addstring](reference/ctoolbarctrl-class.md#addstring)または[addstring](reference/ctoolbarctrl-class.md#addstrings)を呼び出して、ツールバーに文字列を追加します。 /またはを呼び出した後は、 `AddString` `AddStrings` 表示する文字列を取得するために[AutoSize](reference/ctoolbarctrl-class.md#autosize)を呼び出す必要があります。

1. ボタン構造をツールバーに追加するには、 [Addbuttons](reference/ctoolbarctrl-class.md#addbuttons)を呼び出します。

1. ツールヒントが必要な場合は、「[ツールヒント通知の処理](handling-tool-tip-notifications.md)」で説明されているように、ツールバーの [所有者] ウィンドウで**TTN_NEEDTEXT**メッセージを処理します。

1. ユーザーがツールバーをカスタマイズできるようにするには、「[カスタマイズ通知の処理](handling-customization-notifications.md)」の説明に従って、[所有者] ウィンドウでカスタマイズ通知メッセージを処理します。

## <a name="see-also"></a>関連項目

[CToolBarCtrl の使い方](using-ctoolbarctrl.md)<br/>
[制限](controls-mfc.md)
