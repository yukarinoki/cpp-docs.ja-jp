---
title: コンパイラ エラー C3803
ms.date: 11/04/2016
f1_keywords:
- C3803
helpviewer_keywords:
- C3803
ms.assetid: bad5fb9a-ed9a-4c15-96e7-cf06e200a50d
ms.openlocfilehash: f6c255ec18d6dcf94f3ec022f09b173c2c66a1dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400098"
---
# <a name="compiler-error-c3803"></a>コンパイラ エラー C3803

'property': プロパティのアクセサー 'accessor' のいずれかの互換性のない型には

定義されているプロパティの型[プロパティ](../../cpp/property-cpp.md)のアクセサー関数の 1 つの戻り値の型と一致しません。

次の例では、C3803 が生成されます。

```
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