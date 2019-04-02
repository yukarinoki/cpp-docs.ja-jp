---
title: コンパイラ エラー C3101
ms.date: 11/04/2016
f1_keywords:
- C3101
helpviewer_keywords:
- C3101
ms.assetid: 4f673766-d4f7-4632-94a5-d36a83f7f4b5
ms.openlocfilehash: d39afc548010df95bdf31b2c7708bc4fa0310bcd
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58779236"
---
# <a name="compiler-error-c3101"></a>コンパイラ エラー C3101

名前付き属性引数 'field' 式が正しくありません。

名前付き属性引数を初期化するときに、値は、コンパイル時間定数である必要があります。

属性の詳細については、次を参照してください。[ユーザー定義の属性](../../extensions/user-defined-attributes-cpp-component-extensions.md)します。

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