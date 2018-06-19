---
title: コンパイラの警告 (レベル 1) C4445 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4445
dev_langs:
- C++
helpviewer_keywords:
- C4445
ms.assetid: 535e92a0-ba08-4dfc-89b2-af2dcdd7caeb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: abd0d15113373f752bb861d73e48091687b2f0d2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274590"
---
# <a name="compiler-warning-level-1-c4445"></a>コンパイラの警告 (レベル 1) C4445
'function': WinRT またはマネージ型で、仮想関数をプライベートにすることはできません  
  
 仮想関数がプライベートである場合、派生型からアクセスできなくなります。 このエラーを解決するには、仮想メンバー関数のアクセシビリティをプロテクトまたはパブリックに変更します。