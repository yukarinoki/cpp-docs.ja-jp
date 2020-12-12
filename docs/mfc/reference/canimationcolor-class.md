---
description: '詳細情報: CAnimationColor クラス'
title: CAnimationColor クラス
ms.date: 11/04/2016
f1_keywords:
- CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationColor::GetB
- AFXANIMATIONCONTROLLER/CAnimationColor::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetG
- AFXANIMATIONCONTROLLER/CAnimationColor::GetR
- AFXANIMATIONCONTROLLER/CAnimationColor::GetValue
- AFXANIMATIONCONTROLLER/CAnimationColor::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationColor::m_bValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_gValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_rValue
helpviewer_keywords:
- CAnimationColor [MFC], CAnimationColor
- CAnimationColor [MFC], AddTransition
- CAnimationColor [MFC], GetB
- CAnimationColor [MFC], GetDefaultValue
- CAnimationColor [MFC], GetG
- CAnimationColor [MFC], GetR
- CAnimationColor [MFC], GetValue
- CAnimationColor [MFC], SetDefaultValue
- CAnimationColor [MFC], GetAnimationVariableList
- CAnimationColor [MFC], m_bValue
- CAnimationColor [MFC], m_gValue
- CAnimationColor [MFC], m_rValue
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
ms.openlocfilehash: 430f017bc9d60eed5e2d42b71f0303546deecaca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318638"
---
# <a name="canimationcolor-class"></a>CAnimationColor クラス

赤、緑、および青の各色要素をアニメーション化できる機能を実装します。

## <a name="syntax"></a>構文

```
class CAnimationColor : public CAnimationBaseObject;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAnimationColor:: CAnimationColor](#canimationcolor)|オーバーロードされます。 アニメーションカラーオブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAnimationColor:: AddTransition](#addtransition)|赤、緑、および青のコンポーネントの切り替え効果を追加します。|
|[CAnimationColor:: GetB](#getb)|Blue コンポーネントを表す CAnimationVariable へのアクセスを提供します。|
|[CAnimationColor:: GetDefaultValue](#getdefaultvalue)|カラーコンポーネントの既定値を返します。|
|[CAnimationColor:: GetG](#getg)|緑のコンポーネントを表す CAnimationVariable へのアクセスを提供します。|
|[CAnimationColor:: GetR](#getr)|Red コンポーネントを表す CAnimationVariable へのアクセスを提供します。|
|[CAnimationColor:: GetValue](#getvalue)|現在の値を返します。|
|[CAnimationColor:: SetDefaultValue](#setdefaultvalue)|既定値を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CAnimationColor:: Getアニメーション変数の一覧](#getanimationvariablelist)|カプセル化されたアニメーション変数を一覧に配置します。 ( [Canimationbaseobject:: Getmenu変数 list](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)をオーバーライドします)。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CAnimationColor:: operator COLORREF](#operator_colorref)||
|[CAnimationColor:: operator =](#operator_eq)|色を CAnimationColor に割り当てます。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CAnimationColor:: m_bValue](#m_bvalue)|アニメーションの色の青の要素を表す、カプセル化されたアニメーション変数。|
|[CAnimationColor:: m_gValue](#m_gvalue)|アニメーションの色の緑の要素を表す、カプセル化されたアニメーション変数。|
|[CAnimationColor:: m_rValue](#m_rvalue)|アニメーションの色の赤の要素を表す、カプセル化されたアニメーション変数。|

## <a name="remarks"></a>解説

CAnimationColor クラスは、3つの Canimationcolor オブジェクトをカプセル化し、アプリケーションでは色を表すことができます。 たとえば、このクラスを使用して、画面上の任意のオブジェクトの色をアニメーション化することができます (テキストの色、背景色など)。 このクラスをアプリケーションで使用するには、このクラスのオブジェクトをインスタンス化し、CAnimationController:: Addanimation Object を使用してアニメーションコントローラーに追加し、赤、緑、および青のコンポーネントに適用される各遷移に対して、AddTransition を呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationColor`

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationcoloraddtransition"></a><a name="addtransition"></a> CAnimationColor:: AddTransition

赤、緑、および青のコンポーネントの切り替え効果を追加します。

```cpp
void AddTransition(
    CBaseTransition* pRTransition,
    CBaseTransition* pGTransition,
    CBaseTransition* pBTransition);
```

### <a name="parameters"></a>パラメーター

*pRTransition*<br/>
赤のコンポーネントの移行。

*pGTransition*<br/>
緑のコンポーネントの移行。

*pBTransition*<br/>
Blue コンポーネントの移行。

### <a name="remarks"></a>解説

カラーコンポーネントを表すアニメーション変数に適用される遷移の内部リストに、指定した遷移を追加するには、この関数を呼び出します。 切り替え効果を追加すると、すぐには適用されず、内部リストに格納されます。 CAnimationController:: AnimateGroup を呼び出すと、遷移が適用されます (特定の値のストーリーボードに追加されます)。 カラーコンポーネントのいずれかに切り替え効果を適用する必要がない場合は、NULL を渡すことができます。

## <a name="canimationcolorcanimationcolor"></a><a name="canimationcolor"></a> CAnimationColor:: CAnimationColor

CAnimationColor オブジェクトを構築します。

```
CAnimationColor();

CAnimationColor(
    COLORREF color,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>パラメーター

*color*<br/>
既定の色を指定します。

*nGroupID*<br/>
グループ ID を指定します。

*nObjectID*<br/>
オブジェクト ID を指定します。

*dwUserData*<br/>
ユーザー定義データを指定します。

### <a name="remarks"></a>解説

オブジェクトは、赤、緑、青、オブジェクト ID、およびグループ ID の既定値を使用して構築されます。これは0に設定されます。 これらは、後で SetDefaultValue および SetID を使用して実行時に変更できます。

## <a name="canimationcolorgetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationColor:: Getアニメーション変数の一覧

カプセル化されたアニメーション変数を一覧に配置します。

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```

### <a name="parameters"></a>パラメーター

*.lst*<br/>
関数から制御が戻ると、赤、緑、および青のコンポーネントを表す3つの CAnimationVariable オブジェクトへのポインターが含まれます。

## <a name="canimationcolorgetb"></a><a name="getb"></a> CAnimationColor:: GetB

Blue コンポーネントを表す CAnimationVariable へのアクセスを提供します。

```
CAnimationVariable& GetB();
```

### <a name="return-value"></a>戻り値

Blue コンポーネントを表す、カプセル化された CAnimationVariable への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、Blue コンポーネントを表す基になる CAnimationVariable への直接アクセスを取得できます。

## <a name="canimationcolorgetdefaultvalue"></a><a name="getdefaultvalue"></a> CAnimationColor:: GetDefaultValue

カラーコンポーネントの既定値を返します。

```
COLORREF GetDefaultValue();
```

### <a name="return-value"></a>戻り値

RGB コンポーネントの既定値を含む COLORREF value。

### <a name="remarks"></a>解説

コンストラクターまたは SetDefaultValue によって以前に設定された既定値を取得するには、この関数を呼び出します。

## <a name="canimationcolorgetg"></a><a name="getg"></a> CAnimationColor:: GetG

緑のコンポーネントを表す CAnimationVariable へのアクセスを提供します。

```
CAnimationVariable& GetG();
```

### <a name="return-value"></a>戻り値

緑のコンポーネントを表す、カプセル化された CAnimationVariable への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、緑のコンポーネントを表す、基になる CAnimationVariable への直接アクセスを取得できます。

## <a name="canimationcolorgetr"></a><a name="getr"></a> CAnimationColor:: GetR

Red コンポーネントを表す CAnimationVariable へのアクセスを提供します。

```
CAnimationVariable& GetR();
```

### <a name="return-value"></a>戻り値

赤のコンポーネントを表す、カプセル化された CAnimationVariable への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出すと、赤のコンポーネントを表す基になる CAnimationVariable に直接アクセスできます。

## <a name="canimationcolorgetvalue"></a><a name="getvalue"></a> CAnimationColor:: GetValue

現在の値を返します。

```
BOOL GetValue(COLORREF& color);
```

### <a name="parameters"></a>パラメーター

*color*<br/>
出力。 このメソッドが戻るときの現在の値を格納します。

### <a name="return-value"></a>戻り値

現在の値が正常に取得された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

アニメーションカラーの現在の値を取得するには、この関数を呼び出します。 このメソッドが失敗した場合、または色コンポーネントの基になる COM オブジェクトが初期化されていない場合、color には、コンストラクターまたは SetDefaultValue によって以前に設定された既定値が含まれます。

## <a name="canimationcolorm_bvalue"></a><a name="m_bvalue"></a> CAnimationColor:: m_bValue

アニメーションの色の青の要素を表す、カプセル化されたアニメーション変数。

```
CAnimationVariable m_bValue;
```

## <a name="canimationcolorm_gvalue"></a><a name="m_gvalue"></a> CAnimationColor:: m_gValue

アニメーションの色の緑の要素を表す、カプセル化されたアニメーション変数。

```
CAnimationVariable m_gValue;
```

## <a name="canimationcolorm_rvalue"></a><a name="m_rvalue"></a> CAnimationColor:: m_rValue

アニメーションの色の赤の要素を表す、カプセル化されたアニメーション変数。

```
CAnimationVariable m_rValue;
```

## <a name="canimationcoloroperator-colorref"></a><a name="operator_colorref"></a> CAnimationColor:: operator COLORREF

```
operator COLORREF();
```

### <a name="return-value"></a>戻り値

## <a name="canimationcoloroperator"></a><a name="operator_eq"></a> CAnimationColor:: operator =

色を CAnimationColor に割り当てます。

```cpp
void operator=(COLORREF color);
```

### <a name="parameters"></a>パラメーター

*color*<br/>
新しい値のアニメーションの色を指定します。

### <a name="remarks"></a>解説

アニメーションを開始する前にこの操作を実行することをお勧めします。この演算子は SetDefaultValue を呼び出します。これにより、基になる COM オブジェクトが作成されている場合は、そのコンポーネントを再作成します。 このアニメーションオブジェクトをイベント (ValueChanged または IntegerValueChanged) にサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。

## <a name="canimationcolorsetdefaultvalue"></a><a name="setdefaultvalue"></a> CAnimationColor:: SetDefaultValue

既定値を設定します。

```cpp
void SetDefaultValue(COLORREF color);
```

### <a name="parameters"></a>パラメーター

*color*<br/>
赤、緑、および青のコンポーネントの新しい既定値を指定します。

### <a name="remarks"></a>解説

アニメーションオブジェクトに既定値を設定するには、この関数を使用します。 このメソッドは、アニメーションの色のカラーコンポーネントに既定値を割り当てます。 また、基になる COM オブジェクトが作成されている場合は、そのオブジェクトを再作成します。 このアニメーションオブジェクトをイベント (ValueChanged または IntegerValueChanged) にサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
