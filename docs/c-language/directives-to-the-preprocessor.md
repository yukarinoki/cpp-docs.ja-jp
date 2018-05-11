---
title: プリプロセッサへのディレクティブ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 711e28a569cefbb500a98ab33cd22c527a5fd7c5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="directives-to-the-preprocessor"></a>プリプロセッサへのディレクティブ
"ディレクティブ" は、コンパイル前にプログラムのテキストに特定の操作を行うように C プリプロセッサに指示します。 [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)の詳細については、「*プリプロセッサ リファレンス*」を参照してください。 `#define` プリプロセッサ ディレクティブの使用例を次に示します。  
  
```  
#define MAX 100  
```  
  
 このステートメントは、コンパイル前に `MAX` で `100` を置き換えるようコンパイラに指示します。 C コンパイラのプリプロセッサ ディレクティブは次のとおりです。  
  
|#define|#endif|#ifdef|#line|  
|--------------|-------------|-------------|------------|  
|`#elif`|`#error`|**#ifndef**|**#pragma**|  
|`#else`|`#if`|`#include`|`#undef`|  
  
## <a name="see-also"></a>参照  
 [ソース ファイルとソース プログラム](../c-language/source-files-and-source-programs.md)