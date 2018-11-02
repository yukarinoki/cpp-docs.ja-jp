---
title: コンパイラ エラー C3839
ms.date: 11/04/2016
f1_keywords:
- C3839
helpviewer_keywords:
- C3839
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
ms.openlocfilehash: b8382213fbe7cc953dafd9610bfb993ba7837947
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613015"
---
# <a name="compiler-error-c3839"></a>コンパイラ エラー C3839

マネージド型または WinRT 型で配置を変更することはできません

変数の配置では、管理、または Windows ランタイム型が CLR または Windows ランタイムによって制御されでは変更できません[align](../../cpp/align-cpp.md)します。

次の例では C3839 が生成されます。

```
// C3839a.cpp
// compile with: /clr
ref class C
{
public:
   __declspec(align(32)) int m_j; // C3839
};

int main()
{
}
```