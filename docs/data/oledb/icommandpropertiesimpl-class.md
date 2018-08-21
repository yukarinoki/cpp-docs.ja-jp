---
title: ICommandPropertiesImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandPropertiesImpl
- ATL.ICommandPropertiesImpl
- ATL::ICommandPropertiesImpl
- ICommandPropertiesImpl::GetProperties
- ICommandPropertiesImpl.GetProperties
- GetProperties
- ICommandPropertiesImpl.SetProperties
- ICommandPropertiesImpl::SetProperties
- SetProperties
dev_langs:
- C++
helpviewer_keywords:
- ICommandPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b360b56066ecbb5cc605012b234c0ac11afb2a11
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339413"
---
# <a name="icommandpropertiesimpl-class"></a>ICommandPropertiesImpl クラス
実装を提供、 [ICommandProperties](https://msdn.microsoft.com/library/ms723044.aspx)インターフェイス。  
  
## <a name="syntax"></a>構文

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ICommandPropertiesImpl   
   : public ICommandProperties, public CUtlProps<PropClass>  
```  
  
### <a name="parameters"></a>パラメーター  
 *T*  
 派生クラス。  
  
 *PropClass*  
 プロパティ クラス。  

## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="members"></a>メンバー  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[GetProperties](#getproperties)|行セットの現在要求されている行セット プロパティ グループ内のプロパティの一覧を返します。|  
|[SetProperties](#setproperties)|行セット プロパティ グループのプロパティを設定します。|  
  
## <a name="remarks"></a>Remarks  
 これは、コマンドでは必須です。 によって定義された静的関数によって提供される、実装、 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)マクロ。  

## <a name="getproperties"></a> Icommandpropertiesimpl::getproperties
コマンドのプロパティのマップを使用してすべての要求されたプロパティ セットが返されます。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD(GetProperties)(const ULONG cPropertyIDSets,   
   const DBPROPIDSET rgPropertyIDSets[],   
   ULONG * pcPropertySets,   
   DBPROPSET ** prgPropertySets);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[icommandproperties::getproperties](https://msdn.microsoft.com/library/ms723119.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  
  
### <a name="remarks"></a>Remarks  
 「 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)」を参照してください。  
  
## <a name="setproperties"></a> Icommandpropertiesimpl::setproperties
コマンド オブジェクトのプロパティを設定します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[icommandproperties::setproperties](https://msdn.microsoft.com/library/ms711497.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)