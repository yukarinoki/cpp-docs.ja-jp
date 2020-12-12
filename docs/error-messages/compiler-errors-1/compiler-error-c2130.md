---
description: 詳細については、「コンパイラエラー C2130」を参照してください。
title: コンパイラ エラー C2130
ms.date: 11/04/2016
f1_keywords:
- C2130
helpviewer_keywords:
- C2130
ms.assetid: c6fd5a7e-8f28-4f67-99d1-95a13b0dff90
ms.openlocfilehash: 78e7b756d5902562c6093e3f26f9934e87e732ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323182"
---
# <a name="compiler-error-c2130"></a>コンパイラ エラー C2130

\#行にはファイル名を含む文字列が必要ですが、' token ' が見つかりました。

オプションのファイル名トークンの後に続く [#line](../../preprocessor/hash-line-directive-c-cpp.md) `linenumber` は文字列である必要があります。

次の例では C2130 が生成されます。

```cpp
// C2130.cpp
int main() {
   #line 1000 test   // C2130
   #line 1000 "test"   // OK
}
```
