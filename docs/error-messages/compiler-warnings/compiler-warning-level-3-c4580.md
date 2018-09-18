---
title: コンパイラの警告 (レベル 3) C4580 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4580
dev_langs:
- C++
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a9d25a77b6936a3b5b741a1da927c6beb24cbb1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072226"
---
# <a name="compiler-warning-level-3-c4580"></a>コンパイラの警告 (レベル 3) C4580

[attribute] は非推奨とされます。System::Attribute または Platform::Metadata を基底クラスとして指定してください

[[属性](../../windows/attribute.md)] がユーザー定義の属性を作成するための構文をお勧めします。 詳細については、「 [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)」を参照してください。 CLR コードの場合は、`System::Attribute` から属性を派生させます。 Windows ランタイム コードの場合は、`Platform::Metadata` から属性を派生させます。

## <a name="example"></a>例

次の例では、C3454 を生成し、その修正方法を示しています。

```cpp
// C4580.cpp
// compile with: /W3 /c /clr
[attribute]   // C4580
public ref class Attr {
public:
   int m_t;
};

public ref class Attr2 : System::Attribute {
public:
   int m_t;
};
```