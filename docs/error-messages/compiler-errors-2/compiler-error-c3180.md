---
title: コンパイラ エラー C3180 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3180
dev_langs:
- C++
helpviewer_keywords:
- C3180
ms.assetid: 5281f583-7df7-418a-8507-d4da67ed6572
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e08b46dda1d9d350ca955ecd0f05cac4f484cea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254856"
---
# <a name="compiler-error-c3180"></a>コンパイラ エラー C3180
'type name': 名前は 'limit' 文字のメタデータの限度を超えています  
  
 コンパイラでは、メタデータ内のマネージ型の名前が切り捨てられます。 切り捨てを行った後、この型はで使用できなくなります、`#using`ディレクティブ (または、別の言語のと同じ)。  
  
 型名の制限には、すべての名前空間の修飾子が含まれています。