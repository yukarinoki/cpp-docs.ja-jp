---
description: '詳細情報: IGetDataSourceImpl クラス'
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
ms.openlocfilehash: 24cf83b7eb799882f1c7da42854899bcf46fddf2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287269"
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

## <a name="requirements"></a>要件

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

*OLE DB プログラマーリファレンス* の「 [igetdatasource:: getdatasource](/previous-versions/windows/desktop/ms725443(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>解説

データソースオブジェクトのプロパティにアクセスする必要がある場合に便利です。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
