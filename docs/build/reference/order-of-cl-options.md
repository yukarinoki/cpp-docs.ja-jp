---
title: CL オプションの指定順序 |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ffe9a440396df14823775db335e52bca6cacdb3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725024"
---
# <a name="order-of-cl-options"></a>CL オプションの指定順序

オプションは、最後に発生する必要があります/link オプションを除く、CL のコマンド ラインで任意の場所に表示できます。 コンパイラで指定されたオプションから始まります、[環境変数 CL](../../build/reference/cl-environment-variables.md)左から右に、コマンドラインを読むと、それらが発生した順序でコマンド ファイルを処理します。 各オプションは、コマンドラインですべてのファイルに適用されます。 CL では、競合するオプションが検出されると、右端のオプションを使用します。

## <a name="see-also"></a>関連項目

[コンパイラ コマンド ラインの構文](../../build/reference/compiler-command-line-syntax.md)