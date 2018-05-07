---
title: '方法: ユーザー インターフェイス オブジェクトの更新 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- menus [MFC], updating as context changes
- user interface objects [MFC], updating
- user interface objects [MFC]
- update handlers [MFC]
- enabling UI elements [MFC]
- disabling menus [MFC]
- updating user-interface objects [MFC]
- disabling UI elements [MFC]
- commands [MFC], updating UI
- enabling menus [MFC]
ms.assetid: 82f09773-c978-427b-b321-05a6143b7369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 422be3d80614c526c7e634d22a0930458e4b4e26
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-update-user-interface-objects"></a>ユーザー インターフェイス オブジェクトの更新方法
通常、メニュー項目とツール バー ボタンした複数の状態。 たとえば、メニュー項目は淡色表示 (淡色) は現在のコンテキストで使用可能な場合です。 メニュー項目には、オンまたはオフができます。 ツール バー ボタンは、使用できない場合は無効になっても、または確認されることができます。  
  
 これらの項目、メニュー項目は、によって処理されるコマンドを生成する場合、状態の変化を論理的には、プログラムと、たとえば、ドキュメントの状態を更新した意味ドキュメントで、メニュー項目を更新します。 ドキュメントには、おそらく、更新プログラムの基になる情報が含まれています。  
  
 コマンドに複数のユーザー インターフェイス オブジェクト (おそらくはメニュー項目とツール バー ボタン) がある場合は、両方は同じハンドラー関数にルーティングされます。 これには、1 か所で同等のユーザー インターフェイス オブジェクトのすべてのユーザー インターフェイス更新コードがカプセル化します。  
  
 フレームワークは、ユーザー インターフェイス オブジェクトを自動的に更新するための便利なインターフェイスを提供します。 その他の何らかの方法で更新を行うことができますが、提供されるインターフェイスは効率的かつ簡単に使用します。  
  
 次のトピックでは、更新ハンドラーの使用について説明します。  
  
-   [更新ハンドラーが呼び出されるタイミング](../mfc/when-update-handlers-are-called.md)  
  
-   [ON_UPDATE_COMMAND_UI マクロ](../mfc/on-update-command-ui-macro.md)  
  
-   [CCmdUI クラス](../mfc/the-ccmdui-class.md)  
  
## <a name="see-also"></a>関連項目  
 [メニュー](../mfc/menus-mfc.md)

