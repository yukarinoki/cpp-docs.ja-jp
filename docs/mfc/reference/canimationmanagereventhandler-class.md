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
ms.openlocfilehash: 58bb37e9de40f4bc711b417eab107aa55b8ff0e8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750121"
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
|[イベントハンドラー::Cアニメーションマネージャーイベントハンドラー](#canimationmanagereventhandler)|`CAnimationManagerEventHandler` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[イベントハンドラー::インスタンスの作成](#createinstance)|オブジェクトのインスタンスを`CAnimationManagerEventHandler`作成します。|
|[イベントハンドラー::オンマネージャーステータス変更](#onmanagerstatuschanged)|アニメーション マネージャーの状態が変更されたときに呼び出されます。 ( `CUIAnimationManagerEventHandlerBase::OnManagerStatusChanged`をオーバーライドします)。|
|[イベントハンドラー::アニメーションコントローラを設定します。](#setanimationcontroller)|イベントをルーティングするアニメーション コントローラへのポインターを格納します。|

## <a name="remarks"></a>解説

このイベント ハンドラーが作成され、メソッドに渡されます。

## <a name="inheritance-hierarchy"></a>継承階層

`CUIAnimationCallbackBase`

`CUIAnimationManagerEventHandlerBase`

`CAnimationManagerEventHandler`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationmanagereventhandlercanimationmanagereventhandler"></a><a name="canimationmanagereventhandler"></a>イベントハンドラー::Cアニメーションマネージャーイベントハンドラー

Visual Studio 2010 SP1 が必要です。

オブジェクトを構築します。

```
CAnimationManagerEventHandler();
```

## <a name="canimationmanagereventhandlercreateinstance"></a><a name="createinstance"></a>イベントハンドラー::インスタンスの作成

Visual Studio 2010 SP1 が必要です。

オブジェクトのインスタンスを作成します。

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationManagerEventHandler** ppManagerEventHandler);
```

### <a name="parameters"></a>パラメーター

*を切り取る*<br/>
イベントを受け取るアニメーション コントローラへのポインター。

*イベントハンドラー*<br/>
出力。 メソッドが成功すると、アニメーション マネージャのステータス更新を処理する COM オブジェクトへのポインタが含まれます。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="canimationmanagereventhandleronmanagerstatuschanged"></a><a name="onmanagerstatuschanged"></a>イベントハンドラー::オンマネージャーステータス変更

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

*以前のステータス*<br/>
前の状態。

### <a name="return-value"></a>戻り値

現在の実装は常にS_OK返します。

## <a name="canimationmanagereventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a>イベントハンドラー::アニメーションコントローラを設定します。

Visual Studio 2010 SP1 が必要です。

イベントをルーティングするアニメーション コントローラへのポインターを格納します。

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>パラメーター

*を切り取る*<br/>
イベントを受け取るアニメーション コントローラへのポインター。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
