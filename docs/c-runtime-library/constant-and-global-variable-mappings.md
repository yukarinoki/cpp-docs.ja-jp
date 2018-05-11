---
title: 定数とグローバル変数のマップ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _tenviron
- _TEOF
- _tfinddata_t
dev_langs:
- C++
helpviewer_keywords:
- tfinddatat function
- tenviron function
- TEOF type
- _TEOF type
- generic-text mappings
- _tenviron function
- _tfinddata_t function
ms.assetid: 3af4fd3e-9ed5-4ed9-96fd-7031e5126fd1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96c30f939670931ab031349bc5e9ddcce54e1891
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="constant-and-global-variable-mappings"></a>定数とグローバル変数のマップ
ここで説明する汎用テキスト定数、グローバル変数、基本データ型のマッピングは TCHAR.H で定義されており、定数 `_UNICODE` または `_MBCS` がプログラムで定義されているかどうかに依存します。  
  
### <a name="generic-text-constant-and-global-variable-mappings"></a>汎用テキスト定数とグローバル変数のマッピング  
  
|汎用テキスト - オブジェクト名|SBCS (_UNICODE、_MBCS が未定義の場合)|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|----------------------------------|--------------------------------------------|--------------------|-----------------------|  
|`_TEOF`|`EOF`|`EOF`|`WEOF`|  
|`_tenviron`|`_environ`|`_environ`|`_wenviron`|  
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|  
  
## <a name="see-also"></a>参照  
 [汎用テキスト マップ](../c-runtime-library/generic-text-mappings.md)   
 [データ型のマップ](../c-runtime-library/data-type-mappings.md)   
 [ルーチンのマップ](../c-runtime-library/routine-mappings.md)   
 [汎用テキストのプログラム例](../c-runtime-library/a-sample-generic-text-program.md)   
 [汎用テキスト マップの使用](../c-runtime-library/using-generic-text-mappings.md)