---
title: メッセージの種類のユーザー インターフェイス オブジェクトに関連付けられている |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.uiobject.msgs
dev_langs:
- C++
helpviewer_keywords:
- message types and user interface objects [MFC]
ms.assetid: 681ee1a7-f6e6-4ea0-9fc6-1fb53a35516e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bd89f19547eef8ade9d23a6176ea74cb49586857
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860291"
---
# <a name="message-types-associated-with-user-interface-objects"></a>ユーザー インターフェイス オブジェクトに関連付けられたメッセージ

次の表は、使用する次の操作を実行する、オブジェクトの種類とそれらに関連付けられているメッセージの種類を示します。

### <a name="user-interface-objects-and-associated-messages"></a>ユーザー インターフェイス オブジェクトと関連付けられているメッセージ

|オブジェクト ID|メッセージ|
|---------------|--------------|
|格納先ウィンドウを表すクラス名|適切な Windows メッセージ、 [CWnd](../../mfc/reference/cwnd-class.md)-クラスを派生: ダイアログ ボックス、ウィンドウ、子ウィンドウ、MDI 子ウィンドウ、または最上位のフレーム ウィンドウ。|
|メニューまたはアクセラレータの識別子|-コマンド メッセージ (プログラムの関数を実行します)。<br />-UPDATE_COMMAND_UI メッセージ (メニュー項目を動的に更新) します。|
|コントロールの識別子|選択したコントロールの種類の通知メッセージを制御します。|

## <a name="see-also"></a>関連項目

[マップ (関数にメッセージを)](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[クラスの追加](../../ide/adding-a-class-visual-cpp.md)<br/>
[メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[仮想関数のオーバーライド](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[クラス各部へのジャンプ](../../ide/navigating-the-class-structure-visual-cpp.md)
