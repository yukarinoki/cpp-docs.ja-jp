---
title: コンパイラ エラー C2130
ms.date: 11/04/2016
f1_keywords:
- C2130
helpviewer_keywords:
- C2130
ms.assetid: c6fd5a7e-8f28-4f67-99d1-95a13b0dff90
ms.openlocfilehash: aee0931926cad2ac30631c152aeb94bfd24befd2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397602"
---
# <a name="compiler-error-c2130"></a>コンパイラ エラー C2130

\#行が 'token' が見つかりません、ファイル名を含む文字列が必要です。

オプションのファイル名トークンの後に続く [#line](../../preprocessor/hash-line-directive-c-cpp.md) `linenumber` は文字列である必要があります。

次の例では C2130 が生成されます。

```
// C2130.cpp
int main() {
   #line 1000 test   // C2130
   #line 1000 "test"   // OK
}
```