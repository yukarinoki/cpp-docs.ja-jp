---
title: high_property_prefixes |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- high_property_prefixes
dev_langs:
- C++
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ce21958dbb928a29debe21fb7cfaed4b9036141
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2018
ms.locfileid: "42540273"
---
# <a name="highpropertyprefixes"></a>high_property_prefixes
**C++ 固有の仕様**  
  
3 つのプロパティ メソッドの代替プレフィックスを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
high_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
### <a name="parameters"></a>パラメーター  
*GetPrefix*  
使用するプレフィックス、`propget`メソッド。  
  
*PutPrefix*  
使用するプレフィックス、`propput`メソッド。  
  
*PutRefPrefix*  
使用するプレフィックス、`propputref`メソッド。  
  
## <a name="remarks"></a>Remarks  
 
既定では、高度なエラー処理`propget`、 `propput`、および`propputref`メソッドは、というプレフィックスを持つメンバー関数によって公開`Get`、 `Put`、および`PutRef`、それぞれします。  
  
**END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 
[#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)