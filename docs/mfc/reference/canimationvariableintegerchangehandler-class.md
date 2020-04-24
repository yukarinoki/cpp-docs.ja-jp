---
title: CAnimationVariableIntegerChangeHandler クラス
ms.date: 11/04/2016
f1_keywords:
- CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::SetAnimationController
helpviewer_keywords:
- CAnimationVariableIntegerChangeHandler [MFC], CAnimationVariableIntegerChangeHandler
- CAnimationVariableIntegerChangeHandler [MFC], CreateInstance
- CAnimationVariableIntegerChangeHandler [MFC], OnIntegerValueChanged
- CAnimationVariableIntegerChangeHandler [MFC], SetAnimationController
ms.assetid: 6ac8e91b-e514-4ff6-babd-33f77c4b2b61
ms.openlocfilehash: dec940d2f5e68f0531fc917df447b5a1a5cb8189
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755056"
---
# <a name="canimationvariableintegerchangehandler-class"></a>CAnimationVariableIntegerChangeHandler クラス

アニメーション変数の値が変化したときに Animation API によって呼び出されるコールバックを実装します。

## <a name="syntax"></a>構文

```
class CAnimationVariableIntegerChangeHandler : public CUIAnimationVariableIntegerChangeHandlerBase<CAnimationVariableIntegerChangeHandler>;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[変更ハンドラー::Cアニメーション変数整数変更ハンドラー](#canimationvariableintegerchangehandler)|`CAnimationVariableIntegerChangeHandler` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[変更ハンドラー::インスタンスの作成](#createinstance)|コールバックのインスタンスを`CAnimationVariableIntegerChangeHandler`作成します。|
|[変更ハンドラー::オン整数値変更](#onintegervaluechanged)|アニメーション変数の値が変更されたときに呼び出されます。 ( `CUIAnimationVariableIntegerChangeHandlerBase::OnIntegerValueChanged`をオーバーライドします)。|
|[変更ハンドラ::アニメーションを実行します。](#setanimationcontroller)|イベントをルーティングするアニメーション コントローラへのポインターを格納します。|

## <a name="remarks"></a>解説

このイベント ハンドラーが作成され、メソッドに渡されます。

## <a name="inheritance-hierarchy"></a>継承階層

[MFC クラス](../../mfc/reference/mfc-classes.md)

`CUIAnimationCallbackBase`

`CUIAnimationVariableIntegerChangeHandlerBase`

`CAnimationVariableIntegerChangeHandler`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationvariableintegerchangehandlercanimationvariableintegerchangehandler"></a><a name="canimationvariableintegerchangehandler"></a>変更ハンドラー::Cアニメーション変数整数変更ハンドラー

オブジェクトを構築します。

```
CAnimationVariableIntegerChangeHandler ();
```

## <a name="canimationvariableintegerchangehandlercreateinstance"></a><a name="createinstance"></a>変更ハンドラー::インスタンスの作成

コールバックのインスタンスを作成します。

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationVariableIntegerChangeHandler** ppHandler);
```

### <a name="parameters"></a>パラメーター

*を切り取る*<br/>
イベントを受け取るアニメーション コントローラへのポインター。

*ppHandler*

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="canimationvariableintegerchangehandleronintegervaluechanged"></a><a name="onintegervaluechanged"></a>変更ハンドラー::オン整数値変更

アニメーション変数の値が変更されたときに呼び出されます。

```
IFACEMETHOD(OnIntegerValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in INT32 newValue,
    __in INT32 previousValue);
```

### <a name="parameters"></a>パラメーター

*ストーリー ボード*<br/>
変数をアニメーション化しているストーリーボード。

*変数*<br/>
更新されたアニメーション変数。

*newValue*<br/>
新しい丸められた値。

*以前の値*<br/>
直前の丸められた値。

### <a name="return-value"></a>戻り値

メソッドが成功した場合はS_OK。それ以外の場合はE_FAIL。

## <a name="canimationvariableintegerchangehandlersetanimationcontroller"></a><a name="setanimationcontroller"></a>変更ハンドラ::アニメーションを実行します。

イベントをルーティングするアニメーション コントローラへのポインターを格納します。

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>パラメーター

*を切り取る*<br/>
イベントを受け取るアニメーション コントローラへのポインター。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
