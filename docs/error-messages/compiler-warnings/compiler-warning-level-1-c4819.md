---
title: コンパイラの警告 (レベル 1) C4819
ms.date: 11/04/2016
f1_keywords:
- C4819
helpviewer_keywords:
- C4819
ms.assetid: c0316e85-249c-414d-9df0-622d077c6bc2
ms.openlocfilehash: c0ca29a304fbd05cb0c6b7d1b06414304c70fb2a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596613"
---
# <a name="compiler-warning-level-1-c4819"></a>コンパイラの警告 (レベル 1) C4819

ファイルは、現在のコード ページ (数) で表示できない文字を含んでいます。 データの損失を防ぐために、ファイルを Unicode 形式で保存してください。

C4819 は、ANSI ソース ファイルが、ファイル内のすべての文字を表現できないコードページを使用するシステムでコンパイルされたときに発生します。

C4819 を解決するには、ファイルを Unicode 形式で保存します。 Visual Studio で、次のように選択します。**ファイル**、 **保存オプションの**します。 **[保存オプションの**] ダイアログ ボックスで、ファイルのすべての文字を表現できるエンコードを選択します: utf-8 など — 選び、 **[ok]** します。