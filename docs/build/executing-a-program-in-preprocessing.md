---
title: プリプロセスでのプログラムの実行
ms.date: 11/04/2016
helpviewer_keywords:
- program execution [C++]
ms.assetid: 5ecf123a-20e5-40cd-b8d8-dd5a9fdd4b24
ms.openlocfilehash: a78c9ddc498383d460e617bc26f4e70eb7275eec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577425"
---
# <a name="executing-a-program-in-preprocessing"></a>プリプロセスでのプログラムの実行

プリプロセス時にコマンドの終了コードを使用するには、角かっこ () 内の任意の引数を持つ、コマンドを指定します。 コマンドが実行される前に、すべてのマクロが展開されます。 NMAKE は、コマンドの仕様を前処理を制御する式の中で使用できるコマンドの終了コードに置き換えます。

## <a name="see-also"></a>関連項目

[メイクファイル プリプロセスの式](../build/expressions-in-makefile-preprocessing.md)