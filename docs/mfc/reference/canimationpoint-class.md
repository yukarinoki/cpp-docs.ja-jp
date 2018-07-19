---
title: CAnimationPoint クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetX
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetY
- AFXANIMATIONCONTROLLER/CAnimationPoint::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_xValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_yValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationPoint [MFC], CAnimationPoint
- CAnimationPoint [MFC], AddTransition
- CAnimationPoint [MFC], GetDefaultValue
- CAnimationPoint [MFC], GetValue
- CAnimationPoint [MFC], GetX
- CAnimationPoint [MFC], GetY
- CAnimationPoint [MFC], SetDefaultValue
- CAnimationPoint [MFC], GetAnimationVariableList
- CAnimationPoint [MFC], m_xValue
- CAnimationPoint [MFC], m_yValue
ms.assetid: 5dc4d46f-e695-4681-b15c-544b78b3e317
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 58c8c9aaaf212e98fdeff1e639bb09423304e643
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36957404"
---
# <a name="canimationpoint-class"></a>CAnimationPoint クラス
座標をアニメーション化できる点の機能を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CAnimationPoint : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationPoint::CAnimationPoint](#canimationpoint)|オーバーロードされます。 CAnimationPoint オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationPoint::AddTransition](#addtransition)|X の遷移の追加と Y 座標。|  
|[CAnimationPoint::GetDefaultValue](#getdefaultvalue)|X の既定値を返します座標と Y 座標。|  
|[CAnimationPoint::GetValue](#getvalue)|現在の値を返します。|  
|[CAnimationPoint::GetX](#getx)|X 座標の CAnimationVariable へのアクセスを提供します。|  
|[CAnimationPoint::GetY](#gety)|Y 座標の CAnimationVariable へのアクセスを提供します。|  
|[CAnimationPoint::SetDefaultValue](#setdefaultvalue)|既定値を設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationPoint::GetAnimationVariableList](#getanimationvariablelist)|一覧にカプセル化されたアニメーション変数を追加します。 (上書き[CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist))。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationPoint::operator CPoint](#operator_cpoint)|CPoint、CAnimationPoint に変換します。|  
|[CAnimationPoint::operator =](#operator_eq)|CAnimationPoint に ptSrc を割り当てます。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CAnimationPoint::m_xValue](#m_xvalue)|カプセル化されたアニメーション変数を表す X アニメーション ポイントの座標。|  
|[CAnimationPoint::m_yValue](#m_yvalue)|アニメーション ポイントの Y 座標を表すアニメーションをカプセル化された変数です。|  
  
## <a name="remarks"></a>Remarks  
 CAnimationPoint クラスは、2 つの CAnimationVariable オブジェクトをカプセル化して、ポイントをアプリケーションで表すことができます。 たとえば、このクラスを使用すると、(文字列、円、ポイントなど) など、画面上の任意のオブジェクトの位置をアニメーション化します。 アプリケーションでこのクラスを使用するだけこのクラスのオブジェクトをインスタンス化、CAnimationController::AddAnimationObject を使用してアニメーション コント ローラーに追加し、遷移ごとに適用される AddTransition を呼び出す X および Y 座標。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationPoint`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>  CAnimationPoint::AddTransition  
 X の遷移の追加と Y 座標。  
  
```  
void AddTransition(
    CBaseTransition* pXTransition,  
    CBaseTransition* pYTransition);
```  
  
### <a name="parameters"></a>パラメーター  
 *pXTransition*  
 X 座標の遷移へのポインター。  
  
 *pYTransition*  
 Y の遷移へのポインターを調整します。  
  
### <a name="remarks"></a>Remarks  
 変数に適用するアニメーション x への遷移の内部リストに指定された遷移を追加するには、この関数を呼び出すと Y 座標。 切り替え効果を追加すると、いないすぐに適用されるとなり、内部の一覧に格納されています。 遷移を (特定の値のストーリー ボードへの追加) に適用されます CAnimationController::AnimateGroup を呼び出すとします。 座標のいずれかに遷移を適用する必要としない場合は、NULL を渡すことができます。  
  
##  <a name="canimationpoint"></a>  CAnimationPoint::CAnimationPoint  
 CAnimationPoint オブジェクトを構築します。  
  
```  
CAnimationPoint();

 
CAnimationPoint(
    const CPoint& ptDefault,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *ptDefault*  
 ポイント座標の既定値を指定します。  
  
 *nGroupID*  
 グループ ID を指定します  
  
 *nObjectID*  
 オブジェクト ID を指定します  
  
 *dwUserData*  
 ユーザー定義データを指定します。  
  
### <a name="remarks"></a>Remarks  
 既定のプロパティを持つ CAnimationPoint オブジェクトを構築します。 ポイント座標の既定、グループの ID とオブジェクト ID が 0 に設定されます。  
  
##  <a name="getanimationvariablelist"></a>  CAnimationPoint::GetAnimationVariableList  
 一覧にカプセル化されたアニメーション変数を追加します。  
  
```  
virtual void GetAnimationVariableList(CList<CAnimationVariable*, CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>パラメーター  
 *lst*  
 関数から制御が戻るとき、X 座標と Y 座標を表す 2 つの CAnimationVariable オブジェクトへのポインターが含まれています。  
  
##  <a name="getdefaultvalue"></a>  CAnimationPoint::GetDefaultValue  
 X の既定値を返します座標と Y 座標。  
  
```  
CPoint GetDefaultValue();
```  
  
### <a name="return-value"></a>戻り値  
 既定値を含むポイント。  
  
### <a name="remarks"></a>Remarks  
 コンス トラクターまたは SetDefaultValue で以前に設定された既定値を取得するには、この関数を呼び出します。  
  
##  <a name="getvalue"></a>  CAnimationPoint::GetValue  
 現在の値を返します。  
  
```  
BOOL GetValue(CPoint& ptValue);
```  
  
### <a name="parameters"></a>パラメーター  
 *ptValue*  
 出力です。 このメソッドが戻るとき、現在の値が含まれています。  
  
### <a name="return-value"></a>戻り値  
 現在の値の取得が成功した場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>Remarks  
 アニメーション ポイントの現在の値を取得するには、この関数を呼び出します。 このメソッドは失敗または基になる COM オブジェクト X と Y 座標が初期化されていません、ptValue には、コンス トラクターまたは SetDefaultValue によって設定されている既定値が含まれています。  
  
##  <a name="getx"></a>  CAnimationPoint::GetX  
 X 座標の CAnimationVariable へのアクセスを提供します。  
  
```  
CAnimationVariable& GetX();
```  
  
### <a name="return-value"></a>戻り値  
 X を表すカプセル化された CAnimationVariable への参照を調整します。  
  
### <a name="remarks"></a>Remarks  
 X を表す、基になる CAnimationVariable に直接アクセスを取得するには、このメソッドを呼び出すことができますを調整します。  
  
##  <a name="gety"></a>  CAnimationPoint::GetY  
 Y 座標の CAnimationVariable へのアクセスを提供します。  
  
```  
CAnimationVariable& GetY();
```  
  
### <a name="return-value"></a>戻り値  
 Y 座標を表すカプセル化された CAnimationVariable への参照。  
  
### <a name="remarks"></a>Remarks  
 Y 座標を表す、基になる CAnimationVariable に直接アクセスを取得するには、このメソッドを呼び出すことができます。  
  
##  <a name="m_xvalue"></a>  CAnimationPoint::m_xValue  
 カプセル化されたアニメーション変数を表す X アニメーション ポイントの座標。  
  
```  
CAnimationVariable m_xValue;  
```  
  
##  <a name="m_yvalue"></a>  CAnimationPoint::m_yValue  
 アニメーション ポイントの Y 座標を表すアニメーションをカプセル化された変数です。  
  
```  
CAnimationVariable m_yValue;  
```  
  
##  <a name="operator_cpoint"></a>  CAnimationPoint::operator CPoint  
 CPoint、CAnimationPoint に変換します。  
  
```  
operator CPoint();
```   
  
### <a name="return-value"></a>戻り値  
 CPoint として CAnimationPoint の現在の値。  
  
### <a name="remarks"></a>Remarks  
 この関数は、GetValue を内部的に呼び出します。 GetValue 何らかの理由により失敗した場合、返されるポイントが X の既定値を格納する座標と Y 座標。  
  
##  <a name="operator_eq"></a>  CAnimationPoint::operator =  
 CAnimationPoint に ptSrc を割り当てます。  
  
```  
void operator=(const CPoint& ptSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 *ptSrc*  
 CPoint またはポイントを指します。  
  
### <a name="remarks"></a>Remarks  
 CAnimationPoint に ptSrc を割り当てます。 アニメーションの開始前にこの演算子は SetDefaultValue を呼び出すため、基になる COM を再作成するオブジェクトの X 座標と Y 座標が作成されている場合を行うことをお勧めします。 このアニメーション オブジェクト (ValueChanged または IntegerValueChanged) イベントをサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。  
  
##  <a name="setdefaultvalue"></a>  CAnimationPoint::SetDefaultValue  
 既定値を設定します。  
  
```  
void SetDefaultValue(const POINT& ptDefault);
```  
  
### <a name="parameters"></a>パラメーター  
 *ptDefault*  
 ポイントの既定値を指定します。  
  
### <a name="remarks"></a>Remarks  
 既定値をアニメーション オブジェクトに設定するのにには、この関数を使用します。 このメソッドの割り当ての既定値をアニメーション ポイントの X および Y 座標。 それが作成された場合は、基になる COM オブジェクトも再作成します。 このアニメーション オブジェクト (ValueChanged または IntegerValueChanged) イベントをサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
