---
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
ms.openlocfilehash: d1653e50fef03deb8eb23dd9a989d1ca2a529dd8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755094"
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
|[をイベントします。](#createinstance)|コールバックのインスタンスを`CAnimationTimerEventHandler`作成します。|
|[イベントハンドラー::オンポストアップデート](#onpostupdate)|アニメーションの更新が完了した後に発生するイベントを処理します。 ( `CUIAnimationTimerEventHandlerBase::OnPostUpdate`をオーバーライドします)。|
|[イベントハンドラー::オンプレアップデート](#onpreupdate)|アニメーションの更新が開始される前に発生するイベントを処理します。 ( `CUIAnimationTimerEventHandlerBase::OnPreUpdate`をオーバーライドします)。|
|[イベントハンドラー::レンダリングスロー](#onrenderingtooslow)|アニメーションのレンダリング フレーム レートが望ましい最小フレーム レートを下回ったときに発生するイベントを処理します。 ( `CUIAnimationTimerEventHandlerBase::OnRenderingTooSlow`をオーバーライドします)。|
|[を設定します。](#setanimationcontroller)|イベントをルーティングするアニメーション コントローラへのポインターを格納します。|

## <a name="remarks"></a>解説

このイベント ハンドラーが作成され、C アニメーション コントローラーを呼び出すと IUI アニメーション タイマー:::設定タイマー イベント ハンドラーに渡されます。

## <a name="inheritance-hierarchy"></a>継承階層

`CUIAnimationCallbackBase`

`CUIAnimationTimerEventHandlerBase`

`CAnimationTimerEventHandler`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationtimereventhandlercreateinstance"></a><a name="createinstance"></a>をイベントします。

コールバックのインスタンスを作成します。

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationTimerEventHandler** ppTimerEventHandler);
```

### <a name="parameters"></a>パラメーター

*を切り取る*<br/>
イベントを受け取るアニメーション コントローラへのポインター。

*イベントハンドラー*

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="canimationtimereventhandleronpostupdate"></a><a name="onpostupdate"></a>イベントハンドラー::オンポストアップデート

アニメーションの更新が完了した後に発生するイベントを処理します。

```
IFACEMETHOD(OnPostUpdate)();
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合はS_OK。それ以外の場合はE_FAIL。

## <a name="canimationtimereventhandleronpreupdate"></a><a name="onpreupdate"></a>イベントハンドラー::オンプレアップデート

アニメーションの更新が開始される前に発生するイベントを処理します。

```
IFACEMETHOD(OnPreUpdate)();
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合はS_OK。それ以外の場合はE_FAIL。

## <a name="canimationtimereventhandleronrenderingtooslow"></a><a name="onrenderingtooslow"></a>イベントハンドラー::レンダリングスロー

アニメーションのレンダリング フレーム レートが望ましい最小フレーム レートを下回ったときに発生するイベントを処理します。

```
IFACEMETHOD(OnRenderingTooSlow)(UINT32 fps);
```

### <a name="parameters"></a>パラメーター

*Fps*

### <a name="return-value"></a>戻り値

メソッドが成功した場合はS_OK。それ以外の場合はE_FAIL。

## <a name="canimationtimereventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a>を設定します。

イベントをルーティングするアニメーション コントローラへのポインターを格納します。

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>パラメーター

*を切り取る*<br/>
イベントを受け取るアニメーション コントローラへのポインター。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
