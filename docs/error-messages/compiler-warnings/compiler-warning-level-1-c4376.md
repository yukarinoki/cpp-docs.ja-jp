---
title: コンパイラの警告 (レベル 1) C4376
ms.date: 11/04/2016
f1_keywords:
- C4376
helpviewer_keywords:
- C4376
ms.assetid: 5f202c74-9489-48fe-b36f-19cd882b1589
ms.openlocfilehash: 8009d2e5d09ad173f6150ebe9a907be9f4947cd7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162857"
---
# <a name="compiler-warning-level-1-c4376"></a>コンパイラの警告 (レベル 1) C4376

アクセス指定子 'old_specifier:' はサポートされていません。'new_specifier:' を使用してください

メタデータで型とメンバーのアクセシビリティを指定する方法の詳細については、「[方法: クラスと構造体を定義およびC++使用する (/cli)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)」の「[型の可視性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)と[メンバーの可視性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility)」を参照してください。

## <a name="example"></a>例

次の例では、C4376 が生成されます。

```cpp
// C4376.cpp
// compile with: /clr /W1 /c
public ref class G {
public public:   // C4376
   void m2();
};

public ref class H {
public:   // OK
   void m2();
};
```
