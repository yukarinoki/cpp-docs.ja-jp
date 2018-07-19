---
title: NMAKE の致命的なエラー U1033 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1033
dev_langs:
- C++
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1d39d4c35ec66d405d51d601b7c5d2b2ab37b02
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33319271"
---
# <a name="nmake-fatal-error-u1033"></a>NMAKE の致命的なエラー U1033
構文エラー: 'string' が予期しません。  
  
 文字列は、メイクファイルの有効な構文の一部ではありません。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  終わりの山かっこの設定されている場合 (**<<**) のインライン ファイル、行の先頭には、次のエラーが発生します。  
  
    ```  
    syntax error : 'EOF' unexpected  
    ```  
  
2.  メイクファイルのマクロ定義に等号 (=) が含まれているかどうか (**=**)、次のエラーが発生した先行名または名前が定義されている場合は nothing に展開されるマクロ、なし。  
  
    ```  
    syntax error : '=' unexpected  
    ```  
  
3.  場合、セミコロン (**;**) ツール内のコメント行にします。INI は、1 行の先頭に次のエラーが発生します。  
  
    ```  
    syntax error : ';' unexpected  
    ```  
  
4.  Makefile がワード プロセッサでフォーマットされた場合、次のエラーが発生します。  
  
    ```  
    syntax error : ':' unexpected  
    ```