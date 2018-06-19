---
title: CAnimationVariableChangeHandler クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::OnValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::SetAnimationController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationVariableChangeHandler [MFC], OnValueChanged
- CAnimationVariableChangeHandler [MFC], SetAnimationController
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2e35fc33b26fa6bead73458a46d7c4edee1cf136
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350993"
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
|`CAnimationVariableChangeHandler::CreateInstance`|インスタンスを作成`CAnimationVariableChangeHandler`オブジェクト。|  
|[CAnimationVariableChangeHandler::OnValueChanged](#onvaluechanged)|アニメーション変数の値が変更されたときに呼び出されます。 (`CUIAnimationVariableChangeHandlerBase::OnValueChanged` をオーバーライドします)。|  
|[CAnimationVariableChangeHandler::SetAnimationController](#setanimationcontroller)|イベントをルーティングする、アニメーション コント ローラーへのポインターを格納します。|  
  
## <a name="remarks"></a>コメント  
 このイベント ハンドラーが作成されに渡される`IUIAnimationVariable::SetVariableChangeHandler`メソッドを呼び出すときに`CAnimationVariable::EnableValueChangedEvent`または`CAnimationBaseObject::EnableValueChangedEvent`(を有効にするアニメーション オブジェクトにカプセル化されたすべてのアニメーション変数は、このイベント)。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationVariableChangeHandlerBase`  
  
 `CAnimationVariableChangeHandler`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="onvaluechanged"></a>  CAnimationVariableChangeHandler::OnValueChanged  
 アニメーション変数の値が変更されたときに呼び出されます。  
  
```  
IFACEMETHOD(OnValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in DOUBLE newValue,
    __in DOUBLE previousValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `storyboard`  
 変数がアニメーション化するストーリー ボードです。  
  
 `variable`  
 アニメーション変数が更新されたです。  
  
 `newValue`  
 新しい値。  
  
 `previousValue`  
 前の値。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="setanimationcontroller"></a>  CAnimationVariableChangeHandler::SetAnimationController  
 イベントをルーティングする、アニメーション コント ローラーへのポインターを格納します。  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>パラメーター  
 `pAnimationController`  
 イベントを受信するアニメーション コント ローラーへのポインター。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
