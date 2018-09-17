---
title: メイクファイル プリプロセスの式 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- preprocessing makefiles
- expressions [C++], makefile preprocessing
- makefiles, preprocessing
ms.assetid: 37f0f413-97e0-452c-a83f-3c9002c44c92
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1070eb01802bd4b39f62ae24519ad6dabca7eb90
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45719007"
---
# <a name="expressions-in-makefile-preprocessing"></a>メイクファイル プリプロセスの式

**!IF**または **!ELSE IF** `constantexpression` (10 進数または C 言語表記) に整数の定数、文字列定数、またはコマンドで構成されます。 グループ式にかっこを使用します。 式を使用して、C スタイル符号付き長整数演算です。番号は 32 ビット 2 の補数形式、範囲 - 2147483648 ~ 2147483647 です。

式は、定数値、コマンド、文字列、マクロ、およびファイル システム パスからの終了コードで機能する演算子を使用できます。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

[メイクファイルのプリプロセッサ演算子](../build/makefile-preprocessing-operators.md)

[プリプロセスでのプログラムの実行](../build/executing-a-program-in-preprocessing.md)

## <a name="see-also"></a>関連項目

[メイクファイルのプリプロセス](../build/makefile-preprocessing.md)