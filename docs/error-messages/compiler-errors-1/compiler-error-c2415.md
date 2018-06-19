---
title: コンパイラ エラー C2415 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2415
dev_langs:
- C++
helpviewer_keywords:
- C2415
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ad06cdf891c9b958f6cf08e724f4003a8507c2d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198548"
---
# <a name="compiler-error-c2415"></a>コンパイラ エラー C2415
オペランドの型が無効です。  
  
 このオペコードは、この型のオペランドを使いません。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  オペコードに使われているオペランドの数が正しくありません。 アセンブリ言語のリファレンス マニュアルで、正しいオペランド数を調べてください。  
  
2.  最近のプロセッサでは、別の型を使用する命令もサポートされます。 調整、 [/arch (最小限の CPU アーキテクチャ)](../../build/reference/arch-minimum-cpu-architecture.md)それ以降のプロセッサを使用するオプションです。