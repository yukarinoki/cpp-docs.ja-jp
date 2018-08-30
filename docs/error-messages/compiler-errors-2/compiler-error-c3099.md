---
title: コンパイラ エラー C3099 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3099
dev_langs:
- C++
helpviewer_keywords:
- C3099
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea57a79fab92152824b7c9aaf0c5d50c14fee32e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211996"
---
# <a name="compiler-error-c3099"></a>コンパイラ エラー C3099
'keyword': マネージド属性には [System::AttributeUsageAttribute] を使用してください。WinRT 属性には [Windows::Foundation::Metadata::AttributeUsageAttribute] を使用してください。  
  
 使用<xref:System.AttributeUsageAttribute>を宣言する **/clr**属性。 `Windows::Foundation::Metadata::AttributeUsageAttribute` を使用して、Windows ランタイム属性を宣言します。  
  
 /CLR 属性の詳細については、次を参照してください。[ユーザー定義の属性](../../windows/user-defined-attributes-cpp-component-extensions.md)します。 Windows ランタイムでサポートされている属性は、次を参照してください[Windows.Foundation.Metadata 名前空間。](https://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.aspx)  
  
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