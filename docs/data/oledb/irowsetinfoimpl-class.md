---
title: IRowsetInfoImpl クラス
ms.date: 11/04/2016
f1_keywords:
- ATL.IRowsetInfoImpl
- IRowsetInfoImpl
- ATL::IRowsetInfoImpl
- ATL.IRowsetInfoImpl.GetProperties
- IRowsetInfoImpl.GetProperties
- ATL::IRowsetInfoImpl::GetProperties
- IRowsetInfoImpl::GetProperties
- ATL::IRowsetInfoImpl::GetReferencedRowset
- GetReferencedRowset
- ATL.IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl::GetReferencedRowset
- IRowsetInfoImpl::GetSpecification
- ATL.IRowsetInfoImpl.GetSpecification
- IRowsetInfoImpl.GetSpecification
- GetSpecification
- ATL::IRowsetInfoImpl::GetSpecification
helpviewer_keywords:
- IRowsetInfoImpl class
- GetProperties method
- GetReferencedRowset method
- GetSpecification method
ms.assetid: 9c654155-7727-464e-bd31-143e68391a47
ms.openlocfilehash: 691871bfc4a9e63167611a3228807fb12e32d1cb
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077867"
---
# <a name="irowsetinfoimpl-class"></a>IRowsetInfoImpl クラス

[IRowsetInfo](/previous-versions/windows/desktop/ms724541(v=vs.85))インターフェイスの実装を提供します。

## <a name="syntax"></a>構文

```cpp
template <class T, class PropClass = T>
class ATL_NO_VTABLE IRowsetInfoImpl :
   public IRowsetInfo,
   public CUtlProps<PropClass>
```

### <a name="parameters"></a>パラメーター

*T*<br/>
`IRowsetInfoImpl`から派生したクラス。

*PropClass*<br/>
既定で*T*に設定されているユーザー定義可能なプロパティクラス。

## <a name="requirements"></a>必要条件

**ヘッダー:** altdb .h

## <a name="members"></a>メンバー

### <a name="interface-methods"></a>インターフェイス メソッド

|||
|-|-|
|[GetProperties](#getproperties)|行セットによってサポートされているすべてのプロパティの現在の設定を返します。|
|[GetReferencedRowset](#getreferencedrowset)|ブックマークが適用される行セットへのインターフェイスポインターを返します。|
|[GetSpecification](#getspecification)|この行セットを作成したオブジェクト (コマンドまたはセッション) へのインターフェイス ポインターを返します。|

## <a name="remarks"></a>解説

行セットの必須のインターフェイスです。 このクラスは、コマンドクラスで定義された[プロパティセットマップ](../../data/oledb/begin-propset-map.md)を使用して、行セットプロパティを実装します。 行セットクラスはコマンドクラスのプロパティセットを使用しているように見えますが、コマンドまたはセッションオブジェクトによって作成された場合、その行セットには実行時プロパティの独自のコピーが用意されています。

## <a name="irowsetinfoimplgetproperties"></a><a name="getproperties"></a>IRowsetInfoImpl:: GetProperties

`DBPROPSET_ROWSET` グループ内のプロパティの現在の設定を返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (GetProperties )(const ULONG cPropertyIDSets,
   const DBPROPIDSET rgPropertyIDSets[],
   ULONG* pcPropertySets,
   DBPROPSET** prgPropertySets);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IRowsetInfo:: GetProperties](/previous-versions/windows/desktop/ms719611(v=vs.85)) 」を参照してください。

## <a name="irowsetinfoimplgetreferencedrowset"></a><a name="getreferencedrowset"></a>IRowsetInfoImpl:: GetReferencedRowset

ブックマークが適用される行セットへのインターフェイスポインターを返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (GetReferencedRowset )(DBORDINAL iOrdinal,
   REFIID riid,
   IUnknown** ppReferencedRowset);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IRowsetInfo:: GetReferencedRowset](/previous-versions/windows/desktop/ms721145(v=vs.85)) 」を参照してください。 *Iordinal*パラメーターはブックマーク列である必要があります。

## <a name="irowsetinfoimplgetspecification"></a><a name="getspecification"></a>IRowsetInfoImpl:: GetSpecification

この行セットを作成したオブジェクト (コマンドまたはセッション) へのインターフェイス ポインターを返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (GetSpecification )(REFIID riid,
   IUnknown** ppSpecification);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IRowsetInfo:: getspecification](/previous-versions/windows/desktop/ms716746(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>解説

このメソッドを[Igetdatasourceimpl](../../data/oledb/igetdatasourceimpl-class.md)と共に使用して、データソースオブジェクトからプロパティを取得します。

## <a name="see-also"></a>参照

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)