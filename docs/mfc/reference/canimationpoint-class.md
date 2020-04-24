---
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
ms.openlocfilehash: fcdd07efb46c97d27a9f1349c297688b5705f176
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755140"
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
|[Cアニメーションポイント::Cアニメーションポイント](#canimationpoint)|オーバーロードされます。 C アニメーション ポイント オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cアニメーションポイント::トランジションの追加](#addtransition)|X 座標と Y 座標の遷移を追加します。|
|[を取得します。](#getdefaultvalue)|X 座標と Y 座標の既定値を返します。|
|[次の値を取得します。](#getvalue)|現在の値を返します。|
|[アニメーションポイント::ゲットエクス](#getx)|X 座標の C アニメーション変数へのアクセスを提供します。|
|[Cアニメーションポイント::ゲットイ](#gety)|Y 座標の C アニメーション変数へのアクセスを提供します。|
|[を設定します。](#setdefaultvalue)|既定値を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[アニメーションポイント::アニメーション変数リスト](#getanimationvariablelist)|カプセル化されたアニメーション変数をリストに入れます。 (C[アニメーションベースオブジェクト](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)をオーバーライドします。.|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[Cアニメーションポイント::オペレーターCポイント](#operator_cpoint)|C アニメーションポイントを CPoint に変換します。|
|[Cアニメーションポイント::オペレーター=](#operator_eq)|c アニメーションポイントに ptSrc を割り当てます。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[アニメーションポイント::m_xValue](#m_xvalue)|アニメーション ポイントの X 座標を表すカプセル化されたアニメーション変数。|
|[Cアニメーションポイント::m_yValue](#m_yvalue)|アニメーション ポイントの Y 座標を表すカプセル化されたアニメーション変数。|

## <a name="remarks"></a>解説

CAnimationPoint クラスは、2 つの CAnimationVariable オブジェクトをカプセル化し、アプリケーション内でポイントを表すことができます。 たとえば、このクラスを使用して、画面上の任意のオブジェクトの位置(テキスト文字列、円、点など)をアニメーション化できます。 アプリケーションでこのクラスを使用するには、このクラスのオブジェクトをインスタンス化し、CAnimationController::AddAnimationObject を使用してアニメーション コントローラに追加し、X 座標および/または Y 座標に適用される各遷移の AddTransition を呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[オブジェクト](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationPoint`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationpointaddtransition"></a><a name="addtransition"></a>Cアニメーションポイント::トランジションの追加

X 座標と Y 座標の遷移を追加します。

```cpp
void AddTransition(
    CBaseTransition* pXTransition,
    CBaseTransition* pYTransition);
```

### <a name="parameters"></a>パラメーター

*pX トランジション*<br/>
X 座標の遷移へのポインター。

*移行*<br/>
Y 座標の遷移へのポインター。

### <a name="remarks"></a>解説

X 座標と Y 座標のアニメーション変数に適用される遷移の内部リストに、指定された遷移を追加します。 遷移を追加しても、すぐには適用されず、内部リストに保存されます。 CAnimationController::AnimateGroup を呼び出すと、トランジションが適用されます (特定の値のストーリーボードに追加されます)。 いずれかの座標にトランジションを適用する必要がない場合は、NULL を渡すことができます。

## <a name="canimationpointcanimationpoint"></a><a name="canimationpoint"></a>Cアニメーションポイント::Cアニメーションポイント

C アニメーション ポイント オブジェクトを構築します。

```
CAnimationPoint();

CAnimationPoint(
    const CPoint& ptDefault,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>パラメーター

*デフォルト*<br/>
既定のポイント座標を指定します。

*グループ ID*<br/>
グループ ID を指定します。

*オブジェクト ID*<br/>
オブジェクト ID を指定します。

*データ*<br/>
ユーザー定義データを指定します。

### <a name="remarks"></a>解説

既定のポイント座標、グループ ID、およびオブジェクト ID が 0 に設定されている既定のプロパティを持つ CAnimationPoint オブジェクトを構築します。

## <a name="canimationpointgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>アニメーションポイント::アニメーション変数リスト

カプセル化されたアニメーション変数をリストに入れます。

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*, CAnimationVariable*>& lst);
```

### <a name="parameters"></a>パラメーター

*Lst*<br/>
関数が返されるときに、X 座標と Y 座標を表す 2 つの CAnimationVariable オブジェクトへのポインターが含まれています。

## <a name="canimationpointgetdefaultvalue"></a><a name="getdefaultvalue"></a>を取得します。

X 座標と Y 座標の既定値を返します。

```
CPoint GetDefaultValue();
```

### <a name="return-value"></a>戻り値

既定値を含むポイント。

### <a name="remarks"></a>解説

この関数を呼び出して、以前にコンストラクターまたは SetDefaultValue によって設定された既定値を取得します。

## <a name="canimationpointgetvalue"></a><a name="getvalue"></a>次の値を取得します。

現在の値を返します。

```
BOOL GetValue(CPoint& ptValue);
```

### <a name="parameters"></a>パラメーター

*プタバリュー*<br/>
出力。 このメソッドが返されるときに現在の値を格納します。

### <a name="return-value"></a>戻り値

現在の値が正常に取得された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

アニメーション ポイントの現在の値を取得します。 このメソッドが失敗した場合、または X 座標と Y 座標の基になる COM オブジェクトが初期化されていない場合、ptValue には、以前にコンストラクターまたは SetDefaultValue によって設定された既定値が格納されます。

## <a name="canimationpointgetx"></a><a name="getx"></a>アニメーションポイント::ゲットエクス

X 座標の C アニメーション変数へのアクセスを提供します。

```
CAnimationVariable& GetX();
```

### <a name="return-value"></a>戻り値

X 座標を表すカプセル化された CAnimation 変数への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、基になる X 座標を表す CAnimationVariable に直接アクセスできます。

## <a name="canimationpointgety"></a><a name="gety"></a>Cアニメーションポイント::ゲットイ

Y 座標の C アニメーション変数へのアクセスを提供します。

```
CAnimationVariable& GetY();
```

### <a name="return-value"></a>戻り値

Y 座標を表すカプセル化された CAnimation 変数への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、Y 座標を表す基になる CAnimationVariable に直接アクセスできます。

## <a name="canimationpointm_xvalue"></a><a name="m_xvalue"></a>アニメーションポイント::m_xValue

アニメーション ポイントの X 座標を表すカプセル化されたアニメーション変数。

```
CAnimationVariable m_xValue;
```

## <a name="canimationpointm_yvalue"></a><a name="m_yvalue"></a>Cアニメーションポイント::m_yValue

アニメーション ポイントの Y 座標を表すカプセル化されたアニメーション変数。

```
CAnimationVariable m_yValue;
```

## <a name="canimationpointoperator-cpoint"></a><a name="operator_cpoint"></a>Cアニメーションポイント::オペレーターCポイント

C アニメーションポイントを CPoint に変換します。

```
operator CPoint();
```

### <a name="return-value"></a>戻り値

CPoint としての C アニメーションポイントの現在の値。

### <a name="remarks"></a>解説

この関数は、内部的に GetValue を呼び出します。 何らかの理由で GetValue が失敗した場合、返されるポイントには X 座標と Y 座標の既定値が含まれます。

## <a name="canimationpointoperator"></a><a name="operator_eq"></a>Cアニメーションポイント::オペレーター=

c アニメーションポイントに ptSrc を割り当てます。

```cpp
void operator=(const CPoint& ptSrc);
```

### <a name="parameters"></a>パラメーター

*ptSrc*<br/>
CPoint またはポイントを参照します。

### <a name="remarks"></a>解説

c アニメーションポイントに ptSrc を割り当てます。 アニメーションを開始する前に、この演算子は SetDefaultValue を呼び出し、基になる COM オブジェクトが作成されている場合は X 座標と Y 座標を再作成するため、アニメーションを開始する前に行うことをお勧めします。 このアニメーション オブジェクトをイベントにサブスクライブした場合 (ValueChanged または整数値変更)、これらのイベントを再度有効にする必要があります。

## <a name="canimationpointsetdefaultvalue"></a><a name="setdefaultvalue"></a>を設定します。

既定値を設定します。

```cpp
void SetDefaultValue(const POINT& ptDefault);
```

### <a name="parameters"></a>パラメーター

*デフォルト*<br/>
既定のポイント値を指定します。

### <a name="remarks"></a>解説

この関数を使用して、既定値をアニメーション オブジェクトに設定します。 このメソッドは、アニメーション ポイントの X 座標と Y 座標に既定値を割り当てます。 基になる COM オブジェクトが作成されている場合は、そのオブジェクトも再作成されます。 このアニメーション オブジェクトをイベントにサブスクライブした場合 (ValueChanged または整数値変更)、これらのイベントを再度有効にする必要があります。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
