---
title: OMP_SCHEDULE |Microsoft Docs
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
ms.openlocfilehash: fd5bf96706b94ffbba8cb1b9aeeee8701b266e5d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115046"
---
# <a name="ompschedule"></a>OMP_SCHEDULE
動作を変更、[スケジュール](../../../parallel/openmp/reference/schedule.md)句と`schedule(runtime)`で指定された、`for`または`parallel for`ディレクティブ。  
  
## <a name="syntax"></a>構文  
  
```  
set OMP_SCHEDULE[=type[,size]]  
```  
  
## <a name="arguments"></a>引数

*size*<br/>
(省略可能)イテレーションのサイズを指定します。 `size` 正の整数である必要があります。 既定値は 1 の場合を除き、`type`は静的です。 有効でない場合に`type`は`runtime`します。  
  
*type*<br/>
スケジュールの種類。  
  
-   `dynamic`  
  
-   `guided`  
  
-   `runtime`  
  
-   `static`  
  
## <a name="remarks"></a>Remarks  
 OpenMP の標準の Visual C の実装の既定値は`OMP_SCHEDULE=static,0`します。  
  
 詳細については、次を参照してください。 [4.1 OMP_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md)します。  
  
## <a name="example"></a>例  
 次のコマンド セット、 **OMP_SCHEDULE**環境変数。  
  
```  
set OMP_SCHEDULE="guided,2"  
```  
  
 次のコマンドの現在の設定の表示、 **OMP_SCHEDULE**環境変数。  
  
```  
set OMP_SCHEDULE  
```  
  
## <a name="see-also"></a>関連項目  
 [環境変数](../../../parallel/openmp/reference/openmp-environment-variables.md)