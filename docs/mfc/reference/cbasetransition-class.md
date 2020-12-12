---
description: '詳細情報: CBaseTransition クラス'
title: CBaseTransition クラス
ms.date: 03/27/2019
f1_keywords:
- CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboardAtKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::Clear
- AFXANIMATIONCONTROLLER/CBaseTransition::Create
- AFXANIMATIONCONTROLLER/CBaseTransition::GetEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::GetStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::GetType
- AFXANIMATIONCONTROLLER/CBaseTransition::IsAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::SetKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::SetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_transition
- AFXANIMATIONCONTROLLER/CBaseTransition::m_type
helpviewer_keywords:
- CBaseTransition [MFC], CBaseTransition
- CBaseTransition [MFC], AddToStoryboard
- CBaseTransition [MFC], AddToStoryboardAtKeyframes
- CBaseTransition [MFC], Clear
- CBaseTransition [MFC], Create
- CBaseTransition [MFC], GetEndKeyframe
- CBaseTransition [MFC], GetRelatedVariable
- CBaseTransition [MFC], GetStartKeyframe
- CBaseTransition [MFC], GetTransition
- CBaseTransition [MFC], GetType
- CBaseTransition [MFC], IsAdded
- CBaseTransition [MFC], SetKeyframes
- CBaseTransition [MFC], SetRelatedVariable
- CBaseTransition [MFC], m_bAdded
- CBaseTransition [MFC], m_pEndKeyframe
- CBaseTransition [MFC], m_pRelatedVariable
- CBaseTransition [MFC], m_pStartKeyframe
- CBaseTransition [MFC], m_transition
- CBaseTransition [MFC], m_type
ms.assetid: dfe84007-bbc5-43b7-b5b8-fae9145573bf
ms.openlocfilehash: 16a7b5e7f88e292fd2b771c627f7169c70fec2c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122825"
---
# <a name="cbasetransition-class"></a>CBaseTransition クラス

基本遷移を表します。

## <a name="syntax"></a>構文

```
class CBaseTransition : public CObject;
```

## <a name="members"></a>メンバー

### <a name="public-enumerations"></a>パブリック列挙型

|名前|説明|
|----------|-----------------|
|[CBaseTransition:: TRANSITION_TYPE 列挙型](#transition_type_enumeration)|Windows アニメーション API の MFC 実装で現在サポートされている移行の種類を定義します。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CBaseTransition:: CBaseTransition](#cbasetransition)|基本遷移オブジェクトを構築します。|
|[CBaseTransition:: ~ CBaseTransition](#_dtorcbasetransition)|デストラクターです。 遷移オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CBaseTransition:: AddToStoryboard](#addtostoryboard)|ストーリーボードに切り替え効果を追加します。|
|[CBaseTransition:: AddToStoryboardAtKeyframes](#addtostoryboardatkeyframes)|ストーリーボードに切り替え効果を追加します。|
|[CBaseTransition:: Clear](#clear)|カプセル化された Iui' 遷移 COM オブジェクトを解放します。|
|[CBaseTransition:: Create](#create)|COM 遷移を作成します。|
|[CBaseTransition:: GetEndKeyframe フレーム](#getendkeyframe)|開始キーフレームを返します。|
|[CBaseTransition:: Getている変数](#getrelatedvariable)|関連する変数へのポインターを返します。|
|[CBaseTransition:: GetStartKeyframe フレーム](#getstartkeyframe)|開始キーフレームを返します。|
|[CBaseTransition:: GetTransition](#gettransition)|オーバーロードされます。 基になる COM 遷移オブジェクトへのポインターを返します。|
|[CBaseTransition:: GetType](#gettype)|遷移の種類を返します。|
|[CBaseTransition:: IsAdded](#isadded)|遷移がストーリーボードに追加されたかどうかを示します。|
|[CBaseTransition:: SetKeyframes フレーム](#setkeyframes)|遷移のキーフレームを設定します。|
|[CBaseTransition:: Set関係変数](#setrelatedvariable)|アニメーションの変数と遷移の間のリレーションシップを確立します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CBaseTransition:: m_bAdded](#m_badded)|遷移がストーリーボードに追加されているかどうかを指定します。|
|[CBaseTransition:: m_pEndKeyframe](#m_pendkeyframe)|遷移の終了を指定するキーフレームへのポインターを格納します。|
|[CBaseTransition:: m_pRelatedVariable](#m_prelatedvariable)|M_transition に格納されている遷移を使用してアニメーション化されたアニメーション変数へのポインター。|
|[CBaseTransition:: m_pStartKeyframe](#m_pstartkeyframe)|遷移の開始を指定するキーフレームへのポインターを格納します。|
|[CBaseTransition:: m_transition](#m_transition)|Iuiアニメーション遷移へのポインターを格納します。 COM 遷移オブジェクトが作成されていない場合は NULL です。|
|[CBaseTransition:: m_type](#m_type)|遷移の種類を格納します。|

## <a name="remarks"></a>解説

このクラスは、Iuiの遷移インターフェイスをカプセル化し、すべての遷移の基本クラスとして機能します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CBaseTransition`

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="cbasetransitioncbasetransition"></a><a name="_dtorcbasetransition"></a> CBaseTransition:: ~ CBaseTransition

デストラクターです。 遷移オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CBaseTransition();
```

## <a name="cbasetransitionaddtostoryboard"></a><a name="addtostoryboard"></a> CBaseTransition:: AddToStoryboard

ストーリーボードに切り替え効果を追加します。

```
BOOL AddToStoryboard(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>パラメーター

*pStoryboard*<br/>
関連する変数をアニメーション化する、ストーリーボードへのポインター。

### <a name="return-value"></a>戻り値

遷移がストーリーボードに正常に追加された場合は TRUE。

### <a name="remarks"></a>解説

ストーリーボードの関連する変数に切り替え効果を適用します。 このストーリーボードのこの変数に最初に適用された移行である場合は、ストーリーボードの開始時に遷移が開始されます。 それ以外の場合は、最後に追加された遷移が変数に追加されます。

## <a name="cbasetransitionaddtostoryboardatkeyframes"></a><a name="addtostoryboardatkeyframes"></a> CBaseTransition:: AddToStoryboardAtKeyframes

ストーリーボードに切り替え効果を追加します。

```
BOOL AddToStoryboardAtKeyframes(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>パラメーター

*pStoryboard*<br/>
関連する変数をアニメーション化する、ストーリーボードへのポインター。

### <a name="return-value"></a>戻り値

遷移がストーリーボードに正常に追加された場合は TRUE。

### <a name="remarks"></a>解説

ストーリーボードの関連する変数に切り替え効果を適用します。 開始キーフレームが指定されている場合は、そのキーフレームから遷移が開始されます。 終了キーフレームが指定されている場合、遷移は開始キーフレームから開始し、最後のキーフレームで終了します。 Duration パラメーターを指定して移行を作成した場合、その期間は開始キーフレームと終了キーフレームの間の時間で上書きされます。 キーフレームが指定されていない場合は、最後に追加された遷移が変数に追加されます。

## <a name="cbasetransitioncbasetransition"></a><a name="cbasetransition"></a> CBaseTransition:: CBaseTransition

基本遷移オブジェクトを構築します。

```
CBaseTransition();
```

## <a name="cbasetransitionclear"></a><a name="clear"></a> CBaseTransition:: Clear

カプセル化された Iui' 遷移 COM オブジェクトを解放します。

```cpp
void Clear();
```

### <a name="remarks"></a>解説

IUITransition インターフェイスのリークを防ぐために、派生クラスの Create メソッドからこのメソッドを呼び出す必要があります。

## <a name="cbasetransitioncreate"></a><a name="create"></a> CBaseTransition:: Create

COM 遷移を作成します。

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory) = 0;
```

### <a name="parameters"></a>パラメーター

*pLibrary*<br/>
遷移ライブラリへのポインター。これにより、標準遷移が作成されます。 カスタム遷移の場合は NULL にすることができます。

*pFactory*<br/>
遷移ファクトリへのポインター。これにより、カスタム遷移が作成されます。 標準遷移の場合、NULL にすることができます。

### <a name="return-value"></a>戻り値

遷移 COM オブジェクトが正常に作成された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

これは、派生クラスでオーバーライドする必要がある純粋仮想関数です。 これは、基になる COM 遷移オブジェクトをインスタンス化するためにフレームワークによって呼び出されます。

## <a name="cbasetransitiongetendkeyframe"></a><a name="getendkeyframe"></a> CBaseTransition:: GetEndKeyframe フレーム

開始キーフレームを返します。

```
CBaseKeyFrame* GetEndKeyframe();
```

### <a name="return-value"></a>戻り値

キーフレームへの有効なポインター。キーフレーム間に遷移が挿入されない場合は NULL。

### <a name="remarks"></a>解説

このメソッドは、以前に SetKeyframes フレームによって設定されたキーフレームオブジェクトにアクセスするために使用できます。 これは、遷移がストーリーボードに追加されるときにトップレベルコードによって呼び出されます。

## <a name="cbasetransitiongetrelatedvariable"></a><a name="getrelatedvariable"></a> CBaseTransition:: Getている変数

関連する変数へのポインターを返します。

```
CAnimationVariable* GetRelatedVariable();
```

### <a name="return-value"></a>戻り値

アニメーション変数への有効なポインター。アニメーション変数が Setの変数によって設定されていない場合は NULL。

### <a name="remarks"></a>解説

これは、関連するアニメーション変数へのアクセサーです。

## <a name="cbasetransitiongetstartkeyframe"></a><a name="getstartkeyframe"></a> CBaseTransition:: GetStartKeyframe フレーム

開始キーフレームを返します。

```
CBaseKeyFrame* GetStartKeyframe();
```

### <a name="return-value"></a>戻り値

キーフレームへの有効なポインター。キーフレームの後に遷移を開始しない場合は NULL。

### <a name="remarks"></a>解説

このメソッドは、以前に SetKeyframes フレームによって設定されたキーフレームオブジェクトにアクセスするために使用できます。 これは、遷移がストーリーボードに追加されるときにトップレベルコードによって呼び出されます。

## <a name="cbasetransitiongettransition"></a><a name="gettransition"></a> CBaseTransition:: GetTransition

基になる COM 遷移オブジェクトへのポインターを返します。

```
IUIAnimationTransition* GetTransition(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory);

IUIAnimationTransition* GetTransition();
```

### <a name="parameters"></a>パラメーター

*pLibrary*<br/>
遷移ライブラリへのポインター。これにより、標準遷移が作成されます。 カスタム遷移の場合は NULL にすることができます。

*pFactory*<br/>
遷移ファクトリへのポインター。これにより、カスタム遷移が作成されます。 標準遷移の場合、NULL にすることができます。

### <a name="return-value"></a>戻り値

Iuiの Transition への有効なポインター、または基になる遷移を作成できない場合は NULL。

### <a name="remarks"></a>解説

このメソッドは、基になる COM 遷移オブジェクトへのポインターを返し、必要に応じて作成します。

## <a name="cbasetransitiongettype"></a><a name="gettype"></a> CBaseTransition:: GetType

遷移の種類を返します。

```
TRANSITION_TYPE GetType() const;
```

### <a name="return-value"></a>戻り値

TRANSITION_TYPE 列挙値の1つ。

### <a name="remarks"></a>解説

このメソッドを使用すると、遷移オブジェクトをその型で識別できます。 この型は、派生クラスのコンストラクターで設定されます。

## <a name="cbasetransitionisadded"></a><a name="isadded"></a> CBaseTransition:: IsAdded

遷移がストーリーボードに追加されたかどうかを示します。

```
BOOL IsAdded();
```

### <a name="return-value"></a>戻り値

遷移がストーリーボードに追加されている場合は TRUE、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

このフラグは、トップレベルのコードがストーリーボードに切り替え効果を追加するときに、内部的に設定されます。

## <a name="cbasetransitionm_badded"></a><a name="m_badded"></a> CBaseTransition:: m_bAdded

遷移がストーリーボードに追加されているかどうかを指定します。

```
BOOL m_bAdded;
```

## <a name="cbasetransitionm_pendkeyframe"></a><a name="m_pendkeyframe"></a> CBaseTransition:: m_pEndKeyframe

遷移の終了を指定するキーフレームへのポインターを格納します。

```
CBaseKeyFrame* m_pEndKeyframe;
```

## <a name="cbasetransitionm_prelatedvariable"></a><a name="m_prelatedvariable"></a> CBaseTransition:: m_pRelatedVariable

M_transition に格納されている遷移を使用してアニメーション化されたアニメーション変数へのポインター。

```
CAnimationVariable* m_pRelatedVariable;
```

## <a name="cbasetransitionm_pstartkeyframe"></a><a name="m_pstartkeyframe"></a> CBaseTransition:: m_pStartKeyframe

遷移の開始を指定するキーフレームへのポインターを格納します。

```
CBaseKeyFrame* m_pStartKeyframe;
```

## <a name="cbasetransitionm_transition"></a><a name="m_transition"></a> CBaseTransition:: m_transition

Iuiアニメーション遷移へのポインターを格納します。 COM 遷移オブジェクトが作成されていない場合は NULL です。

```
ATL::CComPtr<IUIAnimationTransition> m_transition;
```

## <a name="cbasetransitionm_type"></a><a name="m_type"></a> CBaseTransition:: m_type

遷移の種類を格納します。

```
TRANSITION_TYPE m_type;
```

## <a name="cbasetransitionsetkeyframes"></a><a name="setkeyframes"></a> CBaseTransition:: SetKeyframes フレーム

遷移のキーフレームを設定します。

```cpp
void SetKeyframes(
    CBaseKeyFrame* pStart = NULL,
    CBaseKeyFrame* pEnd = NULL);
```

### <a name="parameters"></a>パラメーター

*pStart*<br/>
遷移の開始を指定するキーフレーム。

*ペン*<br/>
遷移の終了を指定するキーフレーム。

### <a name="remarks"></a>解説

このメソッドは、指定されたキーフレームの後に開始するように遷移に指示します。また、必要に応じて、指定したキーフレームの前に終了します。 Duration パラメーターを指定して移行を作成した場合、その期間は開始キーフレームと終了キーフレームの間の時間で上書きされます。

## <a name="cbasetransitionsetrelatedvariable"></a><a name="setrelatedvariable"></a> CBaseTransition:: Set関係変数

アニメーションの変数と遷移の間のリレーションシップを確立します。

```cpp
void SetRelatedVariable(CAnimationVariable* pVariable);
```

### <a name="parameters"></a>パラメーター

*pVariable*<br/>
関連するアニメーション変数へのポインター。

### <a name="remarks"></a>解説

アニメーションの変数と遷移の間のリレーションシップを確立します。 遷移は、1つの変数にのみ適用できます。

## <a name="cbasetransitiontransition_type-enumeration"></a><a name="transition_type_enumeration"></a> CBaseTransition:: TRANSITION_TYPE 列挙型

Windows アニメーション API の MFC 実装で現在サポートされている移行の種類を定義します。

```
enum TRANSITION_TYPE;
```

### <a name="remarks"></a>解説

遷移の種類は、特定の遷移のコンストラクターで設定されます。 たとえば、CSinusoidalTransitionFromRange は、その型を SINUSOIDAL_FROM_RANGE に設定します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
