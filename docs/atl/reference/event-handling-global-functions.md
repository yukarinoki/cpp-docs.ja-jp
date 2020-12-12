---
description: 詳細については、「イベント処理のグローバル関数」を参照してください。
title: イベント処理のグローバル関数
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
ms.openlocfilehash: 89e5ec38ff8884f5b99592541df6e397e2dd7116
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139855"
---
# <a name="event-handling-global-functions"></a>イベント処理のグローバル関数

この関数は、イベントハンドラーを提供します。

> [!IMPORTANT]
> 次の表に示す関数は、Windows ランタイムで実行するアプリケーションでは使用できません。

|名前|説明|
|-|-|
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|オブジェクトがシグナル状態になるまで待機します。その間、必要に応じてウィンドウメッセージをディスパッチします。|

## <a name="requirements"></a>要件

**ヘッダー:** atlbase. h

## <a name="atlwaitwithmessageloop"></a><a name="atlwaitwithmessageloop"></a> AtlWaitWithMessageLoop

オブジェクトがシグナル状態になるまで待機します。その間、必要に応じてウィンドウ メッセージをディスパッチします。

> [!IMPORTANT]
> この関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```

### <a name="parameters"></a>パラメーター

*hEvent*<br/>
から待機するオブジェクトのハンドル。

### <a name="return-value"></a>戻り値

オブジェクトがシグナル状態になった場合に TRUE を返します。

### <a name="remarks"></a>解説

これは、オブジェクトのイベントが発生するまで待機し、待機中にウィンドウメッセージをディスパッチできるようにする場合に便利です。

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)
