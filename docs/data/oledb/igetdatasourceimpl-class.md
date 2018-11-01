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
ms.openlocfilehash: 75b95f871023d7bfdea198a69377b1f360ab115f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637841"
---
# <a name="igetdatasourceimpl-class"></a>IGetDataSourceImpl クラス

実装を提供、 [IGetDataSource](/previous-versions/windows/desktop/ms709721)オブジェクト。

## <a name="syntax"></a>構文

```cpp
template <class T>
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource
```

### <a name="parameters"></a>パラメーター

*T*<br/>
派生したクラス、`IGetDataSourceImpl`します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="interface-methods"></a>インターフェイス メソッド

|||
|-|-|
|[GetDataSource](#getdatasource)|セッションを作成したデータ ソース オブジェクトのインターフェイス ポインターを返します。|

## <a name="remarks"></a>Remarks

これは、データ ソース オブジェクトへのインターフェイス ポインターを取得するためのセッションで、必須のインターフェイスです。

## <a name="getdatasource"></a> Igetdatasourceimpl::getdatasource

セッションを作成したデータ ソース オブジェクトのインターフェイス ポインターを返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(GetDataSource)(REFIID riid, 
   IUnknown ** ppDataSource);
```

#### <a name="parameters"></a>パラメーター

参照してください[IGetDataSource::GetDataSource](/previous-versions/windows/desktop/ms725443)で、 *OLE DB プログラマーズ リファレンス*します。

### <a name="remarks"></a>Remarks

データ ソース オブジェクトのプロパティにアクセスする必要がある場合に役立ちます。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)