---
title: IRowsetCreatorImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IRowsetCreatorImpl
- ATL.IRowsetCreatorImpl
- ATL::IRowsetCreatorImpl<T>
- ATL.IRowsetCreatorImpl<T>
- IRowsetCreatorImpl
- IRowsetCreatorImpl.SetSite
- IRowsetCreatorImpl<T>::SetSite
- IRowsetCreatorImpl::SetSite
- SetSite
- ATL.IRowsetCreatorImpl.SetSite
- ATL::IRowsetCreatorImpl<T>::SetSite
- ATL::IRowsetCreatorImpl::SetSite
- ATL.IRowsetCreatorImpl<T>.SetSite
dev_langs:
- C++
helpviewer_keywords:
- IRowsetCreatorImpl class
- SetSite method
ms.assetid: 92cc950f-7978-4754-8d9a-defa63867d82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 51534ffb027e35bbab5a9473cf4190c14b384808
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118146"
---
# <a name="irowsetcreatorimpl-class"></a>IRowsetCreatorImpl クラス

同じ機能を実行します。 `IObjectWithSite` OLE DB プロパティができますが、`DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS`します。  
  
## <a name="syntax"></a>構文

```cpp
template < class T >  
class ATL_NO_VTABLE IRowsetCreatorImpl   
   : public IObjectWithSiteImpl< T >  
```  
  
### <a name="parameters"></a>パラメーター  

*T*<br/>
派生したクラス`IRowsetCreator`します。  

## <a name="requirements"></a>要件  

**ヘッダー:** atldb.h  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[SetSite](#setsite)|行セット オブジェクトを含むサイトを設定します。|  
  
## <a name="remarks"></a>Remarks  

このクラスから継承[IObjectWithSite](/windows/desktop/api/ocidl/nn-ocidl-iobjectwithsite)と上書き[IObjectWithSite::SetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-setsite)します。 プロバイダー コマンドまたはセッション オブジェクトは、行セットを作成するときに呼び出す`QueryInterface`、行セット オブジェクトを探して`IObjectWithSite`と呼び出し`SetSite`、行セット オブジェクトの引き渡し`IUnkown`サイト インターフェイスとしてインターフェイス。  

## <a name="setsite"></a> Irowsetcreatorimpl::setsite

行セット オブジェクトを含むサイトを設定します。 詳細については、次を参照してください。 [IObjectWithSite::SetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-setsite)します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD(SetSite )(IUnknown* pCreator);  
```  
  
#### <a name="parameters"></a>パラメーター  

*pCreator*<br/>
[in]ポインター、`IUnknown`行セット オブジェクトを管理するサイトのインターフェイス ポインター。  
  
### <a name="return-value"></a>戻り値  

標準の HRESULT です。  
  
### <a name="remarks"></a>Remarks  

さらに、`IRowsetCreatorImpl::SetSite`により、OLE DB`DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS`プロパティ。 

## <a name="see-also"></a>関連項目  

[OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)