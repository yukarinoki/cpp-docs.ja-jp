---
title: 前処理でプログラムを実行する |Microsoft ドキュメント
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
ms.openlocfilehash: da87a87a2e97736d202b7ddb9be2dbec54fed44d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367200"
---
# <a name="executing-a-program-in-preprocessing"></a>プリプロセスでのプログラムの実行
プリプロセス時にコマンドの終了コードを使用するには、角かっこ () 内の任意の引数を指定して、コマンドを指定します。 すべてのマクロは、コマンドを実行前に展開します。 (Nmake の) は、コマンドの仕様を前処理を制御する式の中で使用できるコマンドの終了コードに置き換えます。  
  
## <a name="see-also"></a>関連項目  
 [メイクファイル プリプロセスの式](../build/expressions-in-makefile-preprocessing.md)