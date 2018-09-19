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
ms.openlocfilehash: 9ecc830937e36e213177205549ee4dd4e989e0ed
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118701"
---
# <a name="igetdatasourceimpl-class"></a>IGetDataSourceImpl クラス

実装を提供、 [IGetDataSource](/previous-versions/windows/desktop/ms709721\(v=vs.85\))オブジェクト。  
  
## <a name="syntax"></a>構文

```cpp
template <class T>  
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource  
```  
  
### <a name="parameters"></a>パラメーター  

*T*<br/>
派生したクラス、`IGetDataSourceImpl`します。  

## <a name="requirements"></a>要件  

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

参照してください[IGetDataSource::GetDataSource](/previous-versions/windows/desktop/ms725443\(v=vs.85\))で、 *OLE DB プログラマーズ リファレンス*します。  
  
### <a name="remarks"></a>Remarks  

データ ソース オブジェクトのプロパティにアクセスする必要がある場合に役立ちます。  
  
## <a name="see-also"></a>関連項目  

[OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)