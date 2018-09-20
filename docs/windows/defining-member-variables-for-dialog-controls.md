---
title: ダイアログ コントロール (C++) のメンバー変数の定義 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- member variables, defining for controls
- variables, dialog box control member variables
- controls [C++], member variables
- Dialog Editor [C++], defining member variables for controls
ms.assetid: 84347c63-c33c-4b04-91f5-6d008c45ba58
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fa4d894fb3fc436abab84bfee11199f59bd66f78
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402396"
---
# <a name="defining-member-variables-for-dialog-controls-c"></a>ダイアログ コントロール (C++) のメンバー変数の定義

ボタン以外のダイアログ ボックス コントロールのメンバー変数を定義するには、次の手順を使用できます。

> [!NOTE]
> この記事に該当するのは、MFC プロジェクト内のダイアログ コントロールだけです。 ATL プロジェクトで使用する必要があります、**新しい Windows メッセージおよびイベント ハンドラー**  ダイアログ ボックス。

### <a name="to-define-a-member-variable-for-a-non-button-dialog-box-control"></a>ボタン以外のダイアログ ボックス コントロールのメンバー変数を定義するには

1. [ダイアログ エディター](../windows/dialog-editor.md)コントロールを選択します。

2. キーを押しながら、 **Ctrl**キーをダイアログ ボックス コントロールをダブルクリックします。

   [メンバー変数の追加ウィザード](../ide/add-member-variable-wizard.md)が表示されます。

3. 適切な情報を入力、**メンバー変数の追加**ウィザード。 詳細については、次を参照してください。[ダイアログ データ エクス チェンジ](../mfc/dialog-data-exchange.md)します。

4. をクリックして**OK**に戻ります、**ダイアログ**エディター。

   > [!TIP]
   > ダイアログ ボックス コントロールから既存のハンドラーにジャンプするには、コントロールをダブルクリックします。

使用することも、**メンバー変数**] タブの [ **MFC クラス ウィザード**して既に定義されているものを指定されたクラスの新しいメンバー変数を追加します。

## <a name="requirements"></a>要件

MFC

## <a name="see-also"></a>関連項目

[マップ (関数にメッセージを)](../mfc/reference/mapping-messages-to-functions.md)<br/>
[コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[MFC クラス ウィザード](../mfc/reference/mfc-class-wizard.md)<br/>
[クラスの追加](../ide/adding-a-class-visual-cpp.md)<br/>
[メンバー関数の追加](../ide/adding-a-member-function-visual-cpp.md)<br/>
[メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)<br/>
[仮想関数のオーバーライド](../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC メッセージ ハンドラー](../mfc/reference/adding-an-mfc-message-handler.md)