---
description: '詳細情報: CL オプションの順序'
title: CL オプションの順序 (C++)-Visual Studio
ms.date: 12/14/2018
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
ms.openlocfilehash: bc0290164ff40cf45d8d0a1e9f07e683e408c251
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226416"
---
# <a name="order-of-cl-options"></a>CL オプションの指定順序

オプションは、最後に実行する必要がある/link オプションを除き、CL コマンドライン上の任意の場所に表示できます。 コンパイラは、 [CL 環境変数](cl-environment-variables.md) で指定されたオプションを使用して開始し、コマンドラインを左から右に読み取ります。コマンドファイルは、その順序で処理されます。 各オプションは、コマンドラインのすべてのファイルに適用されます。 CL で競合するオプションが検出されると、右端のオプションが使用されます。

## <a name="see-also"></a>関連項目

[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
