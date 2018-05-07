---
title: BSCMAKE エラー BK1503 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1503
dev_langs:
- C++
helpviewer_keywords:
- BK1503
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06d4a05a8f2d04c3f8a991d4444b35295408a7b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="bscmake-error-bk1503"></a>BSCMAKE エラー BK1503
'filename' をファイルに書き込みできません [: 理由]  
  
 BSCMAKE では、ブラウザーの 1 つのデータベースへのコンパイル中に生成された .sbr ファイルを結合します。 結果として得られるブラウザー データベースは、64 MB を超えた場合、または入力 (.sbr) ファイルの数が 4092 個を超えた場合は、このエラーが出力されます。  
  
 問題の原因が 4092 以上の .sbr ファイルである場合は、入力ファイルの数を減らす必要があります。 Visual Studio 内でこれには、によって[/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) 、プロジェクト全体、ファイルをファイルごとに再チェックします。  
  
 問題の原因が、64 MB より大きい .bsc ファイルである場合は、入力としての .sbr ファイルの数を減らすと、生成された .bsc ファイルのサイズが低下します。 さらに、/Em (マクロ展開シンボルを除外する)、/El (ローカル変数の除外)、および/Es (システム ファイルを除外する) を使用してブラウザー情報の量を削減する可能性があります。  
  
## <a name="see-also"></a>関連項目  
 [BSCMAKE オプション](../../build/reference/bscmake-options.md)