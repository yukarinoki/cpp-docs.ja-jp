---
title: 数値演算エラー M6110 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6110
dev_langs:
- C++
helpviewer_keywords:
- M6110
ms.assetid: aac9ae37-6a6d-46e9-85d4-dfe03f1c3e11
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f97918c38f896dd5fccd3abeae86a3104cf80694
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33316057"
---
# <a name="math-error-m6110"></a>数値演算エラー M6110
スタック オーバーフロー  
  
 浮動小数点式には、浮動小数点スタック オーバーフローが発生しました。  
  
 スタック オーバーフロー浮動小数点の例外は、8087/287/387 コプロセッサでサポートされる通常 8 つのレベルに加え、7 つのレベルの上限に達するまでトラップします。  
  
 プログラムは、終了コード 138 で終了します。