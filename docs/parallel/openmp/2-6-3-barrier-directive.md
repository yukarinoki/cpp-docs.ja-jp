---
title: 2.6.3 barrier ディレクティブ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68df92207feb45a77055098cdb1227a68b04bcab
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689793"
---
# <a name="263-barrier-directive"></a>2.6.3 barrier ディレクティブ
**バリア**ディレクティブは、チーム内のすべてのスレッドを同期します。 発生した場合、チーム内の各スレッドはすべて、他のユーザーのこのポイントに到達するまで待機します。 構文、**バリア**ディレクティブは、次のようにします。  
  
```  
#pragma omp barrier new-line  
```  
  
 チームのすべてのスレッドがバリアを検出した後、チーム内の各スレッドは並列 barrier ディレクティブの後、ステートメントの実行を開始します。 ため、**バリア**ディレクティブには、その構文の一部として、C 言語のステートメントはありません、プログラム内で配置する場合に制限があります。 参照してください[付録 C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md)正式な文法にします。 次の例は、これらの制限を示しています。  
  
```  
/* ERROR - The barrier directive cannot be the immediate  
*          substatement of an if statement  
*/  
if (x!=0)  
   #pragma omp barrier  
...  
  
/* OK - The barrier directive is enclosed in a  
*      compound statement.  
*/  
if (x!=0) {  
   #pragma omp barrier  
}  
```