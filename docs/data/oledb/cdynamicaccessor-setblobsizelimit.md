---
title: Cdynamicaccessor::setblobsizelimit |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicAccessor::SetBlobSizeLimit
- SetBlobSizeLimit
- CDynamicAccessor.SetBlobSizeLimit
- ATL.CDynamicAccessor.SetBlobSizeLimit
- ATL::CDynamicAccessor::SetBlobSizeLimit
dev_langs:
- C++
helpviewer_keywords:
- SetBlobSizeLimit method
ms.assetid: fb8cb85d-f841-408e-a344-37895b10993f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8731857507fa096d500a31f31a7c31ef4f94cfc6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096081"
---
# <a name="cdynamicaccessorsetblobsizelimit"></a>CDynamicAccessor::SetBlobSizeLimit
BLOB の最大サイズをバイト単位で設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      void SetBlobSizeLimit(DBLENGTH nBlobSize);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nBlobSize`  
 BLOB のサイズの上限を指定します。  
  
## <a name="remarks"></a>コメント  
 BLOB の最大サイズ (バイト単位) に設定します。この値より大きい列のデータは、BLOB として扱われます。 一部のプロバイダーは、(2 GB) などの列のサイズがかなり大きくを提供します。 列サイズのメモリを割り当てるしようとするではなく、通常しようとする Blob としてこれらの列をバインドします。 その方法ですべてのメモリを割り当てることがないが、まだ切り捨てを心配せず、すべてのデータを読み取ることができます。 ただし、場合がありますを強制する`CDynamicAccessor`ネイティブ データ型の大きな列をバインドします。 これを行うには、呼び出す`SetBlobSizeLimit`呼び出す前に**開く**です。  
  
 コンス トラクター メソッド[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) BLOB の最大サイズを 8,000 バイトの既定値に設定します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)