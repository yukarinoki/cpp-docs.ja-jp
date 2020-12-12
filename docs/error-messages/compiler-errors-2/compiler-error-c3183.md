---
description: 詳細については、「コンパイラエラー C3183」を参照してください。
title: コンパイラエラー C3183
ms.date: 11/04/2016
f1_keywords:
- C3183
helpviewer_keywords:
- C3183
ms.assetid: dbd0f020-c739-43c9-947e-9ce21537331b
ms.openlocfilehash: 1a2b761af05ec9285e4222a874e1641466106c9a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174105"
---
# <a name="compiler-error-c3183"></a>コンパイラエラー C3183

マネージド型または WinRT 型 'type' の中で名前のないクラス、構造体またはユニオンを定義することはできません。

マネージド型または WinRT 型に埋め込まれる型の名前を指定する必要があります。

次の例では C3183 エラーが生成されます。

```cpp
// C3183a.cpp
// compile with: /clr /c
ref class Test
{
   ref class
   {  // C3183, delete class or name it
      int a;
      int b;
   };
};
```
