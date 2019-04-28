---
title: リンカ ツール エラー LNK2033
ms.date: 11/04/2016
f1_keywords:
- LNK2033
helpviewer_keywords:
- LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
ms.openlocfilehash: 7e95823e23215848ff3e5d201171523c9009eb2d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298907"
---
# <a name="linker-tools-error-lnk2033"></a>リンカ ツール エラー LNK2033

'type' の未解決の typeref トークン (トークン)

型の MSIL のメタデータで定義がありません。

LNK2033 はでコンパイルするときに発生する可能性が **/clr:safe** MSIL モジュールの型が参照されている場所、MSIL モジュールの型の事前宣言のみがあるとします。

型は、下で定義する必要がある **/clr:safe**します。

詳細については、「[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。

## <a name="example"></a>例

次の例では、LNK2033 が生成されます。

```
// LNK2033.cpp
// compile with: /clr:safe
// LNK2033 expected
ref class A;
ref class B {};

int main() {
   A ^ aa = nullptr;
   B ^ bb = nullptr;   // OK
};
```