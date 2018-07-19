---
title: CAnimationRect クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationRect::GetBottom
- AFXANIMATIONCONTROLLER/CAnimationRect::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetLeft
- AFXANIMATIONCONTROLLER/CAnimationRect::GetRight
- AFXANIMATIONCONTROLLER/CAnimationRect::GetTop
- AFXANIMATIONCONTROLLER/CAnimationRect::GetValue
- AFXANIMATIONCONTROLLER/CAnimationRect::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bFixedSize
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bottomValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_leftValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_rightValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_szInitial
- AFXANIMATIONCONTROLLER/CAnimationRect::m_topValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationRect [MFC], CAnimationRect
- CAnimationRect [MFC], AddTransition
- CAnimationRect [MFC], GetBottom
- CAnimationRect [MFC], GetDefaultValue
- CAnimationRect [MFC], GetLeft
- CAnimationRect [MFC], GetRight
- CAnimationRect [MFC], GetTop
- CAnimationRect [MFC], GetValue
- CAnimationRect [MFC], SetDefaultValue
- CAnimationRect [MFC], GetAnimationVariableList
- CAnimationRect [MFC], m_bFixedSize
- CAnimationRect [MFC], m_bottomValue
- CAnimationRect [MFC], m_leftValue
- CAnimationRect [MFC], m_rightValue
- CAnimationRect [MFC], m_szInitial
- CAnimationRect [MFC], m_topValue
ms.assetid: 0294156d-241e-4a57-92b2-31234fe557d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3959ae03d40bac93ca6453c254e894b8782f5333
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36957199"
---
# <a name="canimationrect-class"></a>CAnimationRect クラス
四角形の 4 辺をアニメーション化できる機能を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CAnimationRect : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationRect::CAnimationRect](#canimationrect)|オーバーロードされます。 アニメーション rect オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationRect::AddTransition](#addtransition)|左、上、右下隅の座標の遷移を追加します。|  
|[CAnimationRect::GetBottom](#getbottom)|下の座標を表す CAnimationVariable へのアクセスを提供します。|  
|[CAnimationRect::GetDefaultValue](#getdefaultvalue)|四角形の境界の既定値を返します。|  
|[CAnimationRect::GetLeft](#getleft)|左座標を表す CAnimationVariable へのアクセスを提供します。|  
|[CAnimationRect::GetRight](#getright)|右側の座標を表す CAnimationVariable にアクセスを提供します。|  
|[CAnimationRect::GetTop](#gettop)|上部の座標を表す CAnimationVariable にアクセスを提供します。|  
|[CAnimationRect::GetValue](#getvalue)|現在の値を返します。|  
|[CAnimationRect::SetDefaultValue](#setdefaultvalue)|既定値を設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationRect::GetAnimationVariableList](#getanimationvariablelist)|一覧にカプセル化されたアニメーション変数を追加します。 (上書き[CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist))。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationRect::operator RECT](#operator_rect)|CAnimationRect を可変噴出口に変換します。|  
|[CAnimationRect::operator =](#operator_eq)|CAnimationRect に rect を割り当てます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationRect::m_bFixedSize](#m_bfixedsize)|四角形に固定サイズがあるかどうかを指定します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CAnimationRect::m_bottomValue](#m_bottomvalue)|アニメーションの四角形の下端を表すカプセル化されたアニメーション変数をバインドします。|  
|[CAnimationRect::m_leftValue](#m_leftvalue)|アニメーションの四角形の左を表すカプセル化されたアニメーション変数をバインドします。|  
|[CAnimationRect::m_rightValue](#m_rightvalue)|アニメーションの四角形の右側を表すカプセル化されたアニメーション変数をバインドします。|  
|[CAnimationRect::m_szInitial](#m_szinitial)|アニメーションの四角形の初期サイズを指定します。|  
|[CAnimationRect::m_topValue](#m_topvalue)|アニメーションの四角形の上部を表すカプセル化されたアニメーション変数をバインドします。|  
  
## <a name="remarks"></a>Remarks  
 CAnimationRect クラスは、4 つの CAnimationVariable オブジェクトをカプセル化して、四角形のアプリケーションで表すことができます。 アプリケーションでこのクラスを使用するには、このクラスのオブジェクトをインスタンス化、CAnimationController::AddAnimationObject を使用してアニメーション コント ローラーに追加してだけ左側、右側の上部と下部の座標に適用される各移行につき AddTransition の呼び出しです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationRect`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>  CAnimationRect::AddTransition  
 左、上、右下隅の座標の遷移を追加します。  
  
```  
void AddTransition(
    CBaseTransition* pLeftTransition,  
    CBaseTransition* pTopTransition,  
    CBaseTransition* pRightTransition,  
    CBaseTransition* pBottomTransition);
```  
  
### <a name="parameters"></a>パラメーター  
 *pLeftTransition*  
 左側の遷移を指定します。  
  
 *pTopTransition*  
 上側の遷移を指定します。  
  
 *pRightTransition*  
 右側の遷移を指定します。  
  
 *pBottomTransition*  
 下の辺の遷移を指定します。  
  
### <a name="remarks"></a>Remarks  
 各四角形の辺をアニメーション変数に適用するへの遷移の内部リストに指定された遷移を追加するには、この関数を呼び出します。 切り替え効果を追加すると、いないすぐに適用されるとなり、内部の一覧に格納されています。 遷移を (特定の値のストーリー ボードへの追加) に適用されます CAnimationController::AnimateGroup を呼び出すとします。 四角形の辺のいずれかに遷移を適用を必要としない場合は、NULL を渡すことができます。  
  
##  <a name="canimationrect"></a>  CAnimationRect::CAnimationRect  
 CAnimationRect オブジェクトを構築します。  
  
```  
CAnimationRect();

 
CAnimationRect(
    const CRect& rect,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);

 
CAnimationRect(
    const CPoint& pt,  
    const CSize& sz,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);

 
CAnimationRect(
    int nLeft,  
    int nTop,  
    int nRight,  
    int nBottom,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *rect*  
 既定の四角形を指定します。  
  
 *nGroupID*  
 グループ ID を指定します  
  
 *nObjectID*  
 オブジェクト ID を指定します  
  
 *dwUserData*  
 ユーザー定義データを指定します。  
  
 *pt*  
 左上隅の座標。  
  
 *sz*  
 四角形のサイズです。  
  
 *nLeft*  
 左側のバインドの座標を指定します。  
  
 *nTop*  
 バインドされている最上位の座標を指定します。  
  
 *nRight*  
 右側のバインドの座標を指定します。  
  
 *nBottom*  
 下限の座標を指定します。  
  
### <a name="remarks"></a>Remarks  
 既定値を左、上、右および下、オブジェクト ID とグループの ID を 0 に設定されますには、オブジェクトを構築します。 これらは、SetDefaultValue および SetID を使用して実行時に後で変更することができます。  
  
##  <a name="getanimationvariablelist"></a>  CAnimationRect::GetAnimationVariableList  
 一覧にカプセル化されたアニメーション変数を追加します。  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>パラメーター  
 *lst*  
 関数から返されたときに、四角形の座標を表す 4 つの CAnimationVariable オブジェクトへのポインターを格納します。  
  
##  <a name="getbottom"></a>  CAnimationRect::GetBottom  
 下の座標を表す CAnimationVariable へのアクセスを提供します。  
  
```  
CAnimationVariable& GetBottom();
```  
  
### <a name="return-value"></a>戻り値  
 下の座標を表すカプセル化された CAnimationVariable への参照。  
  
### <a name="remarks"></a>Remarks  
 下の座標を表す、基になる CAnimationVariable に直接アクセスを取得するには、このメソッドを呼び出すことができます。  
  
##  <a name="getdefaultvalue"></a>  CAnimationRect::GetDefaultValue  
 四角形の境界の既定値を返します。  
  
```  
CRect GetDefaultValue();
```  
  
### <a name="return-value"></a>戻り値  
 左、右、上と下の既定値を含む CRect 値。  
  
### <a name="remarks"></a>Remarks  
 コンス トラクターまたは SetDefaultValue で以前に設定された既定値を取得するには、この関数を呼び出します。  
  
##  <a name="getleft"></a>  CAnimationRect::GetLeft  
 左座標を表す CAnimationVariable へのアクセスを提供します。  
  
```  
CAnimationVariable& GetLeft();
```  
  
### <a name="return-value"></a>戻り値  
 左側の座標を表すカプセル化された CAnimationVariable への参照。  
  
### <a name="remarks"></a>Remarks  
 左側の座標を表す、基になる CAnimationVariable に直接アクセスを取得するには、このメソッドを呼び出すことができます。  
  
##  <a name="getright"></a>  CAnimationRect::GetRight  
 右側の座標を表す CAnimationVariable にアクセスを提供します。  
  
```  
CAnimationVariable& GetRight();
```  
  
### <a name="return-value"></a>戻り値  
 右側の座標を表すカプセル化された CAnimationVariable への参照。  
  
### <a name="remarks"></a>Remarks  
 右側の座標を表す、基になる CAnimationVariable に直接アクセスを取得するには、このメソッドを呼び出すことができます。  
  
##  <a name="gettop"></a>  CAnimationRect::GetTop  
 上部の座標を表す CAnimationVariable にアクセスを提供します。  
  
```  
CAnimationVariable& GetTop();
```  
  
### <a name="return-value"></a>戻り値  
 上部の座標を表すカプセル化された CAnimationVariable への参照。  
  
### <a name="remarks"></a>Remarks  
 上部の座標を表す、基になる CAnimationVariable に直接アクセスを取得するには、このメソッドを呼び出すことができます。  
  
##  <a name="getvalue"></a>  CAnimationRect::GetValue  
 現在の値を返します。  
  
```  
BOOL GetValue(CRect& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 *rect*  
 出力です。 このメソッドが戻るとき、現在の値が含まれています。  
  
### <a name="return-value"></a>戻り値  
 現在の値の取得が成功した場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>Remarks  
 四角形のアニメーションの現在の値を取得するには、この関数を呼び出します。 このメソッドは失敗または基になる COM は、左のオブジェクト、上、右、下が初期化されていない、rect には SetDefaultValue、コンス トラクターで設定されている既定値が含まれています。  
  
##  <a name="m_bfixedsize"></a>  CAnimationRect::m_bFixedSize  
 四角形に固定サイズがあるかどうかを指定します。  
  
```  
BOOL m_bFixedSize;  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバーが true の場合は、右側の四角形のサイズが固定されてし、下の値が左上隅が固定サイズに応じて移動するたびに再計算します。 この値を画面の周りの四角形を簡単に移動する場合は TRUE に設定します。 ここでは右下隅の座標に適用される遷移は無視されます。 オブジェクトを構築または、SetDefaultValue を呼び出すとき、サイズが内部的に格納されます。 既定では、このメンバーは FALSE に設定します。  
  
##  <a name="m_bottomvalue"></a>  CAnimationRect::m_bottomValue  
 アニメーションの四角形の下端を表すカプセル化されたアニメーション変数をバインドします。  
  
```  
CAnimationVariable m_bottomValue;  
```  
  
##  <a name="m_leftvalue"></a>  CAnimationRect::m_leftValue  
 アニメーションの四角形の左を表すカプセル化されたアニメーション変数をバインドします。  
  
```  
CAnimationVariable m_leftValue;  
```  
  
##  <a name="m_rightvalue"></a>  CAnimationRect::m_rightValue  
 アニメーションの四角形の右側を表すカプセル化されたアニメーション変数をバインドします。  
  
```  
CAnimationVariable m_rightValue;  
```  
  
##  <a name="m_szinitial"></a>  CAnimationRect::m_szInitial  
 アニメーションの四角形の初期サイズを指定します。  
  
```  
CSize m_szInitial;  
```  
  
##  <a name="m_topvalue"></a>  CAnimationRect::m_topValue  
 アニメーションの四角形の上部を表すカプセル化されたアニメーション変数をバインドします。  
  
```  
CAnimationVariable m_topValue;  
```  
  
##  <a name="operator_rect"></a>  CAnimationRect::operator RECT  
 CAnimationRect を可変噴出口に変換します。  
  
```  
operator RECT();
```   
  
### <a name="return-value"></a>戻り値  
 可変噴出口四角形のアニメーションの現在の値  
  
### <a name="remarks"></a>Remarks  
 この関数は、GetValue を内部的に呼び出します。 GetValue 何らかの理由により失敗した場合、返された RECT すべて四角形の座標の既定値が含まれます。  
  
##  <a name="operator_eq"></a>  CAnimationRect::operator =  
 CAnimationRect に rect を割り当てます。  
  
```  
void operator=(const RECT& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 *rect*  
 アニメーションの四角形の新しい値。  
  
### <a name="remarks"></a>Remarks  
 お勧めをアニメーションの開始前に行うにはこの演算子は、それが作成された場合の色要素の基になる COM オブジェクトを作成し直さ SetDefaultValue を呼び出すためです。 このアニメーション オブジェクト (ValueChanged または IntegerValueChanged) イベントをサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。  
  
##  <a name="setdefaultvalue"></a>  CAnimationRect::SetDefaultValue  
 既定値を設定します。  
  
```  
void SetDefaultValue(const CRect& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 *rect*  
 左、上、右および下の新しい既定値を指定します。  
  
### <a name="remarks"></a>Remarks  
 既定値をアニメーション オブジェクトに設定するのにには、この関数を使用します。 このメソッドは、既定値を四角形の境界に割り当てます。 それが作成された場合は、基になる COM オブジェクトも再作成します。 このアニメーション オブジェクト (ValueChanged または IntegerValueChanged) イベントをサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
