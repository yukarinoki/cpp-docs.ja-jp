---
title: 3.1.8 omp_get_dynamic 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: af7755173ab884a40a5f8a41f432f265cc1e6c32
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686192"
---
# <a name="318-ompgetdynamic-function"></a>3.1.8 omp_get_dynamic 関数
**Omp_get_dynamic**場合は、スレッドを動的に調整が有効であり、それ以外の場合は 0 を返します関数は 0 以外の値を返します。 形式は次のとおりです。  
  
```  
#include <omp.h>  
int omp_get_dynamic(void);  
```  
  
 実装がスレッドの数を動的に調整を実装していない場合、この関数は常に 0 を返します。  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   動的なスレッド調整については、次を参照してください。[セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)ページ 39 にします。