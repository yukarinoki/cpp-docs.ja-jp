---
title: コンパイラ エラー C3646 |Microsoft Docs
ms.custom: ''
ms.date: 06/14/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3646
dev_langs:
- C++
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c038520c1a35fa5264e1e98b074687efb336d028
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "35658612"
---
# <a name="compiler-error-c3646"></a>コンパイラ エラー C3646

> 'specifier': 不明なオーバーライド指定子

## <a name="remarks"></a>Remarks

オーバーライド指定子では、これが必要ですが、トークンが、コンパイラによって認識されない位置でトークンが見つかりました。

たとえば場合、認識されない*指定子*は **_NOEXCEPT**、キーワードに置き換えます**noexcept**します。

詳細については、次を参照してください。[オーバーライド指定子を](../../windows/override-specifiers-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C3646 を生成し、その修正方法を示しています。

```cpp
// C3646.cpp
// compile with: /clr /c
ref class C {
   void f() unknown;   // C3646
   // try the following line instead
   // virtual void f() abstract;
};
```