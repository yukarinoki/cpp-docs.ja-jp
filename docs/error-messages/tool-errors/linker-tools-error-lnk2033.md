---
description: 詳細については、「リンカツール Error LNK2033」を参照してください。
title: リンカ ツール エラー LNK2033
ms.date: 11/04/2016
f1_keywords:
- LNK2033
helpviewer_keywords:
- LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
ms.openlocfilehash: 46ee94e0aff4379a6d28a508ed1394e90ef9a96d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275647"
---
# <a name="linker-tools-error-lnk2033"></a>リンカ ツール エラー LNK2033

' type ' の未解決の typeref トークン (トークン)

型には、MSIL メタデータの定義がありません。

LNK2033 は、 **/clr: safe** を使用してコンパイルするときに発生する可能性があります。 msil モジュールでは、型が msil モジュールで参照されている型の事前宣言のみが存在します。

型は、 **/clr: safe** で定義する必要があります。

詳細については、「 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。

## <a name="example"></a>例

次の例では、LNK2033 が生成されます。

```cpp
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
