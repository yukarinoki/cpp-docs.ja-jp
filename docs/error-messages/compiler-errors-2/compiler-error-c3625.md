---
description: 詳細については、「コンパイラエラー C3625」を参照してください。
title: コンパイラ エラー C3625
ms.date: 11/04/2016
f1_keywords:
- C3625
helpviewer_keywords:
- C3625
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
ms.openlocfilehash: ee28175eac35e05ca2a4620dffa84cf995e053a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144496"
---
# <a name="compiler-error-c3625"></a>コンパイラ エラー C3625

'native_type': ネイティブ型はマネージド型または WinRT 型の 'type' から派生することはできません

マネージド クラスまたは WinRT クラスからネイティブ クラスを継承できません。 詳細については、「[クラスと構造体](../../extensions/classes-and-structs-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では警告 C3625 が生成されます。

```cpp
// C3625.cpp
// compile with: /clr /c
ref class B {};
class D : public B {};   // C3625 cannot inherit from a managed class
```
