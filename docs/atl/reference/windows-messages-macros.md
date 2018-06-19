---
title: Windows メッセージ マクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::WM_FORWARDMSG
dev_langs:
- C++
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21bb273b94f871e253ab927238c96256f46e2b3a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360218"
---
# <a name="windows-messages-macros"></a>Windows メッセージ マクロ
このマクロは、ウィンドウ メッセージを転送します。  
  
|||  
|-|-|  
|[WM_FORWARDMSG](#wm_forwardmsg)|処理するための別のウィンドウのウィンドウで受信メッセージの転送に使用します。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h 
   
##  <a name="wm_forwardmsg"></a>  WM_FORWARDMSG  
 このマクロは、処理の別のウィンドウをウィンドウによって受信されたメッセージを転送します。  
  
```
WM_FORWARDMSG
```  
  
### <a name="return-value"></a>戻り値  
 0 以外のメッセージが処理された場合は 0 以外の場合。  
  
### <a name="remarks"></a>コメント  
 使用して`WM_FORWARDMSG`を処理するための別のウィンドウのウィンドウで受信メッセージを転送します。 LPARAM と WPARAM パラメーターは、次のように使用されます。  
  
|パラメーター|使用法|  
|---------------|-----------|  
|WPARAM|ユーザーによって定義されるデータ|  
|LPARAM|ポインター、`MSG`メッセージに関する情報を格納する構造体|  
  
### <a name="example"></a>例  
 次の例では、`m_hWndOther`はこのメッセージを受信する他のウィンドウを表します。  
  
 [!code-cpp[NVC_ATL_Windowing#137](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [[マクロ]](../../atl/reference/atl-macros.md)
