---
description: 詳細については、「コンパイラの警告 C4936」を参照してください。
title: コンパイラの警告 C4936
ms.date: 11/04/2016
f1_keywords:
- C4936
helpviewer_keywords:
- C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
ms.openlocfilehash: e12cb789d3d008ec61672591cde78f1b7dc61da6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314985"
---
# <a name="compiler-warning-c4936"></a>コンパイラの警告 C4936

> この __declspec は、/clr または /clr:pure でコンパイルされるときのみサポートされます

## <a name="remarks"></a>解説

**/Clr: pure** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

**`__declspec`** 修飾子が使用されましたが **`__declspec`** 、この修飾子は、いずれかの [/clr](../../build/reference/clr-common-language-runtime-compilation.md)オプションでコンパイルされた場合にのみ有効です。

詳細については、「 [appdomain](../../cpp/appdomain.md) 」および「 [process](../../cpp/process.md)」を参照してください。

C4936 は、常にエラーとして表示されます。  [warning](../../preprocessor/warning.md) プラグマを使用して、C4936 を無効にすることができます。

## <a name="example"></a>例

次の例では C4936 が生成されます。

```cpp
// C4936.cpp
// compile with: /c
// #pragma warning (disable : 4936)
__declspec(process) int i;   // C4936
__declspec(appdomain) int j;   // C4936
```
