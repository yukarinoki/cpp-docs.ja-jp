---
title: コンパイラ エラー C2441 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2441
dev_langs:
- C++
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6557e913f2bd34fda9d435d44020697a925af4e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2441"></a>コンパイラ エラー C2441
'variable': __declspec(process) と共に宣言されたシンボルで const を指定する必要があります: 純粋モード  
  
 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で非推奨とされています。  
  
 既定では、変数は、アプリケーション ドメインごと **/clr: 純粋な**します。 変数のマーク`__declspec(process)` **/clr: 純粋な**が 1 つのアプリケーション ドメインで変更し、別の読み取り場合に発生したエラーを生じやすくなります。  
  
 コンパイラが 1 つのプロセス変数ではそのため、 `const`  **/clr: 純粋な**、すべてのアプリケーション ドメインでのみ読み取りそれらを作成します。  
  
 詳細については、次を参照してください。[プロセス](../../cpp/process.md)と[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)です。  
  
## <a name="example"></a>例  
 次の例では、C2441 を生成します。  
  
```  
// C2441.cpp  
// compile with: /clr:pure /c  
__declspec(process) int i;   // C2441  
__declspec(process) const int j = 0;   // OK  
```