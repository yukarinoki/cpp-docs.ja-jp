---
title: コンパイラ エラー C2441
ms.date: 11/04/2016
f1_keywords:
- C2441
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
ms.openlocfilehash: 4e5d5335717ec77c61069ad08e209f9e1851dc2f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205310"
---
# <a name="compiler-error-c2441"></a>コンパイラ エラー C2441

> '*variable*': __declspec (process) で宣言されたシンボルは、/clr: pure モードでは const である必要があります

## <a name="remarks"></a>解説

**/Clr: pure**および **/clr: safe**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

既定では、変数は、 **/clr: pure**の下のアプリケーションドメインごとに設定されます。 **/Clr: pure**の下で `__declspec(process)` とマークされた変数は、あるアプリケーションドメインで変更され、別のアプリケーションドメインで読み取られた場合、エラーが発生しやすくなります。

したがって、コンパイラは、プロセスごとの変数を **/clr: pure**の下で `const` し、すべてのアプリケーションドメインで読み取り専用にします。

詳細については、「 [process](../../cpp/process.md) and [/Clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。

## <a name="example"></a>例

次の例では、C2441 が生成されます。

```cpp
// C2441.cpp
// compile with: /clr:pure /c
__declspec(process) int i;   // C2441
__declspec(process) const int j = 0;   // OK
```
