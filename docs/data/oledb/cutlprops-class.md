---
description: '詳細情報: CUtlProps クラス'
title: CUtlProps クラス
ms.date: 11/04/2016
f1_keywords:
- CUtlProps
- CUtlProps::GetPropValue
- CUtlProps.GetPropValue
- GetPropValue
- CUtlProps::IsValidValue
- CUtlProps.IsValidValue
- IsValidValue
- OnPropertyChanged
- CUtlProps.OnPropertyChanged
- CUtlProps::OnPropertyChanged
- SetPropValue
- ATL::CUtlProps<T>::SetPropValue
- ATL.CUtlProps<T>.SetPropValue
- ATL.CUtlProps.SetPropValue
- CUtlProps::SetPropValue
- CUtlProps<T>::SetPropValue
- CUtlProps.SetPropValue
- CUtlProps<T>.SetPropValue
- ATL::CUtlProps::SetPropValue
helpviewer_keywords:
- CUtlProps class
- GetPropValue method
- IsValidValue method
- OnInterfaceRequested method
- OnPropertyChanged method
- SetPropValue method
ms.assetid: bb525178-765c-4e23-a110-c0fd70c05437
ms.openlocfilehash: 535da4b2dd7d3214633a1e76c04be1e4627b965a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287750"
---
# <a name="cutlprops-class"></a>CUtlProps クラス

さまざまな OLE DB プロパティインターフェイス (、、など) のプロパティを `IDBProperties` 実装 `IDBProperties` `IRowsetInfo` します。

## <a name="syntax"></a>構文

```cpp
template < class T >
class ATL_NO_VTABLE CUtlProps : public CUtlPropsBase
```

### <a name="parameters"></a>パラメーター

*T*<br/>
を格納しているクラス `BEGIN_PROPSET_MAP` 。

## <a name="requirements"></a>要件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|-|-|
|[GetPropValue](#getpropvalue)|プロパティセットからプロパティを取得します。|
|[IsValidValue](#isvalidvalue)|プロパティを設定する前に値を検証するために使用されます。|
|[OnInterfaceRequested](#oninterfacerequested)|コンシューマーがオブジェクト作成インターフェイスでメソッドを呼び出すときに、省略可能なインターフェイスの要求を処理します。|
|[OnPropertyChanged](#onpropertychanged)|プロパティを設定した後に、チェーンプロパティを処理するために呼び出されます。|
|[SetPropValue](#setpropvalue)|プロパティセット内のプロパティを設定します。|

## <a name="remarks"></a>解説

このクラスのほとんどは実装の詳細です。

`CUtlProps` 内部的にプロパティを設定するための2つのメンバー ( [getpropvalue](#getpropvalue) と [setpropvalue](#setpropvalue)) が含まれています。

プロパティセットマップで使用されるマクロの詳細については、「 [BEGIN_PROPSET_MAP](./macros-for-ole-db-provider-templates.md#begin_propset_map) 」および「 [END_PROPSET_MAP](./macros-for-ole-db-provider-templates.md#end_propset_map)」を参照してください。

## <a name="cutlpropsgetpropvalue"></a><a name="getpropvalue"></a> CUtlProps:: GetPropValue

プロパティセットからプロパティを取得します。

### <a name="syntax"></a>構文

```cpp
OUT_OF_LINE HRESULT GetPropValue(const GUID* pguidPropSet,
   DBPROPID dwPropId,
   VARIANT* pvValue);
```

#### <a name="parameters"></a>パラメーター

*pguidPropSet*<br/>
からPropSet の GUID。

*dwPropId*<br/>
からプロパティインデックス。

*pvValue*<br/>
入出力新しいプロパティ値を格納している variant へのポインター。

### <a name="return-value"></a>戻り値

`Failure` 失敗した場合は、成功した場合は S_OK。

## <a name="cutlpropsisvalidvalue"></a><a name="isvalidvalue"></a> CUtlProps:: IsValidValue

プロパティを設定する前に値を検証するために使用されます。

### <a name="syntax"></a>構文

```cpp
virtual HRESULT CUtlPropsBase::IsValidValue(ULONG /* iCurSet */,
   DBPROP* pDBProp);
```

#### <a name="parameters"></a>パラメーター

*iCurSet*<br/>
プロパティセット配列へのインデックス。プロパティセットが1つしかない場合は0。

*pDBProp*<br/>
[DBPROP](/previous-versions/windows/desktop/ms717970(v=vs.85))構造体のプロパティ ID と新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT です。 既定の戻り値は S_OK です。

### <a name="remarks"></a>解説

プロパティの設定に使用しようとしている値に対して実行する検証ルーチンがある場合は、この関数をオーバーライドする必要があります。 たとえば、パスワードテーブルに対して DBPROP_AUTH_PASSWORD を検証して、有効な値を判断することができます。

## <a name="cutlpropsoninterfacerequested"></a><a name="oninterfacerequested"></a> CUtlProps:: OnInterfaceRequested

コンシューマーがオブジェクト作成インターフェイスの1つでメソッドを呼び出したときに、オプションのインターフェイスの要求を処理します。

### <a name="syntax"></a>構文

```cpp
virtual HRESULT CUtlPropsBase::OnInterfaceRequested(REFIID riid);
```

#### <a name="parameters"></a>パラメーター

*riid*<br/>
から要求されたインターフェイスの IID。 詳細については、  `ICommand::Execute` *OLE DB プログラマーのリファレンス*( *MDAC SDK*) にある、の riid パラメーターの説明を参照してください。

### <a name="remarks"></a>解説

`OnInterfaceRequested` コンシューマーがオブジェクト作成インターフェイス (、、、など) のいずれかでメソッドを呼び出したときに、オプションのインターフェイスのコンシューマー要求を処理 `IDBCreateSession` `IDBCreateCommand` `IOpenRowset` `ICommand` します。 これは、要求されたインターフェイスに対応する OLE DB プロパティを設定します。 たとえば、コンシューマーから要求された場合、は `IID_IRowsetLocate` `OnInterfaceRequested` インターフェイスを設定し `DBPROP_IRowsetLocate` ます。 これにより、行セットの作成時に適切な状態が維持されます。

このメソッドは、コンシューマーがまたはを呼び出したときに呼び出され `IOpenRowset::OpenRowset` `ICommand::Execute` ます。

コンシューマーがオブジェクトを開き、オプションのインターフェイスを要求する場合、プロバイダーはそのインターフェイスに関連付けられたプロパティを VARIANT_TRUE に設定する必要があります。 プロパティ固有の処理を許可するに `OnInterfaceRequested` は、プロバイダーのメソッドが呼び出される前に、が呼び出され `Execute` ます。 既定では、は `OnInterfaceRequested` 次のインターフェイスを処理します。

- `IRowsetLocate`

- `IRowsetChange`

- `IRowsetUpdate`

- `IConnectionPointContainer`

- `IRowsetScroll`

他のインターフェイスを処理する場合は、関数を処理するために、データソース、セッション、コマンド、または行セットクラスでこの関数をオーバーライドします。 このオーバーライドでは、通常の set/get プロパティインターフェイスを使用して、設定プロパティにチェーンプロパティも設定されていることを確認する必要があります (「 [OnPropertyChanged](#onpropertychanged)」を参照してください)。

## <a name="cutlpropsonpropertychanged"></a><a name="onpropertychanged"></a> CUtlProps:: OnPropertyChanged

プロパティを設定した後に、チェーンプロパティを処理するために呼び出されます。

### <a name="syntax"></a>構文

```cpp
virtual HRESULT OnPropertyChanged(ULONG /* iCurSet */,
   DBPROP* pDBProp);
```

#### <a name="parameters"></a>パラメーター

*iCurSet*<br/>
プロパティセット配列へのインデックス。プロパティセットが1つしかない場合は0。

*pDBProp*<br/>
[DBPROP](/previous-versions/windows/desktop/ms717970(v=vs.85))構造体のプロパティ ID と新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT です。 既定の戻り値は S_OK です。

### <a name="remarks"></a>解説

値が別のプロパティの値に依存するブックマークや更新などの連結されたプロパティを処理する場合は、この関数をオーバーライドする必要があります。

### <a name="example"></a>例

この関数では、ユーザーはパラメーターからプロパティ ID を取得し `DBPROP*` ます。 これで、ID をプロパティとチェーンに比較することができます。 プロパティが見つかった場合 `SetProperties` は、他のプロパティと共に設定されるプロパティを使用してが呼び出されます。 この場合、1つが、、のいずれかのプロパティを取得すると、 `DBPROP_IRowsetLocate` `DBPROP_LITERALBOOKMARKS` プロパティを `DBPROP_ORDEREDBOOKMARKS` 設定でき `DBPROP_BOOKMARKS` ます。

[!code-cpp[NVC_OLEDB_Provider#2](../../data/oledb/codesnippet/cpp/cutlprops-onpropertychanged_1.h)]

## <a name="cutlpropssetpropvalue"></a><a name="setpropvalue"></a> CUtlProps:: SetPropValue

プロパティセット内のプロパティを設定します。

### <a name="syntax"></a>構文

```cpp
HRESULT SetPropValue(const GUID* pguidPropSet,
   DBPROPID dwPropId,
   VARIANT* pvValue);
```

#### <a name="parameters"></a>パラメーター

*pguidPropSet*<br/>
からPropSet の GUID。

*dwPropId*<br/>
からプロパティインデックス。

*pvValue*<br/>
から新しいプロパティ値を格納している variant へのポインター。

### <a name="return-value"></a>戻り値

`Failure` 失敗した場合は、成功した場合は S_OK。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
