---
title: コンパイラ エラー C2465 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2465
dev_langs:
- C++
helpviewer_keywords:
- C2465
ms.assetid: 65ba2a9f-d95e-4af3-b60b-1ac59a1e307c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f27ea349e4955bc78b2115d3de4622a09290eb22
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060552"
---
# <a name="compiler-error-c2465"></a>コンパイラ エラー C2465

名前のない構造体、共用体、または、列挙型がかっこの式内で定義されました。

匿名構造体、共用体、または列挙型は、かっこで囲まれた式の内部で定義されます。 この定義は関数スコープにおいて意味がないため、これは C++ では無効です。