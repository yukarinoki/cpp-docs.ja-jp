---
description: '詳細情報: CAnimationStoryboardEventHandler クラス'
title: CAnimationStoryboardEventHandler クラス
ms.date: 11/04/2016
f1_keywords:
- CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::OnStoryboardStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::OnStoryboardUpdated
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationStoryboardEventHandler [MFC], CAnimationStoryboardEventHandler
- CAnimationStoryboardEventHandler [MFC], CreateInstance
- CAnimationStoryboardEventHandler [MFC], OnStoryboardStatusChanged
- CAnimationStoryboardEventHandler [MFC], OnStoryboardUpdated
- CAnimationStoryboardEventHandler [MFC], SetAnimationController
ms.assetid: 10a7e86b-c02d-4124-9a2e-61ecf8ac62fc
ms.openlocfilehash: 7208ba91ec78a6de688699183b55a691b8e3d28d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254743"
---
# <a name="canimationstoryboardeventhandler-class"></a>CAnimationStoryboardEventHandler クラス

ストーリーボードのステータスの変更時またはストーリーボードの更新時に Animation API によって呼び出されるコールバックを実装します。

## <a name="syntax"></a>構文

```
class CAnimationStoryboardEventHandler : public CUIAnimationStoryboardEventHandlerBase<CAnimationStoryboardEventHandler>;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAnimationStoryboardEventHandler:: CAnimationStoryboardEventHandler](#canimationstoryboardeventhandler)|`CAnimationStoryboardEventHandler` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAnimationStoryboardEventHandler:: CreateInstance](#createinstance)|コールバックのインスタンスを作成し `CAnimationStoryboardEventHandler` ます。|
|[CAnimationStoryboardEventHandler:: OnStoryboardStatusChanged](#onstoryboardstatuschanged)|`OnStoryboardStatusChanged`ストーリーボードの状態が変化したときに発生するイベントを処理 `CUIAnimationStoryboardEventHandlerBase::OnStoryboardStatusChanged` します (オーバーライドします)。|
|[CAnimationStoryboardEventHandler:: OnStoryboardUpdated](#onstoryboardupdated)|`OnStoryboardUpdated`ストーリーボードが更新されたときに発生するイベントを処理 `CUIAnimationStoryboardEventHandlerBase::OnStoryboardUpdated` します (オーバーライドします)。|
|[CAnimationStoryboardEventHandler:: Setアニメーションコントローラー](#setanimationcontroller)|イベントをルーティングするアニメーションコントローラーへのポインターを格納します。|

## <a name="remarks"></a>解説

このイベントハンドラーは、を呼び出すときに作成され、メソッドに渡され `IUIAnimationStoryboard::SetStoryboardEventHandler` `CAnimationController::EnableStoryboardEventHandler` ます。

## <a name="inheritance-hierarchy"></a>継承階層

`CUIAnimationCallbackBase`

`CUIAnimationStoryboardEventHandlerBase`

`CAnimationStoryboardEventHandler`

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationstoryboardeventhandlercanimationstoryboardeventhandler"></a><a name="canimationstoryboardeventhandler"></a> CAnimationStoryboardEventHandler:: CAnimationStoryboardEventHandler

CAnimationStoryboardEventHandler オブジェクトを構築します。

```
CAnimationStoryboardEventHandler();
```

## <a name="canimationstoryboardeventhandlercreateinstance"></a><a name="createinstance"></a> CAnimationStoryboardEventHandler:: CreateInstance

CAnimationStoryboardEventHandler callback のインスタンスを作成します。

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationStoryboardEventHandler** ppHandler);
```

### <a name="parameters"></a>パラメーター

*pAnimationController*<br/>
イベントを受信するアニメーションコントローラーへのポインター。

*ppHandler*

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラーコードを返します。

## <a name="canimationstoryboardeventhandleronstoryboardstatuschanged"></a><a name="onstoryboardstatuschanged"></a> CAnimationStoryboardEventHandler:: OnStoryboardStatusChanged

ストーリーボードの状態が変化したときに発生する OnStoryboardStatusChanged イベントを処理します。

```
IFACEMETHOD(OnStoryboardStatusChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in UI_ANIMATION_STORYBOARD_STATUS newStatus,
    __in UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```

### <a name="parameters"></a>パラメーター

*storyboard*<br/>
状態が変化したストーリーボードへのポインター。

*newStatus*<br/>
新しいストーリーボードの状態を指定します。

*前の状態*<br/>
前のストーリーボードの状態を指定します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は S_OK。それ以外の場合は E_FAIL。

## <a name="canimationstoryboardeventhandleronstoryboardupdated"></a><a name="onstoryboardupdated"></a> CAnimationStoryboardEventHandler:: OnStoryboardUpdated

ストーリーボードが更新されたときに発生する OnStoryboardUpdated イベントを処理します

```
IFACEMETHOD(OnStoryboardUpdated) (__in IUIAnimationStoryboard* storyboard);
```

### <a name="parameters"></a>パラメーター

*storyboard*<br/>
更新されたストーリーボードへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は S_OK。それ以外の場合は E_FAIL。

## <a name="canimationstoryboardeventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a> CAnimationStoryboardEventHandler:: Setアニメーションコントローラー

イベントをルーティングするアニメーションコントローラーへのポインターを格納します。

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>パラメーター

*pAnimationController*<br/>
イベントを受信するアニメーションコントローラーへのポインター。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
