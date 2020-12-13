---
description: 詳細については、「コンパイラエラー C2410」を参照してください。
title: コンパイラ エラー C2410
ms.date: 11/04/2016
f1_keywords:
- C2410
helpviewer_keywords:
- C2410
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
ms.openlocfilehash: 921ccdcff64bca28c3a771dd0931b8b7abf83e52
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341894"
---
# <a name="compiler-error-c2410"></a>コンパイラ エラー C2410

' identifier ': ' context ' のメンバー名があいまいです

この識別子は、このコンテキスト内の複数の構造体または共用体のメンバーです。

エラーの原因となったオペランドで構造体または共用体の指定子を使用してください。 構造体または共用体の指定子は、型 **`struct`** または **`union`** ( **`typedef`** 参照されている構造体または共用体と同じ型の変数) の識別子です。 指定子は、オペランドを使用するために、最初のメンバー選択演算子 (.) の左オペランドである必要があります。
