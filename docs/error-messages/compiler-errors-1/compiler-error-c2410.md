---
title: コンパイラ エラー C2410 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2410
dev_langs:
- C++
helpviewer_keywords:
- C2410
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ba4c2b57bcae062ccf811e33cf1deaea45f83737
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052453"
---
# <a name="compiler-error-c2410"></a>コンパイラ エラー C2410

'identifier': 'context' であいまいなメンバー名

識別子は、1 つ以上の構造体またはこのコンテキストで共用体のメンバーです。

エラーの原因となったオペランドでは、構造体または共用体の指定子を使用します。 構造体または共用体の指定子は、型の識別子`struct`または`union`(、`typedef`名または構造体または共用体が参照されていると同じ型の変数)。 指定子は、オペランドを使用する最初のメンバー選択演算子 (.) の左のオペランドである必要があります。