---
title: コンパイラ エラー C2393 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2393
dev_langs:
- C++
helpviewer_keywords:
- C2393
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: efa8da496c6067381937820db365a5b37a19e843
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2393"></a>コンパイラ エラー C2393
'symbol': appdomain ごとのシンボルをセグメント 'segment' に割り当てることはできません  
  
 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で非推奨とされています。  
  
 使用[appdomain](../../cpp/appdomain.md)変数を使ってコンパイルすることを意味する **/clr: 純粋な**または **/clr:safe**、安全なまたは純粋なイメージは、データ セグメントを含めることはできません。  
  
 参照してください[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例では、C2393 を生成します。  
  
```  
// C2393.cpp  
// compile with: /clr:pure /c  
#pragma data_seg("myseg")  
int n = 0;   // C2393  
```