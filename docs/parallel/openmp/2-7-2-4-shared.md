---
title: 2.7.2.4 共有 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c9c5d653-58fc-4620-ab0a-443ac4f8ba2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1de0e32e16d889acb8f1339d783bc194b3508dda
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33695695"
---
# <a name="2724-shared"></a>2.7.2.4 shared
この句に表示される変数を共有する、*変数一覧*チーム内のすべてのスレッド間でします。 チーム内のすべてのスレッドの同じ記憶域にアクセス**共有**変数。  
  
 構文、**共有**句を次に示します。  
  
```  
shared(variable-list)  
```