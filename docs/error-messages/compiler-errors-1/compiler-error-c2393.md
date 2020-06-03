---
title: コンパイラ エラー C2393
ms.date: 11/04/2016
f1_keywords:
- C2393
helpviewer_keywords:
- C2393
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
ms.openlocfilehash: cc3c124f1a4daea0f2517a93c6b354b8233aa5e5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205986"
---
# <a name="compiler-error-c2393"></a>コンパイラ エラー C2393

> '*symbol*': appdomain ごとのシンボルをセグメント '*segment*' に割り当てることはできません

## <a name="remarks"></a>解説

**/Clr: pure**および **/clr: safe**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

[Appdomain](../../cpp/appdomain.md)変数を使用することは、 **/clr: pure**または **/clr: safe**を使用してコンパイルすることを意味します。また、safe または純粋なイメージにデータセグメントを含めることはできません。

詳細については、「 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md) 」を参照してください。

## <a name="example"></a>例

次の例では、C2393 が生成されます。 この問題を解決するには、データセグメントを作成しないでください。

```cpp
// C2393.cpp
// compile with: /clr:pure /c
#pragma data_seg("myseg")
int n = 0;   // C2393
```
