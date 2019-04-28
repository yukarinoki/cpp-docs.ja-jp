---
title: コンパイラ エラー C2768
ms.date: 11/04/2016
f1_keywords:
- C2768
helpviewer_keywords:
- C2768
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
ms.openlocfilehash: 9c0fb8fb0a98830aaf061ba980e7bdd7903f25e1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257622"
---
# <a name="compiler-error-c2768"></a>コンパイラ エラー C2768

'function': 明示的なテンプレート引数の不正な使用

コンパイラは関数の定義が、関数テンプレートの明示的な特殊化になる場合、または関数の定義が、新しい関数になる場合を判断できませんでした。

このエラーは、Visual Studio .NET 2003 でコンパイラ準拠の機能強化の一部として導入されました。

次の例では、C2768 が生成されます。

```
// C2768.cpp
template<typename T>
void f(T) {}

void f<int>(int) {}   // C2768

// an explicit specialization
template<>
void f<int>(int) {}

// global nontemplate function overload
void f(int) {}
```