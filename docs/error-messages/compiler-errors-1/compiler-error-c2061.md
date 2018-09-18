---
title: コンパイラ エラー C2061 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2061
dev_langs:
- C++
helpviewer_keywords:
- C2061
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 896fdb21c57e0f558b87ec23e2be309cf49f8095
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057965"
---
# <a name="compiler-error-c2061"></a>コンパイラ エラー C2061

構文エラー: 識別子 'identifier'

コンパイラは、識別子を検出されなかったが必要です。 確認します`identifier`使用する前に宣言されています。

初期化子は、かっこで囲むことができます。 この問題を避けるためには、宣言子をかっこで囲むかを`typedef`します。

コンパイラはクラス テンプレート引数として式を検出したときに、このエラーを発生する可能性がありますも使用して、 [typename](../../cpp/typename.md)には、型をコンパイラに指示します。

次の例では、C2061 が生成されます。

```
// C2061.cpp
// compile with: /c
template < A a >   // C2061
// try the following line instead
// template < typename b >
class c{};
```

C2061 は、インスタンス名を渡す場合に発生する可能性が[typeid](../../windows/typeid-cpp-component-extensions.md):

```
// C2061b.cpp
// compile with: /clr
ref struct G {
   int i;
};

int main() {
   G ^ pG = gcnew G;
   System::Type ^ pType = typeid<pG>;   // C2061
   System::Type ^ pType2 = typeid<G>;   // OK
}
```