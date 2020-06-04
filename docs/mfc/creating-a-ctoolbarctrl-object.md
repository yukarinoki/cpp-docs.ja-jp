---
title: CToolBarCtrl オブジェクトの作成
ms.date: 11/04/2016
helpviewer_keywords:
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: a4f6bf0c-0195-4dbf-a09e-aee503e19dc3
ms.openlocfilehash: cf1d2eeb9efd2f8a1e7b433c0e18dd868a8b9aca
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445896"
---
# <a name="creating-a-ctoolbarctrl-object"></a>CToolBarCtrl オブジェクトの作成

[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)オブジェクトにはいくつかの内部データ構造が含まれています。ボタンイメージビットマップの一覧、ボタンラベル文字列のリスト、および `TBBUTTON` 構造体の一覧。ボタンの位置、スタイル、状態、およびコマンド ID にイメージや文字列を関連付けます。 これらのデータ構造体の各要素は、0から始まるインデックスによって参照されます。 `CToolBarCtrl` オブジェクトを使用する前に、これらのデータ構造を設定する必要があります。 データ構造の一覧については、「Windows SDK の[ツールバーコントロール](controls-mfc.md)」を参照してください。 文字列のリストは、ボタンラベルに対してのみ使用できます。ツールバーから文字列を取得することはできません。

`CToolBarCtrl` オブジェクトを使用するには、通常、次の手順を実行します。

### <a name="to-use-a-ctoolbarctrl-object"></a>CToolBarCtrl オブジェクトを使用するには

1. [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)オブジェクトを構築します。

1. [Create](../mfc/reference/ctoolbarctrl-class.md#create)を呼び出して、Windows ツールバーコモンコントロールを作成し、`CToolBarCtrl` オブジェクトにアタッチします。 ボタンにビットマップイメージが必要な場合は、 [AddBitmap](../mfc/reference/ctoolbarctrl-class.md#addbitmap)を呼び出して、ボタンのビットマップをツールバーに追加します。 ボタンに文字列ラベルが必要な場合は、 [Addstring](../mfc/reference/ctoolbarctrl-class.md#addstring)または[addstring](../mfc/reference/ctoolbarctrl-class.md#addstrings)を呼び出して、ツールバーに文字列を追加します。 `AddString` や `AddStrings`を呼び出した後、表示する文字列を取得するために[AutoSize](../mfc/reference/ctoolbarctrl-class.md#autosize)を呼び出す必要があります。

1. ボタン構造をツールバーに追加するには、 [Addbuttons](../mfc/reference/ctoolbarctrl-class.md#addbuttons)を呼び出します。

1. ツールヒントが必要な場合は、「[ツールヒント通知の処理](../mfc/handling-tool-tip-notifications.md)」で説明されているように、ツールバーの [所有者] ウィンドウで**TTN_NEEDTEXT**メッセージを処理します。

1. ユーザーがツールバーをカスタマイズできるようにするには、「[カスタマイズ通知の処理](../mfc/handling-customization-notifications.md)」の説明に従って、[所有者] ウィンドウでカスタマイズ通知メッセージを処理します。

## <a name="see-also"></a>参照

[CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
