---
description: '詳細情報: CAnimationRect クラス'
title: CAnimationRect クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 590b1382992a32e0eb3d49e0ea562d10193c1990
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207892"
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
|[CAnimationRect:: CAnimationRect](#canimationrect)|オーバーロードされます。 アニメーションの rect オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAnimationRect:: AddTransition](#addtransition)|左、上、右、および下の座標の遷移を追加します。|
|[CAnimationRect:: GetBottom](#getbottom)|下の座標を表す CAnimationVariable へのアクセスを提供します。|
|[CAnimationRect:: GetDefaultValue](#getdefaultvalue)|四角形の境界の既定値を返します。|
|[CAnimationRect:: GetLeft](#getleft)|左座標を表す CAnimationVariable へのアクセスを提供します。|
|[CAnimationRect:: GetRight](#getright)|右座標を表す CAnimationVariable へのアクセスを提供します。|
|[CAnimationRect:: GetTop](#gettop)|Top 座標を表す CAnimationVariable へのアクセスを提供します。|
|[CAnimationRect:: GetValue](#getvalue)|現在の値を返します。|
|[CAnimationRect:: SetDefaultValue](#setdefaultvalue)|既定値を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CAnimationRect:: Getアニメーション変数の一覧](#getanimationvariablelist)|カプセル化されたアニメーション変数を一覧に配置します。 ( [Canimationbaseobject:: Getmenu変数 list](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)をオーバーライドします)。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CAnimationRect:: operator RECT](#operator_rect)|CAnimationRect を RECT に変換します。|
|[CAnimationRect:: operator =](#operator_eq)|Rect を CAnimationRect に割り当てます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CAnimationRect:: m_bFixedSize](#m_bfixedsize)|四角形のサイズが固定されているかどうかを指定します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CAnimationRect:: m_bottomValue](#m_bottomvalue)|アニメーションの四角形の下端を表す、カプセル化されたアニメーション変数。|
|[CAnimationRect:: m_leftValue](#m_leftvalue)|アニメーション四角形の左境界を表す、カプセル化されたアニメーション変数。|
|[CAnimationRect:: m_rightValue](#m_rightvalue)|アニメーション四角形の右境界を表すカプセル化されたアニメーション変数。|
|[CAnimationRect:: m_szInitial](#m_szinitial)|アニメーションの四角形の初期サイズを指定します。|
|[CAnimationRect:: m_topValue](#m_topvalue)|アニメーション四角形の上部境界を表すカプセル化されたアニメーション変数。|

## <a name="remarks"></a>解説

CAnimationRect クラスは、4つの Canimationrect オブジェクトをカプセル化し、アプリケーション内で四角形を表すことができます。 このクラスをアプリケーションで使用するには、このクラスのオブジェクトをインスタンス化し、CAnimationController:: Addanimation Object を使用してアニメーションコントローラーに追加します。また、各遷移を左、右、下の座標に適用するには、AddTransition を呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationRect`

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationrectaddtransition"></a><a name="addtransition"></a> CAnimationRect:: AddTransition

左、上、右、および下の座標の遷移を追加します。

```cpp
void AddTransition(
    CBaseTransition* pLeftTransition,
    CBaseTransition* pTopTransition,
    CBaseTransition* pRightTransition,
    CBaseTransition* pBottomTransition);
```

### <a name="parameters"></a>パラメーター

*私の移行*<br/>
左側の移行を指定します。

*pTopTransition*<br/>
上側の遷移を指定します。

*pRightTransition*<br/>
右側の遷移を指定します。

*P下端への移行*<br/>
下側の移行を指定します。

### <a name="remarks"></a>解説

この関数を呼び出して、指定された遷移を各四角形の辺のアニメーション変数に適用される遷移の内部リストに追加します。 切り替え効果を追加すると、すぐには適用されず、内部リストに格納されます。 CAnimationController:: AnimateGroup を呼び出すと、遷移が適用されます (特定の値のストーリーボードに追加されます)。 四角形のいずれかの辺に切り替え効果を適用する必要がない場合は、NULL を渡すことができます。

## <a name="canimationrectcanimationrect"></a><a name="canimationrect"></a> CAnimationRect:: CAnimationRect

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

*rect*<br/>
既定の四角形を指定します。

*nGroupID*<br/>
グループ ID を指定します。

*nObjectID*<br/>
オブジェクト ID を指定します。

*dwUserData*<br/>
ユーザー定義データを指定します。

*pt*<br/>
左上隅の座標。

*sz*<br/>
四角形のサイズ。

*n 左*<br/>
左境界の座標を指定します。

*nTop*<br/>
上の境界の座標を指定します。

*nRight*<br/>
右バインドの座標を指定します。

*nBottom*<br/>
下限の座標を指定します。

### <a name="remarks"></a>解説

オブジェクトは、left、top、right、bottom、Object ID、および Group ID の既定値を使用して構築されます。この値は0に設定されます。 これらは、後で SetDefaultValue および SetID を使用して実行時に変更できます。

## <a name="canimationrectgetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationRect:: Getアニメーション変数の一覧

カプセル化されたアニメーション変数を一覧に配置します。

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>パラメーター

*.lst*<br/>
関数から制御が戻ると、四角形の座標を表す4つの CAnimationVariable オブジェクトへのポインターが含まれます。

## <a name="canimationrectgetbottom"></a><a name="getbottom"></a> CAnimationRect:: GetBottom

下の座標を表す CAnimationVariable へのアクセスを提供します。

```
CAnimationVariable& GetBottom();
```

### <a name="return-value"></a>戻り値

下の座標を表す、カプセル化された CAnimationVariable への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、下の座標を表す基になる CAnimationVariable への直接アクセスを取得できます。

## <a name="canimationrectgetdefaultvalue"></a><a name="getdefaultvalue"></a> CAnimationRect:: GetDefaultValue

四角形の境界の既定値を返します。

```
CRect GetDefaultValue();
```

### <a name="return-value"></a>戻り値

Left、right、top、および bottom の既定値を含む CRect 値。

### <a name="remarks"></a>解説

コンストラクターまたは SetDefaultValue によって以前に設定された既定値を取得するには、この関数を呼び出します。

## <a name="canimationrectgetleft"></a><a name="getleft"></a> CAnimationRect:: GetLeft

左座標を表す CAnimationVariable へのアクセスを提供します。

```
CAnimationVariable& GetLeft();
```

### <a name="return-value"></a>戻り値

左座標を表す、カプセル化された CAnimationVariable への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、左の座標を表す基になる CAnimationVariable への直接アクセスを取得できます。

## <a name="canimationrectgetright"></a><a name="getright"></a> CAnimationRect:: GetRight

右座標を表す CAnimationVariable へのアクセスを提供します。

```
CAnimationVariable& GetRight();
```

### <a name="return-value"></a>戻り値

右座標を表す、カプセル化された CAnimationVariable への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、右の座標を表す基になる CAnimationVariable への直接アクセスを取得できます。

## <a name="canimationrectgettop"></a><a name="gettop"></a> CAnimationRect:: GetTop

Top 座標を表す CAnimationVariable へのアクセスを提供します。

```
CAnimationVariable& GetTop();
```

### <a name="return-value"></a>戻り値

上の座標を表す、カプセル化された CAnimationVariable への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、最上位の座標を表す基になる CAnimationVariable への直接アクセスを取得できます。

## <a name="canimationrectgetvalue"></a><a name="getvalue"></a> CAnimationRect:: GetValue

現在の値を返します。

```
BOOL GetValue(CRect& rect);
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
出力。 このメソッドが戻るときの現在の値を格納します。

### <a name="return-value"></a>戻り値

現在の値が正常に取得された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

アニメーション四角形の現在の値を取得するには、この関数を呼び出します。 このメソッドでエラーが発生した場合、または左、上、右、下にある COM オブジェクトが初期化されていない場合、rect には、コンストラクターまたは SetDefaultValue によって以前に設定された既定値が含まれます。

## <a name="canimationrectm_bfixedsize"></a><a name="m_bfixedsize"></a> CAnimationRect:: m_bFixedSize

四角形のサイズが固定されているかどうかを指定します。

```
BOOL m_bFixedSize;
```

### <a name="remarks"></a>解説

このメンバーが true の場合、四角形のサイズは固定されており、右側と下の値は、左上隅が固定サイズに従って移動されるたびに再計算されます。 四角形を画面の周りに簡単に移動するには、この値を TRUE に設定します。 この場合、右と下の座標に適用される遷移は無視されます。 このサイズは、オブジェクトを構築するとき、または SetDefaultValue を呼び出すときに、内部的に格納されます。 既定では、このメンバーは FALSE に設定されています。

## <a name="canimationrectm_bottomvalue"></a><a name="m_bottomvalue"></a> CAnimationRect:: m_bottomValue

アニメーションの四角形の下端を表す、カプセル化されたアニメーション変数。

```
CAnimationVariable m_bottomValue;
```

## <a name="canimationrectm_leftvalue"></a><a name="m_leftvalue"></a> CAnimationRect:: m_leftValue

アニメーション四角形の左境界を表す、カプセル化されたアニメーション変数。

```
CAnimationVariable m_leftValue;
```

## <a name="canimationrectm_rightvalue"></a><a name="m_rightvalue"></a> CAnimationRect:: m_rightValue

アニメーション四角形の右境界を表すカプセル化されたアニメーション変数。

```
CAnimationVariable m_rightValue;
```

## <a name="canimationrectm_szinitial"></a><a name="m_szinitial"></a> CAnimationRect:: m_szInitial

アニメーションの四角形の初期サイズを指定します。

```
CSize m_szInitial;
```

## <a name="canimationrectm_topvalue"></a><a name="m_topvalue"></a> CAnimationRect:: m_topValue

アニメーション四角形の上部境界を表すカプセル化されたアニメーション変数。

```
CAnimationVariable m_topValue;
```

## <a name="canimationrectoperator-rect"></a><a name="operator_rect"></a> CAnimationRect:: operator RECT

CAnimationRect を RECT に変換します。

```
operator RECT();
```

### <a name="return-value"></a>戻り値

アニメーション四角形の現在の値を RECT として指定します。

### <a name="remarks"></a>解説

この関数は、内部的に GetValue を呼び出します。 なんらかの理由で GetValue が失敗した場合、返される RECT には、すべての四角形の座標の既定値が含まれます。

## <a name="canimationrectoperator"></a><a name="operator_eq"></a> CAnimationRect:: operator =

Rect を CAnimationRect に割り当てます。

```cpp
void operator=(const RECT& rect);
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
アニメーション四角形の新しい値。

### <a name="remarks"></a>解説

アニメーションを開始する前にこの操作を実行することをお勧めします。この演算子は SetDefaultValue を呼び出します。これにより、基になる COM オブジェクトが作成されている場合は、そのコンポーネントを再作成します。 このアニメーションオブジェクトをイベント (ValueChanged または IntegerValueChanged) にサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。

## <a name="canimationrectsetdefaultvalue"></a><a name="setdefaultvalue"></a> CAnimationRect:: SetDefaultValue

既定値を設定します。

```cpp
void SetDefaultValue(const CRect& rect);
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
Left、top、right、および bottom の新しい既定値を指定します。

### <a name="remarks"></a>解説

アニメーションオブジェクトに既定値を設定するには、この関数を使用します。 このメソッドは、四角形の境界に既定値を割り当てます。 また、基になる COM オブジェクトが作成されている場合は、そのオブジェクトを再作成します。 このアニメーションオブジェクトをイベント (ValueChanged または IntegerValueChanged) にサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
