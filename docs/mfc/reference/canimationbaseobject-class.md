---
description: '詳細情報: CAnimationBaseObject クラス'
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
ms.openlocfilehash: bc44d0e55b409f66648007eeb27fefd386640d9f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318664"
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
|[CAnimationBaseObject:: CAnimationBaseObject](#canimationbaseobject)|オーバーロードされます。 アニメーションオブジェクトを構築します。|
|[CAnimationBaseObject:: ~ CAnimationBaseObject](#_dtorcanimationbaseobject)|デストラクターです。 アニメーションオブジェクトが破棄されているときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAnimationBaseObject:: ApplyTransitions](#applytransitions)|カプセル化されたアニメーション変数を使用して、ストーリーボードに切り替え効果を追加します。|
|[CAnimationBaseObject:: ClearTransitions](#cleartransitions)|関連するすべての遷移を削除します。|
|[CAnimationBaseObject:: を持つ変数](#containsvariable)|アニメーションオブジェクトに特定のアニメーション変数が含まれているかどうかを判断します。|
|[CAnimationBaseObject:: CreateTransitions](#createtransitions)|アニメーションオブジェクトに関連付けられている遷移を作成します。|
|[CAnimationBaseObject::D etachFromController](#detachfromcontroller)|アニメーションオブジェクトを親のアニメーションコントローラーからデタッチします。|
|[CAnimationBaseObject:: EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|整数値変更イベントハンドラーを設定します。|
|[CAnimationBaseObject:: EnableValueChangedEvent](#enablevaluechangedevent)|値変更イベントハンドラーを設定します。|
|[CAnimationBaseObject:: GetAutodestroyTransitions](#getautodestroytransitions)|関連する遷移が自動的に破棄されるかどうかを示します。|
|[CAnimationBaseObject:: GetGroupID](#getgroupid)|現在のグループ ID を返します。|
|[CAnimationBaseObject:: GetObjectID](#getobjectid)|現在のオブジェクト ID を返します。|
|[CAnimationBaseObject:: GetUserData](#getuserdata)|ユーザー定義データを返します。|
|[CAnimationBaseObject:: SetAutodestroyTransitions](#setautodestroytransitions)|遷移を自動的に破棄するフラグを設定します。|
|[CAnimationBaseObject:: SetID](#setid)|新しい Id を設定します。|
|[CAnimationBaseObject:: SetUserData](#setuserdata)|ユーザー定義データを設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CAnimationBaseObject:: Getアニメーション変数の一覧](#getanimationvariablelist)|含まれているアニメーション変数へのポインターを収集します。|
|[CAnimationBaseObject:: Setparentアニメーションオブジェクト](#setparentanimationobjects)|アニメーションオブジェクトとそのコンテナーに含まれるアニメーション変数間のリレーションシップを確立します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CAnimationBaseObject:: m_bAutodestroyTransitions](#m_bautodestroytransitions)|関連する遷移を自動的に破棄するかどうかを指定します。|
|[CAnimationBaseObject:: m_dwUserData](#m_dwuserdata)|ユーザー定義データを格納します。|
|[CAnimationBaseObject:: m_nGroupID](#m_ngroupid)|アニメーションオブジェクトのグループ ID を指定します。|
|[CAnimationBaseObject:: m_nObjectID](#m_nobjectid)|アニメーションオブジェクトのオブジェクト ID を指定します。|
|[CAnimationBaseObject:: m_pParentController](#m_pparentcontroller)|親アニメーションコントローラーへのポインター。|

## <a name="remarks"></a>解説

このクラスは、すべてのアニメーションオブジェクトの基本メソッドを実装します。 アニメーションオブジェクトは、アプリケーションの値、ポイント、サイズ、四角形、または色、および任意のカスタムエンティティを表すことができます。 アニメーションオブジェクトは、アニメーショングループに格納されます (「CAnimationGroup」を参照)。 各グループは個別にアニメーション化することができ、ストーリーボードのアナログとして扱うことができます。 アニメーションオブジェクトは、論理表現に応じて1つ以上のアニメーション変数 (「CAnimationVariable」を参照) をカプセル化します。 たとえば、CAnimationRect には、四角形の各辺に1つの変数を含む4つのアニメーション変数が含まれています。 各アニメーションオブジェクトクラスは、オーバーロードされた AddTransition メソッドを公開します。これは、カプセル化されたアニメーション変数に遷移を適用するために使用する必要があります。 アニメーションオブジェクトは、オブジェクト ID (必要に応じて) およびグループ ID によって識別できます。 グループ id は、アニメーションオブジェクトを適切なグループに配置するために必要ですが、グループ ID が指定されていない場合、オブジェクトは ID 0 の既定のグループに配置されます。 異なる GroupID を使用して SetID を呼び出すと、animation オブジェクトが別のグループに移動されます (必要に応じて新しいグループが作成されます)。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CAnimationBaseObject`

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationbaseobjectcanimationbaseobject"></a><a name="_dtorcanimationbaseobject"></a> CAnimationBaseObject:: ~ CAnimationBaseObject

デストラクターです。 アニメーションオブジェクトが破棄されているときに呼び出されます。

```
virtual ~CAnimationBaseObject();
```

## <a name="canimationbaseobjectapplytransitions"></a><a name="applytransitions"></a> CAnimationBaseObject:: ApplyTransitions

カプセル化されたアニメーション変数を使用して、ストーリーボードに切り替え効果を追加します。

```
virtual BOOL ApplyTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>パラメーター

*pStoryboard*<br/>
ストーリーボードへのポインター。

*B依存性 Onキーフレーム*<br/>
FALSE の場合、このメソッドは、キーフレームに依存しない遷移だけを追加します。

### <a name="return-value"></a>戻り値

遷移が正常に追加された場合は TRUE。

### <a name="remarks"></a>解説

AddTransition (派生クラスのオーバーロードされたメソッド) を使用して追加された関連する遷移をストーリーボードに追加します。

## <a name="canimationbaseobjectcanimationbaseobject"></a><a name="canimationbaseobject"></a> CAnimationBaseObject:: CAnimationBaseObject

アニメーションオブジェクトを構築します。

```
CAnimationBaseObject();

CAnimationBaseObject(
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>パラメーター

*nGroupID*<br/>
グループ ID を指定します。

*nObjectID*<br/>
オブジェクト ID を指定します。

*dwUserData*<br/>
ユーザー定義データ。アニメーションオブジェクトに関連付けて、後で実行時に取得できます。

### <a name="remarks"></a>解説

アニメーションオブジェクトを構築し、既定のオブジェクト ID (0) とグループ ID (0) を割り当てます。

## <a name="canimationbaseobjectcleartransitions"></a><a name="cleartransitions"></a> CAnimationBaseObject:: ClearTransitions

関連するすべての遷移を削除します。

```
virtual void ClearTransitions(BOOL bAutodestroy);
```

### <a name="parameters"></a>パラメーター

*bAutodestroy*<br/>
遷移オブジェクトを自動的に破棄するか、関連する一覧から削除するかを指定します。

### <a name="remarks"></a>解説

BAutodestroy または m_bAutodestroyTransitions フラグが TRUE の場合、関連するすべての遷移を削除し、それらを破棄します。 遷移は、スタックに割り当てられていない場合にのみ、自動的に破棄されます。 上記のフラグが FALSE の場合は、関連する遷移の内部リストから遷移が削除されます。

## <a name="canimationbaseobjectcontainsvariable"></a><a name="containsvariable"></a> CAnimationBaseObject:: を持つ変数

アニメーションオブジェクトに特定のアニメーション変数が含まれているかどうかを判断します。

```
virtual BOOL ContainsVariable(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>パラメーター

*pVariable*<br/>
アニメーション変数へのポインター。

### <a name="return-value"></a>戻り値

アニメーション変数が animation オブジェクトに含まれている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドを使用すると、pVariable によって指定されたアニメーション変数がアニメーションオブジェクト内に含まれるかどうかを判断できます。 アニメーションオブジェクトは、その型によっては、複数のアニメーション変数を含むことができます。 たとえば、CAnimationColor には、各色成分 (赤、緑、および青) に1つずつ、3つの変数が含まれています。 アニメーション変数の値が変更された場合、Windows アニメーション API は ValueChanged イベントまたは IntegerValueChanged イベント (有効な場合) を送信し、このイベントのパラメーターは、アニメーション変数のインターフェイス Iuianimation 変数へのポインターになります。 このメソッドは、含まれている COM オブジェクトへのポインターからアニメーションへのポインターを取得するのに役立ちます。

## <a name="canimationbaseobjectcreatetransitions"></a><a name="createtransitions"></a> CAnimationBaseObject:: CreateTransitions

アニメーションオブジェクトに関連付けられている遷移を作成します。

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>戻り値

遷移が正常に作成された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

派生アニメーションオブジェクトにカプセル化されたアニメーション変数のリストをループし、各アニメーション変数に関連付けられている遷移を作成します。

## <a name="canimationbaseobjectdetachfromcontroller"></a><a name="detachfromcontroller"></a> CAnimationBaseObject::D etachFromController

アニメーションオブジェクトを親のアニメーションコントローラーからデタッチします。

```cpp
void DetachFromController();
```

### <a name="remarks"></a>解説

このメソッドは、内部的に使用されます。

## <a name="canimationbaseobjectenableintegervaluechangedevent"></a><a name="enableintegervaluechangedevent"></a> CAnimationBaseObject:: EnableIntegerValueChangedEvent

整数値変更イベントハンドラーを設定します。

```
virtual void EnableIntegerValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>パラメーター

*pController*<br/>
親コントローラーへのポインター。

*bEnable*<br/>
整数値の変更イベントを有効にするか無効にするかを指定します。

### <a name="remarks"></a>解説

整数値の変更イベントハンドラーが有効になっている場合は、CAnimationController:: OnAnimationIntegerValueChanged メソッドでこのイベントを処理できます。このメソッドは、CAnimationController 派生クラスでオーバーライドする必要があります。 このメソッドは、アニメーションの整数値が変更されるたびに呼び出されます。

## <a name="canimationbaseobjectenablevaluechangedevent"></a><a name="enablevaluechangedevent"></a> CAnimationBaseObject:: EnableValueChangedEvent

値変更イベントハンドラーを設定します。

```
virtual void EnableValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>パラメーター

*pController*<br/>
親コントローラーへのポインター。

*bEnable*<br/>
値変更イベントを有効にするか無効にするかを指定します。

### <a name="remarks"></a>解説

値変更イベントハンドラーが有効になっている場合は、CAnimationController:: OnAnimationValueChanged メソッドでこのイベントを処理できます。このメソッドは、CAnimationController 派生クラスでオーバーライドする必要があります。 このメソッドは、アニメーションの値が変更されるたびに呼び出されます。

## <a name="canimationbaseobjectgetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationBaseObject:: Getアニメーション変数の一覧

含まれているアニメーション変数へのポインターを収集します。

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& list) = 0;
```

### <a name="parameters"></a>パラメーター

*list*<br/>
アニメーションオブジェクトに含まれるアニメーション変数を格納する必要があるリスト。

### <a name="remarks"></a>解説

この純粋仮想メソッドは、派生クラスでオーバーライドする必要があります。 アニメーションオブジェクトは、その型に応じて1つ以上のアニメーション変数を含みます。 たとえば、CAnimationPoint には、それぞれ X 座標と Y 座標の2つの変数が含まれています。 基本クラスの CAnimationBaseObject は、アニメーション変数のリスト (ApplyTransitions、ClearTransitions、EnableValueChangedEvent、EnableIntegerValueChangedEvent) に対して動作するいくつかのジェネリックメソッドを実装します。 これらのメソッドは Getanimation variables List を呼び出します。このリストは、特定のアニメーションオブジェクトに含まれる実際のアニメーション変数を使用して派生クラスに格納され、リストをループして、必要なアクションを実行します。 カスタムアニメーションオブジェクトを作成する場合、そのオブジェクトに含まれているすべてのアニメーション変数を *一覧表示* するには、を追加する必要があります。

## <a name="canimationbaseobjectgetautodestroytransitions"></a><a name="getautodestroytransitions"></a> CAnimationBaseObject:: GetAutodestroyTransitions

関連する遷移が自動的に破棄されるかどうかを示します。

```
BOOL GetAutodestroyTransitions() const;
```

### <a name="return-value"></a>戻り値

TRUE の場合、関連する遷移は自動的に破棄されます。FALSE の場合は、アプリケーションを呼び出すことによって、遷移オブジェクトの割り当てを解除する必要があります。

### <a name="remarks"></a>解説

既定では、このフラグは TRUE に設定されています。 このフラグを設定するのは、スタックに遷移を割り当てた場合、または呼び出し元のアプリケーションによって遷移が割り当て解除された場合のみです。

## <a name="canimationbaseobjectgetgroupid"></a><a name="getgroupid"></a> CAnimationBaseObject:: GetGroupID

現在のグループ ID を返します。

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>戻り値

現在のグループ ID です。

### <a name="remarks"></a>解説

グループ ID を取得するには、このメソッドを使用します。 グループ ID がコンストラクターまたは SetID で明示的に設定されていない場合は0になります。

## <a name="canimationbaseobjectgetobjectid"></a><a name="getobjectid"></a> CAnimationBaseObject:: GetObjectID

現在のオブジェクト ID を返します。

```
UINT32 GetObjectID() const;
```

### <a name="return-value"></a>戻り値

現在のオブジェクト ID。

### <a name="remarks"></a>解説

オブジェクト ID を取得するには、このメソッドを使用します。 オブジェクト ID がコンストラクターまたは SetID で明示的に設定されていない場合は0になります。

## <a name="canimationbaseobjectgetuserdata"></a><a name="getuserdata"></a> CAnimationBaseObject:: GetUserData

ユーザー定義データを返します。

```
DWORD GetUserData() const;
```

### <a name="return-value"></a>戻り値

カスタムデータの値。

### <a name="remarks"></a>解説

実行時にカスタムデータを取得するには、このメソッドを呼び出します。 コンストラクターまたは SetUserData で明示的に初期化されなかった場合、戻り値は0になります。

## <a name="canimationbaseobjectm_bautodestroytransitions"></a><a name="m_bautodestroytransitions"></a> CAnimationBaseObject:: m_bAutodestroyTransitions

関連する遷移を自動的に破棄するかどうかを指定します。

```
BOOL m_bAutodestroyTransitions;
```

## <a name="canimationbaseobjectm_dwuserdata"></a><a name="m_dwuserdata"></a> CAnimationBaseObject:: m_dwUserData

ユーザー定義データを格納します。

```
DWORD m_dwUserData;
```

## <a name="canimationbaseobjectm_ngroupid"></a><a name="m_ngroupid"></a> CAnimationBaseObject:: m_nGroupID

アニメーションオブジェクトのグループ ID を指定します。

```
UINT32 m_nGroupID;
```

## <a name="canimationbaseobjectm_nobjectid"></a><a name="m_nobjectid"></a> CAnimationBaseObject:: m_nObjectID

アニメーションオブジェクトのオブジェクト ID を指定します。

```
UINT32 m_nObjectID;
```

## <a name="canimationbaseobjectm_pparentcontroller"></a><a name="m_pparentcontroller"></a> CAnimationBaseObject:: m_pParentController

親アニメーションコントローラーへのポインター。

```
CAnimationController* m_pParentController;
```

## <a name="canimationbaseobjectsetautodestroytransitions"></a><a name="setautodestroytransitions"></a> CAnimationBaseObject:: SetAutodestroyTransitions

遷移を自動的に破棄するフラグを設定します。

```cpp
void SetAutodestroyTransitions(BOOL bValue);
```

### <a name="parameters"></a>パラメーター

*bValue*<br/>
自動破棄フラグを指定します。

### <a name="remarks"></a>解説

Operator new を使用して transition オブジェクトを割り当てた場合にのみ、このフラグを設定します。 何らかの理由で遷移オブジェクトがスタックに割り当てられている場合は、auto destroy フラグを FALSE に設定する必要があります。 既定では、このフラグは TRUE に設定されています。

## <a name="canimationbaseobjectsetid"></a><a name="setid"></a> CAnimationBaseObject:: SetID

新しい Id を設定します。

```cpp
void SetID(
    UINT32 nObjectID,
    UINT32 nGroupID = 0);
```

### <a name="parameters"></a>パラメーター

*nObjectID*<br/>
新しいオブジェクト ID を指定します。

*nGroupID*<br/>
新しいグループ ID を指定します。

### <a name="remarks"></a>解説

オブジェクト ID とグループ ID を変更できます。 新しいグループ ID が現在の ID と異なる場合は、アニメーションオブジェクトが別のグループに移動されます (必要に応じて、新しいグループが作成されます)。

## <a name="canimationbaseobjectsetparentanimationobjects"></a><a name="setparentanimationobjects"></a> CAnimationBaseObject:: Setparentアニメーションオブジェクト

アニメーションオブジェクトとそのコンテナーに含まれるアニメーション変数間のリレーションシップを確立します。

```
virtual void SetParentAnimationObjects();
```

### <a name="remarks"></a>解説

このヘルパーを使用すると、アニメーションオブジェクトに含まれるアニメーション変数とそのコンテナーの間のリレーションシップを確立できます。 アニメーション変数をループし、親アニメーションオブジェクトへの戻るポインターを各アニメーション変数に設定します。 現在の実装では、CAnimationBaseObject:: ApplyTransitions で実際の関係が確立されているため、CAnimationGroup:: Animate を呼び出すまで、バックポインターは設定されません。 リレーションシップを理解することは、イベントを処理するときに、CAnimationVariable から親のアニメーションオブジェクトを取得する必要がある場合に役立ちます。 CAnimationVariable:: GetParentAnimationObject を使用します。

## <a name="canimationbaseobjectsetuserdata"></a><a name="setuserdata"></a> CAnimationBaseObject:: SetUserData

ユーザー定義データを設定します。

```cpp
void SetUserData (DWORD dwUserData);
```

### <a name="parameters"></a>パラメーター

*dwUserData*<br/>
カスタムデータを指定します。

### <a name="remarks"></a>解説

このメソッドを使用すると、カスタムデータをアニメーションオブジェクトに関連付けることができます。 このデータは、後で GetUserData によって実行時に取得できます。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
