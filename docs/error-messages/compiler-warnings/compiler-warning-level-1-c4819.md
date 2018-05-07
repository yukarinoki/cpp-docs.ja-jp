---
title: コンパイラの警告 (レベル 1) C4819 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4819
dev_langs:
- C++
helpviewer_keywords:
- C4819
ms.assetid: c0316e85-249c-414d-9df0-622d077c6bc2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 718e0783c3f7afcc9af958f7940f437ac4c944b7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4819"></a>コンパイラの警告 (レベル 1) C4819
ファイルは、現在のコード ページ (数) で表示できない文字を含んでいます。 データの損失を防ぐために、ファイルを Unicode 形式で保存してください。  
  
 C4819 は、ANSI ソース ファイルが、ファイル内のすべての文字を表現できないコードページを使用するシステムでコンパイルされたときに発生します。  
  
 C4819 を解決するには、ファイルを Unicode 形式で保存します。 Visual Studio で、次のように選択します。**ファイル**、**保存オプションの高度な**します。 **[保存オプションの**] ダイアログ ボックスで、ファイル内のすべての文字を表現できるエンコードを選択 — たとえば、utf-8 — を選択し **[ok]** です。