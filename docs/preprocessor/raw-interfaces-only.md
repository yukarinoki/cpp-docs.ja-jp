---
title: raw_interfaces_only |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_interfaces_only
dev_langs:
- C++
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4643181bf70bc92f4ef5e88b8a9add1ba7bdaad7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849302"
---
# <a name="rawinterfacesonly"></a>raw_interfaces_only
**C 固有の仕様**  
  
 エラー処理ラッパー関数の生成を抑制し、[プロパティ](../cpp/property-cpp.md)ラッパー関数を使用して宣言します。  
  
## <a name="syntax"></a>構文  
  
```  
raw_interfaces_only  
```  
  
## <a name="remarks"></a>コメント  
 `raw_interfaces_only` 属性を使用すると、非プロパティ関数の名前付けに使用される既定のプレフィックスも削除されます。 プレフィックスは、通常、 **raw _** です。 この属性を指定すると、タイプ ライブラリの関数名が直接使用されます。  
  
 この属性を使用することで、タイプ ライブラリの低水準の内容のみを公開できます。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)