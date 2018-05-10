---
title: コンパイラの警告 (レベル 4) C4234 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4234
dev_langs:
- C++
helpviewer_keywords:
- C4234
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b8d5b7a2999b77c0b34ee925f5dd85a0a27c63f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4234"></a>コンパイラの警告 (レベル 4) C4234
標準の拡張機能を使用します将来使用するために予約されています 'keyword' キーワード。  
  
 コンパイラは、使用するキーワードをまだ実装されていません。  
  
 この警告は、自動的にエラーになります。 この動作を変更する場合は、使用[#pragma 警告](../../preprocessor/warning.md)です。 たとえば、レベル 4 の警告の問題、c4234  
  
```  
#pragma warning(2:4234)  
```  
  
 をソース コード ファイルに追加します。