---
title: リンカー ツールの警告 LNK4248 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4248
dev_langs:
- C++
helpviewer_keywords:
- LNK4248
ms.assetid: e40523ff-e3cb-4ba6-ab79-23f0f339f6cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ff2c3edd942eb0d38d16a6986044f90358c4e9f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062164"
---
# <a name="linker-tools-warning-lnk4248"></a>リンカー ツールの警告 LNK4248

'type' の未解決の typeref トークン (トークン)イメージは動作しない可能性があります。

型の MSIL のメタデータで定義がありません。

LNK4248 は、MSIL モジュールの型の事前宣言のみがある場合に発生することができます (でコンパイルされた **/clr**) MSIL モジュールの定義を持つネイティブ モジュールとリンクしている場合や、MSIL モジュールの型が参照されている場所型。

このような状況では、リンカーは、MSIL のメタデータでネイティブ型の定義を提供し、これが正しい動作が提供します。

ただし、事前宣言が CLR 型の場合、リンカーのネイティブな型定義できません。

詳細については、「[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. MSIL モジュールの種類の定義を提供します。

## <a name="example"></a>例

次の例では、LNK4248 が生成されます。 解決するのには、構造体 A を定義します。

```
// LNK4248.cpp
// compile with: /clr /W1
// LNK4248 expected
struct A;
void Test(A*){}

int main() {
   Test(0);
}
```

## <a name="example"></a>例

次の例には、型の前方の定義があります。

```
// LNK4248_2.cpp
// compile with: /clr /c
class A;   // provide a definition for A here to resolve
A * newA();
int valueA(A * a);

int main() {
   A * a = newA();
   return valueA(a);
}
```

## <a name="example"></a>例

次の例では、LNK4248 が生成されます。

```
// LNK4248_3.cpp
// compile with: /c
// post-build command: link LNK4248_2.obj LNK4248_3.obj
class A {
public:
   int b;
};

A* newA() {
   return new A;
}

int valueA(A * a) {
   return (int)a;
}
```