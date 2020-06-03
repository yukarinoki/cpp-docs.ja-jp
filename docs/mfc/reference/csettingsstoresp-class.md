---
title: クラス
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
ms.openlocfilehash: 9e22184a4081762a3d505645752e514315146981
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318450"
---
# <a name="csettingsstoresp-class"></a>クラス

クラス`CSettingsStoreSP`は[、CSettingsStore](../../mfc/reference/csettingsstore-class.md)クラスのインスタンスを作成するために使用できるヘルパー クラスです。

## <a name="syntax"></a>構文

```
class CSettingsStoreSP
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[サービスの数を確認します。](#csettingsstoresp)|`CSettingsStoreSP` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ストアSP::作成](#create)|から`CSettingsStore`派生したクラスのインスタンスを作成します。|
|[を設定します。](#setruntimeclass)|ランタイム クラスを設定します。 この`Create`メソッドは、ランタイム クラスを使用して、作成するオブジェクトのクラスを決定します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|`m_dwUserData`|`CSettingsStoreSP`オブジェクトに格納されているカスタム ユーザー データ。 このデータは、オブジェクトのコンストラクターで`CSettingsStoreSP`指定します。|
|`m_pRegistry`|メソッド`CSettingsStore`が作成する`Create`派生オブジェクト。|

## <a name="remarks"></a>解説

このクラスを`CSettingsStoreSP`使用すると、すべての MFC レジストリ操作を XML ファイルやデータベースなどの他の場所にリダイレクトできます。 そのためには、次の手順に従います。

1. などの`CMyStore`クラスを作成し、 から`CSettingsStore`派生させます。

1. 動的な作成を可能にするには[、カスタム](run-time-object-model-services.md#declare_dyncreate)`CSettingsStore`クラスでDECLARE_DYNCREATEと[IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)マクロを使用します。

1. 仮想関数をオーバーライドし、カスタム`Read``Write`クラスに と 関数を実装します。 必要な場所にデータを読み書きするその他の機能を実装します。

1. アプリケーションで、クラスから`CSettingsStoreSP::SetRuntimeClass`取得した[CRuntimeClass 構造体](../../mfc/reference/cruntimeclass-structure.md)へのポインターを呼び出して渡します。

フレームワークは通常、レジストリにアクセスする場合は常に、カスタム クラスを動的にインスタンス化し、データの読み取りまたは書き込みに使用します。

`CSettingsStoreSP::SetRuntimeClass`は、グローバル静的変数を使用します。 したがって、一度に使用できるカスタム ストアは 1 つだけです。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxsettingsstore.h

## <a name="csettingsstorespcreate"></a><a name="create"></a>ストアSP::作成

[から](../../mfc/reference/csettingsstore-class.md)派生したオブジェクトの新しいインスタンスを作成します。

```
CSettingsStore& CSettingsStoreSP Create(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>パラメーター

*b管理者*<br/>
[in]オブジェクトが管理者モードで作成される`CSettingsStore`かどうかを決定するブール値パラメーター。

*読み取り専用*<br/>
[in]読み取り専用アクセス用`CSettingsStore`にオブジェクトを作成するかどうかを決定するブール値パラメーター。

### <a name="return-value"></a>戻り値

新しく作成`CSettingsStore`されたオブジェクトへの参照。

### <a name="remarks"></a>解説

メソッド[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)を使用して、作成するオブジェクト`CSettingsStoreSP::Create`の種類を決定できます。 既定では、このメソッドはオブジェクト`CSettingsStore`を作成します。

管理者モードでオブジェクト`CSettingsStore`を作成した場合、すべてのレジストリ アクセスの既定の場所はHKEY_LOCAL_MACHINE。 それ以外の場合、すべてのレジストリ アクセスの既定の場所はHKEY_CURRENT_USER。

*bAdmin*が TRUE の場合、アプリケーションは管理権限を持っている必要があります。 それ以外の場合は、レジストリにアクセスしようとすると失敗します。

### <a name="example"></a>例

クラスのメソッドの使用方法を`Create`次の例に示します`CSettingsStoreSP`。

[!code-cpp[NVC_MFC_RibbonApp#33](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]

## <a name="csettingsstorespcsettingsstoresp"></a><a name="csettingsstoresp"></a>サービスの数を確認します。

[クラス](../../mfc/reference/csettingsstoresp-class.md)オブジェクトを構築します。

```
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```

### <a name="parameters"></a>パラメーター

*データ*<br/>
[in]オブジェクトが格納する`CSettingsStoreSP`ユーザー定義データ。

### <a name="remarks"></a>解説

オブジェクト`CSettingsStoreSP`は *、dwUserData*のデータをプロテクト メンバー`m_dwUserData`変数 に格納します。

## <a name="csettingsstorespsetruntimeclass"></a><a name="setruntimeclass"></a>を設定します。

ランタイム クラスを設定します。 メソッド[CSettingsStoreSP::Create](#create)は、ランタイム クラスを使用して、作成するオブジェクトの種類を決定します。

```
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```

### <a name="parameters"></a>パラメーター

*pRTI*<br/>
[in][CSettingsStore](../../mfc/reference/csettingsstore-class.md)クラスから派生したクラスのランタイム クラス情報へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE。*pRTI*で識別されるクラスが から`CSettingsStore`派生していない場合は FALSE。

### <a name="remarks"></a>解説

からクラスを派生するには[、CSettingsStoreSP クラス](../../mfc/reference/csettingsstoresp-class.md)を`CSettingsStore`使用できます。 から`CSettingsStore`派生した`SetRuntimeClass`カスタム クラスのオブジェクトを作成する場合は、このメソッドを使用します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CSettingsStore クラス](../../mfc/reference/csettingsstore-class.md)
