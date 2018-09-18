---
title: リンカー ツールの警告 LNK4102 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4102
dev_langs:
- C++
helpviewer_keywords:
- LNK4102
ms.assetid: bfd1b17e-05c7-4bc2-80d6-2888b1a425b2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9daaffc4ddfa9a869c2e60e2c05dc2b7e296d94b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031862"
---
# <a name="linker-tools-warning-lnk4102"></a>リンカー ツールの警告 LNK4102

削除するデストラクター 'name';イメージは正しく動作しない可能性があります。

プログラムが削除するデストラクターをエクスポートしようとしました。 Delete は、DLL 境界を越えて、プロセスが所有していないメモリを解放するように発生します。 .Def ファイルで指定されたシンボルが表示されていないことと、シンボルがの引数として表示されていないことを確認、 **/インポート**または **/export**リンカー コマンドラインのオプション。

C ランタイム ライブラリを再構築する場合は、このメッセージを無視できます。