---
title: コンパイラ エラー C3625
ms.date: 11/04/2016
f1_keywords:
- C3625
helpviewer_keywords:
- C3625
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
ms.openlocfilehash: 08ad1d09cb9149811566f67a585a718340254de9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635396"
---
# <a name="compiler-error-c3625"></a>コンパイラ エラー C3625

'native_type': ネイティブ型はマネージド型または WinRT 型の 'type' から派生することはできません

マネージド クラスまたは WinRT クラスからネイティブ クラスを継承できません。 詳細については、次を参照してください。[クラスと構造体](../../windows/classes-and-structs-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では警告 C3625 が生成されます。

```
// C3625.cpp
// compile with: /clr /c
ref class B {};
class D : public B {};   // C3625 cannot inherit from a managed class
```
