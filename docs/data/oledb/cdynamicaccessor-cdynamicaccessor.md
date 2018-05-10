---
title: Cdynamicaccessor::cdynamicaccessor |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicAccessor::CDynamicAccessor
- ATL::CDynamicAccessor::CDynamicAccessor
- ATL.CDynamicAccessor.CDynamicAccessor
- CDynamicAccessor.CDynamicAccessor
dev_langs:
- C++
helpviewer_keywords:
- CDynamicAccessor class, constructor
ms.assetid: bf40fe81-2c85-473e-9075-51ad9b060b39
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 80446719ac8e523efc5ef885fe55fb89561509e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicaccessorcdynamicaccessor"></a>CDynamicAccessor::CDynamicAccessor
インスタンスを作成し、初期化、`CDynamicAccessor`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp
      CDynamicAccessor(DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,   
   DBLENGTH nBlobSize = 8000);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `eBlobHandling`  
 バイナリ ラージ オブジェクト (BLOB) データを処理する方法を指定します。 既定値は**DBBLOBHANDLING_DEFAULT**です。 参照してください[SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md)の詳細については、 **DBBLOBHANDLINGENUM**値。  
  
 `nBlobSize`  
 BLOB の最大サイズ (バイト単位)この値を列データは、BLOB として扱われます。 既定値は、8,000 です。 参照してください[SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md)詳細についてはします。  
  
## <a name="remarks"></a>コメント  
 初期化するために、コンス トラクターを使用する場合、`CDynamicAccessor`オブジェクト、Blob にバインドする方法を指定することができます。 Blob には、グラフィック、サウンド、またはコンパイル済みコードなどのバイナリ データを含めることができます。 既定の動作が Blob として 8,000 バイトを超える列を扱うに連結するには、`ISequentialStream`オブジェクト。 ただし、BLOB のサイズを別の値を指定することができます。  
  
 指定することも方法`CDynamicAccessor`BLOB データと見なされる列のデータを処理する: 既定の方法で BLOB データを処理できるはスキップできます (バインドされません) や BLOB データです。 プロバイダーに割り当てられたメモリ内の BLOB データをバインドできます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)