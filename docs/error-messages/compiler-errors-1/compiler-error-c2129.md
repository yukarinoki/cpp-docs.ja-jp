---
title: コンパイラ エラー C2129 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2129
dev_langs:
- C++
helpviewer_keywords:
- C2129
ms.assetid: 21a8223e-1d22-4baa-9ca1-922b7f751dd0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d151c774672b1788ca893a9812deb3e41100dc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2129"></a>コンパイラ エラー C2129
静的関数 'function' が宣言されていますが、定義されていません  
  
 前方参照される、`static`定義されていない関数です。  
  
 A`static`ファイル スコープ内で関数を定義する必要があります。 宣言する必要があります、関数が別のファイルで定義されている場合`extern`です。