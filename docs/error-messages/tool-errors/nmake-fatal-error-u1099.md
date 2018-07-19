---
title: NMAKE の致命的なエラー U1099 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1099
dev_langs:
- C++
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7be09691de4212d07b1452ffe33725a3978fc053
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322105"
---
# <a name="nmake-fatal-error-u1099"></a>NMAKE の致命的なエラー U1099
スタック オーバーフロー  
  
 処理中のメイクファイルが複雑すぎるため、現在のスタック割り当て (nmake の)。 NMAKE は、0x3000 (12 K) の割り当てがあります。  
  
 NMAKE のスタック割り当てを増やすを実行、 [editbin/stack](../../build/reference/stack.md)ユーティリティの大きなスタック オプションを使用します。  
  
 **editbin/STACK:reserve (nmake の)。EXE**  
  
 ここで*予約*数値を現在のスタック割り当て (nmake の) を超えています。