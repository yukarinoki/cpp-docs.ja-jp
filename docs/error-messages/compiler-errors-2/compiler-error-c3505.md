---
title: コンパイラ エラー C3505 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3505
dev_langs:
- C++
helpviewer_keywords:
- C3505
ms.assetid: ed73c99e-93a1-4f3a-bac7-ba7ed5d836e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e0ea8edd3237db2085365450f43b4b955d36f33
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3505"></a>コンパイラ エラー C3505

> タイプ ライブラリを読み込むことができません '*guid*'  
  
C3505 は、32 ビット、x86 ホスト クロス コンパイラ 64 ビット版を実行している場合に発生することが、32 ビット レジストリ ハイブから読み取られた x64 64 ビットのターゲットが、コンパイラが WOW64 の下で実行されているため、コンピューターし、のみことができます。  
  
インポートしようとするタイプ ライブラリの 32 ビットおよび 64 ビットの両方のバージョンを作成してこのエラーを解決し、その両方を登録できます。  ネイティブの 64 ビットのコンパイラは、変更する必要がありますを使用することも、 **vc++ ディレクトリ**64 ビット コンパイラをポイントするための IDE でのプロパティです。  
  
詳細については、次のトピックを参照してください。  
  
-   [方法: 64 ビットの Visual C++ ツールセットをコマンド ラインから有効にする](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)  
  
-   [方法 : Visual C++ プロジェクトを 64 ビット、x64 プラットフォーム用に設定する](../../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)