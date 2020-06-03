---
title: コンパイラの警告 (レベル 3) C4638
ms.date: 08/27/2018
f1_keywords:
- C4638
helpviewer_keywords:
- C4638
ms.assetid: 2c07923a-e103-4e40-bd11-fdfed428a5ec
ms.openlocfilehash: 3662116359f906ef6f0a004fada8efd6771d0a0a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174129"
---
# <a name="compiler-warning-level-3-c4638"></a>コンパイラの警告 (レベル 3) C4638

> XML ドキュメントコメントの対象: 不明なシンボル '*symbol*' への参照です

## <a name="remarks"></a>解説

コンパイラがシンボル (*symbol*) を解決できませんでした。 シンボルはコンパイルで有効である必要があります。

## <a name="example"></a>例

次の例では C4638 が生成されます。

```cpp
// C4638.cpp
// compile with: /clr /doc /LD /W3
using namespace System;

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <summary> Text </summary>
   /// <see cref="aSymbolThatAppearsNowhereInMyProject"/>
   // Try the following line instead:
   // /// <see cref="System::Console::WriteLine"/>
   void MyMethod() {}
};   // C4638
```
