---
title: raw_property_prefixes |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_property_prefixes
dev_langs:
- C++
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c1f548c9513a086dd4741a9c61c51acebebb25db
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="rawpropertyprefixes"></a>raw_property_prefixes
**C 固有の仕様**  
  
 3 つのプロパティ メソッドの代替プレフィックスを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
raw_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
#### <a name="parameters"></a>パラメーター  
 `GetPrefix`  
 使用するプレフィックス、 **propget**メソッドです。  
  
 `PutPrefix`  
 使用するプレフィックス、 **propput**メソッドです。  
  
 `PutRefPrefix`  
 使用するプレフィックス、 **propputref**メソッドです。  
  
## <a name="remarks"></a>コメント  
 既定では、低レベル**propget**、 **propput**、および**propputref**メソッドは、というプレフィックスを持つメンバー関数によって公開**get _**、 **put _**、および**putref _** それぞれします。 これらのプレフィックスは、MIDL によって生成されるヘッダー ファイルで使用される名前と互換性があります。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)