---
title: ヘッダー コントロールの作成
ms.date: 11/04/2016
helpviewer_keywords:
- CHeaderCtrl class [MFC], creating
- header controls [MFC], creating
ms.assetid: 7864d9d2-4a2c-4622-b58b-7b110a1e28d2
ms.openlocfilehash: b08dd4d3f12c70ae495b20b936d44f6a695d1ae1
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616243"
---
# <a name="creating-the-header-control"></a>ヘッダー コントロールの作成

ヘッダーコントロールは、ダイアログエディターで直接使用することはできません (ただし、ヘッダーコントロールを含むリストコントロールを追加することはできます)。

### <a name="to-put-a-header-control-in-a-dialog-box"></a>ヘッダーコントロールをダイアログボックスに配置するには

1. ダイアログクラスに[CHeaderCtrl](reference/cheaderctrl-class.md)型のメンバー変数を手動で埋め込みます。

1. [OnInitDialog](reference/cdialog-class.md#oninitdialog)で、のスタイルを作成して設定し `CHeaderCtrl` 、配置して表示します。

1. ヘッダーコントロールに項目を追加します。

1. [クラスウィザード](reference/mfc-class-wizard.md)を使用すると、処理する必要があるヘッダーコントロールの通知メッセージのダイアログクラスのハンドラー関数をマップできます (「[関数へのメッセージのマッピング](reference/mapping-messages-to-functions.md)」を参照してください)。

### <a name="to-put-a-header-control-in-a-view-not-a-clistview"></a>(CListView ではなく) ビューにヘッダーコントロールを配置するには

1. [CHeaderCtrl](reference/cheaderctrl-class.md)オブジェクトをビュークラスに埋め込みます。

1. ビューの[OnInitialUpdate](reference/cview-class.md#oninitialupdate)メンバー関数で、ヘッダーコントロールウィンドウのスタイル、位置、および表示を行います。

1. ヘッダーコントロールに項目を追加します。

1. [クラスウィザード](reference/mfc-class-wizard.md)を使用すると、処理する必要があるヘッダーコントロールの通知メッセージのビュークラスのハンドラー関数をマップできます (「[関数へのメッセージのマッピング](reference/mapping-messages-to-functions.md)」を参照してください)。

どちらの場合も、埋め込みコントロールオブジェクトは、ビューまたはダイアログオブジェクトの作成時に作成されます。 次に、 [CHeaderCtrl:: create](reference/cheaderctrl-class.md#create)を呼び出して、コントロールウィンドウを作成する必要があります。 コントロールを配置するには、 [CHeaderCtrl:: Layout](reference/cheaderctrl-class.md#layout)を呼び出して、コントロールの初期サイズと位置を決定し、 [SetWindowPos](reference/cwnd-class.md#setwindowpos)を使用して必要な位置を設定します。 次に[、「ヘッダーコントロールへの項目の追加](adding-items-to-the-header-control.md)」の説明に従って項目を追加します。

詳細については、「Windows SDK での[ヘッダーコントロールの作成](/windows/win32/Controls/header-controls)」を参照してください。

## <a name="see-also"></a>関連項目

[CHeaderCtrl の使い方](using-cheaderctrl.md)<br/>
[制限](controls-mfc.md)
