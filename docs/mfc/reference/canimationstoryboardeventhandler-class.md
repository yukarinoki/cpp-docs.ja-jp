---
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
ms.openlocfilehash: 986555ca91d19dfa838f807665f2cbf9a003bcef
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755110"
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
|[イベントハンドラー::Cアニメーションストーリーボードイベントハンドラ](#canimationstoryboardeventhandler)|`CAnimationStoryboardEventHandler` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[イベントハンドラー::インスタンスの作成](#createinstance)|コールバックのインスタンスを`CAnimationStoryboardEventHandler`作成します。|
|[イベントハンドラー::オンストーリーボードステータス変更](#onstoryboardstatuschanged)|ストーリー`OnStoryboardStatusChanged`ボードの状態が変化したときに発生するイベントを`CUIAnimationStoryboardEventHandlerBase::OnStoryboardStatusChanged`処理します (オーバーライド.|
|[イベントハンドラー::ストーリーボード更新](#onstoryboardupdated)|ストーリー`OnStoryboardUpdated`ボードが更新されたときに発生するイベントを`CUIAnimationStoryboardEventHandlerBase::OnStoryboardUpdated`処理します (オーバーライド .|
|[イベントハンドラー::アニメーションコントローラ](#setanimationcontroller)|イベントをルーティングするアニメーション コントローラへのポインターを格納します。|

## <a name="remarks"></a>解説

このイベント ハンドラは、 を`IUIAnimationStoryboard::SetStoryboardEventHandler`呼び出`CAnimationController::EnableStoryboardEventHandler`すと、メソッドに作成され、メソッドに渡されます。

## <a name="inheritance-hierarchy"></a>継承階層

`CUIAnimationCallbackBase`

`CUIAnimationStoryboardEventHandlerBase`

`CAnimationStoryboardEventHandler`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationstoryboardeventhandlercanimationstoryboardeventhandler"></a><a name="canimationstoryboardeventhandler"></a>イベントハンドラー::Cアニメーションストーリーボードイベントハンドラ

オブジェクトを構築します。

```
CAnimationStoryboardEventHandler();
```

## <a name="canimationstoryboardeventhandlercreateinstance"></a><a name="createinstance"></a>イベントハンドラー::インスタンスの作成

コールバックのインスタンスを作成します。

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationStoryboardEventHandler** ppHandler);
```

### <a name="parameters"></a>パラメーター

*を切り取る*<br/>
イベントを受け取るアニメーション コントローラへのポインター。

*ppHandler*

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="canimationstoryboardeventhandleronstoryboardstatuschanged"></a><a name="onstoryboardstatuschanged"></a>イベントハンドラー::オンストーリーボードステータス変更

ストーリーボードの状態が変更されたときに発生する OnStoryboardStatusChanged イベントを処理します。

```
IFACEMETHOD(OnStoryboardStatusChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in UI_ANIMATION_STORYBOARD_STATUS newStatus,
    __in UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```

### <a name="parameters"></a>パラメーター

*ストーリー ボード*<br/>
状態が変更されたストーリーボードへのポインター。

*newStatus*<br/>
新しいストーリーボードの状態を指定します。

*以前のステータス*<br/>
前のストーリーボードの状態を指定します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合はS_OK。それ以外の場合はE_FAIL。

## <a name="canimationstoryboardeventhandleronstoryboardupdated"></a><a name="onstoryboardupdated"></a>イベントハンドラー::ストーリーボード更新

ストーリーボードが更新されたときに発生する OnStoryboard イベントを処理します。

```
IFACEMETHOD(OnStoryboardUpdated) (__in IUIAnimationStoryboard* storyboard);
```

### <a name="parameters"></a>パラメーター

*ストーリー ボード*<br/>
更新されたストーリーボードへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合はS_OK。それ以外の場合はE_FAIL。

## <a name="canimationstoryboardeventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a>イベントハンドラー::アニメーションコントローラ

イベントをルーティングするアニメーション コントローラへのポインターを格納します。

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>パラメーター

*を切り取る*<br/>
イベントを受け取るアニメーション コントローラへのポインター。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
