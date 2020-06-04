---
title: CAnimationBaseObject クラス
ms.date: 03/27/2019
f1_keywords:
- CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ContainsVariable
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::DetachFromController
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetParentAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_dwUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_pParentController
helpviewer_keywords:
- CAnimationBaseObject [MFC], CAnimationBaseObject
- CAnimationBaseObject [MFC], ApplyTransitions
- CAnimationBaseObject [MFC], ClearTransitions
- CAnimationBaseObject [MFC], ContainsVariable
- CAnimationBaseObject [MFC], CreateTransitions
- CAnimationBaseObject [MFC], DetachFromController
- CAnimationBaseObject [MFC], EnableIntegerValueChangedEvent
- CAnimationBaseObject [MFC], EnableValueChangedEvent
- CAnimationBaseObject [MFC], GetAutodestroyTransitions
- CAnimationBaseObject [MFC], GetGroupID
- CAnimationBaseObject [MFC], GetObjectID
- CAnimationBaseObject [MFC], GetUserData
- CAnimationBaseObject [MFC], SetAutodestroyTransitions
- CAnimationBaseObject [MFC], SetID
- CAnimationBaseObject [MFC], SetUserData
- CAnimationBaseObject [MFC], GetAnimationVariableList
- CAnimationBaseObject [MFC], SetParentAnimationObjects
- CAnimationBaseObject [MFC], m_bAutodestroyTransitions
- CAnimationBaseObject [MFC], m_dwUserData
- CAnimationBaseObject [MFC], m_nGroupID
- CAnimationBaseObject [MFC], m_nObjectID
- CAnimationBaseObject [MFC], m_pParentController
ms.assetid: 76b25917-940e-4eba-940f-31d270702603
ms.openlocfilehash: 1874ddfdd26b8dd371e32f7e68ea8f668c47d8e1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750223"
---
# <a name="canimationbaseobject-class"></a>CAnimationBaseObject クラス

すべてのアニメーション オブジェクトの基底クラスです。

## <a name="syntax"></a>構文

```
class CAnimationBaseObject : public CObject;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[オブジェクト::Cアニメーションベースオブジェクト](#canimationbaseobject)|オーバーロードされます。 アニメーション オブジェクトを構築します。|
|[オブジェクト::~Cアニメーションベースオブジェクト](#_dtorcanimationbaseobject)|デストラクターです。 アニメーション オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cアニメーションベースオブジェクト::移行を適用します。](#applytransitions)|カプセル化されたアニメーション変数を使用して、ストーリーボードに遷移を追加します。|
|[オブジェクト::クリアトランジション](#cleartransitions)|関連するすべてのトランジションを削除します。|
|[オブジェクト::変数を含む](#containsvariable)|アニメーション オブジェクトに特定のアニメーション変数が含まれているかどうかを判断します。|
|[オブジェクト::トランジションの作成](#createtransitions)|アニメーション オブジェクトに関連付けられたトランジションを作成します。|
|[Cアニメーションベースオブジェクト::Dエタッハフロインコントローラー](#detachfromcontroller)|親アニメーション コントローラからアニメーション オブジェクトをデタッチします。|
|[イベントを変更しました。](#enableintegervaluechangedevent)|整数値変更イベント ハンドラーを設定します。|
|[イベントを変更しました。](#enablevaluechangedevent)|値変更イベント ハンドラを設定します。|
|[オブジェクト::取得自動破棄トランジション](#getautodestroytransitions)|関連する遷移が自動的に破棄されるかどうかを示します。|
|[オブジェクトを取得します。](#getgroupid)|現在のグループ ID を返します。|
|[オブジェクトを取得します。](#getobjectid)|現在のオブジェクト ID を返します。|
|[オブジェクト::ユーザーデータを取得します。](#getuserdata)|ユーザー定義データを返します。|
|[Cアニメーションベースオブジェクト::設定オートデストロイトランジション](#setautodestroytransitions)|遷移を自動的に破棄するフラグを設定します。|
|[オブジェクト::セットID](#setid)|新しい ID を設定します。|
|[オブジェクト::セットユーザーデータ](#setuserdata)|ユーザー定義データを設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[オブジェクト::アニメーション変数リスト](#getanimationvariablelist)|含まれているアニメーション変数へのポインターを収集します。|
|[オブジェクト::セットペアレントアニメーションオブジェクト](#setparentanimationobjects)|アニメーション オブジェクトに含まれるアニメーション変数とそのコンテナとの関係を確立します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[オブジェクト::m_bAutodestroyTransitions](#m_bautodestroytransitions)|関連する遷移を自動的に破棄するかどうかを指定します。|
|[オブジェクト::m_dwUserData](#m_dwuserdata)|ユーザー定義データを格納します。|
|[Cアニメーションベースオブジェクト::m_nGroupID](#m_ngroupid)|アニメーション オブジェクトのグループ ID を指定します。|
|[Cアニメーションベースオブジェクト::m_nObjectID](#m_nobjectid)|アニメーション オブジェクトのオブジェクト ID を指定します。|
|[Cアニメーションベースオブジェクト::m_pParentController](#m_pparentcontroller)|親アニメーション コントローラへのポインター。|

## <a name="remarks"></a>解説

このクラスは、すべてのアニメーション オブジェクトの基本メソッドを実装します。 アニメーション オブジェクトは、アプリケーションの値、ポイント、サイズ、四角形、色、および任意のユーザー定義エンティティを表すことができます。 アニメーション オブジェクトは、アニメーション グループに格納されます (CAnimationGroup を参照)。 各グループは、個別にアニメーション化することができ、ストーリーボードのアナログとして扱うことができます。 アニメーション オブジェクトは、その論理表現に応じて、1 つ以上のアニメーション変数をカプセル化します (CAnimationVariable を参照)。 たとえば、CAnimationRect には四つのアニメーション変数 (四角形の各辺に 1 つの変数) が含まれています。 各アニメーション オブジェクト クラスは、カプセル化されたアニメーション変数に遷移を適用するために使用する必要があります、オーバーロードされた AddTransition メソッドを公開します。 アニメーション オブジェクトは、オブジェクト ID (オプション) とグループ ID で識別できます。 グループ ID は、アニメーション オブジェクトを正しいグループに配置するために必要ですが、グループ ID が指定されていない場合は、オブジェクトが ID 0 の既定のグループに配置されます。 異なる GroupID を指定して SetID を呼び出すと、アニメーション オブジェクトは別のグループに移動されます (必要に応じて新しいグループが作成されます)。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CAnimationBaseObject`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationbaseobjectcanimationbaseobject"></a><a name="_dtorcanimationbaseobject"></a>オブジェクト::~Cアニメーションベースオブジェクト

デストラクターです。 アニメーション オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CAnimationBaseObject();
```

## <a name="canimationbaseobjectapplytransitions"></a><a name="applytransitions"></a>Cアニメーションベースオブジェクト::移行を適用します。

カプセル化されたアニメーション変数を使用して、ストーリーボードに遷移を追加します。

```
virtual BOOL ApplyTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>パラメーター

*ストーリーボード*<br/>
ストーリーボードへのポインター。

*ブディペンディオンキーフレーム*<br/>
FALSE の場合、このメソッドは、キーフレームに依存しないトランジションのみを追加します。

### <a name="return-value"></a>戻り値

遷移が正常に追加された場合は TRUE。

### <a name="remarks"></a>解説

AddTransition (派生クラスのオーバーロードされたメソッド) で追加された関連する遷移をストーリーボードに追加します。

## <a name="canimationbaseobjectcanimationbaseobject"></a><a name="canimationbaseobject"></a>オブジェクト::Cアニメーションベースオブジェクト

アニメーション オブジェクトを構築します。

```
CAnimationBaseObject();

CAnimationBaseObject(
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>パラメーター

*グループ ID*<br/>
グループ ID を指定します。

*オブジェクト ID*<br/>
オブジェクト ID を指定します。

*データ*<br/>
ユーザー定義データは、アニメーション オブジェクトに関連付けることができ、後で実行時に取得できます。

### <a name="remarks"></a>解説

アニメーション オブジェクトを構築し、既定のオブジェクト ID (0) とグループ ID (0) を割り当てます。

## <a name="canimationbaseobjectcleartransitions"></a><a name="cleartransitions"></a>オブジェクト::クリアトランジション

関連するすべてのトランジションを削除します。

```
virtual void ClearTransitions(BOOL bAutodestroy);
```

### <a name="parameters"></a>パラメーター

*b自動破壊*<br/>
遷移オブジェクトを自動的に破棄するか、または関連リストから単に削除するかを指定します。

### <a name="remarks"></a>解説

bAutodestroy または m_bAutodestroyTransitions フラグが TRUE の場合、関連するすべての遷移を削除し、破棄します。 遷移は、スタックに割り当てられていない場合にのみ自動的に破棄されます。 上記のフラグが FALSE の場合、遷移は関連する遷移の内部リストから削除されます。

## <a name="canimationbaseobjectcontainsvariable"></a><a name="containsvariable"></a>オブジェクト::変数を含む

アニメーション オブジェクトに特定のアニメーション変数が含まれているかどうかを判断します。

```
virtual BOOL ContainsVariable(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>パラメーター

*変数*<br/>
アニメーション変数へのポインター。

### <a name="return-value"></a>戻り値

アニメーション変数がアニメーション オブジェクトに含まれている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドを使用して、pVariable で指定されたアニメーション変数がアニメーション オブジェクト内に含まれているかどうかを判断できます。 アニメーション オブジェクトは、その種類に応じて、複数のアニメーション変数を含む場合があります。 たとえば、CAnimationColor には、各色コンポーネント (赤、緑、青) に 1 つずつ、3 つの変数が含まれています。 アニメーション変数の値が変更されると、Windows アニメーション API は ValueChanged イベントまたは IntegerValueChanged イベントを送信し (有効な場合)、このイベントのパラメーターはアニメーション変数のインターフェイス IUIAnimationVariable へのポインターです。 このメソッドは、含まれている COM オブジェクトへのポインターからアニメーションへのポインターを取得するのに役立ちます。

## <a name="canimationbaseobjectcreatetransitions"></a><a name="createtransitions"></a>オブジェクト::トランジションの作成

アニメーション オブジェクトに関連付けられたトランジションを作成します。

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>戻り値

遷移が正常に作成された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

派生アニメーション オブジェクトにカプセル化されたアニメーション変数のリストをループし、各アニメーション変数に関連付けられた遷移を作成します。

## <a name="canimationbaseobjectdetachfromcontroller"></a><a name="detachfromcontroller"></a>Cアニメーションベースオブジェクト::Dエタッハフロインコントローラー

親アニメーション コントローラからアニメーション オブジェクトをデタッチします。

```cpp
void DetachFromController();
```

### <a name="remarks"></a>解説

このメソッドは内部的に使用されます。

## <a name="canimationbaseobjectenableintegervaluechangedevent"></a><a name="enableintegervaluechangedevent"></a>イベントを変更しました。

整数値変更イベント ハンドラーを設定します。

```
virtual void EnableIntegerValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>パラメーター

*コントローラ*<br/>
親コントローラへのポインタ。

*b 有効にする*<br/>
整数値変更イベントを有効にするか、無効にするかを指定します。

### <a name="remarks"></a>解説

整数値の変更イベント ハンドラーが有効になっている場合は、CAnimationController 派生クラスでオーバーライドする必要があります、メソッドでこのイベントを処理できます。 このメソッドは、アニメーションの整数値が変更されるたびに呼び出されます。

## <a name="canimationbaseobjectenablevaluechangedevent"></a><a name="enablevaluechangedevent"></a>イベントを変更しました。

値変更イベント ハンドラを設定します。

```
virtual void EnableValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>パラメーター

*コントローラ*<br/>
親コントローラへのポインタ。

*b 有効にする*<br/>
値変更イベントを有効にするか、無効にするかを指定します。

### <a name="remarks"></a>解説

値変更イベント ハンドラーが有効になっている場合は、CAnimationController::OnAnimationValueChanged メソッドでこのイベントを処理できます。 このメソッドは、アニメーションの値が変更されるたびに呼び出されます。

## <a name="canimationbaseobjectgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>オブジェクト::アニメーション変数リスト

含まれているアニメーション変数へのポインターを収集します。

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& list) = 0;
```

### <a name="parameters"></a>パラメーター

*list*<br/>
アニメーション オブジェクトに含まれるアニメーション変数を入力する必要があるリスト。

### <a name="remarks"></a>解説

この純粋仮想メソッドは、派生クラスでオーバーライドする必要があります。 アニメーション オブジェクトは、その種類に応じて、1 つ以上のアニメーション変数を含みます。 たとえば、CAnimationPoint には、X 座標と Y 座標の 2 つの変数がそれぞれ含まれています。 基本クラス CAnimationBaseObject は、アニメーション変数のリストに作用するいくつかのジェネリック メソッドを実装します。 これらのメソッドは、特定のアニメーション オブジェクトに含まれる実際のアニメーション変数を持つ派生クラスに入力される GetAnimationVariableList を呼び出し、リストをループして必要なアクションを実行します。 カスタム アニメーション オブジェクトを作成する場合は、そのオブジェクトに含まれるすべてのアニメーション変数を*追加してリスト*に追加する必要があります。

## <a name="canimationbaseobjectgetautodestroytransitions"></a><a name="getautodestroytransitions"></a>オブジェクト::取得自動破棄トランジション

関連する遷移が自動的に破棄されるかどうかを示します。

```
BOOL GetAutodestroyTransitions() const;
```

### <a name="return-value"></a>戻り値

TRUE の場合、関連する遷移は自動的に破棄されます。FALSE の場合、遷移オブジェクトはアプリケーションを呼び出すことによって割り当てを解除する必要があります。

### <a name="remarks"></a>解説

デフォルトでは、このフラグは TRUE です。 このフラグは、スタックに切り替えまたは遷移を呼び出し元のアプリケーションによって割り当て解除する必要がある場合にのみ設定します。

## <a name="canimationbaseobjectgetgroupid"></a><a name="getgroupid"></a>オブジェクトを取得します。

現在のグループ ID を返します。

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>戻り値

現在のグループ ID。

### <a name="remarks"></a>解説

このメソッドは、グループ ID を取得するために使います。 コンストラクタまたは SetID でグループ ID が明示的に設定されていない場合は 0 です。

## <a name="canimationbaseobjectgetobjectid"></a><a name="getobjectid"></a>オブジェクトを取得します。

現在のオブジェクト ID を返します。

```
UINT32 GetObjectID() const;
```

### <a name="return-value"></a>戻り値

現在のオブジェクト ID。

### <a name="remarks"></a>解説

このメソッドは、オブジェクト ID を取得するために使います。 コンストラクタまたは SetID でオブジェクト ID が明示的に設定されていない場合は 0 です。

## <a name="canimationbaseobjectgetuserdata"></a><a name="getuserdata"></a>オブジェクト::ユーザーデータを取得します。

ユーザー定義データを返します。

```
DWORD GetUserData() const;
```

### <a name="return-value"></a>戻り値

カスタム データの値。

### <a name="remarks"></a>解説

実行時にカスタム データを取得します。 コンストラクターまたは SetUserData を使用して明示的に初期化されていない場合、戻り値は 0 になります。

## <a name="canimationbaseobjectm_bautodestroytransitions"></a><a name="m_bautodestroytransitions"></a>オブジェクト::m_bAutodestroyTransitions

関連する遷移を自動的に破棄するかどうかを指定します。

```
BOOL m_bAutodestroyTransitions;
```

## <a name="canimationbaseobjectm_dwuserdata"></a><a name="m_dwuserdata"></a>オブジェクト::m_dwUserData

ユーザー定義データを格納します。

```
DWORD m_dwUserData;
```

## <a name="canimationbaseobjectm_ngroupid"></a><a name="m_ngroupid"></a>Cアニメーションベースオブジェクト::m_nGroupID

アニメーション オブジェクトのグループ ID を指定します。

```
UINT32 m_nGroupID;
```

## <a name="canimationbaseobjectm_nobjectid"></a><a name="m_nobjectid"></a>Cアニメーションベースオブジェクト::m_nObjectID

アニメーション オブジェクトのオブジェクト ID を指定します。

```
UINT32 m_nObjectID;
```

## <a name="canimationbaseobjectm_pparentcontroller"></a><a name="m_pparentcontroller"></a>Cアニメーションベースオブジェクト::m_pParentController

親アニメーション コントローラへのポインター。

```
CAnimationController* m_pParentController;
```

## <a name="canimationbaseobjectsetautodestroytransitions"></a><a name="setautodestroytransitions"></a>Cアニメーションベースオブジェクト::設定オートデストロイトランジション

遷移を自動的に破棄するフラグを設定します。

```cpp
void SetAutodestroyTransitions(BOOL bValue);
```

### <a name="parameters"></a>パラメーター

*b値*<br/>
自動破棄フラグを指定します。

### <a name="remarks"></a>解説

このフラグは、演算子 new を使用して遷移オブジェクトを割り当てた場合にのみ設定します。 何らかの理由で遷移オブジェクトがスタックに割り当てられている場合、自動破棄フラグは FALSE にする必要があります。 デフォルトでは、このフラグは TRUE です。

## <a name="canimationbaseobjectsetid"></a><a name="setid"></a>オブジェクト::セットID

新しい ID を設定します。

```cpp
void SetID(
    UINT32 nObjectID,
    UINT32 nGroupID = 0);
```

### <a name="parameters"></a>パラメーター

*オブジェクト ID*<br/>
新しいオブジェクト ID を指定します。

*グループ ID*<br/>
新しいグループ ID を指定します。

### <a name="remarks"></a>解説

オブジェクト ID とグループ ID を変更できます。 新しいグループ ID が現在の ID と異なる場合、アニメーション オブジェクトは別のグループに移動されます(必要に応じて新しいグループが作成されます)。

## <a name="canimationbaseobjectsetparentanimationobjects"></a><a name="setparentanimationobjects"></a>オブジェクト::セットペアレントアニメーションオブジェクト

アニメーション オブジェクトに含まれるアニメーション変数とそのコンテナとの関係を確立します。

```
virtual void SetParentAnimationObjects();
```

### <a name="remarks"></a>解説

このヘルパーを使用して、アニメーション オブジェクトに含まれるアニメーション変数とそのコンテナとの関係を確立できます。 アニメーション変数をループし、各アニメーション変数に対する親アニメーション オブジェクトへの戻りポインタを設定します。 現在の実装では、実際の関係は CAnimationBaseObject::ApplyTransitions で確立されているため、CAnimationGroup::アニメーションを呼び出すまでバック ポインターは設定されません。 イベントを処理するときにリレーションシップを知っておくと便利な場合があり、CAnimationVariable から親アニメーション オブジェクトを取得する必要があります。 を使用します。

## <a name="canimationbaseobjectsetuserdata"></a><a name="setuserdata"></a>オブジェクト::セットユーザーデータ

ユーザー定義データを設定します。

```cpp
void SetUserData (DWORD dwUserData);
```

### <a name="parameters"></a>パラメーター

*データ*<br/>
カスタム データを指定します。

### <a name="remarks"></a>解説

このメソッドは、カスタム データをアニメーション オブジェクトに関連付けるために使います。 このデータは、実行時に GetUserData によって後で取得される可能性があります。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
