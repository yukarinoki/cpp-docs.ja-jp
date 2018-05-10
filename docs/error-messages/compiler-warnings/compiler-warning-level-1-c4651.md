---
title: コンパイラの警告 (レベル 1) C4651 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4651
dev_langs:
- C++
helpviewer_keywords:
- C4651
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0015102a44b71f342b125532d20849590157ee0c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4651"></a>コンパイラの警告 (レベル 1) C4651
'定義' プリコンパイル済みヘッダーに定義されていますが、現在のコンパイルではありません。  
  
 このコンパイルされていない場合、プリコンパイル済みヘッダーが生成されたが、定義が指定されました。  
  
 プリコンパイル済みのヘッダー内ではなく、コードの残りの部分定義が有効になります。  
  
 プリコンパイル済みヘッダーがで指定してビルドされていた場合、コンパイラで/Yu コンパイルが指定していない場合にこの警告が生成されます。  /Yu コマンドラインに指定してを追加するには、この警告が解決されます。