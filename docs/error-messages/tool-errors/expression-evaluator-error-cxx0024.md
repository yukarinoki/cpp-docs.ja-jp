---
title: 式エバリュエーター エラー CXX0024 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0024
dev_langs:
- C++
helpviewer_keywords:
- CXX0024
- CAN0024
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 50a07297ddabf269b003a1f14d967d1187fea96d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="expression-evaluator-error-cxx0024"></a>式エバリュエーター エラー CXX0024
操作には、左辺値が必要があります。  
  
 左辺値ではない式は左辺値を必要とする操作に指定されました。  
  
 (と呼ばれる、代入ステートメントの左側に表示される) 左辺値は、メモリの場所を参照する式です。  
  
 たとえば、`buffer[count]`有効な左辺値は、特定のメモリの場所を指しているためです。 論理比較`zed != 0`メモリ アドレスが TRUE または FALSE に評価されるため、有効な左辺値ではありません。  
  
 このエラーは、can0024 と同じものと同じです。