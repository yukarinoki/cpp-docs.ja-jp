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
ms.openlocfilehash: 432fb57b1505733b4f9cbda4e558699a8108a3ad
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083997"
---
# <a name="icommandpropertiesimpl-class"></a>ICommandPropertiesImpl クラス

実装を提供、 [ICommandProperties](/previous-versions/windows/desktop/ms723044)インターフェイス。  
  
## <a name="syntax"></a>構文

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ICommandPropertiesImpl   
   : public ICommandProperties, public CUtlProps<PropClass>  
```  
  
### <a name="parameters"></a>パラメーター  

*T*<br/>
派生クラス。  
  
*PropClass*<br/>
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

参照してください[icommandproperties::getproperties](/previous-versions/windows/desktop/ms723119)で、 *OLE DB プログラマーズ リファレンス*します。  
  
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

参照してください[icommandproperties::setproperties](/previous-versions/windows/desktop/ms711497)で、 *OLE DB プログラマーズ リファレンス*します。  
  
## <a name="see-also"></a>関連項目  

[OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)