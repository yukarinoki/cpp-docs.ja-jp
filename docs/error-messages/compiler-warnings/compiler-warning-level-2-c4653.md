---
title: コンパイラの警告 (レベル 2) C4653 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4653
dev_langs:
- C++
helpviewer_keywords:
- C4653
ms.assetid: 90ec3317-3d39-4b4c-bcd1-97e7c799e1b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c312b7530fa11bb734dc99a872b36e926890f658
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290997"
---
# <a name="compiler-warning-level-2-c4653"></a>コンパイラの警告 (レベル 2) C4653
コンパイラ オプション 'option' はプリコンパイル済みヘッダーです。現在のコマンド ライン オプションが無視されます。  
  
 プリコンパイル済みヘッダーの使用で指定されたオプション ([/Yu](../../build/reference/yu-use-precompiled-header-file.md)) オプションがプリコンパイル済みヘッダーの作成時に指定されたオプションと矛盾しています。 このコンパイルでは、プリコンパイル済みヘッダーの作成時に指定されたオプションを使用します。  
  
 ときに、さまざまなオプションの値、パックの構造体に、この警告が発生することが ([/Zp](../../build/reference/zp-struct-member-alignment.md)) プリコンパイル済みヘッダーのコンパイル時に指定されました。