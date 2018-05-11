---
title: 2.2 条件付きコンパイル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8f9c914d-736c-48cf-899d-c8029dbe1e32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3d8c7073548c015d9982b721387176a0ca658c2
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="22-conditional-compilation"></a>2.2 条件付きコンパイル
_**OPENMP**マクロ名が 10 進定数として OpenMP 準拠の実装によって定義された*yyyymm*、承認済みの仕様の月と年になる予定です。 このマクロのサブジェクトをすることはできません、 **#define**または **#undef**プリプロセッサ ディレクティブです。  
  
```  
#ifdef _OPENMP  
iam = omp_get_thread_num() + index;  
#endif  
```  
  
 ベンダーは、OpenMP に拡張機能を定義する場合は、追加の定義済みマクロを指定、可能性があります。