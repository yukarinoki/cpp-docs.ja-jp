---
title: コンパイラ エラー C2410
ms.date: 11/04/2016
f1_keywords:
- C2410
helpviewer_keywords:
- C2410
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
ms.openlocfilehash: e4d30ff0fbca7428fb1dcf252bcad50bd53488d7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205700"
---
# <a name="compiler-error-c2410"></a>コンパイラ エラー C2410

' identifier ': ' context ' のメンバー名があいまいです

この識別子は、このコンテキスト内の複数の構造体または共用体のメンバーです。

エラーの原因となったオペランドで構造体または共用体の指定子を使用してください。 構造体または共用体の指定子は `struct` または `union` 型の識別子です (`typedef` 名または参照されている構造体または共用体と同じ型の変数)。 指定子は、オペランドを使用するために、最初のメンバー選択演算子 (.) の左オペランドである必要があります。
