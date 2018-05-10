---
title: 式エバリュエーター エラー CXX0015 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0015
dev_langs:
- C++
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 945dbda4759fa2989acb0411d1a3216a5e9a036c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="expression-evaluator-error-cxx0015"></a>式エバリュエーター エラー CXX0015
式が複雑すぎます (スタック オーバーフロー)  
  
 入力された式は、複雑すぎるか、C の式エバリュエーターを使用可能なストレージの量に対してレベルが深すぎます入れ子になったでした。  
  
 オーバーフローは、通常、多数の保留中の計算により発生します。  
  
 その他の部分式を計算するを待たずにするのではなくが検出すると、式の各コンポーネントを評価できるように、式のレイアウトを変更します。  
  
 式を複数のコマンドに分割します。  
  
 このエラーは、can0015 と同じものと同じです。