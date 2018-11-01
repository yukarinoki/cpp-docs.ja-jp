---
title: CCmdUI クラス
ms.date: 11/04/2016
f1_keywords:
- CCmdUI
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
ms.openlocfilehash: 47ef359f71d9dd30f2ba1ff1c4cf504bccd33ffd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667949"
---
# <a name="the-ccmdui-class"></a>CCmdUI クラス

更新コマンドをハンドラーにルーティングするとき、フレームワーク、ハンドラーに渡しますへのポインターを`CCmdUI`オブジェクト (またはのオブジェクトを`CCmdUI`-派生クラス)。 このオブジェクトは、メニュー項目またはツール バー ボタンまたはコマンドを作成した他のユーザー インターフェイス オブジェクトを表します。 更新ハンドラーは、メンバーの関数を呼び出して、`CCmdUI`ユーザー インターフェイス オブジェクトを更新するポインターを通じて構造体。 たとえば、すべてクリア メニュー項目の更新ハンドラーを示します。

[!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]

このハンドラーを呼び出す、`Enable`メニュー アイテムへのアクセスを持つオブジェクトのメンバー関数。 `Enable` 使用可能な項目は、します。

## <a name="see-also"></a>関連項目

[ユーザー インターフェイス オブジェクトの更新方法](../mfc/how-to-update-user-interface-objects.md)

