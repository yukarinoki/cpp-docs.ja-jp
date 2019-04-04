---
title: コンパイラ エラー C3099
ms.date: 11/04/2016
f1_keywords:
- C3099
helpviewer_keywords:
- C3099
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
ms.openlocfilehash: 0f3eac1c232ef159d220a347d6b6dc3aed2fdd9a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58771488"
---
# <a name="compiler-error-c3099"></a>コンパイラ エラー C3099

'keyword': マネージド属性には [System::AttributeUsageAttribute] を使用してください。WinRT 属性には [Windows::Foundation::Metadata::AttributeUsageAttribute] を使用してください。

使用<xref:System.AttributeUsageAttribute>を宣言する **/clr**属性。 `Windows::Foundation::Metadata::AttributeUsageAttribute` を使用して、Windows ランタイム属性を宣言します。

/CLR 属性の詳細については、[ユーザー定義の属性](../../extensions/user-defined-attributes-cpp-component-extensions.md)を参照してください。 Windows ランタイムでサポートされている属性は、次を参照してください[Windows.Foundation.Metadata 名前空間。](/uwp/api/windows.foundation.metadata)

## <a name="example"></a>例

次の例では C3099 を生成し、その修正方法を示しています。

```
// C3099.cpp
// compile with: /clr /c
using namespace System;
[usage(10)]   // C3099
// try the following line instead
// [AttributeUsageAttribute(AttributeTargets::All)]
ref class A : Attribute {};
```