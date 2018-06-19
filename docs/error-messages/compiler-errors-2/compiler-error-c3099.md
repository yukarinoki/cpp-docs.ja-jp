---
title: コンパイラ エラー C3099 |Microsoft ドキュメント
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
ms.openlocfilehash: 27059beb1cb587b9060da8c5cc5702ea966422f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33249756"
---
# <a name="compiler-error-c3099"></a>コンパイラ エラー C3099
'keyword': マネージ属性には [System::AttributeUsageAttribute] を使用してください。WinRT 属性には [Windows::Foundation::Metadata::AttributeUsageAttribute] を使用してください。  
  
 使用して<xref:System.AttributeUsageAttribute>を宣言する **/clr**属性。 `Windows::Foundation::Metadata::AttributeUsageAttribute` を使用して、Windows ランタイム属性を宣言します。  
  
 /CLR 属性の詳細については、次を参照してください。[ユーザー定義の属性](../../windows/user-defined-attributes-cpp-component-extensions.md)です。 Windows ランタイムでサポートされている属性は、次を参照してください[Windows.Foundation.Metadata 名前空間。](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.aspx)  
  
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