---
description: 詳細については、「コンパイラエラー C3369」を参照してください。
title: コンパイラ エラー C3369
ms.date: 11/04/2016
f1_keywords:
- C3369
helpviewer_keywords:
- C3369
ms.assetid: c6ceb9cb-3df9-4334-9a5c-d16db351d476
ms.openlocfilehash: 0391dbd7fe80daf93c8070253181c40fb805fa82
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150801"
---
# <a name="compiler-error-c3369"></a>コンパイラ エラー C3369

'module name': 既に定義された idl_module

DLL の定義に [idl_module](../../windows/attributes/idl-module.md) を使用できるのは、プログラム内で 1 回だけです。

次の例では C3369 が生成されます。

```cpp
// C3369.cpp
// compile with: /c
[idl_module(name="name1", dllname="x.dll")]; // C3369
[idl_module(name="name1", dllname="x.dll")];
```
