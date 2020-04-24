---
title: CAnimationSize クラス
ms.date: 11/04/2016
f1_keywords:
- CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCX
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCY
- AFXANIMATIONCONTROLLER/CAnimationSize::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetValue
- AFXANIMATIONCONTROLLER/CAnimationSize::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cxValue
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cyValue
helpviewer_keywords:
- CAnimationSize [MFC], CAnimationSize
- CAnimationSize [MFC], AddTransition
- CAnimationSize [MFC], GetCX
- CAnimationSize [MFC], GetCY
- CAnimationSize [MFC], GetDefaultValue
- CAnimationSize [MFC], GetValue
- CAnimationSize [MFC], SetDefaultValue
- CAnimationSize [MFC], GetAnimationVariableList
- CAnimationSize [MFC], m_cxValue
- CAnimationSize [MFC], m_cyValue
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
ms.openlocfilehash: 1f4a5b8b52d8bd37d1ed83618e7451dd85f84c32
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755121"
---
# <a name="canimationsize-class"></a>CAnimationSize クラス

サイズをアニメーション化できるサイズ オブジェクトの機能を実装します。

## <a name="syntax"></a>構文

```
class CAnimationSize : public CAnimationBaseObject;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[アニメーションサイズ::Cアニメーションサイズ](#canimationsize)|オーバーロードされます。 アニメーション サイズ オブジェクトを作成します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[アニメーションサイズ::トランジションの追加](#addtransition)|幅と高さのトランジションを追加します。|
|[アニメーションサイズ::ゲットCX](#getcx)|幅を表す CAnimation 変数へのアクセスを提供します。|
|[アニメーションサイズ::ゲットシー](#getcy)|高さを表す CAnimation 変数へのアクセスを提供します。|
|[次の値を取得します。](#getdefaultvalue)|幅と高さの既定値を返します。|
|[アニメーションサイズ::値を取得します。](#getvalue)|現在の値を返します。|
|[サイズ::デフォルト値の設定](#setdefaultvalue)|既定値を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[アニメーションサイズ::アニメーション変数リスト](#getanimationvariablelist)|カプセル化されたアニメーション変数をリストに入れます。 (C[アニメーションベースオブジェクト](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)をオーバーライドします。.|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[Cアニメーションサイズ::オペレーターCサイズ](#operator_csize)|を C サイズに変換します。|
|[アニメーションサイズ::演算子=](#operator_eq)|c アニメーションサイズに szSrc を割り当てます。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[アニメーションサイズ::m_cxValue](#m_cxvalue)|アニメーションサイズの幅を表すカプセル化されたアニメーション変数。|
|[アニメーションサイズ::m_cyValue](#m_cyvalue)|アニメーション サイズの高さを表すカプセル化されたアニメーション変数。|

## <a name="remarks"></a>解説

クラスは 2 つの CAnimationVariable オブジェクトをカプセル化し、アプリケーションでサイズを表すことができます。 たとえば、このクラスを使用して、画面上の任意の 2 次元オブジェクトのサイズ (四角形、コントロールなど) をアニメーション化できます。 アプリケーションでこのクラスを使用するには、このクラスのオブジェクトをインスタンス化し、CAnimationController::AddAnimationObject を使用してアニメーション コントローラに追加し、幅と高さ/または高さに適用される各遷移の AddTransition を呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[オブジェクト](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationSize`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationsizeaddtransition"></a><a name="addtransition"></a>アニメーションサイズ::トランジションの追加

幅と高さのトランジションを追加します。

```cpp
void AddTransition(
    CBaseTransition* pCXTransition,
    CBaseTransition* pCYTransition);
```

### <a name="parameters"></a>パラメーター

*移行*<br/>
幅の遷移へのポインター。

*移行*<br/>
高さの遷移へのポインター。

### <a name="remarks"></a>解説

幅と高さのアニメーション変数に適用される遷移の内部リストに指定された遷移を追加します。 遷移を追加しても、すぐには適用されず、内部リストに保存されます。 CAnimationController::AnimateGroup を呼び出すと、トランジションが適用されます (特定の値のストーリーボードに追加されます)。 いずれかの寸法にトランジションを適用する必要がない場合は、NULL を渡すことができます。

## <a name="canimationsizecanimationsize"></a><a name="canimationsize"></a>アニメーションサイズ::Cアニメーションサイズ

アニメーション サイズ オブジェクトを作成します。

```
CAnimationSize();

CAnimationSize(
    const CSize& szDefault,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>パラメーター

*デフォルト*<br/>
既定のサイズを指定します。

*グループ ID*<br/>
グループ ID を指定します。

*オブジェクト ID*<br/>
オブジェクト ID を指定します。

*データ*<br/>
ユーザー定義データを指定します。

### <a name="remarks"></a>解説

オブジェクトは、幅、高さ、オブジェクト ID、およびグループ ID の既定値で構築され、0 に設定されます。 これらは、設定の既定値と SetID を使用して、実行時に後で変更できます。

## <a name="canimationsizegetanimationvariablelist"></a><a name="getanimationvariablelist"></a>アニメーションサイズ::アニメーション変数リスト

カプセル化されたアニメーション変数をリストに入れます。

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>パラメーター

*Lst*<br/>
関数が返されるときに、幅と高さを表す 2 つの CAnimationVariable オブジェクトへのポインターが含まれています。

## <a name="canimationsizegetcx"></a><a name="getcx"></a>アニメーションサイズ::ゲットCX

幅を表す CAnimation 変数へのアクセスを提供します。

```
CAnimationVariable& GetCX();
```

### <a name="return-value"></a>戻り値

幅を表すカプセル化された CAnimation 変数への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、幅を表す基になる CAnimationVariable に直接アクセスできます。

## <a name="canimationsizegetcy"></a><a name="getcy"></a>アニメーションサイズ::ゲットシー

高さを表す CAnimation 変数へのアクセスを提供します。

```
CAnimationVariable& GetCY();
```

### <a name="return-value"></a>戻り値

高さを表すカプセル化された CAnimation 変数への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、高さを表す基になる CAnimationVariable に直接アクセスできます。

## <a name="canimationsizegetdefaultvalue"></a><a name="getdefaultvalue"></a>次の値を取得します。

幅と高さの既定値を返します。

```
CSize GetDefaultValue();
```

### <a name="return-value"></a>戻り値

既定値を含む CSize オブジェクト。

### <a name="remarks"></a>解説

この関数を呼び出して、以前にコンストラクターまたは SetDefaultValue によって設定された既定値を取得します。

## <a name="canimationsizegetvalue"></a><a name="getvalue"></a>アニメーションサイズ::値を取得します。

現在の値を返します。

```
BOOL GetValue(CSize& szValue);
```

### <a name="parameters"></a>パラメーター

*sz値*<br/>
出力。 このメソッドが返されるときに現在の値を格納します。

### <a name="return-value"></a>戻り値

現在の値が正常に取得された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

アニメーション サイズの現在の値を取得します。 このメソッドが失敗した場合、または Width および Size の基になる COM オブジェクトが初期化されていない場合、szValue には、以前にコンストラクターまたは SetDefaultValue によって設定された既定値が含まれます。

## <a name="canimationsizem_cxvalue"></a><a name="m_cxvalue"></a>アニメーションサイズ::m_cxValue

アニメーションサイズの幅を表すカプセル化されたアニメーション変数。

```
CAnimationVariable m_cxValue;
```

## <a name="canimationsizem_cyvalue"></a><a name="m_cyvalue"></a>アニメーションサイズ::m_cyValue

アニメーション サイズの高さを表すカプセル化されたアニメーション変数。

```
CAnimationVariable m_cyValue;
```

## <a name="canimationsizeoperator-csize"></a><a name="operator_csize"></a>Cアニメーションサイズ::オペレーターCサイズ

を C サイズに変換します。

```
operator CSize();
```

### <a name="return-value"></a>戻り値

アニメーション サイズの現在の値を CSize として指定します。

### <a name="remarks"></a>解説

この関数は、内部的に GetValue を呼び出します。 何らかの理由で GetValue が失敗した場合、返されるサイズには幅と高さの既定値が含まれます。

## <a name="canimationsizeoperator"></a><a name="operator_eq"></a>アニメーションサイズ::演算子=

c アニメーションサイズに szSrc を割り当てます。

```cpp
void operator=(const CSize& szSrc);
```

### <a name="parameters"></a>パラメーター

*szSrc*<br/>
CSize またはサイズを参照します。

### <a name="remarks"></a>解説

c アニメーションサイズに szSrc を割り当てます。 この演算子は SetDefaultValue を呼び出し、基になる COM オブジェクトが作成されている場合は Width と Height を再作成するため、アニメーションを開始する前に行うことをお勧めします。 このアニメーション オブジェクトをイベントにサブスクライブした場合 (ValueChanged または整数値変更)、これらのイベントを再度有効にする必要があります。

## <a name="canimationsizesetdefaultvalue"></a><a name="setdefaultvalue"></a>サイズ::デフォルト値の設定

既定値を設定します。

```cpp
void SetDefaultValue(const CSize& szDefault);
```

### <a name="parameters"></a>パラメーター

*デフォルト*<br/>
新しい既定のサイズを指定します。

### <a name="remarks"></a>解説

この関数を使用して、既定値をアニメーション オブジェクトに設定します。 このメソッドは、既定値をアニメーション サイズの幅と高さに割り当てます。 基になる COM オブジェクトが作成されている場合は、そのオブジェクトも再作成されます。 このアニメーション オブジェクトをイベントにサブスクライブした場合 (ValueChanged または整数値変更)、これらのイベントを再度有効にする必要があります。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
