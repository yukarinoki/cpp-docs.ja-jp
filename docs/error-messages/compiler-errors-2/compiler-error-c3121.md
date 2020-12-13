---
description: 詳細については、「コンパイラエラー C3121」を参照してください。
title: コンパイラ エラー C3121
ms.date: 11/04/2016
f1_keywords:
- C3121
helpviewer_keywords:
- C3121
ms.assetid: 1d3c7be4-d42d-4def-8d53-182c0c5cc237
ms.openlocfilehash: 62f12d17d8696e500cc21084645533825e7f25f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151061"
---
# <a name="compiler-error-c3121"></a>コンパイラ エラー C3121

クラス ' class_name ' の GUID を変更できません

[__Declspec (uuid)](../../cpp/uuid-cpp.md)を使用してクラス ID を変更しようとしました。

たとえば、次のコードでは C3121 が生成されます。

```cpp
// C3121.cpp
[emitidl];
[module(name="MyLibrary")];

[coclass, uuid="00000000-0000-0000-0000-111111111111"]
class __declspec(uuid("00000000-0000-0000-0000-111111111112")) A   // C3121
{
};
int main()
{
}
```
