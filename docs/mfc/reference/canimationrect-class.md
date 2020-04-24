---
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
ms.openlocfilehash: 273ea2b548d35722ebf937d2db2b589fef5e69fa
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755135"
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
|[Cアニメーションレック::Cアニメーションレック](#canimationrect)|オーバーロードされます。 アニメーション rect オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cアニメーションレクト::トランジションの追加](#addtransition)|左、上、右、下の座標のトランジションを追加します。|
|[Cアニメーションレック::ゲットボトム](#getbottom)|底辺の座標を表す CAnimation 変数へのアクセスを提供します。|
|[を返します。](#getdefaultvalue)|四角形の境界の既定値を返します。|
|[Cアニメーションレック::ゲットレフト](#getleft)|左座標を表す CAnimation 変数へのアクセスを提供します。|
|[Cアニメーションレック::ゲットライト](#getright)|右座標を表す CAnimation 変数へのアクセスを提供します。|
|[Cアニメーションレック::ゲットトップ](#gettop)|上座標を表す CAnimation 変数へのアクセスを提供します。|
|[Cアニメーションレック::値を取得します。](#getvalue)|現在の値を返します。|
|[を設定します。](#setdefaultvalue)|既定値を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[C アニメーションレクスト::アニメーション変数リスト](#getanimationvariablelist)|カプセル化されたアニメーション変数をリストに入れます。 (C[アニメーションベースオブジェクト](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)をオーバーライドします。.|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[コアニメーションレック::オペレーターRECT](#operator_rect)|C アニメーションのレクトを RECT に変換します。|
|[Cアニメーションレック::演算子=](#operator_eq)|Rect を CAnimationRect に割り当てます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[コアニメーションレック::m_bFixedSize](#m_bfixedsize)|四角形のサイズが固定されているかどうかを指定します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[コアニメーションレック::m_bottomValue](#m_bottomvalue)|アニメーション四角形の下端境界を表すカプセル化されたアニメーション変数。|
|[コアニメーションレック::m_leftValue](#m_leftvalue)|アニメーション四角形の左の境界を表すカプセル化されたアニメーション変数。|
|[Cアニメーションレック::m_rightValue](#m_rightvalue)|アニメーション四角形の右の境界を表すカプセル化されたアニメーション変数。|
|[Cアニメーションレック::m_szInitial](#m_szinitial)|アニメーション四角形の初期サイズを指定します。|
|[コアニメーションレック::m_topValue](#m_topvalue)|アニメーション四角形の上の境界を表すカプセル化されたアニメーション変数。|

## <a name="remarks"></a>解説

CAnimationRect クラスは、4 つの CAnimationVariable オブジェクトをカプセル化し、アプリケーションで四角形を表すことができます。 アプリケーションでこのクラスを使用するには、このクラスのオブジェクトをインスタンス化し、CAnimationController::AddAnimationObject を使用してアニメーション コントローラに追加し、左、右、下の座標に適用される各遷移の AddTransition を呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[オブジェクト](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationRect`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationrectaddtransition"></a><a name="addtransition"></a>Cアニメーションレクト::トランジションの追加

左、上、右、下の座標のトランジションを追加します。

```cpp
void AddTransition(
    CBaseTransition* pLeftTransition,
    CBaseTransition* pTopTransition,
    CBaseTransition* pRightTransition,
    CBaseTransition* pBottomTransition);
```

### <a name="parameters"></a>パラメーター

*左遷移*<br/>
左側の遷移を指定します。

*移行*<br/>
上側のトランジションを指定します。

*右トランジション*<br/>
右側の遷移を指定します。

*移行*<br/>
下側の遷移を指定します。

### <a name="remarks"></a>解説

各四角形の辺のアニメーション変数に適用される遷移の内部リストに指定された遷移を追加します。 遷移を追加しても、すぐには適用されず、内部リストに保存されます。 CAnimationController::AnimateGroup を呼び出すと、トランジションが適用されます (特定の値のストーリーボードに追加されます)。 四角形の辺のいずれかにトランジションを適用する必要がない場合は、NULL を渡すことができます。

## <a name="canimationrectcanimationrect"></a><a name="canimationrect"></a>Cアニメーションレック::Cアニメーションレック

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

*Rect*<br/>
既定の四角形を指定します。

*グループ ID*<br/>
グループ ID を指定します。

*オブジェクト ID*<br/>
オブジェクト ID を指定します。

*データ*<br/>
ユーザー定義データを指定します。

*Pt*<br/>
左上隅の座標です。

*Sz*<br/>
四角形のサイズ。

*n左*<br/>
左境界の座標を指定します。

*Ntop*<br/>
上端の境界の座標を指定します。

*n右*<br/>
右境界の座標を指定します。

*n ボトム*<br/>
底部の境界の座標を指定します。

### <a name="remarks"></a>解説

オブジェクトは、左、上、右、下、オブジェクト ID、グループ ID の既定値で構築され、0 に設定されます。 これらは、設定の既定値と SetID を使用して、実行時に後で変更できます。

## <a name="canimationrectgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>C アニメーションレクスト::アニメーション変数リスト

カプセル化されたアニメーション変数をリストに入れます。

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>パラメーター

*Lst*<br/>
関数が返されるときに、四角形の座標を表す 4 つの CAnimationVariable オブジェクトへのポインターが含まれています。

## <a name="canimationrectgetbottom"></a><a name="getbottom"></a>Cアニメーションレック::ゲットボトム

底辺の座標を表す CAnimation 変数へのアクセスを提供します。

```
CAnimationVariable& GetBottom();
```

### <a name="return-value"></a>戻り値

下の座標を表すカプセル化された CAnimation 変数への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、下側の座標を表す基になる CAnimationVariable に直接アクセスできます。

## <a name="canimationrectgetdefaultvalue"></a><a name="getdefaultvalue"></a>を返します。

四角形の境界の既定値を返します。

```
CRect GetDefaultValue();
```

### <a name="return-value"></a>戻り値

左、右、上、下の既定値を含む CRect 値。

### <a name="remarks"></a>解説

この関数を呼び出して、以前にコンストラクターまたは SetDefaultValue によって設定された既定値を取得します。

## <a name="canimationrectgetleft"></a><a name="getleft"></a>Cアニメーションレック::ゲットレフト

左座標を表す CAnimation 変数へのアクセスを提供します。

```
CAnimationVariable& GetLeft();
```

### <a name="return-value"></a>戻り値

左座標を表すカプセル化された CAnimation 変数への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、左座標を表す基になる CAnimationVariable に直接アクセスできます。

## <a name="canimationrectgetright"></a><a name="getright"></a>Cアニメーションレック::ゲットライト

右座標を表す CAnimation 変数へのアクセスを提供します。

```
CAnimationVariable& GetRight();
```

### <a name="return-value"></a>戻り値

右座標を表すカプセル化された CAnimation 変数への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、基になる CAnimationVariable に直接アクセスして、適切な座標を表すことができます。

## <a name="canimationrectgettop"></a><a name="gettop"></a>Cアニメーションレック::ゲットトップ

上座標を表す CAnimation 変数へのアクセスを提供します。

```
CAnimationVariable& GetTop();
```

### <a name="return-value"></a>戻り値

上座標を表すカプセル化された CAnimation 変数への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、上位座標を表す基になる CAnimationVariable に直接アクセスできます。

## <a name="canimationrectgetvalue"></a><a name="getvalue"></a>Cアニメーションレック::値を取得します。

現在の値を返します。

```
BOOL GetValue(CRect& rect);
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
出力。 このメソッドが返されるときに現在の値を格納します。

### <a name="return-value"></a>戻り値

現在の値が正常に取得された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

アニメーション四角形の現在の値を取得します。 このメソッドが失敗した場合、または左、上、右、下の COM オブジェクトが初期化されていない場合、rect には、以前にコンストラクターまたは SetDefaultValue で設定された既定値が含まれます。

## <a name="canimationrectm_bfixedsize"></a><a name="m_bfixedsize"></a>コアニメーションレック::m_bFixedSize

四角形のサイズが固定されているかどうかを指定します。

```
BOOL m_bFixedSize;
```

### <a name="remarks"></a>解説

このメンバーが true の場合、四角形のサイズは固定され、左上隅が固定サイズに従って移動するたびに右と下の値が再計算されます。 この値を TRUE に設定すると、画面の周囲で四角形が簡単に移動できます。 この場合、右辺と下の座標に適用される遷移は無視されます。 サイズは、オブジェクトを構築するときや SetDefaultValue を呼び出すときに内部的に格納されます。 既定では、このメンバは FALSE に設定されています。

## <a name="canimationrectm_bottomvalue"></a><a name="m_bottomvalue"></a>コアニメーションレック::m_bottomValue

アニメーション四角形の下端境界を表すカプセル化されたアニメーション変数。

```
CAnimationVariable m_bottomValue;
```

## <a name="canimationrectm_leftvalue"></a><a name="m_leftvalue"></a>コアニメーションレック::m_leftValue

アニメーション四角形の左の境界を表すカプセル化されたアニメーション変数。

```
CAnimationVariable m_leftValue;
```

## <a name="canimationrectm_rightvalue"></a><a name="m_rightvalue"></a>Cアニメーションレック::m_rightValue

アニメーション四角形の右の境界を表すカプセル化されたアニメーション変数。

```
CAnimationVariable m_rightValue;
```

## <a name="canimationrectm_szinitial"></a><a name="m_szinitial"></a>Cアニメーションレック::m_szInitial

アニメーション四角形の初期サイズを指定します。

```
CSize m_szInitial;
```

## <a name="canimationrectm_topvalue"></a><a name="m_topvalue"></a>コアニメーションレック::m_topValue

アニメーション四角形の上の境界を表すカプセル化されたアニメーション変数。

```
CAnimationVariable m_topValue;
```

## <a name="canimationrectoperator-rect"></a><a name="operator_rect"></a>コアニメーションレック::オペレーターRECT

C アニメーションのレクトを RECT に変換します。

```
operator RECT();
```

### <a name="return-value"></a>戻り値

RECT としてのアニメーション四角形の現在の値。

### <a name="remarks"></a>解説

この関数は、内部的に GetValue を呼び出します。 何らかの理由で GetValue が失敗した場合、返される RECT には、すべての四角形座標の既定値が含まれます。

## <a name="canimationrectoperator"></a><a name="operator_eq"></a>Cアニメーションレック::演算子=

Rect を CAnimationRect に割り当てます。

```cpp
void operator=(const RECT& rect);
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
アニメーション四角形の新しい値。

### <a name="remarks"></a>解説

この演算子は SetDefaultValue を呼び出し、カラー コンポーネントの基になる COM オブジェクトが作成されている場合に再作成するため、アニメーションを開始する前に行うことをお勧めします。 このアニメーション オブジェクトをイベントにサブスクライブした場合 (ValueChanged または整数値変更)、これらのイベントを再度有効にする必要があります。

## <a name="canimationrectsetdefaultvalue"></a><a name="setdefaultvalue"></a>を設定します。

既定値を設定します。

```cpp
void SetDefaultValue(const CRect& rect);
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
左、上、右、下の新しい既定値を指定します。

### <a name="remarks"></a>解説

この関数を使用して、既定値をアニメーション オブジェクトに設定します。 このメソッドは、四角形の境界に既定値を割り当てます。 基になる COM オブジェクトが作成されている場合は、そのオブジェクトも再作成されます。 このアニメーション オブジェクトをイベントにサブスクライブした場合 (ValueChanged または整数値変更)、これらのイベントを再度有効にする必要があります。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
