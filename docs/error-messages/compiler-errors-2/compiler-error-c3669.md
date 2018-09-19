---
title: コンパイラ エラー C3669 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3669
dev_langs:
- C++
helpviewer_keywords:
- C3669
ms.assetid: be9c7ae4-e96f-47ab-922a-39a3537d5ca6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7588ec3862c914fd998a7b5a3f59ff4d0bb5bbf2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088671"
---
# <a name="compiler-error-c3669"></a>コンパイラ エラー C3669

'member': オーバーライド指定子 'override'、静的メンバー関数またはコンス トラクターでは許可されていません

上書きが正しく指定されていません。 詳細については、次を参照してください。[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C3669 が生成されます。

```
// C3669.cpp
// compile with: /clr
public ref struct R {
   R() override {}   // C3669
};
```