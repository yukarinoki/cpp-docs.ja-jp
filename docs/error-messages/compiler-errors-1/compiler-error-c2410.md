---
title: コンパイラ エラー C2410 |Microsoft ドキュメント
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
ms.openlocfilehash: f9c2a2df0941130c4f2416806a05ce0378373eb4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33226448"
---
# <a name="compiler-error-c2410"></a>コンパイラ エラー C2410
'identifier': 'context' であいまいなメンバー名  
  
 識別子は、1 つ以上の構造体または共用体には、このコンテキストのメンバーです。  
  
 エラーが発生したオペランドを構造体または共用体の指定子を使用します。 構造体または共用体の指定子は型の識別子`struct`または`union`(、`typedef`名または構造体または共用体が参照されていると同じ型の変数)。 指定子は、オペランドを使用する最初のメンバー選択演算子 (.) の左オペランドである必要があります。