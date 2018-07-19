---
title: 使用状況をスタック |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6f711636089a6f2966002002220aac88cebe17a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379859"
---
# <a name="stack-usage"></a>スタックの使用
RSP の現在のアドレスを超えるすべてのメモリは不安定なものと見なされます: OS、または、デバッガーは、ユーザーのデバッグ セッションでは、または、割り込みハンドラーの中にこのメモリを上書き可能性があります。 したがって、RSP は常に読み取りまたはスタックのフレームの値の書き込みを試行する前に設定する必要があります。  
  
 このセクションでは、ローカル変数のスタック領域の割り当てを説明し、 **alloca**組み込みです。  
  
-   [スタック割り当て](../build/stack-allocation.md)  
  
-   [動的なパラメーター スタック領域の構成](../build/dynamic-parameter-stack-area-construction.md)  
  
-   [関数の型](../build/function-types.md)  
  
-   [malloc アライメント](../build/malloc-alignment.md)  
  
-   [alloca](../build/alloca.md)  
  
## <a name="see-also"></a>関連項目  
 [x64 ソフトウェア規約](../build/x64-software-conventions.md)