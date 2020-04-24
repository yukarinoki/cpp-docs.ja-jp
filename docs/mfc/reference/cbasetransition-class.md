---
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
ms.openlocfilehash: 9abe4ae55d9d84ea435cd5d82925ff8b8a544480
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752965"
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
|[列挙体をTRANSITION_TYPE](#transition_type_enumeration)|Windows アニメーション API の MFC 実装で現在サポートされている遷移の種類を定義します。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cベーストランジション::Cベーストランジション](#cbasetransition)|基本遷移オブジェクトを構築します。|
|[Cベーストランジション:~Cベーストランジション](#_dtorcbasetransition)|デストラクターです。 遷移オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ソーストランジション::ストーリーボードに追加](#addtostoryboard)|ストーリーボードにトランジションを追加します。|
|[コベーストランジション::キーフレーム](#addtostoryboardatkeyframes)|ストーリーボードにトランジションを追加します。|
|[Cベーストランジション::クリア](#clear)|カプセル化された IUI アニメーショントランジション COM オブジェクトを解放します。|
|[CBaseトランジション::作成](#create)|COM 遷移を作成します。|
|[ソーストランジション::ゲットエンドキーフレーム](#getendkeyframe)|開始キーフレームを返します。|
|[ソーストランジション::関連する変数を取得します。](#getrelatedvariable)|関連する変数へのポインターを返します。|
|[ソーストランジション::スタートキーフレーム](#getstartkeyframe)|開始キーフレームを返します。|
|[移行を行う](#gettransition)|オーバーロードされます。 基になる COM 遷移オブジェクトへのポインターを返します。|
|[ソーストランジション::取得タイプ](#gettype)|遷移の種類を返します。|
|[Cベーストランジション::IsAdded](#isadded)|トランジションがストーリーボードに追加されたかどうかを示します。|
|[Cベーストランジション::キーフレームを設定します。](#setkeyframes)|トランジションのキーフレームを設定します。|
|[Cベーストランジション::セット関連変数](#setrelatedvariable)|アニメーション変数と遷移の関係を確立します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[Cベーストランジション::m_bAdded](#m_badded)|ストーリーボードにトランジションが追加されているかどうかを指定します。|
|[Cベーストランジション::m_pEndKeyframe](#m_pendkeyframe)|トランジションの終了を指定するキーフレームへのポインターを格納します。|
|[Cベーストランジション::m_pRelatedVariable](#m_prelatedvariable)|m_transitionに格納されている遷移でアニメーション化されるアニメーション変数へのポインター。|
|[コベーストランジション::m_pStartKeyframe](#m_pstartkeyframe)|トランジションの開始位置を指定するキーフレームへのポインターを格納します。|
|[コベーストランジション::m_transition](#m_transition)|へのポインターを格納します。 COM 遷移オブジェクトが作成されていない場合は NULL。|
|[Cベーストランジション::m_type](#m_type)|遷移の種類を格納します。|

## <a name="remarks"></a>解説

このクラスは、インターフェイスをカプセル化し、すべての遷移の基本クラスとして機能します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CBaseTransition`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="cbasetransitioncbasetransition"></a><a name="_dtorcbasetransition"></a>Cベーストランジション:~Cベーストランジション

デストラクターです。 遷移オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CBaseTransition();
```

## <a name="cbasetransitionaddtostoryboard"></a><a name="addtostoryboard"></a>ソーストランジション::ストーリーボードに追加

ストーリーボードにトランジションを追加します。

```
BOOL AddToStoryboard(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>パラメーター

*ストーリーボード*<br/>
関連する変数をアニメーション化するストーリーボードへのポインター。

### <a name="return-value"></a>戻り値

True (遷移がストーリーボードに正常に追加された場合)

### <a name="remarks"></a>解説

ストーリーボードの関連する変数に遷移を適用します。 これがこのストーリーボード内でこの変数に適用される最初の遷移である場合、遷移はストーリーボードの先頭から開始されます。 それ以外の場合、遷移は、変数に最後に追加された遷移に追加されます。

## <a name="cbasetransitionaddtostoryboardatkeyframes"></a><a name="addtostoryboardatkeyframes"></a>コベーストランジション::キーフレーム

ストーリーボードにトランジションを追加します。

```
BOOL AddToStoryboardAtKeyframes(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>パラメーター

*ストーリーボード*<br/>
関連する変数をアニメーション化するストーリーボードへのポインター。

### <a name="return-value"></a>戻り値

True (遷移がストーリーボードに正常に追加された場合)

### <a name="remarks"></a>解説

ストーリーボードの関連する変数に遷移を適用します。 開始キーフレームが指定されている場合、トランジションはそのキーフレームから開始されます。 終了キーフレームを指定した場合、トランジションは開始キーフレームから開始し、終了キーフレームで停止します。 トランジションが duration パラメータを指定して作成された場合、そのデュレーションは開始キーフレームと終了キーフレーム間の期間で上書きされます。 キーフレームが指定されていない場合、変数に最後に追加されたトランジションにトランジションが追加されます。

## <a name="cbasetransitioncbasetransition"></a><a name="cbasetransition"></a>Cベーストランジション::Cベーストランジション

基本遷移オブジェクトを構築します。

```
CBaseTransition();
```

## <a name="cbasetransitionclear"></a><a name="clear"></a>Cベーストランジション::クリア

カプセル化された IUI アニメーショントランジション COM オブジェクトを解放します。

```cpp
void Clear();
```

### <a name="remarks"></a>解説

このメソッドは、IUITransition インターフェイス リークを防ぐために、派生クラスの Create メソッドから呼び出す必要があります。

## <a name="cbasetransitioncreate"></a><a name="create"></a>CBaseトランジション::作成

COM 遷移を作成します。

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory) = 0;
```

### <a name="parameters"></a>パラメーター

*pライブラリ*<br/>
標準遷移を作成する遷移ライブラリへのポインター。 カスタムトランジションの場合は NULL を指定できます。

*pFactory*<br/>
カスタム遷移を作成する遷移ファクトリへのポインター。 標準遷移の場合は NULL を指定できます。

### <a name="return-value"></a>戻り値

遷移 COM オブジェクトが正常に作成された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

これは純粋仮想関数で、派生クラスでオーバーライドする必要があります。 基になる COM 遷移オブジェクトをインスタンス化するために、フレームワークによって呼び出されます。

## <a name="cbasetransitiongetendkeyframe"></a><a name="getendkeyframe"></a>ソーストランジション::ゲットエンドキーフレーム

開始キーフレームを返します。

```
CBaseKeyFrame* GetEndKeyframe();
```

### <a name="return-value"></a>戻り値

キーフレームへの有効なポインター。または、キーフレーム間にトランジションを挿入しない場合は NULL。

### <a name="remarks"></a>解説

このメソッドを使用すると、SetKeyframes で以前に設定されたキーフレーム オブジェクトにアクセスできます。 このメソッドは、ストーリーボードにトランジションが追加されるときに、トップレベルのコードによって呼び出されます。

## <a name="cbasetransitiongetrelatedvariable"></a><a name="getrelatedvariable"></a>ソーストランジション::関連する変数を取得します。

関連する変数へのポインターを返します。

```
CAnimationVariable* GetRelatedVariable();
```

### <a name="return-value"></a>戻り値

アニメーション変数への有効なポインター、またはアニメーション変数が SetRelatedVariable によって設定されていない場合は NULL。

### <a name="remarks"></a>解説

これは、関連するアニメーション変数のアクセサーです。

## <a name="cbasetransitiongetstartkeyframe"></a><a name="getstartkeyframe"></a>ソーストランジション::スタートキーフレーム

開始キーフレームを返します。

```
CBaseKeyFrame* GetStartKeyframe();
```

### <a name="return-value"></a>戻り値

キーフレームへの有効なポインター。または、キーフレームの後にトランジションを開始しない場合は NULL。

### <a name="remarks"></a>解説

このメソッドを使用すると、SetKeyframes で以前に設定されたキーフレーム オブジェクトにアクセスできます。 このメソッドは、ストーリーボードにトランジションが追加されるときに、トップレベルのコードによって呼び出されます。

## <a name="cbasetransitiongettransition"></a><a name="gettransition"></a>移行を行う

基になる COM 遷移オブジェクトへのポインターを返します。

```
IUIAnimationTransition* GetTransition(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory);

IUIAnimationTransition* GetTransition();
```

### <a name="parameters"></a>パラメーター

*pライブラリ*<br/>
標準遷移を作成する遷移ライブラリへのポインター。 カスタムトランジションの場合は NULL を指定できます。

*pFactory*<br/>
カスタム遷移を作成する遷移ファクトリへのポインター。 標準遷移の場合は NULL を指定できます。

### <a name="return-value"></a>戻り値

基になる遷移を作成できない場合は、IUIAnimationTransition への有効なポインターまたは NULL。

### <a name="remarks"></a>解説

このメソッドは、基になる COM 遷移オブジェクトへのポインターを返し、必要に応じて作成します。

## <a name="cbasetransitiongettype"></a><a name="gettype"></a>ソーストランジション::取得タイプ

遷移の種類を返します。

```
TRANSITION_TYPE GetType() const;
```

### <a name="return-value"></a>戻り値

TRANSITION_TYPE列挙値の 1 つ。

### <a name="remarks"></a>解説

このメソッドを使用すると、遷移オブジェクトをその型で識別できます。 型は、派生クラスのコンストラクターで設定されます。

## <a name="cbasetransitionisadded"></a><a name="isadded"></a>Cベーストランジション::IsAdded

トランジションがストーリーボードに追加されたかどうかを示します。

```
BOOL IsAdded();
```

### <a name="return-value"></a>戻り値

トランジションがストーリーボードに追加されている場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

このフラグは、最上位レベルのコードがストーリーボードに遷移を追加するときに内部的に設定されます。

## <a name="cbasetransitionm_badded"></a><a name="m_badded"></a>Cベーストランジション::m_bAdded

ストーリーボードにトランジションが追加されているかどうかを指定します。

```
BOOL m_bAdded;
```

## <a name="cbasetransitionm_pendkeyframe"></a><a name="m_pendkeyframe"></a>Cベーストランジション::m_pEndKeyframe

トランジションの終了を指定するキーフレームへのポインターを格納します。

```
CBaseKeyFrame* m_pEndKeyframe;
```

## <a name="cbasetransitionm_prelatedvariable"></a><a name="m_prelatedvariable"></a>Cベーストランジション::m_pRelatedVariable

m_transitionに格納されている遷移でアニメーション化されるアニメーション変数へのポインター。

```
CAnimationVariable* m_pRelatedVariable;
```

## <a name="cbasetransitionm_pstartkeyframe"></a><a name="m_pstartkeyframe"></a>コベーストランジション::m_pStartKeyframe

トランジションの開始位置を指定するキーフレームへのポインターを格納します。

```
CBaseKeyFrame* m_pStartKeyframe;
```

## <a name="cbasetransitionm_transition"></a><a name="m_transition"></a>コベーストランジション::m_transition

へのポインターを格納します。 COM 遷移オブジェクトが作成されていない場合は NULL。

```
ATL::CComPtr<IUIAnimationTransition> m_transition;
```

## <a name="cbasetransitionm_type"></a><a name="m_type"></a>Cベーストランジション::m_type

遷移の種類を格納します。

```
TRANSITION_TYPE m_type;
```

## <a name="cbasetransitionsetkeyframes"></a><a name="setkeyframes"></a>Cベーストランジション::キーフレームを設定します。

トランジションのキーフレームを設定します。

```cpp
void SetKeyframes(
    CBaseKeyFrame* pStart = NULL,
    CBaseKeyFrame* pEnd = NULL);
```

### <a name="parameters"></a>パラメーター

*pスタート*<br/>
トランジションの開始位置を指定するキーフレーム。

*Pend*<br/>
トランジションの終了を指定するキーフレーム。

### <a name="remarks"></a>解説

このメソッドは、指定されたキーフレームの後に開始するようにトランジションを指示し、オプションで pEnd が NULL でない場合は、指定されたキーフレームの前に終了します。 トランジションが duration パラメータを指定して作成された場合、そのデュレーションは開始キーフレームと終了キーフレーム間の期間で上書きされます。

## <a name="cbasetransitionsetrelatedvariable"></a><a name="setrelatedvariable"></a>Cベーストランジション::セット関連変数

アニメーション変数と遷移の関係を確立します。

```cpp
void SetRelatedVariable(CAnimationVariable* pVariable);
```

### <a name="parameters"></a>パラメーター

*変数*<br/>
関連するアニメーション変数へのポインター。

### <a name="remarks"></a>解説

アニメーション変数と遷移の関係を確立します。 遷移は、1 つの変数にのみ適用できます。

## <a name="cbasetransitiontransition_type-enumeration"></a><a name="transition_type_enumeration"></a>列挙体をTRANSITION_TYPE

Windows アニメーション API の MFC 実装で現在サポートされている遷移の種類を定義します。

```
enum TRANSITION_TYPE;
```

### <a name="remarks"></a>解説

遷移の種類は、特定の遷移のコンストラクターで設定されます。 たとえば、CSinusoidalTransitionFromRange は、その型をSINUSOIDAL_FROM_RANGEに設定します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
