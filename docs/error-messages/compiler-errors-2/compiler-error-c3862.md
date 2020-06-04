---
title: コンパイラ エラー C3862
ms.date: 11/04/2016
f1_keywords:
- C3862
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
ms.openlocfilehash: 0b9c1e1213949d7d700094caa6687232df881ce6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165484"
---
# <a name="compiler-error-c3862"></a>コンパイラ エラー C3862

> '*function*':/clr: pure または/clr: safe でアンマネージ関数をコンパイルすることはできません

## <a name="remarks"></a>解説

**/Clr: pure**および **/clr: safe**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

**/Clr: pure**または **/clr: safe**を使用したコンパイルでは、ネイティブ (アンマネージ) コードを含まない、MSIL のみのイメージが生成されます。  したがって、 **/clr: pure**または **/clr: safe**コンパイルでは `unmanaged` プラグマを使用できません。

詳細については、「 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md) 」および「[マネージ、アンマネージ](../../preprocessor/managed-unmanaged.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3862 が生成されます。

```cpp
// C3862.cpp
// compile with: /clr:pure /c
#pragma unmanaged
void f() {}   // C3862
```
