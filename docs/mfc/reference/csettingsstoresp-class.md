---
description: CSettingsStoreSP クラスの詳細情報
title: CSettingsStoreSP クラス
ms.date: 11/04/2016
f1_keywords:
- CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::Create
- AFXSETTINGSSTORE/CSettingsStoreSP::SetRuntimeClass
helpviewer_keywords:
- CSettingsStoreSP [MFC], CSettingsStoreSP
- CSettingsStoreSP [MFC], Create
- CSettingsStoreSP [MFC], SetRuntimeClass
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
ms.openlocfilehash: 67e9f881fc43722ab568aa7f149fc7a2b44cc764
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264688"
---
# <a name="csettingsstoresp-class"></a>CSettingsStoreSP クラス

クラスは、 `CSettingsStoreSP` [Csettingsstore クラス](../../mfc/reference/csettingsstore-class.md)のインスタンスを作成するために使用できるヘルパークラスです。

## <a name="syntax"></a>構文

```
class CSettingsStoreSP
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSettingsStoreSP:: CSettingsStoreSP](#csettingsstoresp)|`CSettingsStoreSP` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSettingsStoreSP:: Create](#create)|から派生したクラスのインスタンスを作成し `CSettingsStore` ます。|
|[CSettingsStoreSP:: SetRuntimeClass](#setruntimeclass)|ランタイムクラスを設定します。 メソッドは、ランタイムクラスを使用して、 `Create` 作成するオブジェクトのクラスを決定します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|`m_dwUserData`|オブジェクトに格納されているカスタムユーザーデータ `CSettingsStoreSP` 。 このデータは、オブジェクトのコンストラクターで指定し `CSettingsStoreSP` ます。|
|`m_pRegistry`|`CSettingsStore`メソッドによって作成される派生オブジェクト `Create` 。|

## <a name="remarks"></a>解説

クラスを使用し `CSettingsStoreSP` て、すべての MFC レジストリ操作を、XML ファイルやデータベースなどの他の場所にリダイレクトできます。 その手順は次のとおりです。

1. クラス (など) を作成 `CMyStore` し、から派生させ `CSettingsStore` ます。

1. [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate)を使用し、カスタムクラスでマクロを[IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)して、動的な `CSettingsStore` 作成を有効にします。

1. 仮想関数をオーバーライドし、 `Read` `Write` カスタムクラスでおよび関数を実装します。 その他の機能を実装して、目的の場所にデータを読み書きします。

1. アプリケーションで、を呼び出し、 `CSettingsStoreSP::SetRuntimeClass` クラスから取得した [CRuntimeClass 構造体](../../mfc/reference/cruntimeclass-structure.md) へのポインターを渡します。

通常、フレームワークはレジストリにアクセスするたびに、カスタムクラスを動的にインスタンス化し、それを使用してデータの読み取りまたは書き込みを行います。

`CSettingsStoreSP::SetRuntimeClass` グローバルな静的変数を使用します。 そのため、一度に使用できるカスタムストアは1つだけです。

## <a name="requirements"></a>要件

**ヘッダー:** afxsettingsstore

## <a name="csettingsstorespcreate"></a><a name="create"></a> CSettingsStoreSP:: Create

[Csettingsstore クラス](../../mfc/reference/csettingsstore-class.md)から派生したオブジェクトの新しいインスタンスを作成します。

```
CSettingsStore& CSettingsStoreSP Create(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>パラメーター

*bAdmin*<br/>
から `CSettingsStore` オブジェクトが管理者モードで作成されているかどうかを示すブール型パラメーターです。

*bReadOnly*<br/>
から `CSettingsStore` オブジェクトを読み取り専用アクセス用に作成するかどうかを決定するブール型パラメーターです。

### <a name="return-value"></a>戻り値

新しく作成されたオブジェクトへの参照 `CSettingsStore` 。

### <a name="remarks"></a>解説

[Csettingsstoresp:: SetRuntimeClass](#setruntimeclass)メソッドを使用して、作成するオブジェクトの型を決定でき `CSettingsStoreSP::Create` ます。 既定では、このメソッドはオブジェクトを作成し `CSettingsStore` ます。

`CSettingsStore`管理者モードでオブジェクトを作成した場合、すべてのレジストリアクセスの既定の場所は HKEY_LOCAL_MACHINE です。 それ以外の場合、すべてのレジストリアクセスの既定の場所は HKEY_CURRENT_USER です。

*Badmin* が TRUE の場合、アプリケーションは管理権限を持っている必要があります。 それ以外の場合は、レジストリにアクセスしようとすると失敗します。

### <a name="example"></a>例

クラスのメソッドを使用する方法を次の例に示し `Create` `CSettingsStoreSP` ます。

[!code-cpp[NVC_MFC_RibbonApp#33](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]

## <a name="csettingsstorespcsettingsstoresp"></a><a name="csettingsstoresp"></a> CSettingsStoreSP:: CSettingsStoreSP

[Csettingsstoresp クラス](../../mfc/reference/csettingsstoresp-class.md)オブジェクトを構築します。

```
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```

### <a name="parameters"></a>パラメーター

*dwUserData*<br/>
からオブジェクトに格納されているユーザー定義データ `CSettingsStoreSP` 。

### <a name="remarks"></a>解説

オブジェクトは、 `CSettingsStoreSP` *dwuserdata* のデータをプロテクトメンバー変数に格納し `m_dwUserData` ます。

## <a name="csettingsstorespsetruntimeclass"></a><a name="setruntimeclass"></a> CSettingsStoreSP:: SetRuntimeClass

ランタイムクラスを設定します。 [Csettingsstoresp:: create](#create)メソッドは、ランタイムクラスを使用して、作成するオブジェクトの型を決定します。

```
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```

### <a name="parameters"></a>パラメーター

*pRTI*<br/>
から [Csettingsstore クラス](../../mfc/reference/csettingsstore-class.md)から派生したクラスのランタイムクラス情報へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE。 *PRTI* によって識別されるクラスがから派生していない場合は FALSE `CSettingsStore` 。

### <a name="remarks"></a>解説

[Csettingsstoresp クラス](../../mfc/reference/csettingsstoresp-class.md)を使用して、からクラスを派生させることができ `CSettingsStore` ます。 `SetRuntimeClass`から派生したカスタムクラスのオブジェクトを作成する場合は、メソッドを使用し `CSettingsStore` ます。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CSettingsStore クラス](../../mfc/reference/csettingsstore-class.md)
