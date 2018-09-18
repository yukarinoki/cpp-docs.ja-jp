---
title: コンパイラ エラー C3291 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3291
dev_langs:
- C++
helpviewer_keywords:
- C3291
ms.assetid: ed2e9f89-8dbc-4387-bc26-cc955e840858
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0f92c45a70c86da2cf2272cd6a49aaf230ed8a7a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024217"
---
# <a name="compiler-error-c3291"></a>コンパイラ エラー C3291

'default': trivial プロパティの名前にすることはできません

trivial プロパティに `default`という名前を付けることはできません。 詳細については、「 [property](../../windows/property-cpp-component-extensions.md) 」を参照してください。

## <a name="example"></a>例

次の例では C3291 が生成されます。

```
// C3291.cpp
// compile with: /clr /c
ref struct C {
   property System::String ^ default;   // C3291
   property System::String ^ Default;   // OK
};
```