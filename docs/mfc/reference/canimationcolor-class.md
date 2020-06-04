---
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
ms.openlocfilehash: 7c1c98d739aa1c17bb30df2d9d4ce8c41558c76d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750199"
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
|[Cアニメーションカラー::Cアニメーションカラー](#canimationcolor)|オーバーロードされます。 アニメーション カラー オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cアニメーションカラー::トランジションの追加](#addtransition)|赤、緑、青のコンポーネントのトランジションを追加します。|
|[アニメーションカラー::ゲットB](#getb)|青コンポーネントを表す CAnimation 変数へのアクセスを提供します。|
|[プロパティの値を取得します。](#getdefaultvalue)|カラーコンポーネントの既定値を返します。|
|[アニメーションカラー::ゲットグ](#getg)|緑のコンポーネントを表す CAnimation 変数へのアクセスを提供します。|
|[アニメーションカラー::ゲットラー](#getr)|赤コンポーネントを表す CAnimation 変数へのアクセスを提供します。|
|[アニメーションカラー::値を取得します。](#getvalue)|現在の値を返します。|
|[カラー::デフォルト値の設定](#setdefaultvalue)|既定値を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[アニメーションの色::アニメーション変数リスト](#getanimationvariablelist)|カプセル化されたアニメーション変数をリストに入れます。 (C[アニメーションベースオブジェクト](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)をオーバーライドします。.|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[カラー:オペレーターカラーレフ](#operator_colorref)||
|[カラー::オペレーター=](#operator_eq)|C アニメーションカラーに色を割り当てます。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[アニメーションカラー::m_bValue](#m_bvalue)|アニメーションカラーの Blue コンポーネントを表すカプセル化されたアニメーション変数。|
|[アニメーションカラー::m_gValue](#m_gvalue)|アニメーションカラーの緑コンポーネントを表すカプセル化されたアニメーション変数。|
|[アニメーションカラー::m_rValue](#m_rvalue)|アニメーションカラーの赤コンポーネントを表すカプセル化されたアニメーション変数。|

## <a name="remarks"></a>解説

CAnimationColor クラスは、3 つの CAnimationVariable オブジェクトをカプセル化し、アプリケーションで色を表すことができます。 たとえば、このクラスを使用して、画面上の任意のオブジェクトの色(テキストの色、背景色など)をアニメーション化できます。 アプリケーションでこのクラスを使用するには、このクラスのオブジェクトをインスタンス化し、CAnimationController::AddAnimationObject を使用してアニメーション コントローラに追加し、赤、緑、青の各コンポーネントに適用される各遷移の AddTransition を呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[オブジェクト](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationColor`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationcoloraddtransition"></a><a name="addtransition"></a>Cアニメーションカラー::トランジションの追加

赤、緑、青のコンポーネントのトランジションを追加します。

```cpp
void AddTransition(
    CBaseTransition* pRTransition,
    CBaseTransition* pGTransition,
    CBaseTransition* pBTransition);
```

### <a name="parameters"></a>パラメーター

*移行*<br/>
赤コンポーネントの遷移。

*移行*<br/>
緑コンポーネントの遷移。

*移行*<br/>
青コンポーネントの遷移。

### <a name="remarks"></a>解説

色コンポーネントを表すアニメーション変数に適用される遷移の内部リストに指定された遷移を追加します。 遷移を追加しても、すぐには適用されず、内部リストに保存されます。 CAnimationController::AnimateGroup を呼び出すと、トランジションが適用されます (特定の値のストーリーボードに追加されます)。 いずれかのカラーコンポーネントにトランジションを適用する必要がない場合は、NULL を渡すことができます。

## <a name="canimationcolorcanimationcolor"></a><a name="canimationcolor"></a>Cアニメーションカラー::Cアニメーションカラー

オブジェクトを構築します。

```
CAnimationColor();

CAnimationColor(
    COLORREF color,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
既定の色を指定します。

*グループ ID*<br/>
グループ ID を指定します。

*オブジェクト ID*<br/>
オブジェクト ID を指定します。

*データ*<br/>
ユーザー定義データを指定します。

### <a name="remarks"></a>解説

オブジェクトは、赤、緑、青、オブジェクト ID、グループ ID の既定値で構築され、0 に設定されます。 これらは、設定の既定値と SetID を使用して、実行時に後で変更できます。

## <a name="canimationcolorgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>アニメーションの色::アニメーション変数リスト

カプセル化されたアニメーション変数をリストに入れます。

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```

### <a name="parameters"></a>パラメーター

*Lst*<br/>
関数が返されるときに、赤、緑、青のコンポーネントを表す 3 つの CAnimationVariable オブジェクトへのポインターが含まれています。

## <a name="canimationcolorgetb"></a><a name="getb"></a>アニメーションカラー::ゲットB

青コンポーネントを表す CAnimation 変数へのアクセスを提供します。

```
CAnimationVariable& GetB();
```

### <a name="return-value"></a>戻り値

青色のコンポーネントを表すカプセル化された CAnimation 変数への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、基になる CAnimationVariable に直接アクセスして、青のコンポーネントを表すことができます。

## <a name="canimationcolorgetdefaultvalue"></a><a name="getdefaultvalue"></a>プロパティの値を取得します。

カラーコンポーネントの既定値を返します。

```
COLORREF GetDefaultValue();
```

### <a name="return-value"></a>戻り値

RGB コンポーネントの既定値を含む COLORREF 値。

### <a name="remarks"></a>解説

この関数を呼び出して、以前にコンストラクターまたは SetDefaultValue によって設定された既定値を取得します。

## <a name="canimationcolorgetg"></a><a name="getg"></a>アニメーションカラー::ゲットグ

緑のコンポーネントを表す CAnimation 変数へのアクセスを提供します。

```
CAnimationVariable& GetG();
```

### <a name="return-value"></a>戻り値

緑のコンポーネントを表すカプセル化された CAnimation 変数への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、緑のコンポーネントを表す基になる CAnimationVariable に直接アクセスできます。

## <a name="canimationcolorgetr"></a><a name="getr"></a>アニメーションカラー::ゲットラー

赤コンポーネントを表す CAnimation 変数へのアクセスを提供します。

```
CAnimationVariable& GetR();
```

### <a name="return-value"></a>戻り値

赤のコンポーネントを表すカプセル化された CAnimation 変数への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、Red コンポーネントを表す基になる CAnimationVariable に直接アクセスできます。

## <a name="canimationcolorgetvalue"></a><a name="getvalue"></a>アニメーションカラー::値を取得します。

現在の値を返します。

```
BOOL GetValue(COLORREF& color);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
出力。 このメソッドが返されるときに現在の値を格納します。

### <a name="return-value"></a>戻り値

現在の値が正常に取得された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

アニメーションの色の現在の値を取得します。 このメソッドが失敗した場合、または色コンポーネントの基になる COM オブジェクトが初期化されていない場合、色には既定値が含まれます。

## <a name="canimationcolorm_bvalue"></a><a name="m_bvalue"></a>アニメーションカラー::m_bValue

アニメーションカラーの Blue コンポーネントを表すカプセル化されたアニメーション変数。

```
CAnimationVariable m_bValue;
```

## <a name="canimationcolorm_gvalue"></a><a name="m_gvalue"></a>アニメーションカラー::m_gValue

アニメーションカラーの緑コンポーネントを表すカプセル化されたアニメーション変数。

```
CAnimationVariable m_gValue;
```

## <a name="canimationcolorm_rvalue"></a><a name="m_rvalue"></a>アニメーションカラー::m_rValue

アニメーションカラーの赤コンポーネントを表すカプセル化されたアニメーション変数。

```
CAnimationVariable m_rValue;
```

## <a name="canimationcoloroperator-colorref"></a><a name="operator_colorref"></a>カラー:オペレーターカラーレフ

```
operator COLORREF();
```

### <a name="return-value"></a>戻り値

## <a name="canimationcoloroperator"></a><a name="operator_eq"></a>カラー::オペレーター=

C アニメーションカラーに色を割り当てます。

```cpp
void operator=(COLORREF color);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
新しい値アニメーションの色を指定します。

### <a name="remarks"></a>解説

この演算子は SetDefaultValue を呼び出し、カラー コンポーネントの基になる COM オブジェクトが作成されている場合に再作成するため、アニメーションを開始する前に行うことをお勧めします。 このアニメーション オブジェクトをイベントにサブスクライブした場合 (ValueChanged または整数値変更)、これらのイベントを再度有効にする必要があります。

## <a name="canimationcolorsetdefaultvalue"></a><a name="setdefaultvalue"></a>カラー::デフォルト値の設定

既定値を設定します。

```cpp
void SetDefaultValue(COLORREF color);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
赤、緑、青のコンポーネントの新しい既定値を指定します。

### <a name="remarks"></a>解説

この関数を使用して、既定値をアニメーション オブジェクトに設定します。 このメソッドは、アニメーションカラーのカラーコンポーネントにデフォルト値を割り当てます。 基になる COM オブジェクトが作成されている場合は、そのオブジェクトも再作成されます。 このアニメーション オブジェクトをイベントにサブスクライブした場合 (ValueChanged または整数値変更)、これらのイベントを再度有効にする必要があります。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
