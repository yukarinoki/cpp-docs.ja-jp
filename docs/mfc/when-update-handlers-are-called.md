---
title: 更新ハンドラーが呼び出されるタイミング |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c033d33dd6b1e6c0ccd5bbdb4b6af6939521f592
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956175"
---
# <a name="when-update-handlers-are-called"></a>更新ハンドラーが呼び出されるタイミング
たとえば、ユーザーがポインター メッセージを生成して、[ファイル] メニューにマウスをクリックします。 ドロップダウン メニュー、ユーザーが確認できるようにする前に、フレームワークの更新の機構は総称して [ファイル] メニューのすべての項目を更新します。  
  
 これを行うには、framework ルートは、すべてのメニュー項目の標準コマンド ルーティングに沿ったポップアップ メニューのコマンドを更新します。 ルーティング上のコマンド ターゲットを適切なメッセージ マップ エントリと update コマンドを照合することでメニュー項目を更新する機会があります (形式の`ON_UPDATE_COMMAND_UI`)「更新ハンドラー」関数を呼び出すとします。 したがって、6 つのメニュー項目を含むメニューの 6 つの update コマンド、送出されます。更新ハンドラーがメニュー項目のコマンド id が存在する場合は、更新を行う呼び出されます。 ない場合、フレームワークのコマンド ID のハンドラーの存在を確認し、有効またはに応じて、メニュー項目を無効にします。  
  
 フレームワークが見つけられない場合、`ON_UPDATE_COMMAND_UI`コマンド ルーティング中にエントリが自動的に有効に、ユーザー インターフェイス オブジェクトがある場合、`ON_COMMAND`同じコマンド ID を持つ任意の場所エントリ それ以外の場合、ユーザー インターフェイス オブジェクトを無効にします。 そのため、ユーザー インターフェイス オブジェクトが有効になっていることを確認するには、オブジェクトを生成するコマンドのハンドラーを指定したり、更新ハンドラーを指定します。 トピックの図を参照してください[ユーザー インターフェイス オブジェクトとコマンド Id](../mfc/user-interface-objects-and-command-ids.md)です。  
  
 ユーザー インターフェイス オブジェクトの既定の無効化を無効にすることができます。 詳細については、次を参照してください。、 [m_bAutoMenuEnable](../mfc/reference/cframewnd-class.md#m_bautomenuenable)クラスのメンバー`CFrameWnd`で、 *『 MFC リファレンス*です。  
  
 メニューの初期化は、自動 framework では、アプリケーションがポインター メッセージを受信時に発生します。 アイドル ループ時に、フレームワークは、コマンド ルーティング ボタン更新ハンドラーのほぼ同じ方法でメニューの場合と同様を検索します。  
  
## <a name="see-also"></a>関連項目  
 [ユーザー インターフェイス オブジェクトの更新方法](../mfc/how-to-update-user-interface-objects.md)

