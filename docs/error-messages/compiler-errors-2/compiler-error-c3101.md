---
title: コンパイラ エラー C3101
ms.date: 11/04/2016
f1_keywords:
- C3101
helpviewer_keywords:
- C3101
ms.assetid: 4f673766-d4f7-4632-94a5-d36a83f7f4b5
ms.openlocfilehash: 8db1ba622a0c83a7f2a6421d79ff5853cbc4d9a9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555559"
---
# <a name="compiler-error-c3101"></a>コンパイラ エラー C3101

名前付き属性引数 'field' 式が正しくありません。

名前付き属性引数を初期化するときに、値は、コンパイル時間定数である必要があります。

属性の詳細については、次を参照してください。[ユーザー定義の属性](../../windows/user-defined-attributes-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C3101 が生成されます。

```
// C3101.cpp
// compile with: /clr /c
ref class AAttribute : System::Attribute {
public:
   int Field;
};

extern int i;

[assembly:A(Field = i)];   // C3101
[assembly:A(Field = 0)];   // OK
```