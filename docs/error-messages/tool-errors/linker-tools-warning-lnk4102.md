---
title: リンカー ツールの警告 LNK4102
ms.date: 11/04/2016
f1_keywords:
- LNK4102
helpviewer_keywords:
- LNK4102
ms.assetid: bfd1b17e-05c7-4bc2-80d6-2888b1a425b2
ms.openlocfilehash: 0f9c8649988dd3056e98730ac4b02022a8c9dd51
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643093"
---
# <a name="linker-tools-warning-lnk4102"></a>リンカー ツールの警告 LNK4102

削除するデストラクター 'name';イメージは正しく動作しない可能性があります。

プログラムが削除するデストラクターをエクスポートしようとしました。 Delete は、DLL 境界を越えて、プロセスが所有していないメモリを解放するように発生します。 .Def ファイルで指定されたシンボルが表示されていないことと、シンボルがの引数として表示されていないことを確認、 **/インポート**または **/export**リンカー コマンドラインのオプション。

C ランタイム ライブラリを再構築する場合は、このメッセージを無視できます。