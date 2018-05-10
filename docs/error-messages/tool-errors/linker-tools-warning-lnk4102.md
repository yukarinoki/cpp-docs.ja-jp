---
title: リンカー ツールの警告 LNK4102 |Microsoft ドキュメント
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
ms.openlocfilehash: 16d13dcbc6d15efd7cf3a7ea0a310de4ab7b0c93
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4102"></a>リンカー ツールの警告 LNK4102
削除するデストラクター 'name';イメージは正しく動作しない可能性があります。  
  
 プログラムは削除するデストラクターをエクスポートしようとしています。 結果として得られる削除は、DLL の境界を越えて、プロセスが所有していないメモリを解放するように発生します。 特定のシンボルが、.def ファイルに表示されていないことと、シンボルがの引数として表示されていないことを確認してください、 **/インポート**または **/export**リンカーのコマンドラインでオプションです。  
  
 C ランタイム ライブラリを再構築する場合は、このメッセージを無視できます。