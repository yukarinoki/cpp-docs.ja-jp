---
title: イベント処理グローバル関数
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
ms.openlocfilehash: f2f8269dcf0f59a5d0794d3f16d4c4f85d8841ac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330138"
---
# <a name="event-handling-global-functions"></a>イベント処理グローバル関数

この関数は、イベント ハンドラーを提供します。

> [!IMPORTANT]
> 次の表に示す関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

|||
|-|-|
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|オブジェクトがシグナル状態になるまで待機し、同時に必要に応じてウィンドウ メッセージをディスパッチします。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="atlwaitwithmessageloop"></a><a name="atlwaitwithmessageloop"></a>メッセージループを使用する

オブジェクトがシグナル状態になるまで待機します。その間、必要に応じてウィンドウ メッセージをディスパッチします。

> [!IMPORTANT]
> この関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```

### <a name="parameters"></a>パラメーター

*Hevent*<br/>
[in]待機するオブジェクトのハンドル。

### <a name="return-value"></a>戻り値

オブジェクトがシグナル状態になっている場合は TRUE を返します。

### <a name="remarks"></a>解説

これは、オブジェクトのイベントが発生するのを待ち、そのイベントが発生したことを通知するが、待機中にウィンドウメッセージをディスパッチできるようにする場合に便利です。

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)
