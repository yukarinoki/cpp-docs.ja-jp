---
title: ポップアップ メニューを C++ アプリケーションに接続する |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- pop-up menus [C++], connecting to applications
- context menus [C++], connecting to applications
- menus [C++], pop-up
- shortcut menus [C++], connecting to applications
ms.assetid: 295cbf0e-6416-478e-bc3d-472fb98e0e52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f1ebb5e2151fe770e6a59210ac564237155fafd4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412081"
---
# <a name="connecting-a-pop-up-menu-to-your-c-application"></a>ポップアップ メニューを C++ アプリケーションに接続します。

### <a name="to-connect-a-pop-up-menu-to-your-application"></a>ショートカット メニューをアプリケーションに関連付けるには

1. (たとえば) WM_CONTEXTMENU のメッセージ ハンドラーを追加します。 詳細については、次を参照してください。[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md)します。

2. 次のコードをメッセージ ハンドラーに追加します。

    ```cpp
    CMenu menu;
    VERIFY(menu.LoadMenu(IDR_MENU1));
    CMenu* pPopup = menu.GetSubMenu(0);
    ASSERT(pPopup != NULL);
    pPopup->TrackPopupMenu(TPM_LEFTALIGN | TPM_RIGHTBUTTON, point.x, point.y, AfxGetMainWnd());
    ```

   > [!NOTE]
   > [CPoint](../atl-mfc-shared/reference/cpoint-class.md)渡されたハンドラーが画面座標では、メッセージによって。

## <a name="requirements"></a>要件

MFC

## <a name="see-also"></a>関連項目

[ショートカット メニューの作成](../windows/creating-pop-up-menus.md)<br/>
[メニュー エディター](../windows/menu-editor.md)  