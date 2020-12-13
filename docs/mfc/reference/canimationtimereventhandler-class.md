---
description: '詳細情報: CAnimationTimerEventHandler クラス'
title: CAnimationTimerEventHandler クラス
ms.date: 11/04/2016
f1_keywords:
- CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPostUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPreUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnRenderingTooSlow
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationTimerEventHandler [MFC], CreateInstance
- CAnimationTimerEventHandler [MFC], OnPostUpdate
- CAnimationTimerEventHandler [MFC], OnPreUpdate
- CAnimationTimerEventHandler [MFC], OnRenderingTooSlow
- CAnimationTimerEventHandler [MFC], SetAnimationController
ms.assetid: 188dea3b-4b5e-4f6b-8df9-09d993a21619
ms.openlocfilehash: 5d5f3e07eeb7ffe3f3bb226afd566330808303ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336752"
---
# <a name="canimationtimereventhandler-class"></a>CAnimationTimerEventHandler クラス

タイミング イベントの発生時に Animation API によって呼び出されるコールバックを実装します。

## <a name="syntax"></a>構文

```
class CAnimationTimerEventHandler : public CUIAnimationTimerEventHandlerBase<CAnimationTimerEventHandler>;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAnimationTimerEventHandler:: CreateInstance](#createinstance)|コールバックのインスタンスを作成し `CAnimationTimerEventHandler` ます。|
|[CAnimationTimerEventHandler:: OnPostUpdate](#onpostupdate)|アニメーションの更新が完了した後に発生するイベントを処理します。 ( `CUIAnimationTimerEventHandlerBase::OnPostUpdate`をオーバーライドします)。|
|[CAnimationTimerEventHandler:: OnPreUpdate](#onpreupdate)|アニメーションの更新が開始される前に発生するイベントを処理します。 ( `CUIAnimationTimerEventHandlerBase::OnPreUpdate`をオーバーライドします)。|
|[CAnimationTimerEventHandler:: OnRenderingTooSlow](#onrenderingtooslow)|アニメーションのレンダリングフレームレートが望ましいフレームレートの最小値を下回ると発生するイベントを処理します。 ( `CUIAnimationTimerEventHandlerBase::OnRenderingTooSlow`をオーバーライドします)。|
|[CAnimationTimerEventHandler:: Setアニメーションコントローラー](#setanimationcontroller)|イベントをルーティングするアニメーションコントローラーへのポインターを格納します。|

## <a name="remarks"></a>解説

このイベントハンドラーは作成され、CAnimationController:: EnableAnimationTimerEventHandler を呼び出すと Iui、Timer:: SetTimerEventHandler に渡されます。

## <a name="inheritance-hierarchy"></a>継承階層

`CUIAnimationCallbackBase`

`CUIAnimationTimerEventHandlerBase`

`CAnimationTimerEventHandler`

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationtimereventhandlercreateinstance"></a><a name="createinstance"></a> CAnimationTimerEventHandler:: CreateInstance

CAnimationTimerEventHandler コールバックのインスタンスを作成します。

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationTimerEventHandler** ppTimerEventHandler);
```

### <a name="parameters"></a>パラメーター

*pAnimationController*<br/>
イベントを受信するアニメーションコントローラーへのポインター。

*ppTimerEventHandler*

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラーコードを返します。

## <a name="canimationtimereventhandleronpostupdate"></a><a name="onpostupdate"></a> CAnimationTimerEventHandler:: OnPostUpdate

アニメーションの更新が完了した後に発生するイベントを処理します。

```
IFACEMETHOD(OnPostUpdate)();
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合は S_OK。それ以外の場合は E_FAIL。

## <a name="canimationtimereventhandleronpreupdate"></a><a name="onpreupdate"></a> CAnimationTimerEventHandler:: OnPreUpdate

アニメーションの更新が開始される前に発生するイベントを処理します。

```
IFACEMETHOD(OnPreUpdate)();
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合は S_OK。それ以外の場合は E_FAIL。

## <a name="canimationtimereventhandleronrenderingtooslow"></a><a name="onrenderingtooslow"></a> CAnimationTimerEventHandler:: OnRenderingTooSlow

アニメーションのレンダリングフレームレートが望ましいフレームレートの最小値を下回ると発生するイベントを処理します。

```
IFACEMETHOD(OnRenderingTooSlow)(UINT32 fps);
```

### <a name="parameters"></a>パラメーター

*fps*

### <a name="return-value"></a>戻り値

メソッドが成功した場合は S_OK。それ以外の場合は E_FAIL。

## <a name="canimationtimereventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a> CAnimationTimerEventHandler:: Setアニメーションコントローラー

イベントをルーティングするアニメーションコントローラーへのポインターを格納します。

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>パラメーター

*pAnimationController*<br/>
イベントを受信するアニメーションコントローラーへのポインター。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
