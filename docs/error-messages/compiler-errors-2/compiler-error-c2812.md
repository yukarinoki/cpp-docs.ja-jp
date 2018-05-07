---
title: コンパイラ エラー C2812 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2812
dev_langs:
- C++
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28d46b0f9744f192d677d7b2df27b67e734de1b8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2812"></a>コンパイラ エラー C2812
\#インポートは/clr でサポートされていません:/clr:pure および/clr:safe  
  
 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で非推奨とされています。  
  
 [#import ディレクティブ](../../preprocessor/hash-import-directive-cpp.md)でサポートされていない **/clr: 純粋な**と **/clr:safe**ため`#import`ネイティブ コンパイラのサポート ライブラリの使用が必要です。  
  
## <a name="example"></a>例  
 次の例では、C2812 を生成します。  
  
```  
// C2812.cpp  
// compile with: /clr:pure /c  
#import "importlib.tlb"   // C2812  
```