---
title: コンパイラの警告 (レベル 1) C4819 |Microsoft Docs
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
ms.openlocfilehash: ac468bc605c261b66f47fdf40efd1a01a5383d58
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074280"
---
# <a name="compiler-warning-level-1-c4819"></a>コンパイラの警告 (レベル 1) C4819

ファイルは、現在のコード ページ (数) で表示できない文字を含んでいます。 データの損失を防ぐために、ファイルを Unicode 形式で保存してください。

C4819 は、ANSI ソース ファイルが、ファイル内のすべての文字を表現できないコードページを使用するシステムでコンパイルされたときに発生します。

C4819 を解決するには、ファイルを Unicode 形式で保存します。 Visual Studio で、次のように選択します。**ファイル**、 **保存オプションの**します。 **[保存オプションの**] ダイアログ ボックスで、ファイルのすべての文字を表現できるエンコードを選択します: utf-8 など — 選び、 **[ok]** します。