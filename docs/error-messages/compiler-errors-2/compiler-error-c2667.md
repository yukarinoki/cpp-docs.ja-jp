---
title: コンパイラ エラー C2667 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2667
dev_langs:
- C++
helpviewer_keywords:
- C2667
ms.assetid: 3c91d9d1-18fa-4e0d-a9ba-984d38980ca3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5d6d14cf04ae399b10cbaa393d9e9fcc7133f274
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095249"
---
# <a name="compiler-error-c2667"></a>コンパイラ エラー C2667

'function': 最適な変換がある数のオーバー ロードのいずれも

オーバー ロードされた関数呼び出しはあいまいであり、解決することはできません。

オーバー ロードされた関数の 1 つの関数呼び出しの実際のパラメーターに一致するように必要な変換は、その他のすべてのオーバー ロードされた関数に必要な変換よりも厳密である必要があります。

関数テンプレートの部分的な順序付けの詳細については、サポート技術情報記事 Q240869 を参照してください。