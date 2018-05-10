---
title: 2.6.4 atomic コンストラクト |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e4232ef1-4058-42ce-9de0-0ca788312aba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 66f0dc8469d1d70b2697df1fe120f10142d90dbe
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="264-atomic-construct"></a>2.6.4 atomic コンストラクト
`atomic`ディレクティブは、複数の可能性を公開することではなく特定のメモリ位置がアトミックに、更新されたことにより、同時スレッドを作成します。 構文、`atomic`ディレクティブは、次のようにします。  
  
```  
#pragma omp atomic new-lineexpression-stmt  
```  
  
 式ステートメントは、次の形式のいずれかが必要です。  
  
 *x binop*= *expr*  
  
 x++  
  
 ++x  
  
 x--  
  
 --x  
  
 上記の式では。  
  
-   *x*スカラー型の左辺値式を指定します。  
  
-   *expr*スカラー型の式は、によって指定されたオブジェクトを参照していない*x*です。  
  
-   `binop` オーバー ロードされた演算子ではないとの 1 つは、+、*、-、/、&、^、 &#124;、<\<、または >> です。  
  
 実装定義されているかどうか、実装をすべて置き換えます`atomic`ディレクティブを**重要な**と同じ一意であるディレクティブ*名前*、`atomic`ディレクティブでは、最適化の向上です。 多くの場合、ハードウェアの手順については、最小限のオーバーヘッドでアトミックな更新プログラムを実行することができます。  
  
 読み込みとによって指定されたオブジェクトの格納のみ*x*はアトミック; の評価*expr*アトミックではないです。 競合状態を避けるためには、並列の場所のすべての更新プログラムを保護する必要があります、`atomic`ディレクティブ競合状態を含まないことが知られているものを除き、します。  
  
 制限は、`atomic`ディレクティブは、次のようにします。  
  
-   プログラム全体で記憶域の場所 x へのすべての分割不可能な参照は、互換性のある型である必要があります。  
  
## <a name="examples"></a>次に例を示します。  
  
```  
extern float a[], *p = a, b;  
/* Protect against races among multiple updates. */  
#pragma omp atomic  
a[index[i]] += b;  
/* Protect against races with updates through a. */  
#pragma omp atomic  
p[i] -= 1.0f;  
  
extern union {int n; float x;} u;  
/* ERROR - References through incompatible types. */  
#pragma omp atomic  
u.n++;  
#pragma omp atomic  
u.x -= 1.0f;  
```