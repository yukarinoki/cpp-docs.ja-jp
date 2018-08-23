---
title: no_dual_interfaces |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_dual_interfaces
dev_langs:
- C++
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1e919e48b79c9fe98a7a33257ebd0f70061d788
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2018
ms.locfileid: "42538835"
---
# <a name="nodualinterfaces"></a>no_dual_interfaces
**C++ 固有の仕様**  
  
コンパイラがデュアル インターフェイス メソッドのラッパー関数を生成する方法を変更します。  
  
## <a name="syntax"></a>構文  
  
```  
no_dual_interfaces  
```  
  
## <a name="remarks"></a>Remarks  
 
通常、ラッパーは、そのインターフェイスの仮想関数テーブルからメソッドを呼び出します。 **No_dual_interfaces**、ラッパーを呼び出す代わりに`IDispatch::Invoke`メソッドを呼び出します。  
  
**END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 
[#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)