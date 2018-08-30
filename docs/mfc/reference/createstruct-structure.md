---
title: CREATESTRUCT 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CREATESTRUCT
dev_langs:
- C++
helpviewer_keywords:
- CREATESTRUCT structure [MFC]
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 594f71d5166261dbb1bb08422a564157bfce2721
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203662"
---
# <a name="createstruct-structure"></a>CREATESTRUCT 構造体
`CREATESTRUCT`構造体は、アプリケーションのウィンドウ プロシージャに渡される初期化パラメーターを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagCREATESTRUCT {  
    LPVOID lpCreateParams;  
    HANDLE hInstance;  
    HMENU hMenu;  
    HWND hwndParent;  
    int cy;  
    int cx;  
    int y;  
    int x;  
    LONG style;  
    LPCSTR lpszName;  
    LPCSTR lpszClass;  
    DWORD dwExStyle;  
} CREATESTRUCT;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *lpCreateParams*  
 ウィンドウを作成するためのデータへのポインター。  
  
 *hInstance*  
 新しいウィンドウを所有しているモジュールのモジュール インスタンス ハンドルを識別します。  
  
 *hMenu*  
 新しいウィンドウで使用するメニューを識別します。 子ウィンドウの場合は、整数の ID が含まれています  
  
 *hwndParent*  
 新しいウィンドウを所有しているウィンドウを識別します。 新しいウィンドウが最上位ウィンドウの場合、このメンバーは NULL です。  
  
 *cy*  
 新しいウィンドウの高さを指定します。  
  
 *cx*  
 新しいウィンドウの幅を指定します。  
  
 *y*  
 新しいウィンドウの左上隅の y 座標を指定します。 新しいウィンドウが子ウィンドウの場合に、親ウィンドウとの相対座標はそれ以外の場合、座標は画面の原点は。  
  
 *x*  
 新しいウィンドウの左上隅の x 座標を指定します。 新しいウィンドウが子ウィンドウの場合に、親ウィンドウとの相対座標はそれ以外の場合、座標は画面の原点は。  
  
 *style*  
 新しいウィンドウの指定[スタイル](../../mfc/reference/styles-used-by-mfc.md)します。  
  
 *lpszName*  
 新しいウィンドウの名前を指定する null で終わる文字列へのポインター。  
  
 *lpszClass*  
 新しいウィンドウの Windows クラス名を指定する null で終わる文字列の指す (、 [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576)構造体は、詳細については、Windows SDK を参照してください)。  
  
 *dwExStyle*  
 指定します、[拡張スタイル](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)新しいウィンドウの。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)


