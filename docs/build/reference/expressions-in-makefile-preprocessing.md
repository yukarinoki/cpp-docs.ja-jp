---
description: '詳細情報: メイクファイルのプリプロセスの式'
title: メイクファイル プリプロセスの式
ms.date: 11/04/2016
helpviewer_keywords:
- preprocessing makefiles
- expressions [C++], makefile preprocessing
- makefiles, preprocessing
ms.assetid: 37f0f413-97e0-452c-a83f-3c9002c44c92
ms.openlocfilehash: 9b30900db493a2a87e0527e6f3c062185bb4ab43
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200794"
---
# <a name="expressions-in-makefile-preprocessing"></a>メイクファイル プリプロセスの式

**!また** は **!それ以外の場合** は `constantexpression` 、整数定数 (10 進表記または C 言語表記)、文字列定数、またはコマンドで構成されます。 式をグループ化するには、かっこを使用します。 式では、C スタイルの符号付き長整数演算が使用されます。数値は、32ビットの2の補数形式で、-2147483648 ~ 2147483647 の範囲で指定します。

式では、定数値、コマンドからの終了コード、文字列、マクロ、およびファイルシステムパスを操作する演算子を使用できます。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

[メイクファイルのプリプロセッサ演算子](makefile-preprocessing-operators.md)

[プリプロセスでのプログラムの実行](executing-a-program-in-preprocessing.md)

## <a name="see-also"></a>関連項目

[メイクファイルのプリプロセス](makefile-preprocessing.md)
