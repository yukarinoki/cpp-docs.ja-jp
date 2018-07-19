---
title: Cdynamicaccessor::setblobhandling |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicAccessor::SetBlobHandling
- CDynamicAccessor.SetBlobHandling
- ATL::CDynamicAccessor::SetBlobHandling
- SetBlobHandling
- ATL.CDynamicAccessor.SetBlobHandling
dev_langs:
- C++
helpviewer_keywords:
- SetBlobHandling method
ms.assetid: fa8b0bb3-a21b-4d64-aeef-e79bf61d079c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8ee2c2d57f9f413346bb33a178fc3d8fa90439e1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095847"
---
# <a name="cdynamicaccessorsetblobhandling"></a>CDynamicAccessor::SetBlobHandling
BLOB の現在の行の値の処理を設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      bool SetBlobHandling(DBBLOBHANDLINGENUM eBlobHandling);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `eBlobHandling`  
 BLOB データを処理する方法を指定します。 次の値がかかることができます。  
  
-   **DBBLOBHANDLING_DEFAULT**: よりも大きい列のデータを処理`nBlobSize`(によって設定`SetBlobSizeLimit`) として BLOB データとを通じて取得、`ISequentialStream`または`IStream`オブジェクト。 このオプションはよりも大きいデータを含むすべての列をバインドしよう`nBlobSize`として示すまたは**DBTYPE_IUNKNOWN** BLOB データとして。  
  
-   **DBBLOBHANDLING_NOSTREAMS**: よりも大きい列のデータを処理`nBlobSize`(によって設定`SetBlobSizeLimit`) として BLOB データと、プロバイダーに割り当てられた、コンシューマー所有のメモリ内の参照を取得します。 このオプションは、1 つ以上の BLOB 列を含むテーブルに対して便利とプロバイダーがサポートする 1 つだけ`ISequentialStream`アクセサーごとのオブジェクト。  
  
-   **DBBLOBHANDLING_SKIP**: Skip (バインドしない) を含む Blob として修飾列 (アクセサーはバインドまたは列の値を取得されませんが、列のステータスや長さも取得されます)。  
  
## <a name="remarks"></a>コメント  
 呼び出す必要があります`SetBlobHandling`呼び出す前に**開く**です。  
  
 コンス トラクター メソッド[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) BLOB 処理する値を設定**DBBLOBHANDLING_DEFAULT**です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)