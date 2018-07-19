---
title: CCmdUI クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CCmdUI
dev_langs:
- C++
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a857d1cddcc78c7cfff4243b9c99194986af3d9b
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956487"
---
# <a name="the-ccmdui-class"></a>CCmdUI クラス
そのハンドラーを update コマンドにルーティング、フレームワークに渡しますハンドラーへのポインター、`CCmdUI`オブジェクト (またはオブジェクトへの`CCmdUI`-派生クラス)。 このオブジェクトは、メニュー項目またはツール バー ボタンまたはコマンドを作成した他のユーザー インターフェイス オブジェクトを表します。 更新ハンドラーは、メンバーの関数を呼び出して、`CCmdUI`ユーザー インターフェイス オブジェクトを更新するポインターを通じて構造体。 たとえば、すべてクリア メニュー項目の更新ハンドラーを次に示します。  
  
 [!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]  
  
 このハンドラーを呼び出す、`Enable`メニュー項目へのアクセスを持つオブジェクトのメンバー関数。 `Enable` 項目を使用するためが可能になります。  
  
## <a name="see-also"></a>関連項目  
 [ユーザー インターフェイス オブジェクトの更新方法](../mfc/how-to-update-user-interface-objects.md)

