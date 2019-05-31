---
title: コンパイラ エラー C3872
ms.date: 11/04/2016
f1_keywords:
- C3872
helpviewer_keywords:
- C3872
ms.assetid: 519e95be-5641-40cc-894c-da4819506604
ms.openlocfilehash: bd056a63ab60cd5a2504c6a0bc19e388f71b068b
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450059"
---
# <a name="compiler-error-c3872"></a>コンパイラ エラー C3872

'char': この文字を識別子で使用することはできません

C++ コンパイラは、識別子で許可される文字に関する C++11 標準に従います。 識別子では、特定の範囲の文字とユニバーサル文字名しか使用できません。 識別子の最初の文字に追加の制限が適用されます。 許可される文字の一覧とユニバーサル文字名の範囲については、「 [Identifiers](../../cpp/identifiers-cpp.md)」を参照してください。

識別子で許可される文字の範囲は、C++/CLI コードをコンパイルする場合よりも制限されません。 /Clr を使用してコンパイルされたコード内の識別子が従う必要があります[標準 ECMA 335。共通言語基盤 (CLI)](https://www.ecma-international.org/publications/standards/Ecma-335.htm)します。

次の例では警告 C3872 が生成されます。

```
// C3872.cpp
int main() {
   int abc_\u0040;   // C3872, U+0040 is in base char set
   int abc_\u3001;   // C3872, U+3001 is not in allowed range
   int \u30A2_abc_\u3042;   // OK, UCNs in allowed range
}
```