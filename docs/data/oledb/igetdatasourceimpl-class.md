---
title: IGetDataSourceImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IGetDataSourceImpl
- ATL.IGetDataSourceImpl<T>
- ATL.IGetDataSourceImpl
- ATL::IGetDataSourceImpl
- ATL::IGetDataSourceImpl<T>
- GetDataSource
- IGetDataSourceImpl.GetDataSource
- IGetDataSourceImpl::GetDataSource
helpviewer_keywords:
- IGetDataSourceImpl class
- GetDataSource method
ms.assetid: d63f3178-d663-4f01-8c09-8aab2dd6805a
ms.openlocfilehash: 4c8af66f41724c5a99dfe271a7dd8babc3a993a5
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843964"
---
# <a name="igetdatasourceimpl-class"></a>IGetDataSourceImpl クラス

[Igetdatasource](/previous-versions/windows/desktop/ms709721(v=vs.85))オブジェクトの実装を提供します。

## <a name="syntax"></a>構文

```cpp
template <class T>
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource
```

### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IGetDataSourceImpl` 。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="interface-methods"></a>インターフェイス メソッド

| 名前 | 説明 |
|-|-|
|[GetDataSource](#getdatasource)|セッションを作成したデータソースオブジェクトのインターフェイスポインターを返します。|

## <a name="remarks"></a>解説

これは、データソースオブジェクトへのインターフェイスポインターを取得するための、セッションでの必須のインターフェイスです。

## <a name="igetdatasourceimplgetdatasource"></a><a name="getdatasource"></a> IGetDataSourceImpl:: GetDataSource

セッションを作成したデータソースオブジェクトのインターフェイスポインターを返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(GetDataSource)(REFIID riid,
   IUnknown ** ppDataSource);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [igetdatasource:: getdatasource](/previous-versions/windows/desktop/ms725443(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>解説

データソースオブジェクトのプロパティにアクセスする必要がある場合に便利です。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
