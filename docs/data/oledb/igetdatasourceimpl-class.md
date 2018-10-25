---
title: IGetDataSourceImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IGetDataSourceImpl
- ATL.IGetDataSourceImpl<T>
- ATL.IGetDataSourceImpl
- ATL::IGetDataSourceImpl
- ATL::IGetDataSourceImpl<T>
- GetDataSource
- IGetDataSourceImpl.GetDataSource
- IGetDataSourceImpl::GetDataSource
dev_langs:
- C++
helpviewer_keywords:
- IGetDataSourceImpl class
- GetDataSource method
ms.assetid: d63f3178-d663-4f01-8c09-8aab2dd6805a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7467a658ca8739ba933f266f58e756b8f7a3ba02
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055451"
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