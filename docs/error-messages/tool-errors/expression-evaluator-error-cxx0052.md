---
title: 式エバリュエーター エラー CXX0052 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0052
dev_langs:
- C++
helpviewer_keywords:
- CXX0052
- CAN0052
ms.assetid: 5060d479-d0a4-4682-b858-c8b9a4f324e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c9f4b6fb0db87a77f433775fedea9880f3f24bd9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="expression-evaluator-error-cxx0052"></a>式エバリュエーター エラー CXX0052
メンバー関数がありません。  
  
 メンバー関数は、ブレークポイントとして指定されましたが、見つかりませんでした。 インライン展開されている関数にブレークポイントを設定と、このエラーが発生することができます。  
  
 使用してファイルを再コンパイル インライン展開を強制的に切断 (/Ob0) この関数にブレークポイントを設定します。  
  
 式には、定義されていない関数が呼び出されます。  
  
 このエラーは、can0052 と同じものと同じです。