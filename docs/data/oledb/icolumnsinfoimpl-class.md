---
title: IColumnsInfoImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IColumnsInfoImpl<T>
- ATL::IColumnsInfoImpl
- IColumnsInfoImpl
- ATL.IColumnsInfoImpl
- ATL::IColumnsInfoImpl<T>
- GetColumnInfo
- ATL::IColumnsInfoImpl::GetColumnInfo
- ATL.IColumnsInfoImpl.GetColumnInfo
- ATL::IColumnsInfoImpl<T>::GetColumnInfo
- IColumnsInfoImpl::GetColumnInfo
- IColumnsInfoImpl<T>::GetColumnInfo
- IColumnsInfoImpl.GetColumnInfo
- IColumnsInfoImpl<T>::MapColumnIDs
- MapColumnIDs
- ATL::IColumnsInfoImpl::MapColumnIDs
- IColumnsInfoImpl.MapColumnIDs
- ATL::IColumnsInfoImpl<T>::MapColumnIDs
- IColumnsInfoImpl::MapColumnIDs
- ATL.IColumnsInfoImpl<T>.MapColumnIDs
- ATL.IColumnsInfoImpl.MapColumnIDs
dev_langs:
- C++
helpviewer_keywords:
- IColumnsInfoImpl class
- GetColumnInfo method
- MapColumnIDs method
ms.assetid: ba74c1c5-2eda-4452-8b57-84919fa0d066
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e95ab02abaf4dd536ad6a081708a76cf54cca6b0
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337243"
---
# <a name="icolumnsinfoimpl-class"></a>IColumnsInfoImpl クラス
実装を提供、 [IColumnsInfo](https://msdn.microsoft.com/library/ms724541.aspx)インターフェイス。  
  
## <a name="syntax"></a>構文

```cpp
template <class T>  
class ATL_NO_VTABLE IColumnsInfoImpl :   
   public IColumnsInfo,    
   public CDBIDOps  
```  
  
### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス、`IColumnsInfoImpl`します。  

## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[GetColumnInfo](#getcolumninfo)|ほとんどのコンシューマーが必要な列のメタデータを返します。|  
|[MapColumnIDs](#mapcolumnids)|指定した列の Id によって識別される行セット内の列の序数の配列を返します。|  
  
## <a name="remarks"></a>Remarks  
 行セットとコマンドの必須のインターフェイスです。 プロバイダーの動作を変更する`IColumnsInfo`実装では、プロバイダーの列マップを変更する必要があります。  

## <a name="getcolumninfo"></a> Icolumnsinfoimpl::getcolumninfo
ほとんどのコンシューマーが必要な列のメタデータを返します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD (GetColumnInfo)(DBORDINAL* pcColumns,  
   DBCOLUMNINFO** prgInfo,  
   OLECHAR** ppStringsBuffer);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[icolumnsinfo::getcolumninfo](https://msdn.microsoft.com/library/ms722704.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  

## <a name="mapcolumnids"></a> Icolumnsinfoimpl::mapcolumnids
指定した列の Id によって識別される行セット内の列の序数の配列を返します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD (MapColumnIDs)(DBORDINAL cColumnIDs,  
   const DBID rgColumnIDs[],  
   DBORDINAL rgColumns[]);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[IColumnsInfo::MapColumnIDs](https://msdn.microsoft.com/library/ms714200.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)