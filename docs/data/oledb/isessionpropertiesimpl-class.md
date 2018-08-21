---
title: ISessionPropertiesImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ISessionPropertiesImpl
- ISessionPropertiesImpl::GetProperties
- ISessionPropertiesImpl.GetProperties
- GetProperties
- ISessionPropertiesImpl.SetProperties
- SetProperties
- ISessionPropertiesImpl::SetProperties
dev_langs:
- C++
helpviewer_keywords:
- ISessionPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5da668814888c11c5aaa0734be5ebc39b943778e
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337256"
---
# <a name="isessionpropertiesimpl-class"></a>ISessionPropertiesImpl クラス
実装を提供、 [ISessionProperties](https://msdn.microsoft.com/library/ms713721.aspx)インターフェイス。  
  
## <a name="syntax"></a>構文

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ISessionPropertiesImpl :  
   public ISessionProperties,    
   public CUtlProps<PropClass>  
```  
  
### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス、`ISessionPropertiesImpl`します。  
  
 *PropClass*  
 その既定値はユーザー定義プロパティ クラス*T*します。  

## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="members"></a>メンバー  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[GetProperties](#getproperties)|セッションで現在設定されているセッション プロパティ グループ内のプロパティの一覧を返します。|  
|[SetProperties](#setproperties)|セッション プロパティ グループのプロパティを設定します。|  
  
## <a name="remarks"></a>Remarks  
 セッションの必須インターフェイス。 このクラスでは、セッションのプロパティを実装によって定義された静的関数を呼び出すことによって、[プロパティ セットのマップ](../../data/oledb/begin-propset-map.md)します。 セッション クラスでは、プロパティ セットのマップを指定する必要があります。  
  
## <a name="getproperties"></a> Isessionpropertiesimpl::getproperties
プロパティの一覧を返します、`DBPROPSET_SESSION`セッションで現在設定されているプロパティ グループ。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD(GetProperties)(ULONG cPropertyIDSets,   
   const DBPROPIDSET rgPropertyIDSets[],   
   ULONG * pcPropertySets,   
   DBPROPSET ** prgPropertySets);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[ISessionProperties::GetProperties](https://msdn.microsoft.com/library/ms723643.aspx)で、 *OLE DB プログラマーズ リファレンス*します。 

## <a name="setproperties"></a> Isessionpropertiesimpl::setproperties
プロパティを設定、`DBPROPSET_SESSION`プロパティ グループ。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[ISessionProperties::SetProperties](https://msdn.microsoft.com/library/ms714405.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)