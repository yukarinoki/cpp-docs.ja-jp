---
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
ms.openlocfilehash: 7f45fdad00bacf56e2ee8c30b76e99d626902534
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377094"
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
|`CAnimationVariableChangeHandler::CreateInstance`|オブジェクトのインスタンスを`CAnimationVariableChangeHandler`作成します。|
|[変更ハンドラ::オンバリュー変更](#onvaluechanged)|アニメーション変数の値が変更されたときに呼び出されます。 ( `CUIAnimationVariableChangeHandlerBase::OnValueChanged`をオーバーライドします)。|
|[を変更します。](#setanimationcontroller)|イベントをルーティングするアニメーション コントローラへのポインターを格納します。|

## <a name="remarks"></a>解説

このイベント ハンドラは、呼び`IUIAnimationVariable::SetVariableChangeHandler`出`CAnimationVariable::EnableValueChangedEvent`し時または`CAnimationBaseObject::EnableValueChangedEvent`(アニメーション オブジェクトにカプセル化されたすべてのアニメーション変数に対してこのイベントを有効にする) ときに、メソッドに渡されます。

## <a name="inheritance-hierarchy"></a>継承階層

`CUIAnimationCallbackBase`

`CUIAnimationVariableChangeHandlerBase`

`CAnimationVariableChangeHandler`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationvariablechangehandleronvaluechanged"></a><a name="onvaluechanged"></a>変更ハンドラ::オンバリュー変更

アニメーション変数の値が変更されたときに呼び出されます。

```
IFACEMETHOD(OnValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in DOUBLE newValue,
    __in DOUBLE previousValue);
```

### <a name="parameters"></a>パラメーター

*ストーリー ボード*<br/>
変数をアニメーション化しているストーリーボード。

*変数*<br/>
更新されたアニメーション変数。

*newValue*<br/>
新しい値です。

*以前の値*<br/>
前の値。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="canimationvariablechangehandlersetanimationcontroller"></a><a name="setanimationcontroller"></a>を変更します。

イベントをルーティングするアニメーション コントローラへのポインターを格納します。

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>パラメーター

*を切り取る*<br/>
イベントを受け取るアニメーション コントローラへのポインター。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
