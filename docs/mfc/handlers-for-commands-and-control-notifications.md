---
description: 詳細については、「コマンドとコントロール通知のハンドラー」を参照してください。
title: コマンドとコントロール通知のハンドラー
ms.date: 11/04/2016
helpviewer_keywords:
- commands [MFC], handlers for
- functions [MFC], handler
- handlers [MFC]
- controls [MFC], notifications
- handlers [MFC], control notification [MFC]
- notifications [MFC], handlers for control
- handlers [MFC], command
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
ms.openlocfilehash: 1e5e3284d5898d1e6349765dc7a1bcdc864c80ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189185"
---
# <a name="handlers-for-commands-and-control-notifications"></a>コマンドとコントロール通知のハンドラー

コマンドまたはコントロール通知メッセージの既定のハンドラーはありません。 したがって、これらのメッセージカテゴリのハンドラーに名前を付けるには、規則によってのみバインドされます。 コマンドまたはコントロールの通知をハンドラーにマップすると、 [クラスウィザード](reference/mfc-class-wizard.md) によって、コマンド ID またはコントロール通知コードに基づいて名前が提示されます。 提案された名前をそのまま使用するか、変更するか、置き換えることができます。

規則は、それらが表すユーザーインターフェイスオブジェクトの両方のカテゴリにハンドラー名を指定することを示しています。 したがって、[編集] メニューの [切り取り] コマンドのハンドラーは、という名前になります。

[!code-cpp[NVC_MFCMessageHandling#4](codesnippet/cpp/handlers-for-commands-and-control-notifications_1.h)]

Cut コマンドはアプリケーションで一般的に実装されているので、事前というフレームワークは、Cut コマンドのコマンド ID を **ID_EDIT_CUT** として使用します。 定義済みのすべてのコマンド Id の一覧については、AFXRES.H ファイルを参照してください。 詳細については、「 [標準コマンド](standard-commands.md)」を参照してください。

また、規則では、"My Button" というラベルが付いたボタンから **BN_CLICKED** 通知メッセージのハンドラーを指定することもできます。

[!code-cpp[NVC_MFCMessageHandling#5](codesnippet/cpp/handlers-for-commands-and-control-notifications_2.h)]

このコマンドは、アプリケーション固有のユーザーインターフェイスオブジェクトと同等であるため、 **IDC_MY_BUTTON** の ID として割り当てることができます。

どちらのカテゴリのメッセージも引数を取らず、値を返しません。

## <a name="see-also"></a>関連項目

[メッセージハンドラー関数の宣言](declaring-message-handler-functions.md)
