---
title: WINDOWPLACEMENT 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- WINDOWPLACEMENT
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPLACEMENT structure [MFC]
ms.assetid: ea7d61f6-eb57-478e-9b08-7c1d07091aa8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 829b3c90acb089bd91d71c498df5906fff919f22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="windowplacement-structure"></a>WINDOWPLACEMENT 構造体
`WINDOWPLACEMENT`構造体には、画面上のウィンドウの配置に関する情報が含まれています。**です。**  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagWINDOWPLACEMENT {     /* wndpl */  
    UINT length;  
    UINT flags;  
    UINT showCmd;  
    POINT ptMinPosition;  
    POINT ptMaxPosition;  
    RECT rcNormalPosition;  
} WINDOWPLACEMENT;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *length*  
 構造体のバイト単位で長さを指定**です。**  
  
 `flags`  
 最小化ウィンドウと、ウィンドウを復元する方法の位置を制御するフラグを指定します。 このメンバーは、次のフラグの一方または両方を指定できます。  
  
- **WPF_SETMINPOSITION**最小化されたウィンドウの x 位置と y 位置を指定できることを示す**です。** このフラグである必要があります指定されたかどうかに、座標を設定、 **ptMinPosition**メンバー。  
  
- **WPF_RESTORETOMAXIMIZED**復元されたウィンドウが最大化される、最小化する前に、最大化されていたかどうかに関係なくを指定します。 この設定は、ウィンドウが復元されるときにのみ有効です。 既定の復元動作は変わりません。 このフラグは有効な場合にのみ、 **SW_SHOWMINIMIZED**値が指定されて、 **showCmd**メンバー。  
  
 *showCmd*  
 ウィンドウの現在の表示状態を指定します。 このメンバーは、次の値のいずれかになります。  
  
- **SW_HIDE**ウィンドウを非表示にし、別のウィンドウをアクティブ化を渡します。  
  
- **SW_MINIMIZE**指定されたウィンドウを最小化し、システムの一覧にあるトップレベル ウィンドウをアクティブにします。  
  
- **SW_RESTORE**にアクティブとウィンドウが表示されます。 ウィンドウが最小または最大化、Windows に復元されます、元のサイズと位置 (同じ**SW_SHOWNORMAL**)。  
  
- **SW_SHOW**ウィンドウをアクティブにし、現在のサイズと位置で表示します。  
  
- **SW_SHOWMAXIMIZED**ウィンドウをアクティブにし、最大化されたウィンドウとして表示します。  
  
- **このメンバーは**ウィンドウをアクティブにし、アイコンとして表示します。  
  
- **SW_SHOWMINNOACTIVE**ウィンドウをアイコンとして表示します。 現在アクティブなウィンドウは、アクティブなままです。  
  
- **SW_SHOWNA**現在の状態で、ウィンドウを表示します。 現在アクティブなウィンドウは、アクティブなままです。  
  
- **SW_SHOWNOACTIVATE**最新のサイズと位置で、ウィンドウを表示します。 現在アクティブなウィンドウは、アクティブなままです。  
  
- **SW_SHOWNORMAL**にアクティブとウィンドウが表示されます。 ウィンドウが最小または最大化、Windows に復元されます、元のサイズと位置 (同じ**SW_RESTORE**)。  
  
 *ptMinPosition*  
 ウィンドウが最小化したときに、ウィンドウの左上隅の位置を指定します。  
  
 `ptMaxPosition`  
 ウィンドウを最大化するときは、ウィンドウの左上隅の位置を指定します。  
  
 *rcNormalPosition*  
 ウィンドウは、通常の (復元) の位置にあるときは、ウィンドウの座標を指定します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::SetWindowPlacement](../../mfc/reference/cwnd-class.md#setwindowplacement)

