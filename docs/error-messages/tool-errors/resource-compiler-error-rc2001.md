---
title: リソース コンパイラ エラー RC2001 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2001
dev_langs:
- C++
helpviewer_keywords:
- RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ef1fd5d29fc5784ee418a8456cacec37e943b73
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322420"
---
# <a name="resource-compiler-error-rc2001"></a>リソース コンパイラ エラー RC2001
定数の改行  
  
 文字列定数は継続なし 2 行目で、円記号 (**\\**) または決算残高と期首二重引用符 (**"**)。  
  
 ソース ファイル内の 2 つの行にある文字列定数を解除するには、次のいずれかの操作を行います。  
  
-   行連結文字、バック スラッシュで最初の行を終了します。  
  
-   二重引用符で最初の行の文字列を閉じて、もう 1 つ引用符に次の行に文字列を開きます。  
  
 \N、文字列定数で復帰改行文字を埋め込むためのエスケープ シーケンスでは、最初の行を終了するのに十分ではありません。