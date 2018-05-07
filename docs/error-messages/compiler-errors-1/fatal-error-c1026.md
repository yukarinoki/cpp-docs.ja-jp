---
title: 致命的なエラー C1026 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1026
dev_langs:
- C++
helpviewer_keywords:
- C1026
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 24c034d45b7f8b222471094f4580902ae1b8dc66
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1026"></a>致命的なエラー C1026
プログラムの解析でコンパイラ内でスタック オーバーフローが発生しました。プログラムが複雑すぎます。  
  
 プログラムの解析に必要な領域には、コンパイラ スタック オーバーフローが発生します。  
  
 式の複雑さを軽減するには。  
  
-   内の入れ子構造の減少`for`と`switch`ステートメントです。 別の関数により深く入れ子になったステートメントを配置します。  
  
-   コンマ演算子や関数呼び出しを含む長い式に分割することです。