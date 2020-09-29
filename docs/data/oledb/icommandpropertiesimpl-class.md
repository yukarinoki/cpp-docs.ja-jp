---
title: ICommandPropertiesImpl クラス
ms.date: 11/04/2016
f1_keywords:
- ICommandPropertiesImpl
- ATL.ICommandPropertiesImpl
- ATL::ICommandPropertiesImpl
- ICommandPropertiesImpl::GetProperties
- ICommandPropertiesImpl.GetProperties
- ICommandPropertiesImpl.SetProperties
- ICommandPropertiesImpl::SetProperties
helpviewer_keywords:
- ICommandPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
ms.openlocfilehash: bd4dd73c79085a2c2d85a5dbacbfd20bc920108e
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91501761"
---
# <a name="icommandpropertiesimpl-class"></a>ICommandPropertiesImpl クラス

[ICommandProperties](/previous-versions/windows/desktop/ms723044(v=vs.85))インターフェイスの実装を提供します。

## <a name="syntax"></a>構文

```cpp
template <class T, class PropClass = T>
class ATL_NO_VTABLE ICommandPropertiesImpl
   : public ICommandProperties, public CUtlProps<PropClass>
```

### <a name="parameters"></a>パラメーター

*T*<br/>
クラス (から派生)

*PropClass*<br/>
プロパティクラス。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="interface-methods"></a>インターフェイス メソッド

| 名前 | 説明 |
|-|-|
|[GetProperties](#getproperties)|行セットに現在要求されている、行セットプロパティグループ内のプロパティの一覧を返します。|
|[SetProperties](#setproperties)|行セットプロパティグループのプロパティを設定します。|

## <a name="remarks"></a>注釈

これは、コマンドでは必須です。 実装は、 [BEGIN_PROPSET_MAP](./macros-for-ole-db-provider-templates.md#begin_propset_map) マクロによって定義される静的関数によって提供されます。

## <a name="icommandpropertiesimplgetproperties"></a><a name="getproperties"></a> ICommandPropertiesImpl:: GetProperties

コマンドのプロパティマップを使用して、要求されたすべてのプロパティセットを返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(GetProperties)(const ULONG cPropertyIDSets,
   const DBPROPIDSET rgPropertyIDSets[],
   ULONG * pcPropertySets,
   DBPROPSET ** prgPropertySets);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [ICommandProperties:: GetProperties](/previous-versions/windows/desktop/ms723119(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>注釈

「 [BEGIN_PROPSET_MAP](./macros-for-ole-db-provider-templates.md#begin_propset_map)」を参照してください。

## <a name="icommandpropertiesimplsetproperties"></a><a name="setproperties"></a> ICommandPropertiesImpl:: SetProperties

Command オブジェクトのプロパティを設定します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [ICommandProperties:: SetProperties](/previous-versions/windows/desktop/ms711497(v=vs.85)) 」を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
