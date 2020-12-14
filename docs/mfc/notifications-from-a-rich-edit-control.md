---
description: 詳細については、「リッチエディットコントロールからの通知」を参照してください。
title: リッチ エディット コントロールからの通知メッセージ
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
ms.openlocfilehash: 83f76c2b0bf8c27d30d8c113fc1607f3cbd718fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254795"
---
# <a name="notifications-from-a-rich-edit-control"></a>リッチ エディット コントロールからの通知メッセージ

通知メッセージは、リッチエディットコントロール ([CRichEditCtrl](reference/cricheditctrl-class.md)) に影響を与えるイベントを報告します。 これらは、親ウィンドウ、またはリッチエディットコントロール自体によってメッセージリフレクションを使用して処理できます。 リッチエディットコントロールでは、エディットコントロールで使用されるすべての通知メッセージに加えて、いくつかの追加の通知メッセージがサポートされます。 リッチエディットコントロールが親ウィンドウを送信する通知メッセージを特定するには、"イベントマスク" を設定します。

リッチエディットコントロールのイベントマスクを設定するには、 [Seteventmask](reference/cricheditctrl-class.md#seteventmask) メンバー関数を使用します。 リッチエディットコントロールの現在のイベントマスクを取得するには、 [Geteventmask](reference/cricheditctrl-class.md#geteventmask) メンバー関数を使用します。

次の段落では、いくつかの特定の通知とその使用方法を示しています。

- EN_MSGFILTER 通知を処理する EN_MSGFILTER、リッチエディットコントロールまたはその親ウィンドウのいずれかのクラスで、コントロールに対するすべてのキーボードとマウス入力をフィルター処理できます。 ハンドラーでは、キーボードまたはマウスメッセージが処理されないようにすることも、指定した [Msgfilter](/windows/win32/api/richedit/ns-richedit-msgfilter) 構造体を変更することによってメッセージを変更することもできます。

- ユーザーが保護されたテキストを変更しようとしたときに検出する EN_PROTECTED 通知メッセージを EN_PROTECTED 処理します。 テキストの範囲を保護済みとしてマークするには、保護された文字効果を設定します。 詳細については、「 [リッチエディットコントロールでの文字の書式設定](character-formatting-in-rich-edit-controls.md)」を参照してください。

- EN_DROPFILES、ユーザーが EN_DROPFILES 通知メッセージを処理することによって、リッチエディットコントロールにファイルをドロップできるようにすることができます。 指定された [ENDROPFILES](/windows/win32/api/richedit/ns-richedit-endropfiles) 構造体には、削除されるファイルに関する情報が含まれています。

- EN_SELCHANGE アプリケーションは、EN_SELCHANGE 通知メッセージを処理することによって現在の選択範囲が変更されたことを検出できます。 通知メッセージには、新しい選択に関する情報を含む [Selchange](/windows/win32/api/richedit/ns-richedit-selchange) 構造が指定されています。

## <a name="see-also"></a>関連項目

[CRichEditCtrl の使い方](using-cricheditctrl.md)<br/>
[コントロール](controls-mfc.md)
