---
title: IDBPropertiesImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IDBPropertiesImpl
- ATL.IDBPropertiesImpl
- ATL.IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl
- IDBPropertiesImpl::GetProperties
- IDBPropertiesImpl.GetProperties
- IDBPropertiesImpl::GetPropertyInfo
- IDBPropertiesImpl.GetPropertyInfo
- GetPropertyInfo
- IDBPropertiesImpl.SetProperties
- IDBPropertiesImpl::SetProperties
helpviewer_keywords:
- IDBPropertiesImpl class
- GetProperties method
- GetPropertyInfo method
- SetProperties method
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
ms.openlocfilehash: d94c5d121386989d223a55b8ce7626444c3f8950
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509061"
---
# <a name="idbpropertiesimpl-class"></a>IDBPropertiesImpl クラス

インターフェイスの実装を提供 `IDBProperties` します。

## <a name="syntax"></a>構文

```cpp
template <class T>
class ATL_NO_VTABLE IDBPropertiesImpl
   : public IDBProperties, public CUtlProps<T>
```

### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IDBPropertiesImpl` 。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="interface-methods"></a>インターフェイス メソッド

| 名前 | 説明 |
|-|-|
|[GetProperties](#getproperties)|現在データソースオブジェクトに設定されているデータソース、データソース情報、および初期化プロパティグループのプロパティの値、および列挙子に現在設定されている初期化プロパティグループのプロパティの値を返します。|
|[GetPropertyInfo](#getpropertyinfo)|プロバイダーでサポートされているすべてのプロパティに関する情報を返します。|
|[SetProperties](#setproperties)|データソースオブジェクト、または初期化プロパティグループの列挙子について、データソースおよび初期化プロパティグループのプロパティを設定します。|

## <a name="remarks"></a>注釈

[IDBProperties](/previous-versions/windows/desktop/ms719607(v=vs.85)) は、データソースオブジェクトの必須のインターフェイスであり、列挙子のオプションのインターフェイスです。 ただし、列挙子が [IDBInitialize](/previous-versions/windows/desktop/ms713706(v=vs.85))を公開する場合は、を公開する必要があり `IDBProperties` ます。 `IDBPropertiesImpl``IDBProperties` [BEGIN_PROPSET_MAP](./macros-for-ole-db-provider-templates.md#begin_propset_map)によって定義された静的関数を使用してを実装します。

## <a name="idbpropertiesimplgetproperties"></a><a name="getproperties"></a> IDBPropertiesImpl:: GetProperties

現在データソースオブジェクトに設定されているデータソース、データソース情報、および初期化プロパティグループのプロパティの値、および列挙子に現在設定されている初期化プロパティグループのプロパティの値を返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(GetProperties)(ULONG cPropertySets,
   const DBPROPIDSET rgPropertySets[],
   ULONG * pcProperties,
   DBPROPSET ** prgProperties);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IDBProperties:: GetProperties](/previous-versions/windows/desktop/ms714344(v=vs.85)) 」を参照してください。

一部のパラメーターは、「」で説明されている、さまざまな名前の *プログラマの参照パラメーター OLE DB* に対応してい `IDBProperties::GetProperties` ます。

|テンプレートパラメーターの OLE DB|*OLE DB プログラマーの参照* パラメーター|
|--------------------------------|------------------------------------------------|
|*cPropertySets*|*cPropertyIDSets*|
|*rgPropertySets*|*rgPropertyIDSets*|
|*pcProperties*|*pcPropertySets*|
|*prgProperties*|*prgPropertySets*|

### <a name="remarks"></a>注釈

プロバイダーが初期化されている場合、このメソッドは、データソースオブジェクトに現在設定されている DBPROPSET_DATASOURCE、DBPROPSET_DATASOURCEINFO、DBPROPSET_DBINIT プロパティグループのプロパティの値を返します。 プロバイダーが初期化されていない場合は、DBPROPSET_DBINIT グループのプロパティのみが返されます。

## <a name="idbpropertiesimplgetpropertyinfo"></a><a name="getpropertyinfo"></a> IDBPropertiesImpl:: GetPropertyInfo

データソースでサポートされているプロパティ情報を返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(GetPropertyInfo)(ULONG cPropertySets,
   const DBPROPIDSET rgPropertySets[],
   ULONG * pcPropertyInfoSets,
   DBPROPINFOSET ** prgPropertyInfoSets,
   OLECHAR ** ppDescBuffer);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IDBProperties:: GetPropertyInfo](/previous-versions/windows/desktop/ms718175(v=vs.85)) 」を参照してください。

一部のパラメーターは、「」で説明されている、さまざまな名前の *プログラマの参照パラメーター OLE DB* に対応してい `IDBProperties::GetPropertyInfo` ます。

|テンプレートパラメーターの OLE DB|*OLE DB プログラマーの参照* パラメーター|
|--------------------------------|------------------------------------------------|
|*cPropertySets*|*cPropertyIDSets*|
|*rgPropertySets*|*rgPropertyIDSets*|

### <a name="remarks"></a>注釈

では、 [IDBInitializeImpl:: m_pCUtlPropInfo](./idbinitializeimpl-class.md#pcutlpropinfo) を使用してこの機能を実装します。

## <a name="idbpropertiesimplsetproperties"></a><a name="setproperties"></a> IDBPropertiesImpl:: SetProperties

データソースオブジェクト、または初期化プロパティグループの列挙子について、データソースおよび初期化プロパティグループのプロパティを設定します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IDBProperties:: SetProperties](/previous-versions/windows/desktop/ms723049(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>注釈

プロバイダーが初期化されている場合、このメソッドは、データソースオブジェクトの DBPROPSET_DATASOURCE、DBPROPSET_DATASOURCEINFO、DBPROPSET_DBINIT プロパティグループのプロパティの値を設定します。 プロバイダーが初期化されていない場合は、DBPROPSET_DBINIT グループのプロパティのみが設定されます。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
