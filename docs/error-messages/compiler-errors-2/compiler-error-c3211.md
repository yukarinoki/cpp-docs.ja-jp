---
description: 詳細については、「コンパイラエラー C3211」を参照してください。
title: コンパイラ エラー C3211
ms.date: 11/04/2016
f1_keywords:
- C3211
helpviewer_keywords:
- C3211
ms.assetid: 85e33fed-3b59-4315-97e6-20d31c6a985a
ms.openlocfilehash: eaa495c8759194ed89322bd63298ea186057e8c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173858"
---
# <a name="compiler-error-c3211"></a>コンパイラ エラー C3211

'explicit specialization': 明示的特殊化は、部分的特殊化の構文を使用しています。代わりに、テンプレート <> を使用してください

明示的特殊化の形式が正しくありません。

次の例では C3211 が生成されます。

```cpp
// C3211.cpp
// compile with: /LD
template<class T>
struct s;

template<class T>
// use the following line instead
// template<>
struct s<int>{};   // C3211
```
