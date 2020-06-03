---
title: CL オプションの順序 (C++)-Visual Studio
ms.date: 12/14/2018
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
ms.openlocfilehash: 6c57a68dd15d82a9d6a01bfe145374bda6eb1510
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439201"
---
# <a name="order-of-cl-options"></a>CL オプションの指定順序

オプションは、最後に実行する必要がある/link オプションを除き、CL コマンドライン上の任意の場所に表示できます。 コンパイラは、 [CL 環境変数](cl-environment-variables.md)で指定されたオプションを使用して開始し、コマンドラインを左から右に読み取ります。コマンドファイルは、その順序で処理されます。 各オプションは、コマンドラインのすべてのファイルに適用されます。 CL で競合するオプションが検出されると、右端のオプションが使用されます。

## <a name="see-also"></a>参照

[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
