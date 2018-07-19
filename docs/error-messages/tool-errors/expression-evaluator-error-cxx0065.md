---
title: 式エバリュエーター エラー CXX0065 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0065
dev_langs:
- C++
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78c25c9c6bde27219f10e4047dc7a6ab416f55d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33297538"
---
# <a name="expression-evaluator-error-cxx0065"></a>式エバリュエーター エラー CXX0065
変数には、スタック フレームが必要です。  
  
 式には、現在のスコープ内に存在するが、まだ作成されていない変数が含まれています。  
  
 このエラーは、関数がされていない関数では、スタック フレームのセットアップのプロローグにステップ インするとき、または関数の終了コードにステップ インした場合に発生することができます。  
  
 式を評価する前に設定されているスタック フレームまでプロローグ コードをステップ実行します。  
  
 このエラーは、can0065 と同じものと同じです。