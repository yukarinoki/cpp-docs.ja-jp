---
title: コンパイラ エラー C3851
ms.date: 09/05/2018
f1_keywords:
- C3851
helpviewer_keywords:
- C3851
ms.assetid: da30c21c-33aa-4439-8fb3-2f5021ea4985
ms.openlocfilehash: 97d9ef1eeeffa0e5a63d2c8ae2428a3fad0ff238
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165586"
---
# <a name="compiler-error-c3851"></a>コンパイラ エラー C3851

> '*char*': ユニバーサル文字名で基本文字セットの文字を指定することはできません

## <a name="remarks"></a>解説

C++ としてコンパイルされるコードでは、基本ソース文字セットの文字を表すユニバーサル文字名を使用できません (文字列リテラルまたは文字リテラルの場合を除く)。 詳細については、「 [Character Sets](../../cpp/character-sets.md)」を参照してください。 C としてコンパイルされたコードでは、-0x7f の範囲内の文字にユニバーサル文字名を使用することはできません。ただし、0x24 (' $ ')、0x40 ('\@')、または 0x60 ('\`') は除きます。

## <a name="example"></a>例

次の例では、C3851 が生成され、その修正方法が表示されます。

```cpp
// C3851.cpp
int main()
{
   int test1_\u0041 = 0;   // C3851, \u0041 = 'A' in basic character set
   int test2_A = 0;        // OK
}
```
