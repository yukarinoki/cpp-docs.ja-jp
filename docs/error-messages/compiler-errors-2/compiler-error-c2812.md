---
description: 詳細については、「コンパイラエラー C2812」を参照してください。
title: コンパイラ エラー C2812
ms.date: 11/04/2016
f1_keywords:
- C2812
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
ms.openlocfilehash: d59105397ae773c2a46b04a64eb50da3055c3a4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278424"
---
# <a name="compiler-error-c2812"></a>コンパイラ エラー C2812

> \#インポートは、/clr: pure および/clr: safe ではサポートされていません

## <a name="remarks"></a>解説

**/Clr: pure** および **/clr: safe** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

[#import ディレクティブ](../../preprocessor/hash-import-directive-cpp.md) は、 **/clr: pure** および **/clr: safe** ではサポートされていません。これは、 `#import` ネイティブコンパイラサポートライブラリを使用する必要があるためです。

## <a name="example"></a>例

次の例では、C2812 が生成されます。

```cpp
// C2812.cpp
// compile with: /clr:pure /c
#import "importlib.tlb"   // C2812
```
