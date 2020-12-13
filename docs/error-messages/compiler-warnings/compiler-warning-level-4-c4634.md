---
description: '詳細情報: コンパイラの警告 (レベル 4) C4634'
title: コンパイラの警告 (レベル 4) C4634
ms.date: 11/04/2016
f1_keywords:
- C4634
helpviewer_keywords:
- C4634
ms.assetid: 3e3496ce-2ac7-43d0-a48a-f514c950e81d
ms.openlocfilehash: 87144f1a3c95f46159b07dc776707da06a56ff21
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134128"
---
# <a name="compiler-warning-level-4-c4634"></a>コンパイラの警告 (レベル 4) C4634

XML ドキュメント コメント: 適用できません: 理由

XML ドキュメントのタグは、すべての C++ コンストラクトに適用できません。  たとえば、名前空間またはテンプレートにドキュメント コメントを追加できません。

詳細については、「 [XML Documentation](../../build/reference/xml-documentation-visual-cpp.md)」を参照してください。

## <a name="examples"></a>例

次の例では C4634 警告が生成されます。

```cpp
// C4634.cpp
// compile with: /W4 /doc /c
/// This is a namespace.   // C4634
namespace hello {
   class MyClass  {};
};
```

次の例では C4634 警告が生成されます。

```cpp
// C4634_b.cpp
// compile with: /W4 /doc /c
/// This is a template.   // C4634
template <class T>
class MyClass  {};
```
