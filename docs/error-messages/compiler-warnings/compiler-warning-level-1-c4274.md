---
title: コンパイラの警告 (レベル 1) C4274 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4274
dev_langs:
- C++
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39b941fc0cb32e268e33d3b0e1ae66079e8decaf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33286147"
---
# <a name="compiler-warning-level-1-c4274"></a>コンパイラの警告 (レベル 1) C4274
\#ident が無視されます。#pragma comment (exestr, 'string') のマニュアルを参照してください。  
  
 `#ident`ディレクティブで、オブジェクトまたは実行可能ファイルで、ユーザー指定の文字列を挿入します。 これは推奨されなくなりました。 その結果、コンパイラは、ディレクティブを無視します。  
  
> [!CAUTION]
>  使用するにように勧める警告 C4274、 [#pragma comment (exestr, 'string')](../../preprocessor/comment-c-cpp.md)ディレクティブです。 ただし、このアドバイスは廃止されており、コンパイラの将来のリリースで変更されます。 使用する場合、`#pragma`ディレクティブ、リンカー ツール (LINK.exe) ディレクティブによって生成される、このコメント レコードを無視し、警告を発行[LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)です。 代わりに、`#ident`ディレクティブ、ことをお勧め、アプリケーションでは、ファイル バージョン リソース文字列を使用することです。  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   削除、 `#ident "`*文字列*`"`ディレクティブです。  
  
## <a name="see-also"></a>関連項目  
 [コメント (C/C++)](../../preprocessor/comment-c-cpp.md)   
 [リンカー ツールの警告 LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)   
 [リソース ファイルの操作](../../windows/working-with-resource-files.md)