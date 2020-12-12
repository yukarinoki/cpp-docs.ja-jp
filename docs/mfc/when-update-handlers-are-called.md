---
description: '詳細情報: 更新ハンドラーが呼び出されたとき'
title: 更新ハンドラーが呼び出されるタイミング
ms.date: 11/04/2016
helpviewer_keywords:
- updating user interface objects [MFC]
- command routing [MFC], update commands
- toolbar buttons [MFC], enabling
- disabling toolbar buttons
- menus [MFC], initializing
- update handlers [MFC]
- disabling menu items
- toolbars [MFC], updating
- menus [MFC], updating as context changes
- toolbar controls [MFC], updated during OnIdle method [MFC]
- menu items, enabling
- command routing [MFC], update handlers
- update handlers, calling
ms.assetid: 7359f6b1-4669-477d-bd99-690affed08d9
ms.openlocfilehash: ee5d402eea4121c9ceb4bcbd48e752549c55b1c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297175"
---
# <a name="when-update-handlers-are-called"></a>更新ハンドラーが呼び出されるタイミング

たとえば、ユーザーが [ファイル] メニューでマウスをクリックすると、WM_INITMENUPOPUP メッセージが生成されたとします。 フレームワークの更新メカニズムでは、ユーザーが表示できるように、メニューがドロップされる前に [ファイル] メニューのすべての項目がまとめて更新されます。

これを行うために、フレームワークは、ポップアップメニューのすべてのメニュー項目について、標準のコマンドルーティングに従って更新コマンドをルーティングします。 ルーティングのコマンドターゲットでは、update コマンドと適切なメッセージマップエントリ (フォームの) を照合 `ON_UPDATE_COMMAND_UI` し、"更新ハンドラー" 関数を呼び出すことによって、メニュー項目を更新できます。 このため、メニュー項目が6つあるメニューの場合、6つの更新コマンドが送信されます。メニュー項目のコマンド ID に更新ハンドラーが存在する場合は、更新ハンドラーが呼び出されて更新されます。 それ以外の場合、フレームワークはそのコマンド ID のハンドラーが存在するかどうかを確認し、必要に応じてメニュー項目を有効または無効にします。

`ON_UPDATE_COMMAND_UI`コマンドルーティング中にエントリが見つからない場合は、 `ON_COMMAND` 同じコマンド ID を持つエントリがあると、ユーザーインターフェイスオブジェクトが自動的に有効になります。 それ以外の場合は、ユーザーインターフェイスオブジェクトを無効にします。 したがって、ユーザーインターフェイスオブジェクトが有効になっていることを確認するには、オブジェクトによって生成されるか更新ハンドラーを提供するコマンドのハンドラーを指定します。 「 [ユーザーインターフェイスオブジェクトとコマンド id](../mfc/user-interface-objects-and-command-ids.md)」の図を参照してください。

ユーザーインターフェイスオブジェクトの既定の無効化を無効にすることができます。 詳細については、 [](../mfc/reference/cframewnd-class.md#m_bautomenuenable) `CFrameWnd` *MFC リファレンス* のクラスの m_bAutoMenuEnable メンバーを参照してください。

メニューの初期化はフレームワークで自動的に行われ、アプリケーションが WM_INITMENUPOPUP メッセージを受信すると発生します。 アイドルループ中、フレームワークは、コマンドのルーティングをボタン更新ハンドラーに対して、メニューの場合とほぼ同じ方法で検索します。

## <a name="see-also"></a>関連項目

[方法: User-Interface オブジェクトを更新する](../mfc/how-to-update-user-interface-objects.md)
