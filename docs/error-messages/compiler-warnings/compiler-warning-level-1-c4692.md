---
description: '詳細情報: コンパイラの警告 (レベル 1) C4692'
title: コンパイラの警告 (レベル 1) C4692
ms.date: 11/04/2016
f1_keywords:
- C4692
helpviewer_keywords:
- C4692
ms.assetid: f6fb3acc-8228-491a-9c30-ce302d8a9c75
ms.openlocfilehash: 7c38a2bd4bfd4de943f64483cd8a9e96ece0b580
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249127"
---
# <a name="compiler-warning-level-1-c4692"></a>コンパイラの警告 (レベル 1) C4692

'関数': 公開されたメンバーのシグネチャはアセンブリ プライベート ネイティブ型 'native_type' を含んでいます

アセンブリの外部で参照できる型に、アセンブリの外部で参照できないネイティブ型をシグネチャに含むメンバー関数が含まれています。 このため、そのメンバー関数は、それに含まれる型がアセンブリの外部でインスタンス化されている場合は呼び出すことができません。

詳細については、「 [型の可視性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)」を参照してください。

既定では、この警告はオフに設定されています。 詳細については、「 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。

## <a name="example"></a>例

次の例では、C4692 が生成されます。

```cpp
// C4692.cpp
// compile with: /W1 /c /clr
#pragma warning(default:4692)
class Private_Native_Class {};
public class Public_Native_Class {};
public ref class Public_Ref_Class {
public:
   void Test(Private_Native_Class *) {}   // C4692
   void Test2(Public_Native_Class *) {}   // OK
};
```
