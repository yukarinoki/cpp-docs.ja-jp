---
title: ITopologyExecutionResource 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
dev_langs:
- C++
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: adb456315b2c6d15b7a3696df9a6845a2bd2b899
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686478"
---
# <a name="itopologyexecutionresource-structure"></a>ITopologyExecutionResource 構造体
リソース マネージャーで定義される実行リソースへのインターフェイスです。  
  
## <a name="syntax"></a>構文  
  
```
struct ITopologyExecutionResource;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ITopologyExecutionResource::GetId](#getid)|この実行リソースのリソース マネージャーの一意の識別子を返します。|  
|[ITopologyExecutionResource::GetNext](#getnext)|列挙の順番に次の実行リソースへのインターフェイスを返します。|  
  
## <a name="remarks"></a>コメント  
 このインターフェイスは、通常使用率が低いリソース マネージャーで見られるように、システムのトポロジのすべての要素。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ITopologyExecutionResource`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="getid"></a>  Itopologyexecutionresource::getid メソッド  
 この実行リソースのリソース マネージャーの一意の識別子を返します。  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 この実行リソースのリソース マネージャーの一意の識別子。  
  
##  <a name="getnext"></a>  Itopologyexecutionresource::getnext メソッド  
 列挙の順番に次の実行リソースへのインターフェイスを返します。  
  
```
virtual ITopologyExecutionResource *GetNext() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 列挙の順番に次の実行リソースへのインターフェイス。 この実行リソースが属しているノードの列挙の順番でない複数のノードがある場合、このメソッドは値を返しますが`NULL`です。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)
