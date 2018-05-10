---
title: イベント処理のグローバル関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
dev_langs:
- C++
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb2c7834e7d5475810973a42ef179ea4f5f0079f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="event-handling-global-functions"></a>イベント処理のグローバル関数
この関数は、イベント ハンドラーを提供します。  
  
> [!IMPORTANT]
>  Windows ランタイムで実行するアプリケーションでは、次の表に記載されている関数を使用できません。  
  
|||  
|-|-|  
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|その一方で、必要に応じてウィンドウ メッセージのディスパッチが通知されるオブジェクトを待機します。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  

##  <a name="atlwaitwithmessageloop"></a>  AtlWaitWithMessageLoop  
 オブジェクトがシグナル状態になるまで待機します。その間、必要に応じてウィンドウ メッセージをディスパッチします。  
  
> [!IMPORTANT]
>  この関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```  
  
### <a name="parameters"></a>パラメーター  
 `hEvent`  
 [in]待機するオブジェクトのハンドル。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**オブジェクトがシグナル状態になった場合。  
  
### <a name="remarks"></a>コメント  
 これは、オブジェクトのイベントを発生し、発生していることを通知するを待機するを待機中にディスパッチするウィンドウ メッセージを許可する場合に便利です。  
  
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)
