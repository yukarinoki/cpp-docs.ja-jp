---
title: コンパイラ エラー C2441
ms.date: 11/04/2016
f1_keywords:
- C2441
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
ms.openlocfilehash: aa55392e9f58caa4292cf5f96ef97f65a53bf913
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87207954"
---
# <a name="compiler-error-c2441"></a>コンパイラ エラー C2441

> '*variable*': __declspec (process) で宣言されたシンボルは、/clr: pure モードでは const である必要があります

## <a name="remarks"></a>解説

**/Clr: pure**および **/clr: safe**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

既定では、変数は、 **/clr: pure**の下のアプリケーションドメインごとに設定されます。 `__declspec(process)` **/Clr: pure**の下でマークされた変数は、あるアプリケーションドメインで変更され、別のアプリケーションドメインで読み取られた場合、エラーが発生しやすくなります。

したがって、コンパイラは、プロセスごとの変数を **`const`** **/clr: pure**の下に強制的に適用し、すべてのアプリケーションドメインで読み取り専用にします。

詳細については、「 [process](../../cpp/process.md) and [/Clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。

## <a name="example"></a>例

次の例では、C2441 が生成されます。

```cpp
// C2441.cpp
// compile with: /clr:pure /c
__declspec(process) int i;   // C2441
__declspec(process) const int j = 0;   // OK
```
