---
title: リンカー ツールの警告 LNK4221 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4221
dev_langs:
- C++
helpviewer_keywords:
- LNK4221
ms.assetid: 8e2eb2de-9532-4b85-908a-8c9ff5c4cccb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8906c4308b8586d5b1312739921f58063e820deb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4221"></a>リンカー ツールの警告 LNK4221
このライブラリを使用するリンク操作では使用されませんに、このオブジェクト ファイルで、以前に定義されていないパブリック シンボルが定義されていません  
  
 次の 2 つのコード スニペットを検討してください。  
  
```  
// a.cpp  
#include <atlbase.h>  
```  
  
```  
// b.cpp  
#include <atlbase.h>  
int function()  
{  
   return 0;  
}  
  
```  
  
 ファイルをコンパイルして、2 つのオブジェクト ファイルを作成、実行**cl/c a.cpp b.cpp**コマンド プロンプトでします。 実行して、オブジェクト ファイルをリンクする場合は **/out:test.lib a.obj b.obj を/lib リンク**、LNK4221 警告が表示されます。 実行して、オブジェクトをリンクする場合は **/out:test.lib b.obj a.obj を/lib リンク**警告を受け取ることはありません。  
  
 2 番目のシナリオで警告が発行されない、リンカーは後入れ先出し (LIFO) の方法で動作するためです。 最初のシナリオでは、b.obj a.obj の前に処理され、a.obj に追加する新しいシンボルがありません。 A.obj を最初に処理するようにリンカーを指示するには、警告を回避できます。  
  
 このエラーの一般的な原因は次の 2 つのソース ファイル オプションを指定する場合に[/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)で指定された同じヘッダー ファイルの名前を持つ、**プリコンパイル済みヘッダーの**フィールドです。 この問題の一般的な原因を取り扱います stdafx.h ので、既定では、stdafx.cpp stdafx.h を含む新しいシンボルを追加しません。 別のソース ファイルには、stdafx.h とが含まれている場合 **/Yc** stdafx.obj する前に、関連付けられている .obj ファイルが処理されると、リンカー LNK4221 がスローされます。  
  
 1 つの方法にことを確認してプリコンパイル済みヘッダーごとには、この問題を解決するのには、1 つだけソース ファイルがでこれを含む **/Yc**です。 その他のすべてのソース ファイルには、プリコンパイル済みヘッダーを使用する必要があります。 この設定を変更する方法の詳細については、次を参照してください。 [/Yu (プリコンパイル済みヘッダー ファイルの使用)](../../build/reference/yu-use-precompiled-header-file.md)です。