---
description: '詳細情報: CAnimationSize クラス'
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
ms.openlocfilehash: 894675c485077291c3fca35acfb9bfa9a3d10286
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336775"
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
|[CAnimationSize:: CAnimationSize](#canimationsize)|オーバーロードされます。 アニメーションサイズオブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAnimationSize:: AddTransition](#addtransition)|幅と高さの切り替え効果を追加します。|
|[CAnimationSize:: GetCX](#getcx)|幅を表す CAnimationVariable へのアクセスを提供します。|
|[CAnimationSize:: GetCY](#getcy)|高さを表す CAnimationVariable へのアクセスを提供します。|
|[CAnimationSize:: GetDefaultValue](#getdefaultvalue)|幅と高さの既定値を返します。|
|[CAnimationSize:: GetValue](#getvalue)|現在の値を返します。|
|[CAnimationSize:: SetDefaultValue](#setdefaultvalue)|既定値を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CAnimationSize:: Getアニメーション変数の一覧](#getanimationvariablelist)|カプセル化されたアニメーション変数を一覧に配置します。 ( [Canimationbaseobject:: Getmenu変数 list](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)をオーバーライドします)。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CAnimationSize:: operator CSize](#operator_csize)|CAnimationSize を CSize に変換します。|
|[CAnimationSize:: operator =](#operator_eq)|SzSrc を CAnimationSize に割り当てます。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CAnimationSize:: m_cxValue](#m_cxvalue)|アニメーションサイズの幅を表すカプセル化されたアニメーション変数。|
|[CAnimationSize:: m_cyValue](#m_cyvalue)|アニメーションサイズの高さを表すカプセル化されたアニメーション変数。|

## <a name="remarks"></a>解説

CAnimationSize クラスは、2つの Canimationsize オブジェクトをカプセル化し、アプリケーションではサイズを表すことができます。 たとえば、このクラスを使用して、画面上の任意の2次元オブジェクトのサイズをアニメーション化できます (四角形、コントロールなど)。 このクラスをアプリケーションで使用するには、このクラスのオブジェクトをインスタンス化し、CAnimationController:: Addanimation Object を使用してアニメーションコントローラーに追加し、幅や高さに適用される各遷移に対して AddTransition を呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationSize`

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationsizeaddtransition"></a><a name="addtransition"></a> CAnimationSize:: AddTransition

幅と高さの切り替え効果を追加します。

```cpp
void AddTransition(
    CBaseTransition* pCXTransition,
    CBaseTransition* pCYTransition);
```

### <a name="parameters"></a>パラメーター

*pCXTransition*<br/>
幅に対して遷移するポインター。

*pCYTransition*<br/>
高さの切り替え先のポインター。

### <a name="remarks"></a>解説

この関数を呼び出して、指定された遷移を、幅と高さのアニメーション変数に適用される遷移の内部リストに追加します。 切り替え効果を追加すると、すぐには適用されず、内部リストに格納されます。 CAnimationController:: AnimateGroup を呼び出すと、遷移が適用されます (特定の値のストーリーボードに追加されます)。 遷移をいずれかのディメンションに適用する必要がない場合は、NULL を渡すことができます。

## <a name="canimationsizecanimationsize"></a><a name="canimationsize"></a> CAnimationSize:: CAnimationSize

アニメーションサイズオブジェクトを構築します。

```
CAnimationSize();

CAnimationSize(
    const CSize& szDefault,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>パラメーター

*szDefault*<br/>
既定のサイズを指定します。

*nGroupID*<br/>
グループ ID を指定します。

*nObjectID*<br/>
オブジェクト ID を指定します。

*dwUserData*<br/>
ユーザー定義データを指定します。

### <a name="remarks"></a>解説

オブジェクトは、width、height、Object ID、および Group ID の既定値を使用して構築されます。この値は0に設定されます。 これらは、後で SetDefaultValue および SetID を使用して実行時に変更できます。

## <a name="canimationsizegetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationSize:: Getアニメーション変数の一覧

カプセル化されたアニメーション変数を一覧に配置します。

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>パラメーター

*.lst*<br/>
関数から制御が戻るときに、幅と高さを表す2つの CAnimationVariable オブジェクトへのポインターが含まれています。

## <a name="canimationsizegetcx"></a><a name="getcx"></a> CAnimationSize:: GetCX

幅を表す CAnimationVariable へのアクセスを提供します。

```
CAnimationVariable& GetCX();
```

### <a name="return-value"></a>戻り値

幅を表す、カプセル化された CAnimationVariable への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、幅を表す基になる CAnimationVariable への直接アクセスを取得できます。

## <a name="canimationsizegetcy"></a><a name="getcy"></a> CAnimationSize:: GetCY

高さを表す CAnimationVariable へのアクセスを提供します。

```
CAnimationVariable& GetCY();
```

### <a name="return-value"></a>戻り値

高さを表す、カプセル化された CAnimationVariable への参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、高さを表す基になる CAnimationVariable への直接アクセスを取得できます。

## <a name="canimationsizegetdefaultvalue"></a><a name="getdefaultvalue"></a> CAnimationSize:: GetDefaultValue

幅と高さの既定値を返します。

```
CSize GetDefaultValue();
```

### <a name="return-value"></a>戻り値

既定値を格納している CSize オブジェクト。

### <a name="remarks"></a>解説

コンストラクターまたは SetDefaultValue によって以前に設定された既定値を取得するには、この関数を呼び出します。

## <a name="canimationsizegetvalue"></a><a name="getvalue"></a> CAnimationSize:: GetValue

現在の値を返します。

```
BOOL GetValue(CSize& szValue);
```

### <a name="parameters"></a>パラメーター

*szValue*<br/>
出力。 このメソッドが戻るときの現在の値を格納します。

### <a name="return-value"></a>戻り値

現在の値が正常に取得された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

アニメーションサイズの現在の値を取得するには、この関数を呼び出します。 このメソッドでエラーが発生した場合、またはその基になる COM オブジェクトの幅とサイズが初期化されていない場合、szValue には、コンストラクターまたは SetDefaultValue によって以前に設定された既定値が含まれます。

## <a name="canimationsizem_cxvalue"></a><a name="m_cxvalue"></a> CAnimationSize:: m_cxValue

アニメーションサイズの幅を表すカプセル化されたアニメーション変数。

```
CAnimationVariable m_cxValue;
```

## <a name="canimationsizem_cyvalue"></a><a name="m_cyvalue"></a> CAnimationSize:: m_cyValue

アニメーションサイズの高さを表すカプセル化されたアニメーション変数。

```
CAnimationVariable m_cyValue;
```

## <a name="canimationsizeoperator-csize"></a><a name="operator_csize"></a> CAnimationSize:: operator CSize

CAnimationSize を CSize に変換します。

```
operator CSize();
```

### <a name="return-value"></a>戻り値

アニメーションサイズの現在の値を CSize として指定します。

### <a name="remarks"></a>解説

この関数は、内部的に GetValue を呼び出します。 なんらかの理由で GetValue が失敗した場合、返されるサイズには、幅と高さの既定値が含まれます。

## <a name="canimationsizeoperator"></a><a name="operator_eq"></a> CAnimationSize:: operator =

SzSrc を CAnimationSize に割り当てます。

```cpp
void operator=(const CSize& szSrc);
```

### <a name="parameters"></a>パラメーター

*szSrc*<br/>
は、CSize またはサイズを参照します。

### <a name="remarks"></a>解説

SzSrc を CAnimationSize に割り当てます。 アニメーションを開始する前にこの操作を行うことをお勧めします。この演算子は SetDefaultValue を呼び出します。これにより、基になる COM オブジェクトが作成されている場合は、幅と高さを再作成します。 このアニメーションオブジェクトをイベント (ValueChanged または IntegerValueChanged) にサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。

## <a name="canimationsizesetdefaultvalue"></a><a name="setdefaultvalue"></a> CAnimationSize:: SetDefaultValue

既定値を設定します。

```cpp
void SetDefaultValue(const CSize& szDefault);
```

### <a name="parameters"></a>パラメーター

*szDefault*<br/>
新しい既定のサイズを指定します。

### <a name="remarks"></a>解説

アニメーションオブジェクトに既定値を設定するには、この関数を使用します。 このメソッドは、アニメーションサイズの幅と高さに既定値を割り当てます。 また、基になる COM オブジェクトが作成されている場合は、そのオブジェクトを再作成します。 このアニメーションオブジェクトをイベント (ValueChanged または IntegerValueChanged) にサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
