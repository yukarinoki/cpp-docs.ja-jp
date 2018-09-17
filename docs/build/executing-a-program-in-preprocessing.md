---
title: プリプロセスでのプログラムの実行 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- program execution [C++]
ms.assetid: 5ecf123a-20e5-40cd-b8d8-dd5a9fdd4b24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e2b0571e67e7c5d24cf31dce6fce548735cad966
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721462"
---
# <a name="executing-a-program-in-preprocessing"></a>プリプロセスでのプログラムの実行

プリプロセス時にコマンドの終了コードを使用するには、角かっこ () 内の任意の引数を持つ、コマンドを指定します。 コマンドが実行される前に、すべてのマクロが展開されます。 NMAKE は、コマンドの仕様を前処理を制御する式の中で使用できるコマンドの終了コードに置き換えます。

## <a name="see-also"></a>関連項目

[メイクファイル プリプロセスの式](../build/expressions-in-makefile-preprocessing.md)