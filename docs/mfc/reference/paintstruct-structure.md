---
title: PAINTSTRUCT 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- PAINTSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- PAINTSTRUCT structure [MFC]
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75a3db6c6beb18afe2303b464fcab290b2e132fc
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338211"
---
# <a name="paintstruct-structure"></a>PAINTSTRUCT 構造体
`PAINTSTRUCT`構造体には、ウィンドウのクライアント領域の描画に使用できる情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagPAINTSTRUCT {  
    HDC hdc;  
    BOOL fErase;  
    RECT rcPaint;  
    BOOL fRestore;  
    BOOL fIncUpdate;  
    BYTE rgbReserved[16];  
} PAINTSTRUCT;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *hdc*  
 描画に使用するディスプレイ コンテキストを識別します。  
  
 *fErase*  
 バック グラウンドが再描画する必要があるかどうかを指定します。 アプリケーションがバック グラウンドを再描画する場合は 0。 背景ブラシなし Windows ウィンドウ クラスを作成した場合、背景を描画するため、アプリケーションは、(の説明を参照して、`hbrBackground`のメンバー、 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) Windows SDK の構造)。  
  
 *rcPaint*  
 左上隅を指定して、描画が要求された四角形の右下します。  
  
 *fRestore*  
 予約済みのメンバー。 Windows によって内部的に使用されます。  
  
 *fIncUpdate*  
 予約済みのメンバー。 Windows によって内部的に使用されます。  
  
 *rgbReserved [16]*  
 予約済みのメンバー。 Windows によって内部的に使用されるメモリの予約済みのブロック。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPaintDC::m_ps](../../mfc/reference/cpaintdc-class.md#m_ps)

