---
description: '詳細については、次を参照してください: Canimationchange整数 Changehandler クラス'
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
ms.openlocfilehash: 53a0a1838e021294b4ccc870e6f01b873233a0c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336738"
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
|[Canimation変数整数 Changehandler:: Canimation変数整数 Changehandler](#canimationvariableintegerchangehandler)|`CAnimationVariableIntegerChangeHandler` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Canimation変数整数 Changehandler:: CreateInstance](#createinstance)|コールバックのインスタンスを作成し `CAnimationVariableIntegerChangeHandler` ます。|
|[CanimationOnIntegerValueChanged 整数 Changehandler::](#onintegervaluechanged)|アニメーション変数の値が変更されたときに呼び出されます。 ( `CUIAnimationVariableIntegerChangeHandlerBase::OnIntegerValueChanged`をオーバーライドします)。|
|[Canimation変数整数 Changehandler:: SetAnimationController](#setanimationcontroller)|イベントをルーティングするアニメーションコントローラーへのポインターを格納します。|

## <a name="remarks"></a>解説

このイベントハンドラーは、CAnimationVariable:: EnableIntegerValueChangedEvent または CAnimationBaseObject:: EnableIntegerValueChangedEvent を呼び出したときに、Iuianimation Variable:: Setvariables 整数の Changehandler メソッドに渡されます。これにより、アニメーションオブジェクトにカプセル化されているすべてのアニメーション変数に対してこのイベントが有効になります。

## <a name="inheritance-hierarchy"></a>継承階層

[MFC クラス](../../mfc/reference/mfc-classes.md)

`CUIAnimationCallbackBase`

`CUIAnimationVariableIntegerChangeHandlerBase`

`CAnimationVariableIntegerChangeHandler`

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationvariableintegerchangehandlercanimationvariableintegerchangehandler"></a><a name="canimationvariableintegerchangehandler"></a> Canimation変数整数 Changehandler:: Canimation変数整数 Changehandler

Canimationwhere-object 整数の Changehandler オブジェクトを構築します。

```
CAnimationVariableIntegerChangeHandler ();
```

## <a name="canimationvariableintegerchangehandlercreateinstance"></a><a name="createinstance"></a> Canimation変数整数 Changehandler:: CreateInstance

Canimationchange整数 Changehandler コールバックのインスタンスを作成します。

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationVariableIntegerChangeHandler** ppHandler);
```

### <a name="parameters"></a>パラメーター

*pAnimationController*<br/>
イベントを受信するアニメーションコントローラーへのポインター。

*ppHandler*

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラーコードを返します。

## <a name="canimationvariableintegerchangehandleronintegervaluechanged"></a><a name="onintegervaluechanged"></a> CanimationOnIntegerValueChanged 整数 Changehandler::

アニメーション変数の値が変更されたときに呼び出されます。

```
IFACEMETHOD(OnIntegerValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in INT32 newValue,
    __in INT32 previousValue);
```

### <a name="parameters"></a>パラメーター

*storyboard*<br/>
変数をアニメーション化するストーリーボード。

*variable*<br/>
更新されたアニメーション変数。

*newValue*<br/>
新しい丸められた値。

*前の値*<br/>
前の丸められた値。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は S_OK。それ以外の場合は E_FAIL。

## <a name="canimationvariableintegerchangehandlersetanimationcontroller"></a><a name="setanimationcontroller"></a> Canimation変数整数 Changehandler:: SetAnimationController

イベントをルーティングするアニメーションコントローラーへのポインターを格納します。

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>パラメーター

*pAnimationController*<br/>
イベントを受信するアニメーションコントローラーへのポインター。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
