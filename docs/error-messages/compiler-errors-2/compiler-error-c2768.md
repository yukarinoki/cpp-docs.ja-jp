---
description: 詳細については、「コンパイラエラー C2768」を参照してください。
title: コンパイラエラー C2768
ms.date: 11/04/2016
f1_keywords:
- C2768
helpviewer_keywords:
- C2768
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
ms.openlocfilehash: 0911153b9b89996631433d8a19bde9d19fc5f6b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239468"
---
# <a name="compiler-error-c2768"></a>コンパイラエラー C2768

' function ': 明示的なテンプレート引数が不適切に使用しています

コンパイラは、関数定義が関数テンプレートの明示的な特殊化であることが想定されていたか、または関数定義が新しい関数に対して想定されているかどうかを判断できませんでした。

このエラーは、コンパイラ準拠の強化の一環として、Visual Studio .NET 2003 で導入されました。

次の例では、C2768 が生成されます。

```cpp
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
