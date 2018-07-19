---
title: リンカー ツールの警告 LNK4254 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4254
dev_langs:
- C++
helpviewer_keywords:
- LNK4254
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb57882ab4269c06a53ed73fed2a9d6caf2f2c85
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33316895"
---
# <a name="linker-tools-warning-lnk4254"></a>リンカー ツールの警告 LNK4254
セクション '「section1」' (オフセット) が 'セクション 2' にマージ異なる属性を持つ (オフセット)  
  
 1 つのセクションの内容は、別にマージされたが、2 つのセクションの属性が異なります。 プログラムには、予期しない結果が得られます可能性があります。 たとえば、読み取るしたいデータのみようになりましたがあります書き込み可能なセクションで。  
  
 LNK4254 を解決するには、変更またはマージ要求を削除します。  
  
 X86 を対象とするときにマシンと、C++ での Windows CE ターゲット (ARM、MIPS、SH4、および Thumb)、します。CRT のセクションでは、読み取り専用です。 コードが以前の動作に依存する場合 (です。CRT のセクションでは、読み取り/書き込み)、予期しない現象が発生する可能性があります。  
  
 詳細については、次のトピックを参照してください。  
  
-   [/MERGE (セクションのマージ)](../../build/reference/merge-combine-sections.md)  
  
-   [コメント (C/C++)](../../preprocessor/comment-c-cpp.md)  
  
## <a name="example"></a>例  
 次の例では、LNK4254 が生成されます。  
  
```  
// LNK4254.cpp  
// compile with: /W1 /link /WX  
// LNK4254 expected  
#pragma comment(linker, "/merge:.data=.text")  
int main() {}  
```