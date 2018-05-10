---
title: 2.1 ディレクティブの書式 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 918b6445-d35e-4176-9565-b045be941b4d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1eec5a2f0e91df6e8d71797199bd3a3911a3aab0
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="21-directive-format"></a>2.1 ディレクティブの書式
文法では、OpenMP ディレクティブの構文は指定された正式に[付録 C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md)、および次のように非公式。  
  
```  
#pragma omp directive-name  [clause[ [,] clause]...] new-line  
```  
  
 各ディレクティブが始まる **#pragma omp**を他の (非 OpenMP または仕入先の拡張機能と OpenMP) プラグマ ディレクティブと同じ名前の競合が発生する可能性を削減する。 ディレクティブの残りの部分では、C および C++ の標準コンパイラ ディレクティブの規則に従います。 具体的には、前後に空白文字を使用することができます、  **#** ディレクティブで単語を分離する空白文字を使用することはあります。 次のトークンの前処理、 **#pragma omp**マクロ置換されます。  
  
 ディレクティブは、大文字小文字を区別します。 ディレクティブの句が表示される順序は重要ではありません。 必要に応じて、それぞれの句の説明に示された制限される可能性があります、ディレクティブの句を繰り返すことがあります。 場合*変数一覧*変数のみを指定する必要がありますが、句に表示されます。 1 つだけ*ディレクティブ名*ディレクティブごとに指定できます。  たとえば、次のディレクティブは使用できません。  
  
```  
/* ERROR - multiple directive names not allowed */  
#pragma omp parallel barrier  
```  
  
 OpenMP ディレクティブは、最大で 1 つの後続のステートメント、構造化ブロックがあります。 これを適用します。