---
title: CL オプションの指定順序 |Microsoft ドキュメント
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
ms.openlocfilehash: 165e20eefecd20ad9dec9e01b38c5eaa7926e4eb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372810"
---
# <a name="order-of-cl-options"></a>CL オプションの指定順序
オプションはことができます、/link オプション、最後に発生する必要がありますを除く、CL のコマンド ラインで任意の場所が表示されます。 コンパイラがで指定されたオプションで始まる、[環境変数 CL](../../build/reference/cl-environment-variables.md)し、コマンドラインを左から右に読むと — 検出される順序でコマンド ファイルを処理します。 各オプションは、コマンドラインですべてのファイルに適用されます。 CL では、競合するオプションが発生すると、右端のオプションを使用します。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ コマンド ラインの構文](../../build/reference/compiler-command-line-syntax.md)