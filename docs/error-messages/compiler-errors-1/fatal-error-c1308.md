---
description: '詳細情報: 致命的なエラー C1308'
title: 致命的なエラー C1308
ms.date: 11/04/2016
f1_keywords:
- C1308
helpviewer_keywords:
- C1308
ms.assetid: 46177997-069e-433a-8e20-93c846d78ffd
ms.openlocfilehash: 9d9b8cee128b9ed830c4ba3651ee609d91d42eac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177875"
---
# <a name="fatal-error-c1308"></a>致命的なエラー C1308

アセンブリのリンクはサポートされていません

.Netmodule はリンカーへの入力として許可されていますが、アセンブリが指定されていません。 このエラーは、でコンパイルされたアセンブリをリンクしようとしたときに生成され `/clr:safe` ます。

詳細については、「 [リンカー入力としての .netmodule ファイル](../../build/reference/netmodule-files-as-linker-input.md)」を参照してください。

次の例では、C1308 が生成されます。

```cpp
// C1308.cpp
// compile with: /clr:safe /LD
public ref class MyClass {
public:
   int i;
};
```

それから

```cpp
// C1308b.cpp
// compile with: /clr /link C1308b.obj C1308.dll
// C1308 expected
#using "C1308.dll"
int main() {
   MyClass ^ my = gcnew MyClass();
}
```
