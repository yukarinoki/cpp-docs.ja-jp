---
title: CCmdUI クラス |Microsoft Docs
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
ms.openlocfilehash: 18b5675aff2d10f224238a1ba6d3b919e1b285a7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374583"
---
# <a name="the-ccmdui-class"></a>CCmdUI クラス

更新コマンドをハンドラーにルーティングするとき、フレームワーク、ハンドラーに渡しますへのポインターを`CCmdUI`オブジェクト (またはのオブジェクトを`CCmdUI`-派生クラス)。 このオブジェクトは、メニュー項目またはツール バー ボタンまたはコマンドを作成した他のユーザー インターフェイス オブジェクトを表します。 更新ハンドラーは、メンバーの関数を呼び出して、`CCmdUI`ユーザー インターフェイス オブジェクトを更新するポインターを通じて構造体。 たとえば、すべてクリア メニュー項目の更新ハンドラーを示します。

[!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]

このハンドラーを呼び出す、`Enable`メニュー アイテムへのアクセスを持つオブジェクトのメンバー関数。 `Enable` 使用可能な項目は、します。

## <a name="see-also"></a>関連項目

[ユーザー インターフェイス オブジェクトの更新方法](../mfc/how-to-update-user-interface-objects.md)

