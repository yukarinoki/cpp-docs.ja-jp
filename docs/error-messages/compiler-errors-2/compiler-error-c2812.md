---
title: コンパイラ エラー C2812
ms.date: 11/04/2016
f1_keywords:
- C2812
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
ms.openlocfilehash: 88b071f38cf41db9c929d25ffd526b3f2b7ca468
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531821"
---
# <a name="compiler-error-c2812"></a>コンパイラ エラー C2812

> \#インポートは/clr でサポートされていません:/clr:pure および/clr:safe

## <a name="remarks"></a>Remarks

**/Clr: 純粋な**と **/clr:safe**コンパイラ オプションは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 でサポートされていません。

[#import ディレクティブ](../../preprocessor/hash-import-directive-cpp.md)はサポートされていません **/clr: 純粋な**と **/clr:safe**ため`#import`ネイティブ コンパイラ サポート ライブラリの使用が必要です。

## <a name="example"></a>例

次の例では、C2812 が生成されます。

```cpp
// C2812.cpp
// compile with: /clr:pure /c
#import "importlib.tlb"   // C2812
```