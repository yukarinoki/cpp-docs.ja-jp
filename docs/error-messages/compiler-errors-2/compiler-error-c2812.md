---
title: コンパイラ エラー C2812
ms.date: 11/04/2016
f1_keywords:
- C2812
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
ms.openlocfilehash: cec92982646c64e6c5b669df328e4836d4f44df8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202103"
---
# <a name="compiler-error-c2812"></a>コンパイラ エラー C2812

> \#のインポートは、/clr: pure および/clr: safe ではサポートされていません

## <a name="remarks"></a>解説

**/Clr: pure**および **/clr: safe**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

[#import ディレクティブ](../../preprocessor/hash-import-directive-cpp.md)は、 **/clr: pure**および **/clr: safe**ではサポートされていません。 `#import` では、ネイティブコンパイラサポートライブラリを使用する必要があるためです。

## <a name="example"></a>例

次の例では、C2812 が生成されます。

```cpp
// C2812.cpp
// compile with: /clr:pure /c
#import "importlib.tlb"   // C2812
```
