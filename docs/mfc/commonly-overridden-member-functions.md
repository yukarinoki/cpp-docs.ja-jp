---
description: '詳細情報: 一般的にオーバーライドされるメンバー関数'
title: 通常オーバーライドされるメンバー関数
ms.date: 09/06/2019
helpviewer_keywords:
- CDialog class [MFC], members
- OnInitDialog function
- dialog classes [MFC], commonly overridden member functions
- OnCancel function
- overriding, dialog class members
- OnOK function
- MFC dialog boxes [MFC], overriding member functions
ms.assetid: 78eb566c-e361-4c86-8db5-c7e2791b249a
ms.openlocfilehash: 54fb55716a0e0ac7db0e81ec81ed1b9732f07243
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310578"
---
# <a name="commonly-overridden-member-functions"></a>通常オーバーライドされるメンバー関数

次の表に、の派生クラスでオーバーライドされる可能性の高いメンバー関数を示し `CDialog` ます。

### <a name="commonly-overridden-member-functions-of-class-cdialog"></a>クラス CDialog の通常オーバーライドされるメンバー関数

|メンバー関数|応答メッセージ|上書きの目的|
|---------------------|----------------------------|-----------------------------|
|`OnInitDialog`|**WM_INITDIALOG**|ダイアログボックスのコントロールを初期化します。|
|`OnOK`|ボタン **IDOK** の **BN_CLICKED**|ユーザーが [OK] ボタンをクリックしたときに応答します。|
|`OnCancel`|ボタン **IDCANCEL** の **BN_CLICKED**|ユーザーが [キャンセル] ボタンをクリックしたときに応答します。|

`OnInitDialog`、 `OnOK` 、および `OnCancel` は仮想関数です。 これらをオーバーライドするには、 [MFC クラスウィザード](reference/mfc-class-wizard.md)を使用して、派生ダイアログクラスでオーバーライドする関数を宣言します。

`OnInitDialog` は、ダイアログボックスが表示される直前に呼び出されます。 オーバーライドから既定のハンドラーを呼び出す必要があり `OnInitDialog` ます。通常は、ハンドラーの最初のアクションです。 既定では、は、 `OnInitDialog` ダイアログボックスの最初のコントロールにフォーカスを設定する必要があることを示すために **TRUE** を返します。

`OnOK` は通常、モードレスではオーバーライドされますが、モーダルダイアログボックスには上書きされません。 モーダルダイアログボックスに対してこのハンドラーをオーバーライドする場合は、オーバーライドから基本クラスバージョンを呼び出して、が呼び出されるようにする `EndDialog` か、自分で呼び出す必要が `EndDialog` あります。

`OnCancel` は通常、モードレスダイアログボックスでオーバーライドされます。

これらのメンバー関数の詳細については、 *Mfc リファレンス* のクラス [CDialog](reference/cdialog-class.md)に関する記事と、 [mfc でのダイアログボックスの操作](life-cycle-of-a-dialog-box.md)に関する説明を参照してください。

## <a name="see-also"></a>関連項目

[ダイアログボックス](dialog-boxes.md)<br/>
[一般的に追加されるメンバー関数](commonly-added-member-functions.md)
