---
title: CAnimationVariable クラス
ms.date: 03/27/2019
f1_keywords:
- CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationVariable::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::Create
- AFXANIMATIONCONTROLLER/CAnimationVariable::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_dblDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_lstTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_pParentObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_variable
helpviewer_keywords:
- CAnimationVariable [MFC], CAnimationVariable
- CAnimationVariable [MFC], AddTransition
- CAnimationVariable [MFC], ApplyTransitions
- CAnimationVariable [MFC], ClearTransitions
- CAnimationVariable [MFC], Create
- CAnimationVariable [MFC], CreateTransitions
- CAnimationVariable [MFC], EnableIntegerValueChangedEvent
- CAnimationVariable [MFC], EnableValueChangedEvent
- CAnimationVariable [MFC], GetDefaultValue
- CAnimationVariable [MFC], GetParentAnimationObject
- CAnimationVariable [MFC], GetValue
- CAnimationVariable [MFC], GetVariable
- CAnimationVariable [MFC], SetDefaultValue
- CAnimationVariable [MFC], SetParentAnimationObject
- CAnimationVariable [MFC], m_bAutodestroyTransitions
- CAnimationVariable [MFC], m_dblDefaultValue
- CAnimationVariable [MFC], m_lstTransitions
- CAnimationVariable [MFC], m_pParentObject
- CAnimationVariable [MFC], m_variable
ms.assetid: 506e697e-31a8-4033-a27e-292f4d7b42d9
ms.openlocfilehash: 51cc4732ee8ad5f954e5bd758484cec74cf00fe6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377044"
---
# <a name="canimationvariable-class"></a>CAnimationVariable クラス

アニメーション変数を表します。

## <a name="syntax"></a>構文

```
class CAnimationVariable;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cアニメーション変数::Cアニメーション変数](#canimationvariable)|アニメーション変数オブジェクトを構築します。|
|[Cアニメーション変数::~Cアニメーション変数](#_dtorcanimationvariable)|デストラクターです。 オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cアニメーション変数::トランジションの追加](#addtransition)|トランジションを追加します。|
|[Cアニメーション変数::移行を適用します。](#applytransitions)|内部リストからストーリーボードに遷移を追加します。|
|[Cアニメーション変数::クリアトランジション](#cleartransitions)|トランジションをクリアします。|
|[Cアニメーション変数::作成](#create)|基になるアニメーション変数 COM オブジェクトを作成します。|
|[Cアニメーション変数::移行の作成](#createtransitions)|このアニメーション変数に適用されるすべてのトランジションを作成します。|
|[イベントを変更しました。](#enableintegervaluechangedevent)|イベントを有効または無効にします。|
|[イベントを変更しました。](#enablevaluechangedevent)|イベントを有効または無効にします。|
|[を取得します。](#getdefaultvalue)|既定値を返します。|
|[オブジェクトを取得します。](#getparentanimationobject)|親アニメーション オブジェクトを返します。|
|[Cアニメーション変数::値を取得します。](#getvalue)|オーバーロードされます。 アニメーション変数の現在の値を返します。|
|[Cアニメーション変数::変数を取得します。](#getvariable)|COM オブジェクトへのポインターを返します。|
|[を設定します。](#setdefaultvalue)|既定値を設定し、解放 IUI アニメーション変数 COM オブジェクトです。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[オブジェクトを設定します。](#setparentanimationobject)|アニメーション変数とアニメーション オブジェクトの関係を設定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[Cアニメーション変数::m_bAutodestroyTransitions](#m_bautodestroytransitions)|関連する遷移オブジェクトを削除するかどうかを指定します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[Cアニメーション変数::m_dblDefaultValue](#m_dbldefaultvalue)|既定値を指定します。|
|[Cアニメーション変数::m_lstTransitions](#m_lsttransitions)|このアニメーション変数をアニメーション化する遷移のリストが含まれています。|
|[Cアニメーション変数::m_pParentObject](#m_pparentobject)|このアニメーション変数をカプセル化するアニメーション オブジェクトへのポインター。|
|[Cアニメーション変数::m_variable](#m_variable)|COM オブジェクトへのポインターを格納します。 COM オブジェクトがまだ作成されていない場合、または作成に失敗した場合は NULL。|

## <a name="remarks"></a>解説

クラスは、COM オブジェクトをカプセル化します。 また、ストーリーボードのアニメーション変数に適用される遷移のリストも保持します。 CAnimationVariable オブジェクトはアニメーション オブジェクトに埋め込まれており、アプリケーションでアニメーション化された値、ポイント、サイズ、色、および四角形を表すことができます。

## <a name="inheritance-hierarchy"></a>継承階層

`CAnimationVariable`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationvariablecanimationvariable"></a><a name="_dtorcanimationvariable"></a>Cアニメーション変数::~Cアニメーション変数

デストラクターです。 オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CAnimationVariable();
```

## <a name="canimationvariableaddtransition"></a><a name="addtransition"></a>Cアニメーション変数::トランジションの追加

トランジションを追加します。

```
void AddTransition(CBaseTransition* pTransition);
```

### <a name="parameters"></a>パラメーター

*移行*<br/>
追加する遷移へのポインター。

### <a name="remarks"></a>解説

このメソッドは、アニメーション変数に適用される遷移の内部リストに遷移を追加するために呼び出されます。 アニメーションがスケジュールされている場合は、この一覧をクリアする必要があります。

## <a name="canimationvariableapplytransitions"></a><a name="applytransitions"></a>Cアニメーション変数::移行を適用します。

内部リストからストーリーボードに遷移を追加します。

```
void ApplyTransitions(
    CAnimationController* pController,
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>パラメーター

*コントローラ*<br/>
親アニメーション コントローラへのポインター。

*ストーリーボード*<br/>
ストーリーボードへのポインター。

*ブディペンディオンキーフレーム*<br/>
このメソッドがキーフレームに依存するトランジションを追加する必要がある場合は TRUE。

### <a name="remarks"></a>解説

このメソッドは、内部リストからストーリーボードへの遷移を追加します。 これは、キーフレームに依存しないトランジションを追加し、キーフレームに依存するトランジションを追加するために、トップレベルのコードから複数回呼び出されます。 基になるアニメーション変数 COM オブジェクトが作成されていない場合、このメソッドはこの段階で作成します。

## <a name="canimationvariablecanimationvariable"></a><a name="canimationvariable"></a>Cアニメーション変数::Cアニメーション変数

アニメーション変数オブジェクトを構築します。

```
CAnimationVariable(DOUBLE dblDefaultValue = 0.0);
```

### <a name="parameters"></a>パラメーター

*既定の値*<br/>
既定値を指定します。

### <a name="remarks"></a>解説

アニメーション変数オブジェクトを構築し、その既定値を設定します。 既定値は、変数がアニメーション化されていない場合、またはアニメーション化できない場合に使用されます。

## <a name="canimationvariablecleartransitions"></a><a name="cleartransitions"></a>Cアニメーション変数::クリアトランジション

トランジションをクリアします。

```
void ClearTransitions(BOOL bAutodestroy);
```

### <a name="parameters"></a>パラメーター

*b自動破壊*<br/>
このメソッドで遷移オブジェクトを削除するかどうかを指定します。

### <a name="remarks"></a>解説

このメソッドは、すべての遷移を内部の遷移リストから削除します。 bAutodestroy が TRUE の場合、またはm_bAutodestroyTransitionsが TRUE の場合、トランジションは削除されます。 それ以外の場合、呼び出し元は遷移オブジェクトの割り当てを解除する必要があります。

## <a name="canimationvariablecreate"></a><a name="create"></a>Cアニメーション変数::作成

基になるアニメーション変数 COM オブジェクトを作成します。

```
virtual BOOL Create(IUIAnimationManager* pManager);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
アニメーション マネージャーへのポインター。

### <a name="return-value"></a>戻り値

アニメーション変数が正常に作成された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、基になるアニメーション変数 COM オブジェクトを作成し、既定値を設定します。

## <a name="canimationvariablecreatetransitions"></a><a name="createtransitions"></a>Cアニメーション変数::移行の作成

このアニメーション変数に適用されるすべてのトランジションを作成します。

```
BOOL CreateTransitions(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>パラメーター

*pライブラリ*<br/>
標準遷移のライブラリを定義する[IUIAnimationTransitionLibrary インターフェイス](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)へのポインター。

### <a name="return-value"></a>戻り値

遷移が正常に作成された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、変数の内部遷移リストに追加された遷移を作成する必要がある場合に、フレームワークによって呼び出されます。

## <a name="canimationvariableenableintegervaluechangedevent"></a><a name="enableintegervaluechangedevent"></a>イベントを変更しました。

イベントを有効または無効にします。

```
void EnableIntegerValueChangedEvent (
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>パラメーター

*コントローラ*<br/>
親コントローラーへのポインター。

*b 有効にする*<br/>
TRUE - イベントを有効にする、FALSE - イベントを無効にします。

### <a name="remarks"></a>解説

イベントが有効になっている場合、フレームワークは仮想メソッド C アニメーション コントローラー::オンアニメーション整数値を呼び出します。 このイベントを処理するには、CAnimationController から派生したクラスでオーバーライドする必要があります。 このメソッドは、アニメーション変数の整数値が変更されるたびに呼び出されます。

## <a name="canimationvariableenablevaluechangedevent"></a><a name="enablevaluechangedevent"></a>イベントを変更しました。

イベントを有効または無効にします。

```
void EnableValueChangedEvent (
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>パラメーター

*コントローラ*<br/>
親コントローラーへのポインター。

*b 有効にする*<br/>
TRUE - イベントを有効にする、FALSE - イベントを無効にします。

### <a name="remarks"></a>解説

イベントが有効になっている場合、フレームワークは仮想メソッド C アニメーション コントローラー::OnAnimationValueChanged を呼び出します。 このイベントを処理するには、CAnimationController から派生したクラスでオーバーライドする必要があります。 このメソッドは、アニメーション変数の値が変更されるたびに呼び出されます。

## <a name="canimationvariablegetdefaultvalue"></a><a name="getdefaultvalue"></a>を取得します。

既定値を返します。

```
DOUBLE GetDefaultValue() const;
```

### <a name="return-value"></a>戻り値

既定値。

### <a name="remarks"></a>解説

この関数を使用して、アニメーション変数の既定値を取得します。 既定値は、コンストラクターまたは SetDefaultValue メソッドで設定できます。

## <a name="canimationvariablegetparentanimationobject"></a><a name="getparentanimationobject"></a>オブジェクトを取得します。

親アニメーション オブジェクトを返します。

```
CAnimationBaseObject* GetParentAnimationObject();
```

### <a name="return-value"></a>戻り値

リレーションシップが確立されている場合は、親アニメーション オブジェクトへのポインター。

### <a name="remarks"></a>解説

このメソッドを呼び出して、親アニメーション オブジェクト (コンテナー) へのポインターを取得できます。

## <a name="canimationvariablegetvalue"></a><a name="getvalue"></a>Cアニメーション変数::値を取得します。

アニメーション変数の現在の値を返します。

```
HRESULT GetValue(DOUBLE& dblValue);
HRESULT GetValue(INT32& nValue);
```

### <a name="parameters"></a>パラメーター

*値上げ*<br/>
アニメーション変数の現在の値。

*n値*<br/>
アニメーション変数の現在の値。

### <a name="return-value"></a>戻り値

値が正常に取得されたか、基になるアニメーション変数が作成されていない場合にS_OKします。 それ以外の場合は、HRESULT エラー コードです。

### <a name="remarks"></a>解説

このメソッドを呼び出して、アニメーション変数の現在の値を取得できます。 基になる COM オブジェクトが作成されていない場合、dblValue には、関数が返されるときに既定値が含まれます。

## <a name="canimationvariablegetvariable"></a><a name="getvariable"></a>Cアニメーション変数::変数を取得します。

COM オブジェクトへのポインターを返します。

```
IUIAnimationVariable* GetVariable();
```

### <a name="return-value"></a>戻り値

アニメーション変数が作成されなかった場合、または作成できない場合は NULL を返します。

### <a name="remarks"></a>解説

この関数を使用して、基になる IUIAnimationVariable COM オブジェクトにアクセスし、必要に応じてメソッドを直接呼び出します。

## <a name="canimationvariablem_bautodestroytransitions"></a><a name="m_bautodestroytransitions"></a>Cアニメーション変数::m_bAutodestroyTransitions

関連する遷移オブジェクトを削除するかどうかを指定します。

```
BOOL m_bAutodestroyTransitions;
```

### <a name="remarks"></a>解説

トランジション オブジェクトが内部遷移リストから削除されるときに、トランジション オブジェクトを強制的に削除するには、この値を TRUE に設定します。 この値が FALSE の場合、遷移はアプリケーションを呼び出すことによって削除する必要があります。 アニメーションがスケジュールされた後、遷移のリストは常にクリアされます。 既定値は FALSE です。

## <a name="canimationvariablem_dbldefaultvalue"></a><a name="m_dbldefaultvalue"></a>Cアニメーション変数::m_dblDefaultValue

既定値を指定します。

```
DOUBLE m_dblDefaultValue;
```

## <a name="canimationvariablem_lsttransitions"></a><a name="m_lsttransitions"></a>Cアニメーション変数::m_lstTransitions

このアニメーション変数をアニメーション化する遷移のリストが含まれています。

```
CObList m_lstTransitions;
```

## <a name="canimationvariablem_pparentobject"></a><a name="m_pparentobject"></a>Cアニメーション変数::m_pParentObject

このアニメーション変数をカプセル化するアニメーション オブジェクトへのポインター。

```
CAnimationBaseObject* m_pParentObject;
```

## <a name="canimationvariablem_variable"></a><a name="m_variable"></a>Cアニメーション変数::m_variable

COM オブジェクトへのポインターを格納します。 COM オブジェクトがまだ作成されていない場合、または作成に失敗した場合は NULL。

```
ATL::CComPtr<IUIAnimationVariable> m_variable;
```

## <a name="canimationvariablesetdefaultvalue"></a><a name="setdefaultvalue"></a>を設定します。

既定値を設定し、解放 IUI アニメーション変数 COM オブジェクトです。

```
void SetDefaultValue(DOUBLE dblDefaultValue);
```

### <a name="parameters"></a>パラメーター

*既定の値*<br/>
新しい既定値を指定します。

### <a name="remarks"></a>解説

このメソッドは、既定値をリセットするために使います。 このメソッドは、内部 IUIAnimationVariable COM オブジェクトを解放するため、アニメーション変数が再作成されると、基になる COM オブジェクトは新しい既定値を取得します。 アニメーション変数を表す COM オブジェクトが作成されていない場合、または変数がアニメーション化されていない場合は、既定値が GetValue によって返されます。

## <a name="canimationvariablesetparentanimationobject"></a><a name="setparentanimationobject"></a>オブジェクトを設定します。

アニメーション変数とアニメーション オブジェクトの関係を設定します。

```
void SetParentAnimationObject(CAnimationBaseObject* pParentObject);
```

### <a name="parameters"></a>パラメーター

*オブジェクト*<br/>
この変数を含むアニメーション オブジェクトへのポインター。

### <a name="remarks"></a>解説

このメソッドは、アニメーション変数と、それをカプセル化するアニメーション オブジェクトとの間に 1 対 1 の関係を確立するために内部的に呼び出されます。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
