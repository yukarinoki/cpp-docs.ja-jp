---
description: '詳細情報: CAnimationVariableChangeHandler クラス'
title: CAnimationVariableChangeHandler クラス
ms.date: 11/04/2016
f1_keywords:
- CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::OnValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::SetAnimationController
helpviewer_keywords:
- CAnimationVariableChangeHandler [MFC], OnValueChanged
- CAnimationVariableChangeHandler [MFC], SetAnimationController
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
ms.openlocfilehash: 1c97bc908a29bfb7edf2222f6df117fefdaf4091
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207879"
---
# <a name="canimationvariablechangehandler-class"></a>CAnimationVariableChangeHandler クラス

アニメーション変数の値が変化したときに Animation API によって呼び出されるコールバックを実装します。

## <a name="syntax"></a>構文

```
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|`CAnimationVariableChangeHandler` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CreateInstance`|オブジェクトのインスタンスを作成し `CAnimationVariableChangeHandler` ます。|
|[CAnimationVariableChangeHandler:: OnValueChanged](#onvaluechanged)|アニメーション変数の値が変更されたときに呼び出されます。 ( `CUIAnimationVariableChangeHandlerBase::OnValueChanged`をオーバーライドします)。|
|[CAnimationVariableChangeHandler:: Setアニメーションコントローラー](#setanimationcontroller)|イベントをルーティングするアニメーションコントローラーへのポインターを格納します。|

## <a name="remarks"></a>解説

またはを呼び出すと、このイベントハンドラーが作成され、メソッドに渡され `IUIAnimationVariable::SetVariableChangeHandler` `CAnimationVariable::EnableValueChangedEvent` ます。これにより、 `CAnimationBaseObject::EnableValueChangedEvent` アニメーションオブジェクトにカプセル化されたすべてのアニメーション変数に対してこのイベントが有効になります。

## <a name="inheritance-hierarchy"></a>継承階層

`CUIAnimationCallbackBase`

`CUIAnimationVariableChangeHandlerBase`

`CAnimationVariableChangeHandler`

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationvariablechangehandleronvaluechanged"></a><a name="onvaluechanged"></a> CAnimationVariableChangeHandler:: OnValueChanged

アニメーション変数の値が変更されたときに呼び出されます。

```
IFACEMETHOD(OnValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in DOUBLE newValue,
    __in DOUBLE previousValue);
```

### <a name="parameters"></a>パラメーター

*storyboard*<br/>
変数をアニメーション化するストーリーボード。

*variable*<br/>
更新されたアニメーション変数。

*newValue*<br/>
新しい値。

*前の値*<br/>
前の値。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラーコードを返します。

## <a name="canimationvariablechangehandlersetanimationcontroller"></a><a name="setanimationcontroller"></a> CAnimationVariableChangeHandler:: Setアニメーションコントローラー

イベントをルーティングするアニメーションコントローラーへのポインターを格納します。

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>パラメーター

*pAnimationController*<br/>
イベントを受信するアニメーションコントローラーへのポインター。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
