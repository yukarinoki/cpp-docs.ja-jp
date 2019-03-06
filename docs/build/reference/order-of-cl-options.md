---
title: CL オプションの指定順序
ms.date: 11/04/2016
f1_keywords:
- cl
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
ms.openlocfilehash: d87e3214d4829f81258acd00abebced34d7d969d
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423691"
---
# <a name="order-of-cl-options"></a>CL オプションの指定順序

オプションは、最後に発生する必要があります/link オプションを除く、CL のコマンド ラインで任意の場所に表示できます。 コンパイラで指定されたオプションから始まります、[環境変数 CL](../../build/reference/cl-environment-variables.md)左から右に、コマンドラインを読むと、それらが発生した順序でコマンド ファイルを処理します。 各オプションは、コマンドラインですべてのファイルに適用されます。 CL では、競合するオプションが検出されると、右端のオプションを使用します。

## <a name="see-also"></a>関連項目

[コンパイラ コマンド ラインの構文](../../build/reference/compiler-command-line-syntax.md)
