---
title: CCmdUI クラス
ms.date: 11/04/2016
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
ms.openlocfilehash: 105aa7ad6c5cc6a5563dbde8145327a2b3d066a1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447145"
---
# <a name="the-ccmdui-class"></a>CCmdUI クラス

更新コマンドがハンドラーにルーティングされると、フレームワークは、`CCmdUI` オブジェクト (または `CCmdUI`派生クラスのオブジェクト) へのポインターをハンドラーに渡します。 このオブジェクトは、コマンドを生成したメニュー項目またはツールバーボタンまたはその他のユーザーインターフェイスオブジェクトを表します。 更新ハンドラーは、ポインターを介して `CCmdUI` 構造体のメンバー関数を呼び出して、ユーザーインターフェイスオブジェクトを更新します。 たとえば、次に示すのは、[すべてクリア] メニュー項目の更新ハンドラーです。

[!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]

このハンドラーは、メニュー項目にアクセスできるオブジェクトの `Enable` メンバー関数を呼び出します。 `Enable` 項目を使用できるようにします。

## <a name="see-also"></a>参照

[ユーザー インターフェイス オブジェクトの更新方法](../mfc/how-to-update-user-interface-objects.md)
