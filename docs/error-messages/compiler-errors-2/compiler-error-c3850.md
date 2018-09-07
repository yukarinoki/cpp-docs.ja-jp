---
title: コンパイラ エラー C3850 |Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3850
dev_langs:
- C++
helpviewer_keywords:
- C3850
ms.assetid: 028f3a37-f3ad-4ebc-9168-3cdea47524d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: daa4b6128672b47891c563acfd4399952a17e7e6
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894539"
---
# <a name="compiler-error-c3850"></a>コンパイラ エラー C3850

> '*char*': ユニバーサル文字名に無効な文字を指定します

## <a name="remarks"></a>Remarks

ユニバーサル文字名として表す文字は、0 ～ 10FFFF の範囲の有効な Unicode コード ポイントを表す必要があります。 ユニバーサル文字名に、D800 ～ DFFF の Unicode サロゲート範囲内の値またはエンコードされたサロゲート ペアを含めてはいけません。 コンパイラは、有効なコード ポイントから自動的にサロゲート ペアを生成します。

C としてコンパイルされたコードでユニバーサル文字名を表さない可能性が 0000 ~ 009 f の範囲内の文字が、0024 ('$') の例外の包括的 0040 ('\@') および 0060 (' ')。

C++ としてコンパイルされたコードでは、文字列または文字リテラル内に、有効な Unicode コード ポイントのユニバーサル文字名を使用できます。 リテラルを除き、0000 ～ 001F または 007F ～ 009F の範囲内 (境界を含む) の制御文字、あるいは、基本ソース文字セットのメンバーを表すユニバーサル文字名を使用してはいけません。  詳細については、次を参照してください。[文字セット](../../cpp/character-sets.md)します。

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