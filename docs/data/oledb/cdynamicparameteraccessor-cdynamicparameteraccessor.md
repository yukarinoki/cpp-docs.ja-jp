---
title: Cdynamicparameteraccessor::cdynamicparameteraccessor |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicParameterAccessor::CDynamicParameterAccessor
- CDynamicParameterAccessor.CDynamicParameterAccessor
dev_langs:
- C++
helpviewer_keywords:
- CDynamicParameterAccessor class, constructor
- CDynamicParameterAccessor method
ms.assetid: a1cce5e4-dfb9-43a2-bfb8-0435c653674a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 52ffd2f16211ae25bf1069ad1860dc273c1d5002
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098395"
---
# <a name="cdynamicparameteraccessorcdynamicparameteraccessor"></a>CDynamicParameterAccessor::CDynamicParameterAccessor
コンストラクターです。  
  
## <a name="syntax"></a>構文  
  
```cpp
      typedef CDynamicParameterAccessor _ParamClass;  
CDynamicParameterAccessor(DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,   
   DBLENGTH nBlobSize = 8000 )   
   : CDynamicAccessor(eBlobHandling, nBlobSize )  
```  
  
#### <a name="parameters"></a>パラメーター  
 `eBlobHandling`  
 BLOB データを処理する方法を指定します。 既定値は**DBBLOBHANDLING_DEFAULT**です。 参照してください[cdynamicaccessor::setblobhandling](../../data/oledb/cdynamicaccessor-setblobhandling.md)の詳細については、 **DBBLOBHANDLINGENUM**値。  
  
 `nBlobSize`  
 BLOB の最大サイズ (バイト単位)この値を列データは、BLOB として扱われます。 既定値は、8,000 です。 参照してください[cdynamicaccessor::setblobsizelimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md)詳細についてはします。  
  
## <a name="remarks"></a>コメント  
 参照してください、 [cdynamicaccessor::cdynamicaccessor](../../data/oledb/cdynamicaccessor-cdynamicaccessor.md) BLOB の処理の詳細については、コンス トラクターです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)