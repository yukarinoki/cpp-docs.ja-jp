---
description: 詳細については、「リソースコンパイラの致命的なエラー RW1025」を参照してください。
title: リソース コンパイラの致命的なエラー RW1025
ms.date: 11/04/2016
f1_keywords:
- RW1025
helpviewer_keywords:
- RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
ms.openlocfilehash: 40404f8d6dc16b73f93255a18ce8c632cc1e014a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237193"
---
# <a name="resource-compiler-fatal-error-rw1025"></a>リソース コンパイラの致命的なエラー RW1025

外部ヒープメモリの不足

容量が過剰に占有している可能性のあるメモリ常駐ソフトウェアを確認します。 CHKDSK プログラムを使用して、メモリの容量を確認します。

大きなリソースファイルを作成する場合は、リソーススクリプトを2つのファイルに分割します。 2つの .res ファイルを作成した後、MS-DOS コマンドラインを使用してそれらを結合します。

```
copy first.res /b + second.res /b full.res
```
