---
title: コンパイラ エラー C2158
ms.date: 11/04/2016
f1_keywords:
- C2158
helpviewer_keywords:
- C2158
ms.assetid: 39028899-e95c-4809-8e65-6111118641ee
ms.openlocfilehash: a84c803d45184c19bab0f855ae1eb33744c4e02d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174875"
---
# <a name="compiler-error-c2158"></a>コンパイラ エラー C2158

'type': #pragma make_public ディレクティブは、現在テンプレートでないネイティブの型にのみサポートされています

[make_public](../../preprocessor/make-public.md) プラグマは、ネイティブの非テンプレート型にのみ適用できます。

## <a name="example"></a>例

次の例では C2158 が生成されます。

```
// C2158.cpp
// compile with: /clr /c
ref class A {};
#pragma make_public(A)   // C2158

template< typename T >
class B {};
#pragma make_public(B)   // C2158
#pragma make_public(B<int>)   // C2158

void C () {}
#pragma make_public(C)   // C2158

class D {};
#pragma make_public(D)   // OK
```