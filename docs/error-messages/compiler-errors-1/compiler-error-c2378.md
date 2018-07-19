---
title: コンパイラ エラー C2378 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2378
dev_langs:
- C++
helpviewer_keywords:
- C2378
ms.assetid: 507a91c6-ca72-48df-b3a4-2cf931c86806
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01ba6f8aed7964b36ccfc665e29b393c9a593782
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196050"
---
# <a name="compiler-error-c2378"></a>コンパイラ エラー C2378
'identifier': 再定義されています。シンボルは typedef でオーバーロードできません  
  
 この識別子は `typedef`として定義されました。  
  
 次の例では C2378 が生成されます。  
  
```  
// C2378.cpp  
// compile with: /c  
int i;  
typedef int i;   // C2378  
typedef int b;   // OK  
```