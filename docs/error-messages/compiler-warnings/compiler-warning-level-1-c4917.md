---
title: コンパイラの警告 (レベル 1) C4917
ms.date: 11/04/2016
f1_keywords:
- C4917
helpviewer_keywords:
- C4917
ms.assetid: c05e2610-4a5d-4f4b-a99b-c15fd7f1d5f1
ms.openlocfilehash: c7a2d72b429f762e476286093c7f273a9a546cb6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174675"
---
# <a name="compiler-warning-level-1-c4917"></a>コンパイラの警告 (レベル 1) C4917

' 宣言子 ': GUID はクラス、インターフェイス、または名前空間にのみ関連付けることができます

[クラス](../../cpp/class-cpp.md)、[インターフェイス](../../cpp/interface.md)、または[名前空間](../../cpp/namespaces-cpp.md)以外のユーザー定義構造体に GUID を指定することはできません。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

## <a name="example"></a>例

次のコード例では、C4917 が生成されます。

```cpp
// C4917.cpp
// compile with: /W1
#pragma warning(default : 4917)
__declspec(uuid("00000000-0000-0000-0000-000000000001")) struct S
{
} s;   // C4917, don't put uuid on a struct

int main()
{
}
```
