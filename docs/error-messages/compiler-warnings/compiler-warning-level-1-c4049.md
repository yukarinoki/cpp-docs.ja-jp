---
title: コンパイラの警告 (レベル 1) C4049 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4049
dev_langs:
- C++
helpviewer_keywords:
- C4049
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1eea293ff64ed8fe2bf4bf0d38d897eb82223802
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4049"></a>コンパイラの警告 (レベル 1) C4049
コンパイラの制限: 行番号の出力を中止  
  
 ファイル内の複数の 16,777, 215 (2<sup>24</sup>-1) ソース行です。 コンパイラは、連番が 16,777, 215 を停止します。  
  
 16,777, 215 の行の後のコード。  
  
-   イメージには、行番号のデバッグ情報はありません。  
  
-   いくつかの診断は、不正な行番号で報告されること可能性があります。  
  
-   .asm 一覧 (/FAs) 不正な行番号があります。