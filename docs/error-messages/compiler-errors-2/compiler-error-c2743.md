---
title: コンパイラ エラー C2743
ms.date: 11/04/2016
f1_keywords:
- C2743
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
ms.openlocfilehash: 03cd7c13e093be5073b3df7e7cf29dda870bc47a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228931"
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