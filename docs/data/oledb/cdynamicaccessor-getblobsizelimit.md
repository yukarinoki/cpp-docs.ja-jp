---
title: Cdynamicaccessor::getblobsizelimit |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDynamicAccessor::GetBlobSizeLimit
- CDynamicAccessor.GetBlobSizeLimit
- CDynamicAccessor::GetBlobSizeLimit
- GetBlobSizeLimit
- ATL.CDynamicAccessor.GetBlobSizeLimit
dev_langs:
- C++
helpviewer_keywords:
- GetBlobSizeLimit method
ms.assetid: 7131e7c4-6e05-42f3-9d87-110301b672f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 860b186fc19bcec51c8f1ba3b7cc103b76f4b10d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090758"
---
# <a name="cdynamicaccessorgetblobsizelimit"></a>CDynamicAccessor::GetBlobSizeLimit
BLOB の最大サイズ (バイト単位) を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
const DBLENGTH GetBlobSizeLimit() const;  
  
```  
  
## <a name="remarks"></a>コメント  
 BLOB の処理値を返します`nBlobSize`によって設定[SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)