---
description: 詳細については、「コンパイラエラー C3803」を参照してください。
title: コンパイラ エラー C3803
ms.date: 11/04/2016
f1_keywords:
- C3803
helpviewer_keywords:
- C3803
ms.assetid: bad5fb9a-ed9a-4c15-96e7-cf06e200a50d
ms.openlocfilehash: 23b3c9f38470bca471910bb31f7a0acbdf14693e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291559"
---
# <a name="compiler-error-c3803"></a>コンパイラ エラー C3803

' property ': プロパティに、アクセサー ' accessor ' のいずれかと互換性のない型が含まれています。

[プロパティ](../../cpp/property-cpp.md)で定義されたプロパティの型が、アクセサー関数の1つの戻り値の型と一致しません。

次の例では、C3803 が生成されます。

```cpp
// C3803.cpp
struct A
{
   __declspec(property(get=GetIt)) int i;
   char GetIt()
   {
      return 0;
   }

   /*
   // try the following definition instead
   int GetIt()
   {
      return 0;
   }
   */
}; // C3803

int main()
{
}
```
