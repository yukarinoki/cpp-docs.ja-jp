---
title: イベントの処理に関するグローバル関数 |Microsoft Docs
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
ms.openlocfilehash: fcdf854eeeceb1aa3648ff984e3a2c956d973eeb
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43754677"
---
# <a name="event-handling-global-functions"></a>イベント処理に関するグローバル関数

この関数は、イベント ハンドラーを提供します。

> [!IMPORTANT]
>  Windows ランタイムで実行するアプリケーションでは、次の表に記載されている関数を使用できません。

|||
|-|-|
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|待機オブジェクトがシグナル状態に、その一方で、必要に応じてウィンドウ メッセージをディスパッチします。|  

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

*hEvent*  
[in]待機するオブジェクトのハンドル。

### <a name="return-value"></a>戻り値

オブジェクトがシグナル状態になった場合に TRUE を返します。

### <a name="remarks"></a>Remarks

これは、機能は、し、発生の原因が、通知を受けるオブジェクトのイベントを待機するウィンドウ メッセージを待機中にディスパッチできるようにする場合に便利です。

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)
