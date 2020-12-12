---
description: 詳細については、「コンパイラエラー C3839」を参照してください。
title: コンパイラ エラー C3839
ms.date: 11/04/2016
f1_keywords:
- C3839
helpviewer_keywords:
- C3839
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
ms.openlocfilehash: 8b34cdd7f09bea924d3e184f7ea639c3f8210ed5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180800"
---
# <a name="compiler-error-c3839"></a>コンパイラ エラー C3839

マネージド型または WinRT 型で配置を変更することはできません

マネージ型または Windows ランタイム型の変数のアラインメントは CLR または Windows ランタイムによって制御され、 [align](../../cpp/align-cpp.md)を使用して変更することはできません。

次の例では C3839 が生成されます。

```cpp
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
