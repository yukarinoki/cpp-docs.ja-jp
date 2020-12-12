---
description: 詳細については、「コンパイラエラー C3099」を参照してください。
title: コンパイラ エラー C3099
ms.date: 11/04/2016
f1_keywords:
- C3099
helpviewer_keywords:
- C3099
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
ms.openlocfilehash: d065edd58df1e9196dc6aa31cfd4fb263f062f1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116224"
---
# <a name="compiler-error-c3099"></a>コンパイラ エラー C3099

'keyword': マネージド属性には [System::AttributeUsageAttribute] を使用してください。WinRT 属性には [Windows::Foundation::Metadata::AttributeUsageAttribute] を使用してください。

<xref:System.AttributeUsageAttribute> **/Clr** 属性を宣言するために使用します。 `Windows::Foundation::Metadata::AttributeUsageAttribute` を使用して、Windows ランタイム属性を宣言します。

/CLR 属性の詳細については、「 [ユーザー定義の属性](../../extensions/user-defined-attributes-cpp-component-extensions.md)」を参照してください。 Windows ランタイムでサポートされる属性については、「 [Windows. Foundation. Metadata 名前空間](/uwp/api/windows.foundation.metadata)」を参照してください。

## <a name="example"></a>例

次の例では C3099 を生成し、その修正方法を示しています。

```cpp
// C3099.cpp
// compile with: /clr /c
using namespace System;
[usage(10)]   // C3099
// try the following line instead
// [AttributeUsageAttribute(AttributeTargets::All)]
ref class A : Attribute {};
```
