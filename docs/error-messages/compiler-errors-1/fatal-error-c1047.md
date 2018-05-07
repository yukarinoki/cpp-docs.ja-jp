---
title: 致命的なエラー C1047 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1047
dev_langs:
- C++
helpviewer_keywords:
- C1047
ms.assetid: e1bbbc6b-a5bc-4c23-8203-488120a0ec78
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce88321173ee2c8cc286f18d8ab8f1bf5ec98e13
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1047"></a>致命的なエラー C1047
オブジェクトまたはライブラリ ファイル 'file' は、他のオブジェクトよりも古いコンパイラで作成されました。古いオブジェクトおよびライブラリをリビルドしてください  
  
 C1047 は、 **/LTCG** を指定してビルドされたオブジェクト ファイルまたはライブラリがリンクされるときに、それらのオブジェクト ファイルまたはライブラリが、異なるバージョンの Visual C++ ツールセットでビルドされている場合に発生します。  
  
 これは、新しいバージョンのコンパイラの使用を開始するときに、既存のオブジェクト ファイルまたはライブラリをクリーンにリビルドしない場合に発生することがあります。  
  
 C1047 を解決するには、オブジェクト ファイルまたはライブラリをすべてリビルドします。