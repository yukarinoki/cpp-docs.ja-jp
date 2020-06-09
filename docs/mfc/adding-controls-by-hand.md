---
title: 手動でコントロールを追加する方法
ms.date: 11/04/2016
helpviewer_keywords:
- Windows common controls [MFC], adding
- dialog box controls [MFC], adding to dialog boxes
- controlling input focus
- input focus control
- focus, controlling input [MFC]
- controls [MFC], adding to dialog boxes
- common controls [MFC], adding
ms.assetid: bc843e59-0c51-4b5b-8bf2-343f716469d2
ms.openlocfilehash: 4efd1c23c7e4d6f7d8e6fa9fe046f8de11c825a6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626533"
---
# <a name="adding-controls-by-hand"></a>手動でコントロールを追加する方法

ダイアログ[ボックスにコントロールを追加](using-the-dialog-editor-to-add-controls.md)するには、ダイアログエディターを使用するか、コードを使用して自分でコントロールを追加します。

コントロールオブジェクトを自分で作成するには、通常、c++ のコントロールオブジェクトを C++ ダイアログまたはフレームウィンドウオブジェクトに埋め込みます。 フレームワーク内の他の多くのオブジェクトと同様に、コントロールには2段階の構築が必要です。 親ダイアログボックスまたはフレームウィンドウの作成の一部として、コントロールの**Create** member 関数を呼び出す必要があります。 ダイアログボックスの場合は、通常、 [OnInitDialog](reference/cdialog-class.md#oninitdialog)で、フレームウィンドウの場合は[OnCreate](reference/cwnd-class.md#oncreate)で実行されます。

次の例は、 `CEdit` 派生ダイアログクラスのクラス宣言でオブジェクトを宣言し、でそのメンバー関数を呼び出す方法を示して `Create` `OnInitDialog` います。 オブジェクトは `CEdit` 埋め込みオブジェクトとして宣言されているので、ダイアログオブジェクトの構築時に自動的に作成されますが、それでも独自のメンバー関数を使用して初期化する必要があり `Create` ます。

[!code-cpp[NVC_MFCControlLadenDialog#1](codesnippet/cpp/adding-controls-by-hand_1.h)]

次の `OnInitDialog` 関数は、四角形を設定し、 `Create` を呼び出して Windows のエディットコントロールを作成し、初期化されていないオブジェクトにアタッチし `CEdit` ます。

[!code-cpp[NVC_MFCControlLadenDialog#2](codesnippet/cpp/adding-controls-by-hand_2.cpp)]

編集オブジェクトを作成した後、メンバー関数を呼び出すことによって、入力フォーカスをコントロールに設定することもでき `SetFocus` ます。 最後に、フォーカスを設定したことを示すために、から0を返し `OnInitDialog` ます。 0以外の値を返すと、ダイアログマネージャーによって、ダイアログ項目リストの最初のコントロール項目にフォーカスが設定されます。 ほとんどの場合、ダイアログボックスにコントロールを追加するには、ダイアログエディターを使用します。

## <a name="see-also"></a>関連項目

[コントロールの作成方法と使い方](making-and-using-controls.md)<br/>
[制限](controls-mfc.md)<br/>
[CDialog::OnInitDialog](reference/cdialog-class.md#oninitdialog)
