---
title: コンパイラの警告 (レベル 3) C4622 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4622
dev_langs:
- C++
helpviewer_keywords:
- C4622
ms.assetid: d3c879f0-4492-4f4b-b26d-230993f3a933
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b82e87f37b50b8df727d043889cb35ca02d3f78
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4622"></a>コンパイラの警告 (レベル 3) C4622
オブジェクト ファイル 'file' でデバッグ情報はプリコンパイル済みヘッダーを作成したときに上書きされました  
  
 指定されたファイルの CodeView 情報が、(プリコンパイル済みヘッダーを使用する) [/Yu](../../build/reference/yu-use-precompiled-header-file.md) オプションを指定してコンパイルしたときに失われました。  
  
 プリコンパイル済みヘッダー ファイルを作成または使用する場合は、( [/Fo](../../build/reference/fo-object-file-name.md)を使用して) オブジェクト ファイルの名前を変更し、新しいオブジェクト ファイルを使用してリンクします。