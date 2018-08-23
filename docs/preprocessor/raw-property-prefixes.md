---
title: raw_property_prefixes |Microsoft Docs
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
ms.openlocfilehash: 423a66b698f4e421ff29e6ac3dfddd11fa11c58f
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2018
ms.locfileid: "42541773"
---
# <a name="rawpropertyprefixes"></a>raw_property_prefixes
**C++ 固有の仕様**  
  
3 つのプロパティ メソッドの代替プレフィックスを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
raw_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
### <a name="parameters"></a>パラメーター  
*GetPrefix*  
使用するプレフィックス、`propget`メソッド。  
  
*PutPrefix*  
使用するプレフィックス、`propput`メソッド。  
  
*PutRefPrefix*  
使用するプレフィックス、`propputref`メソッド。  
  
## <a name="remarks"></a>Remarks  
 
既定では、低レベルで`propget`、 `propput`、および`propputref`メソッドは、というプレフィックスを持つメンバー関数によって公開**get _**、 **put _**、および**putref _** それぞれします。 これらのプレフィックスは、MIDL によって生成されるヘッダー ファイルで使用される名前と互換性があります。  
  
**END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 
[#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)