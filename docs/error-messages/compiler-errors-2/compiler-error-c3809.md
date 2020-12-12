---
description: 詳細については、「コンパイラエラー C3809」を参照してください。
title: コンパイラ エラー C3809
ms.date: 11/04/2016
f1_keywords:
- C3809
helpviewer_keywords:
- C3809
ms.assetid: 37eca584-c20c-464e-8e45-a987214b7ce4
ms.openlocfilehash: 62e7ff06e6ed5bf34861fdbae3f823e19ad5aad4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328199"
---
# <a name="compiler-error-c3809"></a>コンパイラ エラー C3809

'class' : マネージド型または WinRT 型にフレンド関数、クラス、インターフェイスを含めることはできません。

マネージド型と Windows ランタイム型では、フレンドは許可されません。 このエラーを修復するには、マネージド型または Windows ランタイム型内でフレンドを宣言しないようにします。

次の例では、C3809 エラーが生成されます。

```cpp
// C3809a.cpp
// compile with: /clr
ref class A {};

ref class B
{
public:
   friend ref class A;   // C3809
};

int main()
{
}
```
