---
title: コマンドとコントロール通知のハンドラー |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- commands [MFC], handlers for
- functions [MFC], handler
- handlers [MFC]
- controls [MFC], notifications
- handlers [MFC], control notification [MFC]
- notifications [MFC], handlers for control
- handlers [MFC], command
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60c66beb3c0c8874bd3d678bfc4331dc766c443a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929132"
---
# <a name="handlers-for-commands-and-control-notifications"></a>コマンドとコントロール通知のハンドラー
コマンドまたはコントロール通知メッセージの既定のハンドラーはありません。 したがって、これらのカテゴリのメッセージのハンドラーの名前付け規則でのみバインドされます。 コマンドまたはコントロールの通知をハンドラーにマップするときに、[プロパティ] ウィンドウは、コマンドの ID またはコントロール通知のコードに基づく名前を提案します。 提案された名前を受け入れる、変更するか、または置換できます。  
  
 規則は、それらが表すユーザー インターフェイス オブジェクトの両方のカテゴリ内のハンドラーを付けることをお勧めします。 したがって、[編集] メニューの [切り取り] コマンドのハンドラーという名前  
  
 [!code-cpp[NVC_MFCMessageHandling#4](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_1.h)]  
  
 コマンド ID として [切り取り] コマンドを使わため切り取りコマンドは、アプリケーションで、 **ID_EDIT_CUT**です。 定義済みのすべてのコマンド Id の一覧は、コマ ファイルを参照してください。H. 詳細については、次を参照してください。[標準コマンド](../mfc/standard-commands.md)です。  
  
 さらに、規則がのハンドラーを提案、 **BN_CLICKED** "My Button"というラベルの付いたボタンからの通知メッセージの名前を指定する場合があります  
  
 [!code-cpp[NVC_MFCMessageHandling#5](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_2.h)]  
  
 このコマンドの ID を割り当てることが**として**アプリケーション固有のユーザー インターフェイス オブジェクトと等価であるためです。  
  
 メッセージの両方のカテゴリは、引数を受け取らずし、値を返しません。  
  
## <a name="see-also"></a>関連項目  
 [メッセージ ハンドラー関数の宣言](../mfc/declaring-message-handler-functions.md)
