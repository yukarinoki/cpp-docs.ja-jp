---
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
ms.openlocfilehash: bbeae4faad4d650d8dc44a61a22b1fcc63a0bc15
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79545553"
---
# <a name="cutlprops-class"></a>CUtlProps クラス

さまざまな OLE DB プロパティインターフェイス (`IDBProperties`、`IDBProperties`、`IRowsetInfo`など) のプロパティを実装します。

## <a name="syntax"></a>構文

```cpp
template < class T >
class ATL_NO_VTABLE CUtlProps : public CUtlPropsBase
```

### <a name="parameters"></a>パラメーター

*T*<br/>
`BEGIN_PROPSET_MAP`を格納しているクラス。

## <a name="requirements"></a>要件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[GetPropValue](#getpropvalue)|プロパティセットからプロパティを取得します。|
|[IsValidValue](#isvalidvalue)|プロパティを設定する前に値を検証するために使用されます。|
|[OnInterfaceRequested](#oninterfacerequested)|コンシューマーがオブジェクト作成インターフェイスでメソッドを呼び出すときに、省略可能なインターフェイスの要求を処理します。|
|[OnPropertyChanged](#onpropertychanged)|プロパティを設定した後に、チェーンプロパティを処理するために呼び出されます。|
|[SetPropValue](#setpropvalue)|プロパティセット内のプロパティを設定します。|

## <a name="remarks"></a>コメント

このクラスのほとんどは実装の詳細です。

`CUtlProps` には、内部的にプロパティを設定するための2つのメンバー ( [getpropvalue](../../data/oledb/cutlprops-getpropvalue.md)と[setpropvalue](../../data/oledb/cutlprops-setpropvalue.md)) が含まれています。

プロパティセットマップで使用されるマクロの詳細については、「 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) 」および「 [END_PROPSET_MAP](../../data/oledb/end-propset-map.md)」を参照してください。

## <a name="cutlpropsgetpropvalue"></a><a name="getpropvalue"></a>CUtlProps:: GetPropValue

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

失敗した場合は `Failure` し、成功した場合は S_OK します。

## <a name="cutlpropsisvalidvalue"></a><a name="isvalidvalue"></a>CUtlProps:: IsValidValue

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

### <a name="remarks"></a>コメント

プロパティの設定に使用しようとしている値に対して実行する検証ルーチンがある場合は、この関数をオーバーライドする必要があります。 たとえば、パスワードテーブルに対して DBPROP_AUTH_PASSWORD を検証して、有効な値を判断することができます。

## <a name="cutlpropsoninterfacerequested"></a><a name="oninterfacerequested"></a>CUtlProps:: OnInterfaceRequested

コンシューマーがオブジェクト作成インターフェイスの1つでメソッドを呼び出したときに、オプションのインターフェイスの要求を処理します。

### <a name="syntax"></a>構文

```cpp
virtual HRESULT CUtlPropsBase::OnInterfaceRequested(REFIID riid);
```

#### <a name="parameters"></a>パラメーター

*riid*<br/>
から要求されたインターフェイスの IID。 詳細については、 *OLE DB プログラマーのリファレンス*( *MDAC SDK*) に含まれる `ICommand::Execute` の*riid*パラメーターの説明を参照してください。

### <a name="remarks"></a>コメント

コンシューマーがオブジェクト作成インターフェイス (`IDBCreateSession`、`IDBCreateCommand`、`IOpenRowset`、`ICommand`など) のいずれかでメソッドを呼び出した場合、`OnInterfaceRequested` は省略可能なインターフェイスのコンシューマー要求を処理します。 これは、要求されたインターフェイスに対応する OLE DB プロパティを設定します。 たとえば、コンシューマーが `IID_IRowsetLocate`を要求した場合、`OnInterfaceRequested` `DBPROP_IRowsetLocate` インターフェイスを設定します。 これにより、行セットの作成時に適切な状態が維持されます。

コンシューマーが `IOpenRowset::OpenRowset` または `ICommand::Execute`を呼び出すと、このメソッドが呼び出されます。

コンシューマーがオブジェクトを開き、オプションのインターフェイスを要求する場合、プロバイダーはそのインターフェイスに関連付けられたプロパティを VARIANT_TRUE に設定する必要があります。 プロパティ固有の処理を許可するには、プロバイダーの `Execute` メソッドが呼び出される前に `OnInterfaceRequested` が呼び出されます。 既定では、`OnInterfaceRequested` は次のインターフェイスを処理します。

- `IRowsetLocate`

- `IRowsetChange`

- `IRowsetUpdate`

- `IConnectionPointContainer`

- `IRowsetScroll`

他のインターフェイスを処理する場合は、関数を処理するために、データソース、セッション、コマンド、または行セットクラスでこの関数をオーバーライドします。 このオーバーライドでは、通常の set/get プロパティインターフェイスを使用して、設定プロパティにチェーンプロパティも設定されていることを確認する必要があります (「 [OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)」を参照してください)。

## <a name="cutlpropsonpropertychanged"></a><a name="onpropertychanged"></a>CUtlProps:: OnPropertyChanged

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

### <a name="remarks"></a>コメント

値が別のプロパティの値に依存するブックマークや更新などの連結されたプロパティを処理する場合は、この関数をオーバーライドする必要があります。

### <a name="example"></a>例

この関数では、ユーザーは `DBPROP*` パラメーターからプロパティ ID を取得します。 これで、ID をプロパティとチェーンに比較することができます。 プロパティが見つかった場合は、他のプロパティと共に設定されるプロパティを使用して `SetProperties` が呼び出されます。 この場合、1つが `DBPROP_IRowsetLocate`、`DBPROP_LITERALBOOKMARKS`、または `DBPROP_ORDEREDBOOKMARKS` プロパティを取得すると、`DBPROP_BOOKMARKS` プロパティを設定できます。

[!code-cpp[NVC_OLEDB_Provider#2](../../data/oledb/codesnippet/cpp/cutlprops-onpropertychanged_1.h)]

## <a name="cutlpropssetpropvalue"></a><a name="setpropvalue"></a>CUtlProps:: SetPropValue

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

失敗した場合は `Failure` し、成功した場合は S_OK します。

## <a name="see-also"></a>参照

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)