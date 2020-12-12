---
description: '詳細情報: CAnimationManagerEventHandler クラス'
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
ms.openlocfilehash: aab944c23822486bbc04bb7710d257dd8c42beed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207947"
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
|[CAnimationManagerEventHandler:: CAnimationManagerEventHandler](#canimationmanagereventhandler)|`CAnimationManagerEventHandler` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAnimationManagerEventHandler:: CreateInstance](#createinstance)|オブジェクトのインスタンスを作成し `CAnimationManagerEventHandler` ます。|
|[CAnimationManagerEventHandler:: OnManagerStatusChanged](#onmanagerstatuschanged)|アニメーションマネージャーの状態が変更されたときに呼び出されます。 ( `CUIAnimationManagerEventHandlerBase::OnManagerStatusChanged`をオーバーライドします)。|
|[CAnimationManagerEventHandler:: Setアニメーションコントローラー](#setanimationcontroller)|イベントをルーティングするアニメーションコントローラーへのポインターを格納します。|

## <a name="remarks"></a>解説

このイベントハンドラーは、CAnimationController:: Enableの Eventhandler イベントを呼び出すときに作成され、IUIAnimationManager:: SetManagerEventHandler メソッドに渡されます。

## <a name="inheritance-hierarchy"></a>継承階層

`CUIAnimationCallbackBase`

`CUIAnimationManagerEventHandlerBase`

`CAnimationManagerEventHandler`

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationmanagereventhandlercanimationmanagereventhandler"></a><a name="canimationmanagereventhandler"></a> CAnimationManagerEventHandler:: CAnimationManagerEventHandler

Visual Studio 2010 SP1 が必要です。

CAnimationManagerEventHandler オブジェクトを構築します。

```
CAnimationManagerEventHandler();
```

## <a name="canimationmanagereventhandlercreateinstance"></a><a name="createinstance"></a> CAnimationManagerEventHandler:: CreateInstance

Visual Studio 2010 SP1 が必要です。

CAnimationManagerEventHandler オブジェクトのインスタンスを作成します。

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationManagerEventHandler** ppManagerEventHandler);
```

### <a name="parameters"></a>パラメーター

*pAnimationController*<br/>
イベントを受信するアニメーションコントローラーへのポインター。

*ppManagerEventHandler*<br/>
出力。 メソッドが成功した場合は、アニメーションマネージャーのステータスの更新を処理する COM オブジェクトへのポインターが含まれています。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラーコードを返します。

## <a name="canimationmanagereventhandleronmanagerstatuschanged"></a><a name="onmanagerstatuschanged"></a> CAnimationManagerEventHandler:: OnManagerStatusChanged

Visual Studio 2010 SP1 が必要です。

アニメーションマネージャーの状態が変更されたときに呼び出されます。

```
IFACEMETHOD(OnManagerStatusChanged)(
    UI_ANIMATION_MANAGER_STATUS newStatus,
    UI_ANIMATION_MANAGER_STATUS previousStatus);
```

### <a name="parameters"></a>パラメーター

*newStatus*<br/>
新しい状態。

*前の状態*<br/>
以前の状態。

### <a name="return-value"></a>戻り値

現在の実装は常に S_OK を返します。

## <a name="canimationmanagereventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a> CAnimationManagerEventHandler:: Setアニメーションコントローラー

Visual Studio 2010 SP1 が必要です。

イベントをルーティングするアニメーションコントローラーへのポインターを格納します。

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>パラメーター

*pAnimationController*<br/>
イベントを受信するアニメーションコントローラーへのポインター。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
