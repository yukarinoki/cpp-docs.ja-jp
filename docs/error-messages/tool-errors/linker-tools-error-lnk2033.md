---
title: リンカ ツール エラー LNK2033 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2033
dev_langs:
- C++
helpviewer_keywords:
- LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6c547b4d35e2e7fe057cdd67f0dad47f58d000c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039994"
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