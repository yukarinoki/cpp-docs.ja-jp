---
title: リソース コンパイラの致命的なエラー RW1025 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW1025
dev_langs:
- C++
helpviewer_keywords:
- RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ba216e63cb0cae92b4541800493a2fb6195553a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33320015"
---
# <a name="resource-compiler-fatal-error-rw1025"></a>リソース コンパイラの致命的なエラー RW1025
相手側のヒープのメモリ不足  
  
 いる可能性がある領域が過度のメモリに常駐するソフトウェアを確認します。 CHKDSK プログラムを使用して、必要があるメモリの量を確認します。  
  
 サイズの大きいリソース ファイルを作成する場合は、2 つのファイルにリソース スクリプトを分割します。 2 つの .res ファイルを作成した後にに結合するのに MS-DOS コマンドラインを使用します。  
  
```  
copy first.res /b + second.res /b full.res  
```