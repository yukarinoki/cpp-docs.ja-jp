---
description: 詳細については、「プリプロセスでのプログラムの実行」を参照してください。
title: プリプロセスでのプログラムの実行
ms.date: 11/04/2016
helpviewer_keywords:
- program execution [C++]
ms.assetid: 5ecf123a-20e5-40cd-b8d8-dd5a9fdd4b24
ms.openlocfilehash: 72743fe1b75e170ce1aa7ea04dd5a0c70440de59
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192370"
---
# <a name="executing-a-program-in-preprocessing"></a>プリプロセスでのプログラムの実行

プリプロセス中にコマンドの終了コードを使用するには、角かっこ ([]) で任意の引数を指定してコマンドを指定します。 コマンドが実行される前に、すべてのマクロが展開されます。 NMAKE はコマンドの指定をコマンドの終了コードに置き換えます。これを式で使用して、前処理を制御できます。

## <a name="see-also"></a>関連項目

[メイクファイルのプリプロセスの式](expressions-in-makefile-preprocessing.md)
