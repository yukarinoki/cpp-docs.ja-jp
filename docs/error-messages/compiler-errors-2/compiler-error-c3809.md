---
title: コンパイラ エラー C3809
ms.date: 11/04/2016
f1_keywords:
- C3809
helpviewer_keywords:
- C3809
ms.assetid: 37eca584-c20c-464e-8e45-a987214b7ce4
ms.openlocfilehash: 5ff57050980ddb770ea2fcfa4d0be4f42f5ee834
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391895"
---
# <a name="compiler-error-c3809"></a>コンパイラ エラー C3809

'class' : マネージド型または WinRT 型にフレンド関数、クラス、インターフェイスを含めることはできません。

マネージド型と Windows ランタイム型では、フレンドは許可されません。 このエラーを修復するには、マネージド型または Windows ランタイム型内でフレンドを宣言しないようにします。

次の例では、C3809 エラーが生成されます。

```
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