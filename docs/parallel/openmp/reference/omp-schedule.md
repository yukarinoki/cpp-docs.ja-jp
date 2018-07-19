---
title: OMP_SCHEDULE |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_SCHEDULE
dev_langs:
- C++
helpviewer_keywords:
- OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2295a801-e584-4d2f-826f-7ca4c88846a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5052aaadc673e38a844ea5b0d1e11ff3a96f3fbe
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691756"
---
# <a name="ompschedule"></a>OMP_SCHEDULE
動作を変更して、[スケジュール](../../../parallel/openmp/reference/schedule.md)句と`schedule(runtime)`で指定された、`for`または`parallel for`ディレクティブです。  
  
## <a name="syntax"></a>構文  
  
```  
set OMP_SCHEDULE[=type[,size]]  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `size` (省略可能)  
 イテレーションのサイズを指定します。 `size` 正の整数を指定する必要があります。 既定値は 1 の場合を除き、`type`は静的です。 有効でない場合に`type`は`runtime`します。  
  
 `type`  
 スケジュールの種類。  
  
-   `dynamic`  
  
-   `guided`  
  
-   `runtime`  
  
-   `static`  
  
## <a name="remarks"></a>コメント  
 OpenMP の標準の Visual C 実装では既定値は`OMP_SCHEDULE=static,0`します。  
  
 詳細については、次を参照してください。 [4.1 OMP_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md)です。  
  
## <a name="example"></a>例  
 次のコマンド セット、 **OMP_SCHEDULE**環境変数。  
  
```  
set OMP_SCHEDULE="guided,2"  
```  
  
 次のコマンドの現在の設定を表示する、 **OMP_SCHEDULE**環境変数。  
  
```  
set OMP_SCHEDULE  
```  
  
## <a name="see-also"></a>関連項目  
 [環境変数](../../../parallel/openmp/reference/openmp-environment-variables.md)