---
title: コンパイラ エラー C2441
ms.date: 11/04/2016
f1_keywords:
- C2441
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
ms.openlocfilehash: 7fcf333f62253eb676c0f0ada1c927ab962ae1ca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551256"
---
# <a name="compiler-error-c2441"></a>コンパイラ エラー C2441

> '*変数*': __declspec(process) と共に宣言されたシンボルは/clr では定数である必要があります: ピュア モード

## <a name="remarks"></a>Remarks

**/Clr: 純粋な**と **/clr:safe**コンパイラ オプションは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 でサポートされていません。

既定では、変数は、アプリケーション ドメインごと **/clr: 純粋な**します。 変数がマークされている`__declspec(process)` **/clr: 純粋な**が 1 つのアプリケーション ドメインで変更され、別の読み取りの場合、エラー傾向があります。

コンパイラが 1 つの変数をするプロセスはそのため、 `const`  **/clr: 純粋な**、すべてのアプリケーション ドメインでのみそれらの読み取りを行う。

詳細については、次を参照してください。[プロセス](../../cpp/process.md)と[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)します。

## <a name="example"></a>例

次の例では、C2441 が生成されます。

```cpp
// C2441.cpp
// compile with: /clr:pure /c
__declspec(process) int i;   // C2441
__declspec(process) const int j = 0;   // OK
```