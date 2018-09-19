---
title: コンパイラの警告 (レベル 1) C4116 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4116
dev_langs:
- C++
helpviewer_keywords:
- C4116
ms.assetid: 25434ef3-061e-4252-91a5-0fe2a4b2ffb3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5f91892bd28733761c187705b8f576007862027b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080702"
---
# <a name="compiler-warning-level-1-c4116"></a>コンパイラの警告 (レベル 1) C4116

かっこで囲まれた名前のない型の定義

構造体、共用体、または名前のない列挙型は、かっこで囲まれた式で定義されます。 型定義は、無意味です。

C の関数呼び出しでは、定義はグローバル スコープを持ちます。 C++ の関数呼び出しでは、定義は呼び出される関数と同じスコープを持ちます。