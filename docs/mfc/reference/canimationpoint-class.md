---
description: '詳細情報: CAnimationPoint クラス'
title: CAnimationPoint クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: ddefb93950f0ff1109478f3574413faf9f60a22a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336783"
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
|[CAnimationPoint:: CAnimationPoint](#canimationpoint)|オーバーロードされます。 CAnimationPoint オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAnimationPoint:: AddTransition](#addtransition)|X 座標と Y 座標の遷移を追加します。|
|[CAnimationPoint:: GetDefaultValue](#getdefaultvalue)|X 座標と Y 座標の既定値を返します。|
|[CAnimationPoint:: GetValue](#getvalue)|現在の値を返します。|
|[CAnimationPoint:: GetX](#getx)|X 座標の CAnimationVariable へのアクセスを提供します。|
|[CAnimationPoint:: GetY](#gety)|Y 座標の CAnimationVariable へのアクセスを提供します。|
|[CAnimationPoint:: SetDefaultValue](#setdefaultvalue)|既定値を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CAnimationPoint:: Getアニメーション変数の一覧](#getanimationvariablelist)|カプセル化されたアニメーション変数を一覧に配置します。 ( [Canimationbaseobject:: Getmenu変数 list](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)をオーバーライドします)。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CAnimationPoint:: operator CPoint](#operator_cpoint)|CAnimationPoint を CPoint に変換します。|
|[CAnimationPoint:: operator =](#operator_eq)|PtSrc を CAnimationPoint に割り当てます。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CAnimationPoint:: m_xValue](#m_xvalue)|アニメーションポイントの X 座標を表すカプセル化されたアニメーション変数。|
|[CAnimationPoint:: m_yValue](#m_yvalue)|アニメーションポイントの Y 座標を表すカプセル化されたアニメーション変数。|

## <a name="remarks"></a>解説

CAnimationPoint クラスは、2つの Canimationpoint オブジェクトをカプセル化し、アプリケーション内でポイントを表すことができます。 たとえば、このクラスを使用して、画面上の任意のオブジェクトの位置をアニメーション化することができます (テキスト文字列、円、ポイントなど)。 このクラスをアプリケーションで使用するには、このクラスのオブジェクトをインスタンス化し、CAnimationController:: Addanimation Object を使用してアニメーションコントローラーに追加します。また、各遷移を X 座標/Y 座標に適用するには、AddTransition を呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationPoint`

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationpointaddtransition"></a><a name="addtransition"></a> CAnimationPoint:: AddTransition

X 座標と Y 座標の遷移を追加します。

```cpp
void AddTransition(
    CBaseTransition* pXTransition,
    CBaseTransition* pYTransition);
```

### <a name="parameters"></a>パラメーター

*pXTransition*<br/>
X 座標の遷移を示すポインター。

*pYTransition*<br/>
Y 座標の遷移を示すポインター。

### <a name="remarks"></a>解説

この関数を呼び出して、指定された遷移を X 座標と Y 座標のアニメーション変数に適用される遷移の内部リストに追加します。 切り替え効果を追加すると、すぐには適用されず、内部リストに格納されます。 CAnimationController:: AnimateGroup を呼び出すと、遷移が適用されます (特定の値のストーリーボードに追加されます)。 いずれかの座標に遷移を適用する必要がない場合は、NULL を渡すことができます。

## <a name="canimationpointcanimationpoint"></a><a name="canimationpoint"></a> CAnimationPoint:: CAnimationPoint

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

*ptDefault*<br/>
既定のポイント座標を指定します。

*nGroupID*<br/>
グループ ID を指定します。

*nObjectID*<br/>
オブジェクト ID を指定します。

*dwUserData*<br/>
ユーザー定義データを指定します。

### <a name="remarks"></a>解説

既定のプロパティを使用して CAnimationPoint オブジェクトを構築します。既定のポイント座標、グループ ID、およびオブジェクト ID は0に設定されます。

## <a name="canimationpointgetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationPoint:: Getアニメーション変数の一覧

カプセル化されたアニメーション変数を一覧に配置します。

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*, CAnimationVariable*>& lst);
```

### <a name="parameters"></a>パラメーター

*.lst*<br/>
関数から制御が戻ると、X 座標と Y 座標を表す2つの CAnimationVariable オブジェクトへのポインターが含まれます。

## <a name="canimationpointgetdefaultvalue"></a><a name="getdefaultvalue"></a> CAnimationPoint:: GetDefaultValue

X 座標と Y 座標の既定値を返します。

```
CPoint GetDefaultValue();
```

### <a name="return-value"></a>戻り値

既定値を格納している点。

### <a name="remarks"></a>解説

コンストラクターまたは SetDefaultValue によって以前に設定された既定値を取得するには、この関数を呼び出します。

## <a name="canimationpointgetvalue"></a><a name="getvalue"></a> CAnimationPoint:: GetValue

現在の値を返します。

```
BOOL GetValue(CPoint& ptValue);
```

### <a name="parameters"></a>パラメーター

*ptValue*<br/>
出力。 このメソッドが戻るときの現在の値を格納します。

### <a name="return-value"></a>戻り値

現在の値が正常に取得された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

アニメーションポイントの現在の値を取得するには、この関数を呼び出します。 このメソッドでエラーが発生した場合、または X 座標と Y 座標の基になる COM オブジェクトが初期化されていない場合は、ptValue に既定値が含まれます。これは、コンストラクターまたは SetDefaultValue で以前に設定されています。

## <a name="canimationpointgetx"></a><a name="getx"></a> CAnimationPoint:: GetX

X 座標の CAnimationVariable へのアクセスを提供します。

```
CAnimationVariable& GetX();
```

### <a name="return-value"></a>戻り値

X 座標を表す、カプセル化された CAnimationVariable への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、X 座標を表す基になる CAnimationVariable への直接アクセスを取得できます。

## <a name="canimationpointgety"></a><a name="gety"></a> CAnimationPoint:: GetY

Y 座標の CAnimationVariable へのアクセスを提供します。

```
CAnimationVariable& GetY();
```

### <a name="return-value"></a>戻り値

Y 座標を表す、カプセル化された CAnimationVariable への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、Y 座標を表す基になる CAnimationVariable への直接アクセスを取得できます。

## <a name="canimationpointm_xvalue"></a><a name="m_xvalue"></a> CAnimationPoint:: m_xValue

アニメーションポイントの X 座標を表すカプセル化されたアニメーション変数。

```
CAnimationVariable m_xValue;
```

## <a name="canimationpointm_yvalue"></a><a name="m_yvalue"></a> CAnimationPoint:: m_yValue

アニメーションポイントの Y 座標を表すカプセル化されたアニメーション変数。

```
CAnimationVariable m_yValue;
```

## <a name="canimationpointoperator-cpoint"></a><a name="operator_cpoint"></a> CAnimationPoint:: operator CPoint

CAnimationPoint を CPoint に変換します。

```
operator CPoint();
```

### <a name="return-value"></a>戻り値

CAnimationPoint の現在の値を CPoint として指定します。

### <a name="remarks"></a>解説

この関数は、内部的に GetValue を呼び出します。 なんらかの理由で GetValue が失敗した場合、返されるポイントには X 座標と Y 座標の既定値が含まれます。

## <a name="canimationpointoperator"></a><a name="operator_eq"></a> CAnimationPoint:: operator =

PtSrc を CAnimationPoint に割り当てます。

```cpp
void operator=(const CPoint& ptSrc);
```

### <a name="parameters"></a>パラメーター

*ptSrc*<br/>
は、CPoint または POINT を参照します。

### <a name="remarks"></a>解説

PtSrc を CAnimationPoint に割り当てます。 アニメーションを開始する前にこの操作を実行することをお勧めします。この演算子は SetDefaultValue を呼び出します。これにより、基になる COM オブジェクトが作成されている場合は、X 座標と Y 座標を再作成します。 このアニメーションオブジェクトをイベント (ValueChanged または IntegerValueChanged) にサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。

## <a name="canimationpointsetdefaultvalue"></a><a name="setdefaultvalue"></a> CAnimationPoint:: SetDefaultValue

既定値を設定します。

```cpp
void SetDefaultValue(const POINT& ptDefault);
```

### <a name="parameters"></a>パラメーター

*ptDefault*<br/>
既定のポイント値を指定します。

### <a name="remarks"></a>解説

アニメーションオブジェクトに既定値を設定するには、この関数を使用します。 このメソッドは、アニメーションポイントの X 座標と Y 座標に既定値を割り当てます。 また、基になる COM オブジェクトが作成されている場合は、そのオブジェクトを再作成します。 このアニメーションオブジェクトをイベント (ValueChanged または IntegerValueChanged) にサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
