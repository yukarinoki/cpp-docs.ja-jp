---
description: '詳細情報: コンパイラの警告 (レベル 1) C4165'
title: コンパイラの警告 (レベル 1) C4165
ms.date: 11/04/2016
f1_keywords:
- C4165
helpviewer_keywords:
- C4165
ms.assetid: f5bed515-2290-4f88-8dab-b45d95fe26ef
ms.openlocfilehash: 7b82db7421493b1687b35e61da988b68a577e8a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267041"
---
# <a name="compiler-warning-level-1-c4165"></a>コンパイラの警告 (レベル 1) C4165

' HRESULT ' は ' bool ' に変換されています。これは必要なものですか?

[If](../../cpp/if-else-statement-cpp.md)ステートメントで hresult を使用する場合、hresult として変数を明示的にテストしない限り、hresult は[ブール](../../cpp/bool-cpp.md)値に変換されます。 既定では、この警告はオフに設定されています。

## <a name="example"></a>例

次の例では、C4165 が生成されます。

```cpp
// C4165.cpp
// compile with: /W1
#include <windows.h>
#pragma warning(1:4165)

extern HRESULT hr;
int main() {
   if (hr) {
   // try either of the following ...
   // if (FAILED(hr)) { // C4165 expected
   // if (hr != S_OK) {
   }
}
```
