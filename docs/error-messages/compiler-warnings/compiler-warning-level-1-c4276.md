---
title: コンパイラの警告 (レベル 1) C4276 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4276
dev_langs:
- C++
helpviewer_keywords:
- C4276
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 40a6c85b460e9718a8816598afb016e9c7a493b9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116023"
---
# <a name="compiler-warning-level-1-c4276"></a>コンパイラの警告 (レベル 1) C4276

'function': プロトタイプがありません。パラメーターがないと仮定します。

持つ関数のアドレスを取得するときに、 [_ _stdcall](../../cpp/stdcall.md)呼び出し規約を付ける必要があります、プロトタイプ、コンパイラは関数の装飾名を作成できるようにします。 *関数*装飾名を作成するときに、コンパイラのプロトタイプがありません、この関数はパラメーターを持たない前提としています。