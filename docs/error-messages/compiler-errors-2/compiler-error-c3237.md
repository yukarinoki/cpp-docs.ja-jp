---
description: 詳細については、「コンパイラエラー C3237」を参照してください。
title: コンパイラ エラー C3237
ms.date: 11/04/2016
f1_keywords:
- C3237
helpviewer_keywords:
- C3237
ms.assetid: 690970c8-e13b-4ff3-96e3-5fd93c4d356b
ms.openlocfilehash: 4cfb42f7b8267623d085794822f2688c8798b2d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307484"
---
# <a name="compiler-error-c3237"></a>コンパイラ エラー C3237

'generic_class' : ジェネリック クラスをカスタム属性にすることはできません

ジェネリック クラスは、ユーザー定義の属性にすることはできません。

## <a name="example"></a>例

次の例では C3237 が生成されます。

```cpp
// C3237.cpp
// compile with: /clr /c
// C3237 expected
using namespace System;

generic <class T>
// Delete the following line to resolve.
[attribute(AttributeTargets::All, AllowMultiple=true)]
public ref class GR {};
```
