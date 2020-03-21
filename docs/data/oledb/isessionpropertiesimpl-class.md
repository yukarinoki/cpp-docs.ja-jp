---
title: ISessionPropertiesImpl クラス
ms.date: 11/04/2016
f1_keywords:
- ISessionPropertiesImpl
- ISessionPropertiesImpl::GetProperties
- ISessionPropertiesImpl.GetProperties
- ISessionPropertiesImpl.SetProperties
- ISessionPropertiesImpl::SetProperties
helpviewer_keywords:
- ISessionPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
ms.openlocfilehash: c1a3539ea4ea705ad8bd1e40acda965ef66e2051
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077712"
---
# <a name="isessionpropertiesimpl-class"></a>ISessionPropertiesImpl クラス

[Isessionproperties](/previous-versions/windows/desktop/ms713721(v=vs.85))インターフェイスの実装を提供します。

## <a name="syntax"></a>構文

```cpp
template <class T, class PropClass = T>
class ATL_NO_VTABLE ISessionPropertiesImpl :
   public ISessionProperties,
   public CUtlProps<PropClass>
```

### <a name="parameters"></a>パラメーター

*T*<br/>
`ISessionPropertiesImpl`から派生したクラス。

*PropClass*<br/>
既定で*T*に設定されているユーザー定義可能なプロパティクラス。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="interface-methods"></a>インターフェイス メソッド

|||
|-|-|
|[GetProperties](#getproperties)|セッションで現在設定されているセッションプロパティグループのプロパティの一覧を返します。|
|[SetProperties](#setproperties)|セッションプロパティグループのプロパティを設定します。|

## <a name="remarks"></a>解説

セッションの必須のインターフェイスです。 このクラスは、[プロパティセットマップ](../../data/oledb/begin-propset-map.md)によって定義された静的関数を呼び出すことによって、セッションプロパティを実装します。 プロパティセットマップは、セッションクラスで指定する必要があります。

## <a name="isessionpropertiesimplgetproperties"></a><a name="getproperties"></a>ISessionPropertiesImpl:: GetProperties

セッションで現在設定されている `DBPROPSET_SESSION` プロパティグループ内のプロパティの一覧を返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(GetProperties)(ULONG cPropertyIDSets,
   const DBPROPIDSET rgPropertyIDSets[],
   ULONG * pcPropertySets,
   DBPROPSET ** prgPropertySets);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の[Isessionproperties:: GetProperties](/previous-versions/windows/desktop/ms723643(v=vs.85))を参照してください。

## <a name="isessionpropertiesimplsetproperties"></a><a name="setproperties"></a>ISessionPropertiesImpl:: SetProperties

`DBPROPSET_SESSION` プロパティグループのプロパティを設定します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の[Isessionproperties:: SetProperties](/previous-versions/windows/desktop/ms714405(v=vs.85))を参照してください。

## <a name="see-also"></a>参照

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)