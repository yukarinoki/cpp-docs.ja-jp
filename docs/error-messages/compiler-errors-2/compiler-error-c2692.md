---
title: コンパイラ エラー C2692 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2692
dev_langs:
- C++
helpviewer_keywords:
- C2692
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a02110750a748b5c520df7d202a87957f227a802
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2692"></a>コンパイラ エラー C2692
'function_name': 完全なプロトタイプ関数が C コンパイラで必要な '/clr' オプション  
  
 マネージ コードを .NET 用にコンパイルするときに、C コンパイラには、ANSI 関数宣言が必要です。 さらに、関数がパラメーターをとらない場合必要があります明示的に宣言する必要が`void`パラメーターの型として。