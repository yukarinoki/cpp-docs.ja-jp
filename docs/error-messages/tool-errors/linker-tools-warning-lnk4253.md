---
title: リンカー ツールの警告 LNK4253 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4253
dev_langs:
- C++
helpviewer_keywords:
- LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bae4e88e1fe1434cd638d5c31cc8fd4d5c02c4de
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33301282"
---
# <a name="linker-tools-warning-lnk4253"></a>リンカー ツールの警告 LNK4253
セクション '「section1」' 'セクション 2;' にマージされていませんセクション '3' に既にマージ  
  
 リンカーが複数検出された競合のマージを要求します。 リンカーは、要求の 1 つでは無視します。  
  
 A **/merge**オプションまたはディレクティブが発生した、`from`セクションは既に別のセクションにより、以前にマージされました **/merge**オプションまたはディレクティブ (またはから暗黙のマージリンカー)。  
  
 LNK4253 を解決するには、マージ要求の 1 つを削除します。  
  
 X86 を対象とするときにマシンと、C++ での Windows CE ターゲット (ARM、MIPS、SH4、および Thumb)、します。CRT のセクションでは今すぐ読み取り専用です。 コードは、以前の動作に依存している場合 (です。CRT のセクションでは、読み取り/書き込み)、予期しない現象が発生する可能性があります。  
  
 詳細については、次のトピックを参照してください。  
  
-   [/MERGE (セクションのマージ)](../../build/reference/merge-combine-sections.md)  
  
-   [コメント (C/C++)](../../preprocessor/comment-c-cpp.md)  
  
## <a name="example"></a>例  
 次の例では、リンカーはマージするように指示、`.rdata`セクションを 2 回セクションが異なります。 次の例では、LNK4253 を生成します。  
  
```  
// LNK4253.cpp  
// compile with: /W1 /link /merge:.rdata=text2  
// LNK4253 expected  
#pragma comment(linker, "/merge:.rdata=.text")  
int main() {}  
```