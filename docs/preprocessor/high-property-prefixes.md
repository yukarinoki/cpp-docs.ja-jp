---
title: high_property_prefixes |Microsoft ドキュメント
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
ms.openlocfilehash: 7269301fed3892fbf4b7cf6427bacb82d9712ef7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="highpropertyprefixes"></a>high_property_prefixes
**C 固有の仕様**  
  
 3 つのプロパティ メソッドの代替プレフィックスを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
high_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
#### <a name="parameters"></a>パラメーター  
 `GetPrefix`  
 使用するプレフィックス、 **propget**メソッドです。  
  
 `PutPrefix`  
 使用するプレフィックス、 **propput**メソッドです。  
  
 `PutRefPrefix`  
 使用するプレフィックス、 **propputref**メソッドです。  
  
## <a name="remarks"></a>コメント  
 既定では、高レベルのエラー処理**propget**、 **propput**、および**propputref**メソッドは、というプレフィックスを持つメンバー関数によって公開**取得**、 `Put`、および**PutRef**、それぞれします。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)