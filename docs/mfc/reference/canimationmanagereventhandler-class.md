---
title: CAnimationManagerEventHandler クラス
ms.date: 11/04/2016
f1_keywords:
- CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::OnManagerStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationManagerEventHandler [MFC], CAnimationManagerEventHandler
- CAnimationManagerEventHandler [MFC], CreateInstance
- CAnimationManagerEventHandler [MFC], OnManagerStatusChanged
- CAnimationManagerEventHandler [MFC], SetAnimationController
ms.assetid: 6089ec07-e661-4805-b227-823b4652aade
ms.openlocfilehash: 6661da55d1091394cff9db4589bc05c721b5ab7c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281071"
---
# <a name="canimationmanagereventhandler-class"></a>CAnimationManagerEventHandler クラス

アニメーション マネージャーのステータスの変更時に Animation API によって呼び出されるコールバックを実装します。

## <a name="syntax"></a>構文

```
class CAnimationManagerEventHandler : public CUIAnimationManagerEventHandlerBase<CAnimationManagerEventHandler>;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAnimationManagerEventHandler::CAnimationManagerEventHandler](#canimationmanagereventhandler)|`CAnimationManagerEventHandler` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAnimationManagerEventHandler::CreateInstance](#createinstance)|インスタンスを作成します`CAnimationManagerEventHandler`オブジェクト。|
|[CAnimationManagerEventHandler::OnManagerStatusChanged](#onmanagerstatuschanged)|アニメーション マネージャーの状態が変更されたときに呼び出されます。 ( `CUIAnimationManagerEventHandlerBase::OnManagerStatusChanged`をオーバーライドします)。|
|[CAnimationManagerEventHandler::SetAnimationController](#setanimationcontroller)|イベントをルーティングするアニメーション コント ローラーへのポインターを格納します。|

## <a name="remarks"></a>Remarks

このイベント ハンドラーが作成され、CAnimationController::EnableAnimationManagerEvent を呼び出すときに、IUIAnimationManager::SetManagerEventHandler メソッドに渡されます。

## <a name="inheritance-hierarchy"></a>継承階層

`CUIAnimationCallbackBase`

`CUIAnimationManagerEventHandlerBase`

`CAnimationManagerEventHandler`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

##  <a name="canimationmanagereventhandler"></a>  CAnimationManagerEventHandler::CAnimationManagerEventHandler

Visual Studio 2010 SP1 が必要です。

CAnimationManagerEventHandler オブジェクトを構築します。

```
CAnimationManagerEventHandler();
```

##  <a name="createinstance"></a>  CAnimationManagerEventHandler::CreateInstance

Visual Studio 2010 SP1 が必要です。

CAnimationManagerEventHandler オブジェクトのインスタンスを作成します。

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationManagerEventHandler** ppManagerEventHandler);
```

### <a name="parameters"></a>パラメーター

*pAnimationController*<br/>
イベントを受信するアニメーション コント ローラーへのポインター。

*ppManagerEventHandler*<br/>
出力します。 メソッドでは、それが成功した場合は、状態が更新され、アニメーション マネージャーを処理する COM オブジェクトへのポインターが含まれています。

### <a name="return-value"></a>戻り値

メソッドが成功すると、S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。

##  <a name="onmanagerstatuschanged"></a>  CAnimationManagerEventHandler::OnManagerStatusChanged

Visual Studio 2010 SP1 が必要です。

アニメーション マネージャーの状態が変更されたときに呼び出されます。

```
IFACEMETHOD(OnManagerStatusChanged)(
  UI_ANIMATION_MANAGER_STATUS newStatus,
  UI_ANIMATION_MANAGER_STATUS previousStatus);
```

### <a name="parameters"></a>パラメーター

*newStatus*<br/>
新しいステータス。

*previousStatus*<br/>
以前の状態。

### <a name="return-value"></a>戻り値

現在の実装を常に S_OK を返します。

##  <a name="setanimationcontroller"></a>  CAnimationManagerEventHandler::SetAnimationController

Visual Studio 2010 SP1 が必要です。

イベントをルーティングするアニメーション コント ローラーへのポインターを格納します。

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>パラメーター

*pAnimationController*<br/>
イベントを受信するアニメーション コント ローラーへのポインター。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
