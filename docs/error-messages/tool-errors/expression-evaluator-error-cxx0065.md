---
title: 式エバリュエーター エラー CXX0065 |Microsoft Docs
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
ms.openlocfilehash: c100b1edbd36f4384e8deb1abf5b36465e8da479
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024165"
---
# <a name="expression-evaluator-error-cxx0065"></a>式エバリュエーター エラー CXX0065

変数には、スタック フレームが必要です。

式には、現在のスコープ内に存在しますが、まだ作成されていない変数が含まれています。

このエラーは、関数がまだを設定するには関数のスタック フレームのプロローグにステップ インする場合、または関数の終了コードにステップ インする場合に発生することができます。

式を評価する前に設定されているスタック フレームまでプロローグ コードをステップ実行します。

このエラーは、can0065 と同じものと同じです。