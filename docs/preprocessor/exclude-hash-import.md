---
title: 除外 (#import) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- exclude
dev_langs:
- C++
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d700f19235ac18af27fa958420aa4ed467807624
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2018
ms.locfileid: "42538439"
---
# <a name="exclude-import"></a>exclude (#import)
**C++ 固有の仕様**  
  
生成されるタイプ ライブラリのヘッダー ファイルから項目を除外します。  
  
## <a name="syntax"></a>構文  
  
```  
exclude("Name1"[, "Name2",...])  
```  
  
### <a name="parameters"></a>パラメーター  
*Name1*  
除外する最初の項目。  
  
*Name2*  
除外する 2 番目の項目 (必要な場合)。  
  
## <a name="remarks"></a>Remarks  
 
タイプ ライブラリは、システム ヘッダーまたはその他のタイプ ライブラリで定義された項目の定義を含むことがあります。 この属性は、任意の数の引数を受け取ることができます。各引数は、除外するトップ レベルのタイプ ライブラリ項目です。  
  
**END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 
[#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)