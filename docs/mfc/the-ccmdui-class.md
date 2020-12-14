---
description: 詳細については、「CCmdUI クラス」を参照してください。
title: CCmdUI クラス
ms.date: 11/04/2016
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
ms.openlocfilehash: 5fae6d2dda948fd3720a29d502d7f050e388bceb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216133"
---
# <a name="the-ccmdui-class"></a>CCmdUI クラス

更新コマンドがハンドラーにルーティングされると、フレームワークは、 `CCmdUI` オブジェクト (またはから派生したクラスのオブジェクト) へのポインターをハンドラーに渡し `CCmdUI` ます。 このオブジェクトは、コマンドを生成したメニュー項目またはツールバーボタンまたはその他のユーザーインターフェイスオブジェクトを表します。 更新ハンドラーは、 `CCmdUI` ポインターを介して構造体のメンバー関数を呼び出し、ユーザーインターフェイスオブジェクトを更新します。 たとえば、次に示すのは、[すべてクリア] メニュー項目の更新ハンドラーです。

[!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]

このハンドラーは、 `Enable` メニュー項目にアクセスできるオブジェクトのメンバー関数を呼び出します。 `Enable` 項目を使用できるようにします。

## <a name="see-also"></a>関連項目

[方法: User-Interface オブジェクトを更新する](../mfc/how-to-update-user-interface-objects.md)
