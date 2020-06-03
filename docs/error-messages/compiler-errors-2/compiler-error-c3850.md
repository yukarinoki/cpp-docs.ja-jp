---
title: コンパイラ エラー C3850
ms.date: 09/05/2018
f1_keywords:
- C3850
helpviewer_keywords:
- C3850
ms.assetid: 028f3a37-f3ad-4ebc-9168-3cdea47524d4
ms.openlocfilehash: 5de7994e8bf46105e94271ab29bf9e27f1da3e76
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165565"
---
# <a name="compiler-error-c3850"></a>コンパイラ エラー C3850

> '*char*': ユニバーサル文字名が無効な文字を指定しています

## <a name="remarks"></a>解説

ユニバーサル文字名として表す文字は、0 ～ 10FFFF の範囲の有効な Unicode コード ポイントを表す必要があります。 ユニバーサル文字名に、D800 ～ DFFF の Unicode サロゲート範囲内の値またはエンコードされたサロゲート ペアを含めてはいけません。 コンパイラは、有効なコード ポイントから自動的にサロゲート ペアを生成します。

C としてコンパイルされたコードでは、ユニバーサル文字名は、0024 (' $ ')、0040 ('\@')、0060 (' ' ') の例外を除いて、0000 ~ 009F の範囲の文字を表すことはできません。

C++ としてコンパイルされたコードでは、文字列または文字リテラル内に、有効な Unicode コード ポイントのユニバーサル文字名を使用できます。 リテラルを除き、0000 ～ 001F または 007F ～ 009F の範囲内 (境界を含む) の制御文字、あるいは、基本ソース文字セットのメンバーを表すユニバーサル文字名を使用してはいけません。  詳細については、「 [Character Sets](../../cpp/character-sets.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3850 を発生させ、その修正方法を示しています。

```cpp
// C3850.cpp
int main() {
   int \u0019 = 0;   // C3850, not in allowed range for an identifier
   const wchar_t * wstr_bad  = L"\UD840DC8A"; // C3850, UCN is surrogate pair
   const wchar_t * wstr_good = L"\U0002008A"; // Okay, UCN is valid code point
}
```
