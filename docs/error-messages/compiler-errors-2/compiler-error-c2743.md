---
title: コンパイラ エラー C2743 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2743
dev_langs:
- C++
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4217a1e7a8475362c654ac34b6a345846341ec35
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056491"
---
# <a name="compiler-error-c2743"></a>コンパイラ エラー C2743

'type': _ _clrcall デストラクターまたはコピー コンス トラクターでネイティブをキャッチすることはできません

コンパイルされたモジュール **/clr**ネイティブ型と型のデストラクターまたはコピー コンス トラクターの使用の例外をキャッチしようとしています。`__clrcall`呼び出し規約。

コンパイルされたときに **/clr**、例外処理をネイティブ型でメンバー関数を想定[_ _cdecl](../../cpp/cdecl.md)および not [_ _clrcall](../../cpp/clrcall.md)します。 ネイティブ型を使用してメンバー関数で`__clrcall`でコンパイルされたモジュールの呼び出し規約をキャッチできない **/clr**します。

詳細については、「[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。

## <a name="example"></a>例

次の例では、C2743 が生成されます。

```
// C2743.cpp
// compile with: /clr
public struct S {
   __clrcall ~S() {}
};

public struct T {
   ~T() {}
};

int main() {
   try {}
   catch(S) {}   // C2743
   // try the following line instead
   // catch(T) {}

   try {}
   catch(S*) {}   // OK
}
```