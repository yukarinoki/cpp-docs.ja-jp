---
title: 数値演算エラー M6102 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6102
dev_langs:
- C++
helpviewer_keywords:
- M6102
ms.assetid: dbd2241f-6595-431e-9597-d9dbdb3a0ca2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9dc1d1064e6ed18870d60e3a421ceec0c54ca855
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="math-error-m6102"></a>数値演算エラー M6102
denormal  
  
 操作が無効であるある非常に小さい浮動小数点数を生成の有効桁数が失われる。 非正規化浮動小数点例外は通常はマスクされ、それらをトラップして操作の対象にします。  
  
 プログラムは、終了コード 130 で終了します。